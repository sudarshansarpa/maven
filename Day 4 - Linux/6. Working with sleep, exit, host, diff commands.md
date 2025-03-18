#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |


# **Working with `sleep`, `exit`, `host`, and `diff` Commands in Linux**  

Linux provides a variety of commands to manage processes, networking, and file comparison. Here’s a detailed breakdown of the `sleep`, `exit`, `host`, and `diff` commands.

## **1. `sleep` Command**  

The `sleep` command **pauses the execution** of a script or command for a specified period.  

### **Syntax:**  
```sh
sleep [NUMBER][SUFFIX]
```
🔹 `NUMBER` → Duration to pause.  
🔹 `SUFFIX` → Unit of time (`s` = seconds, `m` = minutes, `h` = hours, `d` = days).  

### **Examples:**  

#### **Pause for 5 seconds**
```sh
sleep 5
```

#### **Pause for 2 minutes**
```sh
sleep 2m
```

#### **Pause for 1 hour**
```sh
sleep 1h
```

#### **Using `sleep` in a script**
```sh
echo "Wait for 5 seconds..."
sleep 5
echo "Done!"
```
✅ The script pauses for 5 seconds before printing `"Done!"`.

## **2. `exit` Command**  

The `exit` command is used to **terminate a shell session or script**.  

### **Syntax:**  
```sh
exit [STATUS]
```
🔹 `STATUS` → Exit code (0 = success, any other number = error).  

### **Examples:**  

#### **Exit a shell session**
```sh
exit
```
✅ Closes the terminal or SSH session.  

#### **Exit with a specific status**
```sh
exit 1
```
✅ Exits with a status code of `1`, which typically indicates an error.  

#### **Using `exit` in a script**
```sh
#!/bin/bash
echo "This is a script"
exit 0
```
✅ The script exits successfully with code `0`.

## **3. `host` Command**  

The `host` command is used to **find the IP address of a domain** or **perform DNS lookups**.  

### **Syntax:**  
```sh
host [DOMAIN_NAME]
```

### **Examples:**  

#### **Find the IP address of a website**
```sh
host google.com
```
✅ This returns:  
```
google.com has address 142.250.182.206
google.com has IPv6 address 2607:f8b0:400a:0803::200e
```

#### **Check DNS records**
```sh
host -t MX google.com
```
✅ Finds the mail exchange (MX) records for `google.com`.

#### **Find the nameservers of a domain**
```sh
host -t NS google.com
```
✅ Lists the authoritative name servers for `google.com`.

## **4. `diff` Command**  

The `diff` command **compares two files line by line** and highlights the differences.  

### **Syntax:**  
```sh
diff [OPTION] file1 file2
```

### **Examples:**  

#### **Compare two text files**
```sh
diff file1.txt file2.txt
```
✅ Shows differences between `file1.txt` and `file2.txt`.  

#### **Show differences in a side-by-side format**
```sh
diff -y file1.txt file2.txt
```
✅ Displays the differences in **two columns**.  

#### **Ignore case differences**
```sh
diff -i file1.txt file2.txt
```
✅ Compares files but ignores case (`Hello` = `hello`).  

#### **Ignore whitespace differences**
```sh
diff -w file1.txt file2.txt
```
✅ Ignores extra spaces or tabs while comparing files.  
