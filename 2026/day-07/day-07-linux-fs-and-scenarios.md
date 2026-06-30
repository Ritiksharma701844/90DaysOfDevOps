In linux system everything is either file or directory.
/ root is the starting point of file system. only root user can add or modify file in / directory otherwise we get permission denied button.
/bin directory contains binaries of various linux commands that we use daily like cd, ls, mkdir etc.
/boot this directory contains all the files that are required while booting process it contains grub bootloader and essential kernal files that are loaded during boot.
/etc is the directory that contains system-wide configuration files for Linux and its applications.
/home every non root user has its own directory in /home if we create ritik user than /home/ritik file will be created in linux
Applications require shared libraries to run, which are stored in /lib. These include dynamic libraries needed during runtime. For example, Apache server libraries are available here.
/opt is a Linux directory used to store optional or third-party application software and its files.
/tmp is a Linux directory used to store temporary files created by the operating system and applications.
/usr/bin is a Linux directory that contains most user command binaries (executable programs).

ubuntu@ip-172-31-43-65:~$ du -sh /var/log/* 2>/dev/null | sort -h | tail -4
408K    /var/log/cloud-init.log
420K    /var/log/sysstat
580K    /var/log/syslog
17M     /var/log/journal


ubuntu@ip-172-31-43-65:~$ curl ifconfig.me
3.110.178.189ubuntu@ip-172-31-43-65:~$ ls -la
total 36
drwxr-x--- 4 ubuntu ubuntu 4096 Jun 30 06:21 .
drwxr-xr-x 3 root   root   4096 Jun 28 10:01 ..
-rw------- 1 ubuntu ubuntu   61 Jun 30 06:21 .Xauthority
-rw------- 1 ubuntu ubuntu   23 Jun 28 11:05 .bash_history
-rw-r--r-- 1 ubuntu ubuntu  220 Feb 13 12:16 .bash_logout
-rw-r--r-- 1 ubuntu ubuntu 3771 Feb 13 12:16 .bashrc
drwx------ 2 ubuntu ubuntu 4096 Jun 28 10:02 .cache
-rw-r--r-- 1 ubuntu ubuntu  807 Feb 13 12:16 .profile
drwx------ 2 ubuntu ubuntu 4096 Jun 28 10:01 .ssh


ubuntu@ip-172-31-43-65:~$ cat /etc/hostname
ip-172-31-43-65

A web application service called 'myapp' failed to start after a server reboot.
What commands would you run to diagnose the issue?

systemctl status myapp
journalctl -u myapp -n 50
ps -ef | grep myapp
ss -tulnp | grep <port_number>

Your manager reports that the application server is slow.
You SSH into the server. What commands would you run to identify
which process is using high CPU?

first i write htop command where i will se which process is taking more cpu after that i will copy its process id and after that will run ps -fp processid to identify.
top
ps -fp <PID>
journalctl -u myapp -n 50
curl http://localhost:<port>
systemctl restart myapp

ubuntu@ip-172-31-43-65:~$ sudo systemctl status ssh
● ssh.service - OpenBSD Secure Shell server
     Loaded: loaded (/usr/lib/systemd/system/ssh.service; disabled; preset: enabled)
    Drop-In: /usr/lib/systemd/system/ssh.service.d
             └─ec2-instance-connect.conf
     Active: active (running) since Tue 2026-06-30 06:47:31 UTC; 54min ago
 Invocation: ffe56db6ddc043098723cfacc04e239b
TriggeredBy: ● ssh.socket
       Docs: man:sshd(8)
             man:sshd_config(5)
   Main PID: 3664 (sshd)
      Tasks: 1 (limit: 627)
     Memory: 1.2M (peak: 2M)
        CPU: 40ms
     CGroup: /system.slice/ssh.service
             └─3664 "sshd: /usr/sbin/sshd -D -o AuthorizedKeysCommand /usr/share/ec2-instance-connect/eic_run_authorized_keys>

Jun 30 06:47:31 ip-172-31-43-65 sshd[3664]: Server listening on 0.0.0.0 port 22.
Jun 30 06:47:31 ip-172-31-43-65 sshd[3664]: Server listening on :: port 22.

ubuntu@ip-172-31-43-65:~$
ubuntu@ip-172-31-43-65:~$
ubuntu@ip-172-31-43-65:~$ journalctl -u ssh -n 10
Jun 30 06:21:03 ip-172-31-43-65 sshd-session[3079]: Accepted publickey for ubuntu from 49.43.106.54 port 51467 ssh2: RSA SHA2>
Jun 30 06:21:03 ip-172-31-43-65 sshd-session[3079]: pam_unix(sshd:session): session opened for user ubuntu(uid=1000) by ubunt>
Jun 30 06:21:04 ip-172-31-43-65 sshd-session[3081]: Accepted publickey for ubuntu from 49.43.106.54 port 51468 ssh2: RSA SHA2>
Jun 30 06:21:04 ip-172-31-43-65 sshd-session[3081]: pam_unix(sshd:session): session opened for user ubuntu(uid=1000) by ubunt>
Jun 30 06:26:31 ip-172-31-43-65 sshd-session[3310]: banner exchange: Connection from 64.226.85.79 port 48834: invalid format
Jun 30 06:26:32 ip-172-31-43-65 sshd-session[3311]: banner exchange: Connection from 64.226.85.79 port 48850: invalid format
Jun 30 06:47:31 ip-172-31-43-65 systemd[1]: Stopping ssh.service - OpenBSD Secure Shell server...
Jun 30 06:47:31 ip-172-31-43-65 sshd[656]: Received signal 15; terminating.
Jun 30 06:47:31 ip-172-31-43-65 sshd[3664]: Server listening on 0.0.0.0 port 22.
Jun 30 06:47:31 ip-172-31-43-65 sshd[3664]: Server listening on :: port 22.

ubuntu@ip-172-31-43-65:~$
ubuntu@ip-172-31-43-65:~$
ubuntu@ip-172-31-43-65:~$ journalctl -u ssh -f
Jun 30 06:21:03 ip-172-31-43-65 sshd-session[3079]: Accepted publickey for ubuntu from 49.43.106.54 port 51467 ssh2: RSA SHA256:JUN4hF8ekT9SjFm1OSf2jjUAiPKJ7y0JFxNJKZj8b0Y
Jun 30 06:21:03 ip-172-31-43-65 sshd-session[3079]: pam_unix(sshd:session): session opened for user ubuntu(uid=1000) by ubuntu(uid=0)
Jun 30 06:21:04 ip-172-31-43-65 sshd-session[3081]: Accepted publickey for ubuntu from 49.43.106.54 port 51468 ssh2: RSA SHA256:JUN4hF8ekT9SjFm1OSf2jjUAiPKJ7y0JFxNJKZj8b0Y
Jun 30 06:21:04 ip-172-31-43-65 sshd-session[3081]: pam_unix(sshd:session): session opened for user ubuntu(uid=1000) by ubuntu(uid=0)
Jun 30 06:26:31 ip-172-31-43-65 sshd-session[3310]: banner exchange: Connection from 64.226.85.79 port 48834: invalid format
Jun 30 06:26:32 ip-172-31-43-65 sshd-session[3311]: banner exchange: Connection from 64.226.85.79 port 48850: invalid format
Jun 30 06:47:31 ip-172-31-43-65 systemd[1]: Stopping ssh.service - OpenBSD Secure Shell server...
Jun 30 06:47:31 ip-172-31-43-65 sshd[656]: Received signal 15; terminating.
Jun 30 06:47:31 ip-172-31-43-65 sshd[3664]: Server listening on 0.0.0.0 port 22.
Jun 30 06:47:31 ip-172-31-43-65 sshd[3664]: Server listening on :: port 22.











