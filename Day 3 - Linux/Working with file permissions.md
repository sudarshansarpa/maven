#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

# **Working with File Permissions in Linux**  

In Linux, file permissions define who can **read, write, and execute** a file or directory. These permissions ensure that only authorized users can access or modify files.  

There are three types of users in the system:  

- **User (Owner)** – The person who created the file.  
- **Group** – Users who share the same group.  
- **Others** – Everyone else on the system.  

## **1. Understanding File Permissions**  

Each file or directory in Linux has a **permission set** represented by **nine characters**, categorized into three groups:  

| Category | Meaning |
|----------|---------|
| **1st set** | **Owner's permissions** (User who owns the file) |
| **2nd set** | **Group permissions** (Users in the same group as the owner) |
| **3rd set** | **Others' permissions** (Everyone else) |

### **Example Output of `ls -l` Command:**  
```sh
drwxr-xr-x 10 root root 4096 May 27 14:41 maven/
```
#### **Breaking it Down:**  
- **`d`** → Indicates it is a **directory** (If it were a file, this would be `-`).  
- **`rwx` (Owner's permissions)** → Owner (`root`) has **read (r)**, **write (w)**, and **execute (x)** permissions.  
- **`r-x` (Group permissions)** → The group has **read (r)** and **execute (x)** permissions, but **no write (-)** permission.  
- **`r-x` (Others' permissions)** → Other users have **read (r)** and **execute (x)** permissions, but **no write (-)** permission.  

| Position   | Meaning        | Example (`drwxr-xr-x`) |
|------------|----------------|--------------------------|
| **1st character** | File type (`d` = directory, `-` = file) | `d` |
| **1st set (User/Owner)** | `rwx` (Read, Write, Execute) | `rwx` |
| **2nd set (Group)** | `r-x` (Read, No Write, Execute) | `r-x` |
| **3rd set (Others)** | `r-x` (Read, No Write, Execute) | `r-x` |


## **2. File Permission Values**  

Each permission is represented by a **numeric value**, which is useful when setting permissions using `chmod`.  

| Permission | Symbol | Numeric Value |
|------------|--------|--------------|
| Read       | `r`    | 4            |
| Write      | `w`    | 2            |
| Execute    | `x`    | 1            |

To define a permission set, sum up the values of the required permissions:  

- `rwx` = **4 + 2 + 1 = 7**  
- `rw-` = **4 + 2 = 6**  
- `r--` = **4 = 4**  

### **Example Calculation**  
If we set permissions to `777`:  
- Owner (`7`) → **rwx** (4+2+1) = Read, Write, Execute  
- Group (`7`) → **rwx** (4+2+1) = Read, Write, Execute  
- Others (`7`) → **rwx** (4+2+1) = Read, Write, Execute  

If we set permissions to `755`:  
- Owner (`7`) → **rwx** (4+2+1) = Read, Write, Execute  
- Group (`5`) → **r-x** (4+0+1) = Read, No Write, Execute  
- Others (`5`) → **r-x** (4+0+1) = Read, No Write, Execute  

## **3. Changing File Permissions using `chmod`**  

The `chmod` command is used to **modify file permissions** for the owner, group, and others.  

### **Syntax:**  
```sh
chmod permissions filename
```

### **Example 1: Give Full Permissions to Everyone (`777`)**  
```sh
chmod 777 myfile.txt
```
📌 **Permissions Breakdown (`rwxrwxrwx`):**  
- Owner: **rwx** (Read, Write, Execute)  
- Group: **rwx** (Read, Write, Execute)  
- Others: **rwx** (Read, Write, Execute)  

### **Example 2: Give Read and Write to Owner, Read-Only to Others (`644`)**  
```sh
chmod 644 myfile.txt
```
📌 **Permissions Breakdown (`rw-r--r--`):**  
- Owner: **rw-** (Read, Write)  
- Group: **r--** (Read-only)  
- Others: **r--** (Read-only)  

## **4. Changing Directory Permissions Recursively (`chmod -R`)**  

If you want to change the **permissions of a directory and all its files/subdirectories**, use the `-R` flag:  

### **Example: Give Full Permissions to a Directory (`777`)**  
```sh
chmod -R 777 /opt/maven
```
📌 **Permissions Breakdown (`rwxrwxrwx`) for `maven/` and its contents:**  
- Owner: **rwx** (Read, Write, Execute)  
- Group: **rwx** (Read, Write, Execute)  
- Others: **rwx** (Read, Write, Execute)  
