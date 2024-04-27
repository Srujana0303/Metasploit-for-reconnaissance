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
Find out the ip address of the attackers system

![image](https://github.com/Srujana0303/Metasploit-for-reconnaissance/assets/132996836/6602cdf4-f91a-4c8b-a5db-bbdae303d587)

Invoke msfconsole: 

![image](https://github.com/Srujana0303/Metasploit-for-reconnaissance/assets/132996836/2ac26127-557b-4d38-9b04-b6f7e2fbd086)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![image](https://github.com/Srujana0303/Metasploit-for-reconnaissance/assets/132996836/280e8d31-d8f4-4e1e-9987-ee27a6f31afb)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
![image](https://github.com/Srujana0303/Metasploit-for-reconnaissance/assets/132996836/8c07ddd3-a355-4fff-8dc2-a54ceac6b918)

use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later. scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

![image](https://github.com/Srujana0303/Metasploit-for-reconnaissance/assets/132996836/23c4f165-36e2-471d-8b63-b0173f237987)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

![image](https://github.com/Srujana0303/Metasploit-for-reconnaissance/assets/132996836/bd627642-570c-4fb4-bf9f-9d320ee8bc46)

![image](https://github.com/Srujana0303/Metasploit-for-reconnaissance/assets/132996836/c809e6ea-70f6-41a7-9c8a-41c378aae43b)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![image](https://github.com/Srujana0303/Metasploit-for-reconnaissance/assets/132996836/5adfc6fb-b2df-4bad-a14e-931cd515bf58)

The info command provides information regarding a module or platform

![image](https://github.com/Srujana0303/Metasploit-for-reconnaissance/assets/132996836/849165af-4c15-4de4-a0c2-9c1ed839f560)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

![image](https://github.com/Srujana0303/Metasploit-for-reconnaissance/assets/132996836/ac76a8bb-8778-4b99-9bda-f15a1488c8f1)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/Srujana0303/Metasploit-for-reconnaissance/assets/132996836/7165694d-e772-479a-b069-dbb73b9d4d9d)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/Srujana0303/Metasploit-for-reconnaissance/assets/132996836/86100bd0-903f-4b40-83bc-79d1b736742b)

Use the set rhosts command to set the parameter and run the module, as follows:

![image](https://github.com/Srujana0303/Metasploit-for-reconnaissance/assets/132996836/c28a4535-0f00-499a-988e-404353b22464)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![image](https://github.com/Srujana0303/Metasploit-for-reconnaissance/assets/132996836/db9edde5-b076-42e6-8c12-0598b367f0cc)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/Srujana0303/Metasploit-for-reconnaissance/assets/132996836/2704d911-fd53-40f7-8542-54b822f10860)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
