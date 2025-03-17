#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

# **Working with RPM Command in Linux**  

`RPM` (**Red Hat Package Manager**) is a **package management utility** used for managing `.rpm` packages on **RHEL, CentOS, Fedora**, and other RPM-based Linux distributions.  

Unlike `YUM`, **RPM does not resolve dependencies automatically**, so users must manually install dependencies if required.  

## **1. Installing a Package Using RPM**  

To install an RPM package:  
```sh
rpm -ivh package_name.rpm
```

### **Example:** Install `jfrog-artifactory-cpp-ce-7.6.2.rpm`
```sh
rpm -ivh jfrog-artifactory-cpp-ce-7.6.2.rpm
```
✅ Installs the package with a **verbose output** (`-v`) and **progress bar** (`-h`).  

## **2. Checking If an RPM Package Is Installed**  

To check whether a package is installed:  
```sh
rpm -qa package_name
```

### **Example:** Check if `jfrog-artifactory` is installed
```sh
rpm -qa jfrog-artifactory
```
✅ Lists the installed package with its version.  

## **3. Updating a Package Using RPM**  

To update (upgrade) an existing package:  
```sh
rpm -Uvh package_name.rpm
```

### **Example:** Update `jfrog-artifactory`
```sh
rpm -Uvh jfrog-artifactory-cpp-ce-7.6.2.rpm
```
✅ Installs the package if it's **not installed**, otherwise it **upgrades** it to the latest version.  


## **4. Removing a Package Using RPM**  

To uninstall a package:  
```sh
rpm -ev package_name
```

### **Example:** Remove `jfrog-artifactory`
```sh
rpm -ev jfrog-artifactory
```
✅ Removes the package from the system.  

## **5. Installing an RPM Package Without Checking Dependencies**  

If dependencies are missing and you still want to install the package:  
```sh
rpm -ivh --nodeps package_name.rpm
```

### **Example:** Install `jfrog-artifactory` without checking dependencies
```sh
rpm -ivh --nodeps jfrog-artifactory-cpp-ce-7.6.2.rpm
```
✅ Installs the package **without checking for missing dependencies** (use cautiously).  

## **6. Checking Dependencies of an RPM Package Before Installing**  

To check what dependencies a package requires:  
```sh
rpm -qpR package_name.rpm
```

### **Example:** Check dependencies of `jfrog-artifactory`
```sh
rpm -qpR jfrog-artifactory-cpp-ce-7.6.2.rpm
```
✅ Lists all dependencies required by the package.  

## **7. Understanding RPM Options**  

| Option | Description |
|--------|-------------|
| `-i` | Installs a package |
| `-U` | Upgrades or installs a package |
| `-v` | Verbose output |
| `-h` | Shows a progress bar |
| `-q` | Queries a package |
| `-a` | Queries all installed packages |
| `-e` | Removes a package |
| `-p` | Lists capabilities a package provides |
| `-R` | Lists dependencies a package requires |
| `--nodeps` | Ignores dependency checks |

## **8. RPM vs YUM**  

| Feature | RPM | YUM |
|---------|-----|-----|
| **Handles Dependencies** | ❌ No | ✅ Yes |
| **Automatic Updates** | ❌ No | ✅ Yes |
| **Installation Command** | `rpm -ivh package.rpm` | `yum install package -y` |
| **Removal Command** | `rpm -ev package` | `yum remove package -y` |
