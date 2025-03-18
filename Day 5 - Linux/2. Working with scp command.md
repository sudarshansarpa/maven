#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

# **Working with `scp` Command in Linux**  

The `scp` (**Secure Copy Protocol**) command is used to **securely transfer files and directories** between local and remote systems over **SSH**.

## **1️⃣ Copy from Remote Server to Local Machine**  
To download a file **from a remote server** to your local system:  

```sh
scp user@remote:/path/to/remote/file /path/to/local/destination
```

✅ **Example: Copy `backup.sql` from remote server (`43.205.113.179`) to local machine**  
```sh
scp murali@43.205.113.179:/home/ec2-user/backup.sql /home/localuser/
```
📌 **Explanation:**  
- `murali@43.205.113.179` → Remote username & IP address  
- `/home/ec2-user/backup.sql` → Remote file path  
- `/home/localuser/` → Local destination folder  

## **2️⃣ Copy from Local Machine to Remote Server**  
To upload a file **from your local system** to a remote server:  

```sh
scp /path/to/local/file user@remote:/path/to/remote/destination
```

✅ **Example: Upload `sample.txt` from local to remote server (`43.205.113.179`)**  
```sh
scp sample.txt murali@43.205.113.179:/home/ec2-user/
```
📌 **Explanation:**  
- `sample.txt` → Local file to upload  
- `murali@43.205.113.179:/home/ec2-user/` → Destination on the remote server  

## **3️⃣ Copy an Entire Directory Recursively**  
To copy **a folder and all its contents**, use `-r` (recursive):  

✅ **Example: Download `/var/logs/` directory from remote to local**  
```sh
scp -r murali@43.205.113.179:/var/logs/ /home/localuser/logs_backup/
```
✅ **Example: Upload `/projects/` directory from local to remote**  
```sh
scp -r /home/localuser/projects/ murali@43.205.113.179:/home/ec2-user/
```
