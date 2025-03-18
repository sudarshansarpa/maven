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
### **Linux Basic Commands - Part 2**  

1. **`cal` (Show Calendar)**  
   - Displays the current month’s calendar.  
   - Example:  
     ```bash
     cal
     ```
   - Output:  
     ```
        March 2025        
     Su Mo Tu We Th Fr Sa  
                     1  
      2  3  4  5  6  7  8  
      9 10 11 12 13 14 15  
     16 17 18 19 20 21 22  
     23 24 25 26 27 28 29  
     30 31  
     ```

2. **`date` (Show Date & Time)**  
   - Displays the current system date and time.  
   - Example:  
     ```bash
     date
     ```
   - Output:  
     ```
     Mon Mar 17 14:30:00 UTC 2025
     ```

### **3. `history` (Show Command History)**  
   - Displays the list of previously executed commands.  
   - **Example:**  
     ```bash
     history
     ```
   - **Output (sample):**  
     ```
     1  ls
     2  pwd
     3  cd /home/user
     4  cal
     5  date
     ```


### **3.1 Clear Command History (`history -c`)**  
   - Clears all previously executed commands from history.  
   - **Example:**  
     ```bash
     history -c
     ```

### **3.2 Search Command History for "java" (`history | grep java`)**  
   - Filters and displays only commands containing "java".  
   - **Example:**  
     ```bash
     history | grep java
     ```
   - **Output (sample):**  
     ```
     10  java -version
     25  javac HelloWorld.java
     42  history | grep java
     ```
4. **`clear` (Clear Terminal Screen)**  
   - Clears the terminal screen.  
   - Example:  
     ```bash
     clear
     ```
   - After execution, the terminal appears blank, removing previous outputs.  
---
### **Linux Basic Commands - Part 3**  

1. **`man` (Manual Pages for Commands)**  
   - Displays the manual (help) for any command.  
   - Example:  
     ```bash
     man ls
     ```
   - Press **`q`** to exit the manual.  

2. **Check CPU and Memory Info**  

   - **Check CPU Information**  
     ```bash
     cat /proc/cpuinfo
     ```
     - Displays details about the CPU, such as model, cores, and speed.  
   
   - **Check Memory Information**  
     ```bash
     cat /proc/meminfo
     ```
     - Shows total and available system memory.  

   - **Alternative CPU and Memory Check**  
     ```bash
     lscpu    # Summarized CPU information
     free -h  # Shows memory usage in human-readable format
     ```

3. **`ping` (Test Network Connectivity)**  
   - Sends packets to a remote host to check if it's reachable.  
   - Example:  
     ```bash
     ping google.com
     ```
   - To stop, press **Ctrl + C**.  

**4. `curl` (Transfer Data from URLs)**  
   - Fetches data from a given URL.  
   - **Example:**  
     ```bash
     curl https://techworldwithmurali.com
     ```

**4.1 Download a File (-O option)**  
   ```bash
   curl -O https://dlcdn.apache.org/maven/maven-3/3.9.9/binaries/apache-maven-3.9.9-bin.tar.gz
   ```
   - Downloads the file with the same name as on the server.  

**4.2 Download and Save with a Different Name (-o option)**  
   ```bash
   curl -o maven.tar.gz https://dlcdn.apache.org/maven/maven-3/3.9.9/binaries/apache-maven-3.9.9-bin.tar.gz
   ```
   - Saves the file as `maven.tar.gz` instead of the original name.  

**4.3 Ignore SSL Certificate Warnings (-k option)**  
   ```bash
   curl -k https://techworldwithmurali.com
   ```
   - Allows connecting to a server with a self-signed or invalid SSL certificate.  

**4.4 Enable Verbose Mode (-v option)**  
   ```bash
   curl -v https://techworldwithmurali.com
   ```
   - Shows detailed request/response headers and connection details.  

**4.5 Combine `-k` and `-v` (-kv option)**  
   ```bash
   curl -kv https://techworldwithmurali.com
   ```
   - Uses verbose mode (`-v`) and ignores SSL certificate warnings (`-k`).  
   - Useful for debugging HTTPS issues. 🚀  

---
### **Linux Basic Commands - Part 4**

**1. `who` and `whoami`**
- **`who`** → Displays the users currently logged into the system.
  ```sh
  who
  ```
  **Example Output:**
  ```
  e2-user  pts/0  2025-03-17 08:30 (192.168.1.10)
  root  pts/1  2025-03-17 08:45 (192.168.1.11)
  ```

- **`whoami`** → Displays the current logged-in user's name.
  ```sh
  whoami
  ```
  **Example Output:**
  ```
  root
  ```

**2. `wget`**
- **Purpose**: Downloads files from the internet.
- **Example Usage**:
  ```sh
  wget https://dlcdn.apache.org/maven/maven-3/3.9.9/binaries/apache-maven-3.9.9-bin.zip
  ```
  - Downloads `file.zip` from `example.com`.

  **Other useful options:**
  - Download in the background:
    ```sh
    wget -b https://dlcdn.apache.org/maven/maven-3/3.9.9/binaries/apache-maven-3.9.9-bin.zip
    ```
  - Resume a partially downloaded file:
    ```sh
    wget -c https://dlcdn.apache.org/maven/maven-3/3.9.9/binaries/apache-maven-3.9.9-bin.zip
    ```

**3. `grep`**
- **Purpose**: Searches for text patterns in files.
- **Example Usage**:
  ```sh
  grep "error" /var/log/syslog
  ```
  - Searches for the word "error" in the system log file.

  **Other useful options:**
  - Case-insensitive search:
    ```sh
    grep -i "error" /var/log/syslog
    ```
  - Search in multiple files:
    ```sh
    grep "error" *.log
    ```

**4. `tree`**
- **Purpose**: Displays directories and files in a tree-like structure.
- **Example Usage**:
  ```sh
  tree /opt/aws
  ```
  - Shows a tree structure of the `/home/user` directory.

  **Note**: If `tree` is not installed, you can install it using:
  ```sh
  sudo apt install tree  # For Debian-based systems
  sudo yum install tree  # For RHEL-based systems
  ```

**5. `last`**
- **Purpose**: Displays the login history of users.
- **Example Usage**:
  ```sh
  last
  ```
  **Example Output:**
  ```
  ec2-user   pts/0        192.168.1.10   Mon Mar 17 08:30   still logged in
  root   pts/1        192.168.1.11   Mon Mar 17 08:45   still logged in
  reboot  system boot  5.4.0-91-generic Mon Mar 17 08:00
  ```

  **Other useful options:**
  - Show reboots:
    ```sh
    last reboot
    ```
  - Show login history of a specific user:
    ```sh
    last user1
    ```
    
**6. `shutdown`**
- **Purpose**: Shuts down or reboots the system.
- **Example Usage**:
  - Shutdown immediately:
    ```sh
    sudo shutdown now
    ```
  - Schedule shutdown in 10 minutes:
    ```sh
    sudo shutdown +10
    ```
  - Shutdown at a specific time (e.g., 22:00):
    ```sh
    sudo shutdown 22:00
    ```
  - Reboot instead of shutdown:
    ```sh
    sudo shutdown -r now
    ```
  - Cancel a scheduled shutdown:
    ```sh
    sudo shutdown -c
    ```
