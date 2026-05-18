# Day 02 – Linux Architecture, Processes, and systemd

## Core Concepts of Linux

### Kernel
Kernel is the heart of Linux.  
It allows communication between hardware and software.  
It manages:
- CPU
- Memory
- Processes
- Device drivers
- File systems

---

### User Space
User space is the area where applications run such as:
- bash
- chrome
- nginx
- python

Shell accepts commands from the user and communicates with the kernel for execution.

---

### systemd
systemd is the first userspace process started after the kernel boots.

- PID = 1
- Manages services and background processes
- Starts and stops services
- Handles system boot process

Useful command:

ps -ef 
top
systemctl status nginx
kill -9 PID
grep 
