#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |


# **Working with File Ownership in Linux**  

In Linux, each file and directory is associated with an **owner** and a **group**. The `chown` command is used to change the ownership of files and directories. This is useful when transferring files between users or setting up permissions for different groups.

## **1. Understanding File Ownership**  

Every file or directory in Linux has:  

- **User (Owner)** → The user who owns the file.  
- **Group** → A set of users who can share file permissions.  

### **Example Output of `ls -l` Command:**  
```sh
drwxr-xr-x 6 root root 99 Mar 12 00:32 maven
```
#### **Breaking it Down:**  
- **`d`** → Indicates it is a **directory** (`-` for a file).  
- **`rwxr-xr-x`** → Permissions (Owner: `rwx`, Group: `r-x`, Others: `r-x`).  
- **`root root`** → The **first `root`** is the **owner**, and the **second `root`** is the **group**.  
- **`maven`** → The name of the directory.  

In this case, **both the owner and group** of `maven/` are **root**.

## **2. Changing File Ownership with `chown`**  

The `chown` command allows you to change **the owner, group, or both** of a file or directory.  

### **Syntax:**  
```sh
chown username:groupname filename
```

🔹 **`username`** → New owner of the file/directory.  
🔹 **`groupname`** → New group ownership (optional).  
🔹 **`filename`** → The file or directory to change ownership for.  

### **Example: Change File Owner**  
```sh
chown murali myfile.txt
```
✅ Now, `murali` owns `myfile.txt`, but the group remains unchanged.  

### **Example: Change Both Owner and Group**  
```sh
chown murali:devops myfile.txt
```
✅ Now, `murali` owns `myfile.txt`, and the group is changed to `devops`.

### **Example: Change Only the Group (`chgrp` Alternative)**  
```sh
chown :devops myfile.txt
```
✅ The owner remains the same, but the **group is changed** to `devops`.  

## **3. Changing Directory Ownership Recursively (`-R` flag)**  

If you want to change the ownership of a **directory and all its contents**, use the `-R` (recursive) flag.

### **Example: Change Owner and Group for a Directory**  
```sh
chown -R murali:devops /opt/maven
```
✅ Now, **murali** is the owner, and **devops** is the group for `/opt/maven/` **and all files inside it**.


## **4. Checking Ownership After Change**  

After using `chown`, verify the changes using:  
```sh
ls -l filename
```
or  
```sh
ls -ld directoryname
```

### **Example Output After Changing Ownership**  
```sh
drwxr-xr-x 6 murali devops 99 Mar 12 00:32 maven
```
✅ The owner is now `murali`, and the group is `devops`.
