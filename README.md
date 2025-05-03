# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting
### NAME : Naresh kumar R
### REGISTER NUMBER : 212224040213
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

Find out the ip address of the attackers system

## OUTPUT:

![eth 1](https://github.com/user-attachments/assets/8332803d-aabb-43d3-8991-a0ed8037ca0e)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows:

```
systemctl start postgresql

msfdb init
```

Invoke msfconsole:

## OUTPUT:

![eth 2](https://github.com/user-attachments/assets/bf9b8809-8ceb-401b-b5cb-b71c945c9295)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
## OUTPUT:
![eth 3](https://github.com/user-attachments/assets/6cf25aee-59fb-4c42-9d56-0bcc9d88c0b3)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:
![eth 4](https://github.com/user-attachments/assets/53f9b610-6df3-4029-afa6-3428c8cb5bdd)

step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:

![eth 5](https://github.com/user-attachments/assets/f07e7d7f-48ad-4f05-85f3-8cf716c21e9f)

![eth 6](https://github.com/user-attachments/assets/cc9a6d49-81a3-472f-87c0-312489018cd8)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:
![eth 7](https://github.com/user-attachments/assets/f925ab62-ce26-4ce4-89c5-fb13576b86b8)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

## OUTPUT:
![eth 8](https://github.com/user-attachments/assets/99ff07c4-360d-48a0-9142-a8227a5f0c6e)

The info command provides information regarding a module or platform
## OUTPUT:
![eth 9](https://github.com/user-attachments/assets/8ee24e83-459e-45ac-b5f3-fff2e7325edb)


![eth 10](https://github.com/user-attachments/assets/43abe92f-db26-4289-8bcd-e6fcf4754f91)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows:
```
systemctl start postgresql
```
## MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

## OUTPUT:
![eth 11](https://github.com/user-attachments/assets/8c8caa77-45f8-4805-85a9-9003cd5d370f)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

## OUTPUT:
![eth 12](https://github.com/user-attachments/assets/c38ba90a-4675-426e-85ca-dd309a95f77f)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

## OUTPUT:




Use the set rhosts command to set the parameter and run the module, as follows:

## OUTPUT:

![eth 13](https://github.com/user-attachments/assets/81c46f63-3fd2-4739-8851-097159a71792)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
## OUTPUT:
![eth 14](https://github.com/user-attachments/assets/4c29c54b-49b2-4e4f-afd6-67fc244cd61f)


set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists:
```
set PASS_FILE /usr/share/wordlists/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS
```
Set BLANK_PASSWORDS to true in case there is no password set for the root account.
```
set BLANK_PASSWORDS true
```

## OUTPUT:
![eth 15](https://github.com/user-attachments/assets/a43af372-77d8-464a-a66a-0969ef22e674)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
