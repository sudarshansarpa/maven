#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

# **Working with `head` and `tail` Commands in Linux**  

In Linux, the `head` and `tail` commands are used to display specific portions of a file. These commands are helpful when quickly viewing large files without opening them in an editor.

## **1. `head` Command in Linux**  

The `head` command prints the **top N lines** of the given file. By default, it **displays the first 10 lines**.  

### **Syntax:**  
```sh
head filename
```
or  
```sh
head -n NUM filename
```
🔹 **`-n NUM`** → Prints the first **NUM** lines instead of the default 10.  

### **Examples:**  

#### **Example 1: Display the first 10 lines (default behavior)**  
```sh
head murali.txt
```
✅ This will print the first 10 lines of `murali.txt`.  

#### **Example 2: Display the first 5 lines**  
```sh
head -n 5 murali.txt
```
✅ This will print only **the first 5 lines** of `murali.txt`.  

## **2. `tail` Command in Linux**  

The `tail` command prints the **last N lines** of a file. By default, it **displays the last 10 lines**.  

### **Syntax:**  
```sh
tail filename
```
or  
```sh
tail -n NUM filename
```
🔹 **`-n NUM`** → Prints the last **NUM** lines instead of the default 10.  

### **Examples:**  

#### **Example 1: Display the last 10 lines (default behavior)**  
```sh
tail murali.txt
```
✅ This will print the last 10 lines of `murali.txt`.  

#### **Example 2: Display the last 5 lines**  
```sh
tail -n 5 murali.txt
```
✅ This will print **only the last 5 lines** of `murali.txt`.  


## **3. `tail -f` Command in Linux**  

The `tail -f` command is used for **real-time monitoring** of a file, especially useful for watching log files as they are updated. It prints the last 10 lines of a file and continues to display any new lines that are added to the file.

### **Syntax:**  
```sh
tail -f filename
```

🔹 **`-f`** → Follow the file in real time and display new content as it is added.  

### **Examples:**  

#### **Example 1: Monitor a log file in real time**  
```sh
tail -f /var/log/syslog
```
✅ This will display the last 10 lines of `/var/log/syslog` and continue to print any new lines as they are added to the file.

#### **Example 2: Monitor a log file with a custom number of lines**  
```sh
tail -n 20 -f /var/log/syslog
```
✅ This will display the last 20 lines and then continue monitoring the file for new lines.

## **4. Common Use Cases of `head` and `tail`**  

| Command               | Description                                                                                   |
|-----------------------|-----------------------------------------------------------------------------------------------|
| `head -n 20 file.txt` | Show the first **20 lines** of the file.                                                       |
| `tail -n 20 file.txt` | Show the last **20 lines** of the file.                                                        |
| `tail -f logfile.txt` | **Real-time monitoring** of a log file (updates as new lines are added).                       |
| `head -c 50 file.txt` | Show the **first 50 bytes** of a file.                                                         |
| `tail -c 50 file.txt` | Show the **last 50 bytes** of a file.                                                          |
| `tail -f logfile.txt` | Continuously display new lines being added to a file (useful for monitoring log files).       |


