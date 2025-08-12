# dufo.save

Privilege Escalation Enumeration Script
A Bash script designed to automate Linux privilege escalation reconnaissance by gathering key system information, including:

User and group info

Sudo permissions

SUID/SGID binaries

Writable files and directories

Sensitive files in home directories

Cron jobs and systemd timers

Running services and listening network ports

Kernel version with a reference link for known exploits

Purpose: Quickly identify potential privilege escalation vectors during CTFs or security assessments.

Usage:

Save the script and make it executable (chmod +x dufo.save)

Run it on the target machine (./dufo.save)

Review the generated timestamped output directory for findings

This script streamlines the initial enumeration phase to help focus your manual analysis and exploitation efforts.

curl -O https://raw.githubusercontent.com/B-star51/dufo.save/main/dufo.save

