#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

# **Working with `env`, `echo`, and `tac` Commands in Linux**  

These commands are commonly used for **environment management, printing output, and reversing file contents** in Linux.  

## **1. `env` Command – Display and Manage Environment Variables**  

The `env` command **displays the environment variables** of the current shell session. It can also be used to **run a command with a modified environment**.  

### **Syntax:**  
```sh
env
```
or  
```sh
env [variable=value] [command]
```

### **Examples:**  

#### **1. Display All Environment Variables**
```sh
env
```
✅ Lists all environment variables for the current user session.  

#### **2. Run a Command with a Temporary Environment Variable**
```sh
env VAR1="Hello" VAR2="World" bash -c 'echo $VAR1 $VAR2'
```
✅ Temporarily sets **`VAR1`** and **`VAR2`**, runs a new shell, and prints them.  

#### **3. Display the Value of a Specific Variable**
```sh
echo $HOME
```
✅ Prints the **home directory path** of the current user.  

## **2. `echo` Command – Print Text and Variables**  

The `echo` command **prints text, variables, or outputs to a file**.  

### **Syntax:**  
```sh
echo [options] [text]
```

### **Commonly Used Options:**  

| Option | Description |
|--------|-------------|
| `-n` | **Removes** the trailing newline at the end of the output. |
| `-e` | Enables **interpretation of escape characters** (e.g., `\n`, `\t`). |

### **Examples:**  

#### **1. Print a Simple Message**
```sh
echo "Hello, Linux!"
```
✅ Outputs: `Hello, Linux!`  

#### **2. Print Environment Variables**
```sh
echo $USER
```
✅ Displays the **current logged-in user**.  

#### **3. Print with a New Line (`\n`) and Tab (`\t`)**
```sh
echo -e "Hello,\nWelcome to Linux!\tEnjoy your journey!"
```
✅ **`-e`** enables escape sequences:  
```
Hello,
Welcome to Linux!	Enjoy your journey!
```

#### **4. Redirect Output to a File**
```sh
echo "This is a test" > test.txt
```
✅ Writes `This is a test` into `test.txt` (overwrites if the file exists).  

```sh
echo "Another line" >> test.txt
```
✅ Appends `Another line` to `test.txt`.  

## **3. `tac` Command – Reverse File Content**  

The `tac` command is used to **display the contents of a file in reverse order** (last line first).  

### **Syntax:**  
```sh
tac filename
```

### **Examples:**  

#### **1. Display a File in Reverse Order**
```sh
tac myfile.txt
```
✅ If `myfile.txt` contains:
```
Line 1
Line 2
Line 3
```
The output will be:
```
Line 3
Line 2
Line 1
```

#### **2. Reverse a File and Save It**
```sh
tac myfile.txt > reversed.txt
```
✅ Saves the reversed content into `reversed.txt`.  

#### **3. Reverse a Specific File Using a Pipe**
```sh
cat myfile.txt | tac
```
✅ Uses **`cat`** to read the file and **`tac`** to reverse it.  
