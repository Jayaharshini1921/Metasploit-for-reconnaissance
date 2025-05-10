# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:


## OUTPUT:

![Screenshot 2025-05-10 101434](https://github.com/user-attachments/assets/e9efc6fb-3985-4577-960f-b815aed72a23)
invoke msfconsole:
![Screenshot 2025-05-10 101446](https://github.com/user-attachments/assets/b923071c-2508-4ef6-84b6-1925cfe5311b)

![Screenshot 2025-05-10 101455](https://github.com/user-attachments/assets/e9d90a1f-30b2-4dfd-bec2-fd5b4dd795b2)

port scanning:
output:
![Screenshot 2025-05-10 101514](https://github.com/user-attachments/assets/f661903d-5684-4d9a-a13b-6e4faf3a9475)

step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:

![Screenshot 2025-05-10 101524](https://github.com/user-attachments/assets/a29de0dd-cfee-4f2a-abe1-1fc3172e9c8d)



![Screenshot 2025-05-10 101531](https://github.com/user-attachments/assets/b57f1d9a-d99c-452d-a6da-00e81fad485c)

output:
![Screenshot 2025-05-10 101541](https://github.com/user-attachments/assets/4f6966e9-b8a3-4cfd-bbf3-ace2a07e2692)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init
MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![Screenshot 2025-05-10 101549](https://github.com/user-attachments/assets/231e31cd-8f68-470a-ac31-ae7e0add88ff)


Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![Screenshot 2025-05-10 101601](https://github.com/user-attachments/assets/4c5e763f-4d11-40fc-bcf3-c4b268a352b3)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![Screenshot 2025-05-10 101609](https://github.com/user-attachments/assets/e884bffe-ebad-4cf9-9533-830e08ef4e46)


Use the set rhosts command to set the parameter and run the module, as follows:

![Screenshot 2025-05-10 101617](https://github.com/user-attachments/assets/a068641c-693c-4f9c-a29a-0da6a04f920d)




After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![Screenshot 2025-05-10 101626](https://github.com/user-attachments/assets/b81aca27-8a8f-4e94-9ca1-7f90140360d3)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true


![Screenshot 2025-05-10 101635](https://github.com/user-attachments/assets/2431c363-1162-4151-9464-7fa98ab300b6)


![Screenshot 2025-05-10 101643](https://github.com/user-attachments/assets/b9b7f153-c92d-42f4-a044-a45d714c26ed)

RESULT:
The Metasploit framework for reconnaissance is examined successfully.

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
