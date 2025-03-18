#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

# **Working with Directories in Linux**  

Directories (folders) in Linux can be created, managed, and navigated using various commands. The most common command for creating directories is `mkdir`.  

## **1. Creating a Directory**  
The `mkdir` (make directory) command is used to create new directories.  

### **Syntax**  
```sh
mkdir directory_name
```  

### **Example**  
To create a directory named **murali**, run:  
```sh
mkdir murali
```  
📌 **This will create a new directory named `murali`.**  

## **2. Creating Nested (Sub) Directories**  
If you need to create multiple levels of directories at once, use the `-p` option.  

### **Syntax**  
```sh
mkdir -p /path/to/directory
```  

### **Example**  
```sh
mkdir -p /opt/sunil/naresh/siva
```  
📌 **This creates the entire directory structure `/opt/sunil/naresh/siva`, even if parent directories don't exist.**  
