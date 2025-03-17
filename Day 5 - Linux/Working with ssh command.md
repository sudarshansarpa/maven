#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

# **Working with `ssh` Command**  

The `ssh` (**Secure Shell**) command is used to securely connect to remote systems over an encrypted connection. It allows users to manage remote servers, execute commands, and transfer files securely.  

## **1️⃣ Basic SSH Connection**
```sh
ssh user@remote_host
```
📌 **Example: Connect to a remote server**
```sh
ssh murali@192.168.1.100
```
- `user` → The username on the remote system  
- `remote_host` → The **IP address** or **hostname** of the remote system  

## **2️⃣ SSH Using an Identity File (Private Key)**
```sh
ssh -i /path/to/private_key user@remote_host
```
📌 **Example: Connect to an AWS EC2 instance using a `.pem` key**
```sh
ssh -i infra.pem ec2-user@43.205.113.179
```
- `-i infra.pem` → Specifies the **private key file** required for authentication.  
- `ec2-user@43.205.113.179` → Connects as the `ec2-user` to the remote server.  

## **3️⃣ Running a Command on the Remote Server**
Instead of opening a full session, you can execute a command directly on the remote machine.

✅ **Example: List files in the `/home/user` directory**
```sh
ssh user@remote_host "ls -la /home/user"
```
✅ **Example: Check disk space on a remote server**
```sh
ssh -i infra.pem ec2-user@43.205.113.179 "df -h"
```
✅ **Example: Restart Apache server remotely**
```sh
ssh -i infra.pem ec2-user@43.205.113.179 "sudo systemctl restart httpd"
```

📌 **Explanation:**  
- The command inside `"..."` runs on the remote machine **without opening an interactive session**.  
