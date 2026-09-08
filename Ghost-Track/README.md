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
| 6 | [Ghost in the Machine](./Level%206%20-%20Ghost%20in%20the%20Machine/README.md) | Credentials in the environment (`env`), base64 decoys | ✅ |
| 7 | [Lost in Translation](./Level%207%20-%20Lost%20in%20Translation/README.md) | Layered encoding: hex dump (`xxd -r`) over base64 | ✅ |
| 8 | [Something's Running](./Level%208%20-%20Something's%20Running/README.md) | Process environment via `/proc/<pid>/environ`, `runuser -p` | ✅ |
| 9 | [Core Dump](./Level%209%20-%20Core%20Dump/README.md) | Core dumps: recovering an environment with `strings` | ✅ |
| 10 | [Odd Token Out](./Level%2010%20-%20Odd%20Token%20Out/README.md) | Frequency analysis: `sort` piped to `uniq -u` | ✅ |
| 11 | [Unwrap the Stage](./Level%2011%20-%20Unwrap%20the%20Stage/README.md) | Layered compression: reading an extension chain as an unwrap order | ✅ |
| 12 | [Harvested Key](./Level%2012%20-%20Harvested%20Key/README.md) | Stolen SSH keys: `chmod 600`, `ssh-keygen -y`, key-based auth | ✅ |
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
