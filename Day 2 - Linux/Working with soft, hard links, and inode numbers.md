#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

# **Understanding Links in Linux: Soft Links & Hard Links & Inode Number**  

In Linux, links are used to create references to files. There are two types of links: **Soft Links (Symbolic Links)** and **Hard Links**.  

## **1. Soft Link (Symbolic Link) in Linux**  

A **soft link** (symbolic link) is a pointer to the original file, similar to a shortcut. If the original file is deleted, the soft link becomes invalid because it no longer points to an existing file.  

### **Key Features of Soft Links:**  
✔ Works for both **files** and **directories**  
✔ Has a **different inode number** than the original file  
✔ If the original file is deleted, the soft link **becomes invalid**  

### **Syntax: Create a Soft Link**  
```sh
ln -s original_file soft_link_name
```  

### **Example: Create a Soft Link for a File**  
```sh
ln -s myfile.txt mysoftlink
```  
📌 **This creates a symbolic link `mysoftlink` pointing to `myfile.txt`.**  

### **Example: Create a Soft Link for a Directory**  
```sh
ln -s /opt/data /home/user/data_link
```  
📌 **This creates a symbolic link `data_link` pointing to `/opt/data`.**  

## **2. Hard Link in Linux**  

A **hard link** is a direct reference to the same inode as the original file. Even if the original file is deleted, the hard link will still retain the data.  

### **Key Features of Hard Links:**  
✔ Works **only for files** (not directories)  
✔ Has the **same inode number** as the original file  
✔ If the original file is deleted, the hard link **still retains the data**  

### **Syntax: Create a Hard Link**  
```sh
ln original_file hard_link_name
```  

### **Example: Create a Hard Link**  
```sh
ln myfile.txt myhardlink
```  
📌 **Now, `myfile.txt` and `myhardlink` share the same inode number and data.**  

### **Check Inode Numbers to Confirm Hard Link**  
```sh
ls -li myfile.txt myhardlink
```  
📌 **Both files will have the same inode number, meaning they are identical copies.**  

## **3. What is an Inode Number in Linux?**  

An **inode number** is a unique identifier assigned to every file in a Linux/Unix system. It contains metadata about the file (like permissions, ownership, and file type) but **not** the file name.  

### **Check the Inode Number of a File**  
```sh
ls -li filename
```  

### **Example: Display Inode Numbers**  
```sh
ls -li myfile.txt mysoftlink myhardlink
```  
📌 **Soft links have a different inode number, while hard links share the same inode as the original file.**  
