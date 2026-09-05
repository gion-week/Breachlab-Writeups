# Ghost: Linux & Shell Fundamentals

22 levels, the track BreachLab expects you to clear before anything else: shell fluency, the filesystem, processes, networking, encoding, permissions. Everything here runs over SSH, no browser involved.

---

## Access

| Field | Value |
|---|---|
| Host | `204.168.229.209` |
| Port | `2222` |
| Starting user | `ghost0` |
| Starting password | `ghost0` |

```bash
ssh ghost0@204.168.229.209 -p 2222
```

Each level's flag doubles as the SSH password for the next user (`ghost1`, `ghost2`, and so on), and the platform shows it exactly once.

---

## Progression

| # | Level | Main topic | Done |
|---|---|---|:---:|
| 0 | [First Contact](./Level%200%20-%20First%20Contact/README.md) | Shell basics (`ls`/`cat`/`cd`), following planted operator notes | ✅ |
| 1 | [Name Game](./Level%201%20-%20Name%20Game/README.md) | Adversarial filenames: `./` and quoting to beat `cat` | ✅ |
| 2 | [In The Shadows](./Level%202%20-%20In%20The%20Shadows/README.md) | Hidden files and dirs (`ls -a`), globbing | ✅ |
| 3 | [Access Denied](./Level%203%20-%20Access%20Denied/README.md) | Unix group permissions, `id`, `find -readable` | ✅ |
| 4 | [Signal in the Noise](./Level%204%20-%20Signal%20in%20the%20Noise/README.md) | Log triage: deriving a file's vocabulary with `grep`/`sort -u` | ✅ |
| 5 | [The Listener](./Level%205%20-%20The%20Listener/README.md) | Port discovery without `ss`/`netstat`, raw TCP with `nc` | ✅ |
| 6 | Ghost in the Machine |  | ☐ |
| 7 | Lost in Translation |  | ☐ |
| 8 | Something's Running |  | ☐ |
| 9 | Core Dump |  | ☐ |
| 10 | Odd Token Out |  | ☐ |
| 11 | Unwrap the Stage |  | ☐ |
| 12 | Harvested Key |  | ☐ |
| 13 | Credential Broker |  | ☐ |
| 14 | TLS Only |  | ☐ |
| 15 | Ephemeral Port |  | ☐ |
| 16 | Config Drift |  | ☐ |
| 17 | No Shell For You |  | ☐ |
| 18 | Wrong User |  | ☐ |
| 19 | Your First Script |  | ☐ |
| 20 | Cron Discovery |  | ☐ |
| 21 | Secrets in History |  | ☐ |

---

## Tools

Just `ssh` for now. This is the entry-point track, and the list grows as later levels demand more.
