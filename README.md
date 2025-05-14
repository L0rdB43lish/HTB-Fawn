# HTB-Fawn

Resolution of HackTheBox's machine "Fawn".

Spawn machine IP: 10.129.1.14

Questions:

1. What does the 3-letter acronym FTP stand for?  
	``File Transfer Protocol``

2. Which port does the FTP service listen on usually?  
	``21``

3. FTP sends data in the clear, without any encryption. What acronym is used for a later protocol designed to provide similar functionality to FTP but securely, as an extension of the SSH protocol?  
	``SFTP``

4. What is the command we can use to send an ICMP echo request to test our connection to the target?  
	``ping``

I used the `ping` command to verify connectivity with the target machine. As you can see in the screenshot bellow, the target responded successfully to the ICMP echo requests.

![image](https://github.com/L0rdB43lish/HTB-Fawn/blob/594073254cef218d15ec70cfa2586491dd65b136/images/Captura%20de%20tela%202025-05-09%20175418.png)

5. From your scans, what version is FTP running on the target?  
	``vsftpd 3.0.3``

I used the `nmap` tool with the ``-sV`` flag to detect which services were running on the target machine and to verify their versions. The scan revealed an ``FTP`` service on port 21, running ``vsftpd 3.0.3``.  

![image](https://github.com/L0rdB43lish/HTB-Fawn/blob/594073254cef218d15ec70cfa2586491dd65b136/images/Captura%20de%20tela%202025-05-09%20175831.png)

6. From your scans, what OS type is running on the target?  
	``Unix``

7. What is the command we need to run in order to display the 'ftp' client help menu?  
	`ftp -?`

8. What is username that is used over FTP when you want to log in without having an account?  
	``anonymous``

Since the `FTP` service was open, I attempted to connect using the ``anonymous`` username, as I didn't have valid login credentials.  

![image](https://github.com/L0rdB43lish/HTB-Fawn/blob/594073254cef218d15ec70cfa2586491dd65b136/images/Captura%20de%20tela%202025-05-09%20180546.png)


9. What is the response code we get for the FTP message 'Login successful'?  
	`230`

10. There are a couple of commands we can use to list the files and directories available on the FTP server. One is dir. What is the other that is a common way to list files on a Linux system.  
	`ls`

Once connected to the "FTP server", I executed the ``ls`` command to enumerate the contents of the directory.  

![image](https://github.com/L0rdB43lish/HTB-Fawn/blob/594073254cef218d15ec70cfa2586491dd65b136/images/Captura%20de%20tela%202025-05-09%20180721.png)


11. What is the command used to download the file we found on the FTP server?  
	`get`

I identified the `flag.txt` file and used the command ``get`` to retrieve it from the FTP server.  

![image](https://github.com/L0rdB43lish/HTB-Fawn/blob/594073254cef218d15ec70cfa2586491dd65b136/images/Captura%20de%20tela%202025-05-09%20181012.png)

## Flag
I used the ``cat`` command to display the contents of the file.  

![image](https://github.com/L0rdB43lish/HTB-Fawn/blob/594073254cef218d15ec70cfa2586491dd65b136/images/Captura%20de%20tela%202025-05-09%20181115.png)

## What I Learned
By completing this machine, I gained hands-on experience with basic enumeration and FTP exploitation.  
I learned how to use `nmap` to scan for open ports and identify service versions, recognize an unauthenticated FTP service as a potential attack vector, connect to an FTP server using `anonymous` credentials, navigate and enumerate files in an FTP environment, and transfer files from the remote server and extract redable content using `cat`.
