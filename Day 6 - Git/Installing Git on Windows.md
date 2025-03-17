### Installing Git on Windows

### **Step 1: Download Git for Windows**
1. Go to the official Git website: [https://git-scm.com/download/win](https://git-scm.com/download/win).
2. The download should start automatically. If not, click on the provided link for the latest version.

### **Step 2: Run the Installer**
1. Locate the downloaded `.exe` file (usually in your **Downloads** folder).
2. Double-click it to launch the installation.

### **Step 3: Go Through the Installation Wizard**
During the installation, you’ll see several options. Here’s what you can choose:

1. **Select Destination Location**  
   - Choose the folder where Git will be installed. The default is usually fine (`C:\Program Files\Git`).
   - Click **Next**.

2. **Select Components**  
   - Keep the default settings unless you have specific needs.
   - Ensure **“Git Bash Here”** and **“Git GUI Here”** are selected.

3. **Start Menu Folder**  
   - Leave as default or change if needed.
   - Click **Next**.

4. **Choosing the Default Editor**  
   - Select a text editor (default is Vim, but you can choose Notepad++, VS Code, etc.).
   - Click **Next**.

5. **Adjusting Path Environment**  
   - Choose **“Git from the command line and also from 3rd-party software”** (recommended).
   - Click **Next**.

6. **Choosing HTTPS Transport Backend**  
   - Select **“Use the OpenSSL library”** (default).
   - Click **Next**.

7. **Configuring Line Ending Conversions**  
   - Select **“Checkout Windows-style, commit Unix-style line endings”** (recommended).
   - Click **Next**.

8. **Choosing Terminal Emulator**  
   - Choose **“Use MinTTY”** (recommended for Git Bash).
   - Click **Next**.

9. **Extra Options**  
   - Enable **“Enable file system caching”**.
   - Click **Next**.

10. **Completing Installation**  
    - Click **Install** and wait for it to finish.
    - Click **Finish** when done.

### **Step 4: Verify Git Installation**
1. Open **Command Prompt** or **Git Bash**.
2. Type:
   ```sh
   git --version
   ```
3. If Git is installed correctly, it will display the installed version.

### **Step 5: Configure Git (Optional but Recommended)**
Set up your name and email for Git commits:
```sh
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

You're all set! 🚀
