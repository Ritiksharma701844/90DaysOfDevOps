# Linux Commands Cheat Sheet

## Process Management

| Command | Usage |
|----------|---------|
| `ps -ef` | List all running processes |
| `top` | Monitor system processes in real time |
| `htop` | Interactive process viewer |
| `kill <PID>` | Terminate a process |
| `kill -9 <PID>` | Force kill a process |
| `pgrep <name>` | Find process ID by name |
| `pkill <name>` | Kill process by name |
| `jobs` | View background jobs |
| `bg` | Resume job in background |
| `fg` | Bring job to foreground |

## File System

| Command | Usage |
|----------|---------|
| `pwd` | Show current directory |
| `ls -lah` | List files with details |
| `cd <dir>` | Change directory |
| `mkdir <dir>` | Create directory |
| `cp -r src dest` | Copy files/directories |
| `mv src dest` | Move or rename files |
| `rm -rf <dir>` | Remove directory recursively |
| `find /path -name file` | Search files |
| `du -sh *` | Check folder sizes |
| `df -h` | Check disk usage |
| `lsblk` | View disks and partitions |
| `mount` | Show mounted filesystems |

## Log Management

| Command | Usage |
|----------|---------|
| `tail -f /var/log/syslog` | Monitor logs in real time |
| `grep "error" file.log` | Search logs |
| `less file.log` | View large log files |
| `journalctl -xe` | View systemd logs |

## Networking

| Command | Usage |
|----------|---------|
| `ping google.com` | Check connectivity |
| `ip addr` | Show IP addresses |
| `curl https://example.com` | Test web/API access |
| `dig google.com` | DNS lookup |
| `ss -tulnp` | Show listening ports |
| `traceroute google.com` | Trace network path |

## System Information

| Command | Usage |
|----------|---------|
| `uname -a` | Kernel information |
| `hostnamectl` | System details |
| `free -h` | Memory usage |
| `uptime` | System uptime |
| `whoami` | Current user |
| `history` | Command history |

## DevOps Disk Commands

| Command | Usage |
|----------|---------|
| `pvs` | View Physical Volumes |
| `vgs` | View Volume Groups |
| `lvs` | View Logical Volumes |
| `fdisk -l` | List partitions |
| `blkid` | Show filesystem UUIDs |

**Day 03 – Linux Commands Practice**
