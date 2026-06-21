## Process Check 1

Command:
ps -ef | grep nginx

Observation:
Found nginx master process (PID 669) and worker processes (PID 675, 676). Worker processes are child processes of the nginx master process.

## Process Check 2

Command:
pgrep nginx

Output:
669
675
676

Observation:
pgrep displayed the PIDs of nginx processes. PID 669 is the master process and 675, 676 are worker processes.


## Service Check 1

Command:
sudo systemctl status nginx

Observation:
Nginx service was active and running. The service was enabled to start automatically on boot. Main PID was 669 and two worker processes were running.

## Service Check 2

Command:
systemctl is-active nginx

Output:
active

Observation:
Verified that nginx service is currently running.

sudo journalctl -u nginx --no-pager | tail -10
Jun 17 11:04:42 ip-172-31-44-1 systemd[1]: Stopped nginx.service - A high performance web server and a reverse proxy server.
-- Boot ef1aa519e9c343058cff086ce04a6668 --
Jun 19 22:46:53 ip-172-31-44-1 systemd[1]: Starting nginx.service - A high performance web server and a reverse proxy server...
Jun 19 22:46:53 ip-172-31-44-1 systemd[1]: Started nginx.service - A high performance web server and a reverse proxy server.
Jun 20 15:45:14 ip-172-31-44-1 systemd[1]: Stopping nginx.service - A high performance web server and a reverse proxy server...
Jun 20 15:45:15 ip-172-31-44-1 systemd[1]: nginx.service: Deactivated successfully.
Jun 20 15:45:15 ip-172-31-44-1 systemd[1]: Stopped nginx.service - A high performance web server and a reverse proxy server.
-- Boot a40c99d8bee3481f8742504770264610 --
Jun 21 08:57:15 ip-172-31-44-1 systemd[1]: Starting nginx.service - A high performance web server and a reverse proxy server...
Jun 21 08:57:16 ip-172-31-44-1 systemd[1]: Started nginx.service - A high performance web server and a reverse proxy server.


