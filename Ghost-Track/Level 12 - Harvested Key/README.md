<!-- portfolio-desc: A stolen ed25519 key in loot/, and the NOTES that say who still trusts it -->

# Ghost Level 12 - Harvested Key

## Objective

> There is nothing to `cat` for a password on this box. The credential to steal is an SSH private key someone left in `loot/`, and the win condition is proving it still works. The goal: use the key to land on `ghost13`, where a `flag` file holds the value to submit on the BreachLab platform for this level.

---

## Access

| Field | Value |
|---|---|
| Method | `ssh` |
| Host | `204.168.229.209:2222` |
| User | `ghost12` |

```bash
ssh ghost12@204.168.229.209 -p 2222
```

---

## Tools / concepts

- `chmod 600`: SSH refuses a private key that group or others can read
- `ssh-keygen -y -f`: derives the public half from a private key, which validates it and reveals its comment without touching the target
- `ssh -i`: authenticate with a specific key file instead of a password

---

## Solution

### Step 1: Read the loot, and the note that ships with it

`ls -a` in the home directory turns up a `loot` folder. Inside, `ls -a` shows `NOTES.txt`, `id_ed25519`, and `id_ed25519.pub`, a private/public keypair with an operator note attached. `cat NOTES.txt`:

```
Pulled from jump-01:/home/svc-deploy/.ssh/ during the Sept op.
No passphrase set. ghost13 still trusts this key.
```

That note is the whole plan, not background. It says where the key came from (`svc-deploy` on `jump-01`), that it has no passphrase to fight through, and the line that matters: `ghost13 still trusts this key`. So this is a lateral-movement credential, and the target is one hop up. `head -n 2 id_ed25519` confirms the format with the `-----BEGIN OPENSSH PRIVATE KEY-----` header before anything else gets tried.

![loot/ with the keypair and NOTES.txt, plus the private key header](../screenshots/12-private-key.png)

### Step 2: Fix the permissions, verify the key, then use it

The key goes onto a host I control, saved as `ghost12_key`. Straight off disk it lands as `-rw-r--r--`, which SSH treats as unsafe: an over-readable key file triggers the `UNPROTECTED PRIVATE KEY FILE` refusal and a silent fall back to password auth. `chmod 600` closes it down to owner-only.

Before leaning on the key, `ssh-keygen -y -f ghost12_key` derives its public half. It returns the public key without ever prompting for a passphrase, which confirms the note's "no passphrase set", and the trailing comment reads `svc-deploy@jump-01`, matching the provenance in `NOTES.txt`. The key is real and it is the one advertised.

```bash
ssh -i ghost12_key ghost13@204.168.229.209 -p 2222
```

No password prompt. The key authenticates and the `ghost13` banner comes up, the Level 13 briefing already waiting.

![chmod 600, ssh-keygen -y validating the key, then ssh -i landing on ghost13](../screenshots/12-ssh-i.png)

### Step 3: Flag found

This level has no secret to read on the `ghost12` box; the thing you exfiltrate is the key, and it pays off one login later. As `ghost13`, `cat flag` in the home directory prints the completion password for Level 12 to submit on the platform. `[REDACTED]`

---

## Notes

The key never had to leave the target to work. `chmod 600 loot/id_ed25519 && ssh -i loot/id_ed25519 ghost13@localhost` would have done the same job in place. Pulling it to my own box is the more honest model of what harvesting a credential looks like, and it keeps the key somewhere reusable instead of on a host I am about to move off of.

`ssh-keygen -y` earns its place as a pre-flight check. It parses the key, proves there is no passphrase gate, and surfaces the owner comment, all client-side, so I know the credential is good before spending an auth attempt against the real service. The permission gate is worth remembering too: the refusal is the SSH client protecting you, not the server, which is why `600` is mandatory even on a file you created seconds ago.
