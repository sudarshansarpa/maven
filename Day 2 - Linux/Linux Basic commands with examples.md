#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

### **Linux Basic Commands - Part 1**  

1. **`sudo su -` (Switch to Root User)**  
   - Switches to the **root** user with full administrative privileges.  
   - Requires **sudo** access.  
   - Example:  
     ```bash
     sudo su -
     ```
   - After running, the prompt changes to `#`, indicating root access.  

2. **`pwd` (Print Working Directory)**  
   - Displays the current directory path.  
   - Example:  
     ```bash
     pwd
     ```
   - Output:  
     ```
     /root
     ```

3. **`cd` (Change Directory)**  
   - Used to navigate between directories.  
   - Examples:  
     ```bash
     cd /opt/aws  # Move to a specific directory
     cd ..                    # Move one level up
     cd                       # Pressing Enter after 'cd' takes you to the home directory
     cd ~                     # Go to the home directory
     ```

4. **`ls` (List Files & Directories)**  
   - Lists all files and folders in the current directory.  
   - Examples:  
     ```bash
     ls          # List files
     ls -l       # Detailed list with permissions, size, and modification date
     ls -a       # Show hidden files (files starting with .)
     ls -lh      # Human-readable file sizes
     ls -ltr     # List in long format, sorted by modification time (oldest first)
     ```
     ---
