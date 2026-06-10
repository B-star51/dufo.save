<div align="center">

<img src="images/dufo-logo.png" alt="dufo mascot" width="300"/>

# `dufo.save`

**The little green gremlin that digs up your root flag.**

*Linux Privilege Escalation Enumeration — one script, zero dependencies, all the loot.*

</div>

---

## Why "dufo"? 🦎

Glad you asked. **dufo** stands for:

> **D**igs **U**p **F**ootholds & **O**versights

He's a scrappy little filesystem gremlin who scuttles through a freshly-popped box and sniffs out every misconfiguration a sysadmin forgot about — the stray SUID binary, the world-writable file owned by root, the `sudo` rule someone left wide open at 2am.

And the `.save`? It's not a typo. The original script was a 3am scratch file (`dufo.save`) born mid-CTF, when the author muttered *"...what'd you find, dufo?"* at a terminal and the goblin answered with a root shell. The name stuck. The flag got saved. So did the script.

**TL;DR:** dufo enumerates. dufo finds. dufo does not judge your patch management.

---

## What dufo sniffs out 👃

A Bash script that automates Linux privilege-escalation reconnaissance and dumps everything into a tidy, timestamped folder so you can focus on the exploitation, not the typing:

| dufo checks | Why it matters |
|---|---|
| 🪪 **Identity, kernel & OS** | Know your shell, hunt kernel CVEs |
| 👥 **Users, groups & login history** | Who else lives here? |
| 🔑 **`sudo -l` rules** | The #1 privesc shortcut |
| 💣 **SUID / SGID binaries** | GTFOBins fuel |
| 🦸 **File capabilities (`getcap`)** | The check everyone forgets |
| ✍️ **Writable dirs & world-writable root files** | Hijack-me-please |
| 🗝️ **Sensitive files** | `.ssh`, `.netrc`, `.bash_history` |
| ⏰ **Cron jobs & systemd timers** | Scheduled root, anyone? |
| 🌐 **Listening ports & running services** | Internal attack surface |
| 🛣️ **Writable binaries in `$PATH`** | Quiet but deadly |

It even grabs your kernel version and hands you a **[linuxkernelcves.com](https://www.linuxkernelcves.com/)** lookup link, then reminds you to cross-reference findings against **GTFOBins**.

---

## Feed the gremlin 🍽️

```bash
# Pull dufo onto the target
curl -O https://raw.githubusercontent.com/B-star51/dufo.save/main/dufo.save

# Let him loose
chmod +x dufo.save
./dufo.save

# Review the loot
cd enum-quick-*/    # timestamped output dir
cat summary.txt     # start here
```

Every check is saved to its own file inside a `enum-quick-YYYYMMDD-HHMMSS/` directory, with a `summary.txt` highlighting the juicy bits (anything "writable" gets flagged automatically).

---

## Built with good habits 🧠

dufo opens with `set -euo pipefail` — no silent failures, no half-run enumeration. Every command degrades gracefully if a tool is missing, so he runs on a stripped CTF box just as happily as a full distro.

> ⚖️ **For authorised testing only.** Use dufo on machines you own or have explicit permission to assess — CTFs, labs, and engagements with a signed scope. dufo digs; *you* stay legal.

---

<div align="center">

*Part of the [B-star51 security portfolio](https://github.com/B-star51) — Pentester · Top 1% TryHackMe · OSCP in progress*

</div>
