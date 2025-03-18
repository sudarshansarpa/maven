#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

# **Working with YUM Command in Linux**  

`YUM` (**Yellowdog Updater Modified**) is a powerful **package management tool** for **RPM-based** Linux distributions such as **RHEL (Red Hat Enterprise Linux), CentOS, Fedora**, and Amazon Linux.  

It allows system administrators to **install, update, remove, and search** for software packages easily.  

## **1. Installing a Package**  

To install a package (e.g., `git` or `httpd`), use:  
```sh
yum install packagename -y
```
🔹 `-y` → Automatically **confirm** installation.  

### **Example:** Install `git`
```sh
yum install git -y
```
✅ Installs `git` without asking for confirmation.  

## **2. Removing a Package**  

To remove a package from the system, use:  
```sh
yum remove packagename -y
```

### **Example:** Remove `httpd`
```sh
yum remove httpd -y
```
✅ Removes `httpd` from the system.  

## **3. Updating a Package**  

To update a specific package:  
```sh
yum update packagename
```

### **Example:** Update `git`
```sh
yum update git
```
✅ Updates `git` to the latest available version.  

To update **all** packages:  
```sh
yum update -y
```
✅ Updates all installed packages.  

## **4. Checking Available Updates**  

To list all packages that have updates available:  
```sh
yum check-update
```
✅ Displays available updates for installed packages.  


## **5. Checking If a Package Is Installed**  

To check whether a package is installed:  
```sh
yum list installed packagename
```

### **Example:** Check if `httpd` is installed
```sh
yum list installed httpd
```
✅ Shows details if `httpd` is installed.  

## **6. Searching for a Package**  

To search for a package in the YUM repository:  
```sh
yum search packagename
```

### **Example:** Search for `git`
```sh
yum search git
```
✅ Lists all available packages related to `git`.  


## **7. Viewing Package Information**  

To check details about a package, use:  
```sh
yum info packagename
```

### **Example:** Get info about `httpd`
```sh
yum info httpd
```
✅ Shows version, repository, size, and a short description of `httpd`.  

## **8. Viewing YUM Command History**  

To check past package management activities:  
```sh
yum history
```
✅ Displays the history of installed, updated, or removed packages.  


## **Summary of YUM Commands**  

| Command | Description |
|---------|-------------|
| `yum install packagename -y` | Installs a package |
| `yum remove packagename -y` | Removes a package |
| `yum update packagename` | Updates a specific package |
| `yum update -y` | Updates all installed packages |
| `yum check-update` | Lists available updates |
| `yum list installed packagename` | Checks if a package is installed |
| `yum search packagename` | Searches for a package |
| `yum info packagename` | Displays package details |
| `yum history` | Shows YUM command history |
