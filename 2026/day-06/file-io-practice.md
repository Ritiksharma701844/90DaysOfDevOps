ubuntu@ip-172-31-44-1:~$ touch notes.txt
ubuntu@ip-172-31-44-1:~$
ubuntu@ip-172-31-44-1:~$
ubuntu@ip-172-31-44-1:~$ ls -l notes.txt
-rw-rw-r-- 1 ubuntu ubuntu 0 Jun 21 14:19 notes.txt
ubuntu@ip-172-31-44-1:~$
ubuntu@ip-172-31-44-1:~$ echo "my name is ritik" > notes.txt
ubuntu@ip-172-31-44-1:~$ cat notes.txt
my name is ritik
ubuntu@ip-172-31-44-1:~$ echo "want to be a devops engineer" >> np
ubuntu@ip-172-31-44-1:~$ echo "want to be a devops engineer" >> notes.txt
ubuntu@ip-172-31-44-1:~$ cat n
cat: n: No such file or directory
ubuntu@ip-172-31-44-1:~$ cat notes.txt
my name is ritik
want to be a devops engineer
ubuntu@ip-172-31-44-1:~$
ubuntu@ip-172-31-44-1:~$
ubuntu@ip-172-31-44-1:~$ echo "90 days of devops challenge" | tee -a notes.txt
90 days of devops challenge
ubuntu@ip-172-31-44-1:~$
ubuntu@ip-172-31-44-1:~$ cat notes.txt
my name is ritik
want to be a devops engineer
90 days of devops challenge
ubuntu@ip-172-31-44-1:~$ head -2 notes.txt
my name is ritik
want to be a devops engineer
ubuntu@ip-172-31-44-1:~$ tail -2 notes.txt
want to be a devops engineer
90 days of devops challenge
