#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |


# **Working with `df`, `du`, `kill`, and `ps` Commands in Linux**  

These Linux commands are essential for **monitoring disk usage, checking running processes, and terminating unresponsive programs.**  


## **1. `df` Command – Check Available Disk Space**  

The `df` (disk free) command is used to **display available and used disk space** on a Linux system.  

### **Syntax:**  
```sh
df [options]
```  

### **Commonly Used Options:**  

| Option | Description |
|--------|-------------|
| `-h` | Displays output in **human-readable format** (KB, MB, GB). |
| `-a` | Shows **all filesystems**, including those with zero space. |

### **Examples:**  

#### **1. Check Disk Space Usage in Human-Readable Format**
```sh
df -h
```
✅ Displays disk space usage in **KB, MB, or GB** instead of blocks.  

#### **2. Check All Filesystems (Including Zero-Sized)**
```sh
df -a
```
✅ Shows **all filesystems**, even those with zero space used.  

## **2. `du` Command – Check Directory Disk Usage**  

The `du` (disk usage) command shows **how much space a directory or file consumes**.  

### **Syntax:**  
```sh
du [options] [directory]
```  

### **Commonly Used Options:**  

| Option | Description |
|--------|-------------|
| `-h` | Displays **human-readable output** (KB, MB, GB). |
| `-s` | Shows only the **total size** of the directory. |

### **Examples:**  

#### **1. Display Disk Usage in Human-Readable Format**
```sh
du -h
```
✅ Shows directory sizes in **KB, MB, or GB**.  

#### **2. Check Disk Usage of a Specific Directory (`/root`)**
```sh
du -h /root
```
✅ Displays the **disk usage of the `/root` directory**.  

#### **3. Show Only the Total Size of a Directory**
```sh
du -sh /var/log
```
✅ Displays only the **total size of `/var/log`** instead of individual file sizes.  

## **3. `ps` Command – View Running Processes**  

The `ps` (process status) command is used to **view active processes** on a Linux system.  

### **Syntax:**  
```sh
ps [options]
```  

### **Commonly Used Options:**  

| Option | Description |
|--------|-------------|
| `-ef` | Displays **all running processes** in full format. |
| `-A` | Shows **all processes** currently running. |
| `-T` | Displays processes associated with the **current terminal**. |
| `-u username` | Shows processes belonging to a **specific user**. |

### **Examples:**  

#### **1. Display All Running Processes**
```sh
ps -A
```
✅ Shows **all active processes**.  

#### **2. Check Processes Running in the Current Shell**
```sh
ps
```
✅ Displays **processes running in the current terminal session**.  

#### **3. Find a Process by Name (e.g., Port 8080)**
```sh
ps -ef | grep 8080
```
✅ Searches for **processes running on port `8080`**.  

#### **4. Display Processes for a Specific User (`tomcat`)**
```sh
ps -u tomcat
```
✅ Lists **all processes started by `tomcat`**.  


## **4. `kill` Command – Terminate a Process**  

The `kill` command is used to **terminate a process** using its **PID (Process ID)**.  

### **Syntax:**  
```sh
kill [signal] PID
```  

### **Commonly Used Signals:**  

| Signal | Description |
|--------|-------------|
| `-9` | **Force kill** a process immediately. |
| `-15` | Gracefully **terminate** a process (default). |
| `-3` | **Thread dump** for Java processes (JVM). |

### **Examples:**  

#### **1. Kill a Process by PID**
```sh
kill -9 PID
```
✅ Forcefully terminates the process **immediately**.  

#### **2. Gracefully Stop a Process**
```sh
kill -15 PID
```
✅ Sends a **termination signal** for a safe shutdown.  

#### **3. Generate a Thread Dump for Java Applications**
```sh
kill -3 PID
```
✅ Used for troubleshooting **Java applications** by listing active threads in the **Java Virtual Machine (JVM)**.  
