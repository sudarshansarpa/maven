#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

### **Working with Files in Linux**  

In Linux, there are multiple ways to create and manage files. Some common methods include:  
- `touch`
- `cat`
- `vi` / `vim`  

**1. `touch` Command**  
The `touch` command is used to **create an empty file**.  

**Syntax**  
```sh
touch filename
```  

**Example**  
```sh
touch myfile.txt
ls -l myfile.txt
```  
📌 **Output:** Creates an empty file named `myfile.txt`.  

**2. `cat` Command**  
The `cat` (concatenate) command is widely used for **viewing, creating, appending, and copying files**.  

**1. Viewing a File's Content**  
```sh
cat filename
```  
**Example:**  
```sh
cat myfile.txt
```  

**2. Creating a New File Using `cat`**  
```sh
cat > newfile.txt
```  
🔹 **Type some text and press `CTRL + D` to save the file.**  

**3. Copying Contents from One File to Another**  
```sh
cat source.txt > destination.txt
```  
🔹 Copies `source.txt` content into `destination.txt`, replacing existing content.  

**4. Appending Content to an Existing File**  
To add new content to an existing file without overwriting, use:  

```sh
cat >> myfile.txt
```  

🔹 **Example:**  
```sh
cat >> myfile.txt
```  
**(Now type some text, then press `CTRL + D` to save it.)**  

🔹 **Verify the new content:**  
```sh
cat myfile.txt
```  

**3. `vi` / `vim` Command**  
`vi` and `vim` are powerful text editors in Linux. `vim` (Vi IMproved) is an enhanced version of `vi`.  

**1. Opening a File in `vim`**  
```sh
vim filename
```  
🔹 If the file does not exist, this command creates a new file.  

**2. Switching to Insert Mode (to Edit Text)**  
Press **`i`** to enter insert mode and start typing.  

**3. Saving and Exiting in `vim`**  

| Action                     | Command  |
|----------------------------|----------|
| Save without exiting       | `:w`     |
| Save and exit              | `:wq` or `ZZ` |
| Exit without saving        | `:q!`    |

**4. Enabling Line Numbers in `vim`**  
To display line numbers in `vim`, use:  
```sh
:set number
```  
🔹 **Shortcut:** You can also use `:set nu`.  

🔹 To make it permanent, add the following line to your `.vimrc` file:  
```sh
echo "set number" >> ~/.vimrc
```

**5. Deleting, Copying, and Pasting Text**  

| Action                  | Command    |
|-------------------------|------------|
| Delete a single character | `x` |
| Delete a whole line | `dd` |
| Copy a line (yank) | `yy` |
| Paste copied text | `p` |

**6. Searching for Text**  
Press `/` followed by the search term, then hit `Enter`.  

🔹 **Example:**  
```sh
/murali
```  
(This searches for the word "murali" in the file.)  

