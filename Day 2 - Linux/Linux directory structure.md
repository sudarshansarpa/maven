#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

### **What is the Linux Directory Structure?**  

The **Linux directory structure** is a hierarchical organization of files and directories, starting from the **root (`/`) directory**. It follows the **Filesystem Hierarchy Standard (FHS)**, which defines standard locations for different types of files and directories in Linux-based operating systems.

### **Why is the Linux Directory Structure Important?**
- Provides a **standardized way** to organize files.
- Helps users and applications locate system files, configurations, and binaries.
- Ensures proper **separation of system files, user data, and temporary files**.
- Allows **multiple users** to operate on the same system efficiently.

## **Hierarchy of Linux Directories**  
The Linux filesystem starts at **`/` (root directory)**, which contains all other directories and files.  

### **Main Directories in Linux**  

```
/               → Root directory (top-level of the filesystem).
├── /bin        → User Binaries
├── /boot       → Boot Loader Files
├── /dev        → Device Files
├── /etc        → Configuration Files
├── /home       → Home Directories
├── /lib        → System Libraries
├── /lib64      → System Libraries
├── /media      → Mount Point for Removable Media
├── /mnt        → Mount Point for Temporary Filesystems
├── /opt        → Optional Add-on Applications
├── /proc       → Process Information
├── /root       → Root User Directory
├── /sbin       → System Binaries
├── /srv        → Service Data
├── /sys        → Virtual Filesystem
├── /tmp        → Temporary Files
├── /usr        → User Programs
├── /var        → Variable Files
└── /lost+found → Misplaced Data (Used for Recovery)
```

### Detailed explanation of the **Linux Directory Structure** :

### **1. `/` (Root Directory)**
- The top-most directory in Linux.
- All files and directories start from here.
- It contains all essential system directories.



### **2. `/bin` (User Binaries)**
- Stores essential command-line utilities.
- Available for all users.
- Examples:
  - `ls` (List directory)
  - `cp` (Copy files)
  - `rm` (Remove files)
  - `cat` (Display file content)



### **3. `/boot` (Boot Loader Files)**
- Contains boot-related files.
- Stores the Linux kernel and bootloader (e.g., GRUB).
- Examples:
  - `vmlinuz` (Kernel image)
  - `initrd.img` (Initial RAM Disk)



### **4. `/dev` (Device Files)**
- Contains files representing hardware devices.
- Linux treats devices as files.
- Examples:
  - `/dev/sda` (Hard disk)
  - `/dev/usb` (USB device)
  - `/dev/null` (Null device)



### **5. `/etc` (Configuration Files)**
- Stores system-wide configuration files.
- Used for application and system settings.
- Examples:
  - `/etc/passwd` (User accounts)
  - `/etc/hosts` (Hostname to IP mappings)
  - `/etc/ssh/sshd_config` (SSH configuration)



### **6. `/home` (Home Directories)**
- Stores personal files and settings for users.
- Each user gets a separate directory.
- Example:
  - `/home/john/` (Home directory for user **john**)



### **7. `/lib` (System Libraries)**
- Contains shared libraries needed by binaries in `/bin` and `/sbin`.
- Examples:
  - `libc.so` (C standard library)
  - `libm.so` (Math library)



### **8. `/lib64` (System Libraries for 64-bit Systems)**
- Stores 64-bit system libraries.
- Similar to `/lib` but for 64-bit architecture.



### **9. `/media` (Mount Point for Removable Media)**
- Used for mounting external drives like USB and CD-ROMs.
- Example:
  - `/media/usb` (USB device)
  - `/media/cdrom` (CD/DVD drive)



### **10. `/mnt` (Mount Point for Temporary Filesystems)**
- Used for manually mounting filesystems.
- Example:
  ```sh
  mount /dev/sdb1 /mnt
  ```
  - Temporarily mounts an external disk.



### **11. `/opt` (Optional Add-on Applications)**
- Stores third-party software and add-ons.
- Example:
  - `/opt/google/chrome/` (Google Chrome installation)



### **12. `/proc` (Process Information)**
- Virtual filesystem providing real-time system information.
- Contains information about running processes and system hardware.
- Examples:
  - `/proc/cpuinfo` (CPU details)
  - `/proc/meminfo` (Memory usage)
  - `/proc/1234/` (Process ID 1234’s details)



### **13. `/root` (Root User Directory)**
- Home directory for the **root** user.
- Not accessible to normal users.
- Example:
  - Root user’s personal files are stored here.



### **14. `/sbin` (System Binaries)**
- Contains system administration commands.
- Only root users typically run these commands.
- Examples:
  - `fdisk` (Partition management)
  - `fsck` (Filesystem check)
  - `iptables` (Firewall configuration)
  - `reboot` (Restart the system)



### **15. `/srv` (Service Data)**
- Stores service-related data like web servers or FTP servers.
- Example:
  - `/srv/www` (Web server files)
  - `/srv/ftp` (FTP server files)



### **16. `/sys` (Virtual Filesystem for System Info)**
- Provides information about system devices and kernel.
- Similar to `/proc` but specifically for hardware interactions.
- Examples:
  - `/sys/class/net/` (Network interface details)
  - `/sys/class/block/` (Storage devices)



### **17. `/tmp` (Temporary Files)**
- Stores temporary files created by applications.
- Gets cleared on reboot.
- Example:
  - `/tmp/session.log` (Temporary session log)



### **18. `/usr` (User Programs)**
- Stores installed user applications and libraries.
- Examples:
  - `/usr/bin/` (User commands like `vim`, `nano`)
  - `/usr/lib/` (Libraries for installed programs)



### **19. `/var` (Variable Files)**
- Stores log files, temporary files, and caches.
- Examples:
  - `/var/log/` (System logs)
  - `/var/cache/` (Cached data)



### **20. `/lost+found` (Misplaced Data)**
- Used by the **fsck** tool to store recovered corrupted files.
- Found in `ext3` and `ext4` formatted partitions.

