#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |


## **Working with `cp` and `mv` Commands in Linux**  

In Linux, you can use the `cp` command to **copy** files and directories and the `mv` command to **move or rename** them.  

### **1. `cp` Command (Copy Files and Directories)**  

The `cp` command is used to copy files or directories from one location to another.  

### **Syntax**  
```sh
cp source destination
```  

### **Example 1: Copy a File to Another Directory**  
To copy a file named **murali** from `/root` to `/opt`:  
```sh
cp murali /opt
```  
📌 **This creates a copy of `murali` in `/opt` while keeping the original file in `/root`.**  

### **Example 2: Copy a Directory to Another Location**  
To copy a directory named **naresh** from `/root` to `/opt`, use the `-r` (recursive) flag:  
```sh
cp -r naresh/ /opt
```  
📌 **This copies the entire `naresh` directory, including all its contents, to `/opt`.**  

## **2. Preserving File Permissions While Copying**  

By default, when copying files, permissions may not be retained. To **preserve the original permissions, ownership, and timestamps**, use the appropriate flags.  

### **2.1 Preserve File Permissions**  
Use the `-p` option to retain permissions while copying a file.  

#### **Syntax**  
```sh
cp -p source destination
```  

#### **Example: Copy a File While Keeping Permissions**  
```sh
cp -p murali /opt
```  
📌 **This copies `murali` to `/opt` while keeping its original permissions, timestamps, and ownership.**  

### **2.2 Preserve File Permissions, Ownership, and Timestamps for Directories**  
If you want to copy an entire directory **with all permissions and attributes**, use the `-a` (archive) option.  

#### **Syntax**  
```sh
cp -a source_directory destination
```  

#### **Example: Copy a Directory with Permissions**  
```sh
cp -a naresh/ /opt
```  
📌 **This ensures that `naresh/` is copied to `/opt` with the same permissions, ownership, timestamps, and symbolic links.**  


## **3. `mv` Command (Move or Rename Files and Directories)**  

The `mv` command is used to **move** or **rename** files and directories.  

### **Syntax**  
```sh
mv source destination
```  

### **Example 1: Move a File to Another Directory**  
To move the file **murali** from `/root` to `/opt`:  
```sh
mv murali /opt
```  
📌 **This moves `murali` to `/opt`, removing it from `/root`.**  

### **Example 2: Rename a File or Directory**  
To rename a file **muni** to **sunil** in the same directory:  
```sh
mv muni sunil
```  
📌 **This renames `muni` to `sunil` in the current location.**  
