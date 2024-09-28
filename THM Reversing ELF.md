crackme 1

chmod +x crackme1
./crakme1

crackme 2

strings crackme 2
you will see a password 
./crackme2 <password>

crackme 3

chmod +x crackme3
strings crackme3
echo "<the hash>" | base64 -d 
./crackme3 <password>

crackme 4

./crackme 4 
the string is hidden and we used strcmp
chmod +x crackme 4
ltrace ./crackme4 password

crackme 5

chmod +x crackme5
ltrace ./crackme5
the flag will look something like this 
![Screenshot 2024-09-28 231207](https://github.com/user-attachments/assets/d42430c2-572d-465e-8e83-36925a7d0165)

crackme 6

we use a tool called ghidra 
first we go to the symbol tree 
find a function called main 
see something called comapre_pwd
![image](https://github.com/user-attachments/assets/86614d33-e633-4560-aa35-07a2733ffd99)
we go to the compare_pwd function 
![image](https://github.com/user-attachments/assets/171cdfa0-0dde-4d90-9f6d-14d2726490c0)
we will go to the my_secure_test 
![image](https://github.com/user-attachments/assets/9c5d9d0e-4554-4e83-96fe-689a276aa3b7)
we will see the password there 

crackme 7

we use a tool called ghidra 
first we go to the symbol tree 
under the function folder we will see something called main 
![image](https://github.com/user-attachments/assets/1ff4db1e-fca2-43f7-a4ef-64bab6acc8a8)
we see a function that will give us the flag 
![image](https://github.com/user-attachments/assets/02b3d14c-3530-419c-9507-23141bb519ba)

crackme8

we use a tool called ghidra
first we go to the symbol tree
then under the function folder there will be something called main 
we will see a hexdecmial
![image](https://github.com/user-attachments/assets/d6e77b9d-e97a-4f7d-96d2-fdeff02cb655)
then we just need to change the hexdecimal to decimal 
![image](https://github.com/user-attachments/assets/eeb24f37-f92d-4681-87a6-21e312f296eb)
