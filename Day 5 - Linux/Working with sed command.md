#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

# **Working with `sed` Command in Linux**  

The **`sed`** (Stream Editor) command is a powerful text processing tool in Linux used for **searching, finding, replacing, inserting, and deleting text** in files or input streams. It processes text line by line and makes modifications based on specified patterns.

## **1. Basic Syntax of `sed`**  
```sh
sed [options] 'command' filename
```
🔹 The **command** can include **substitutions, deletions, insertions, or other text manipulations**.

## **2. Replacing Text Using `sed` (`s` command)**  

### **Example 1: Replace the first occurrence of a word in each line**  
```sh
sed 's/oldword/newword/' file.txt
```
✅ Replaces **the first occurrence** of `"oldword"` with `"newword"` **on each line** of `file.txt`.

### **Example 2: Replace all occurrences of a word in each line (`g` flag)**  
```sh
sed 's/oldword/newword/g' file.txt
```
✅ The **`g` (global)** flag replaces **all occurrences** of `"oldword"` in each line.

### **Example 3: Replace text only in a specific line (e.g., line 3)**  
```sh
sed '3s/oldword/newword/' file.txt
```
✅ Replaces `"oldword"` with `"newword"` **only in line 3**.

### **Example 4: Replace text in multiple lines (e.g., lines 3 to 5)**  
```sh
sed '3,5s/oldword/newword/g' file.txt
```
✅ Replaces `"oldword"` with `"newword"` in **lines 3 to 5**.

## **3. Deleting Lines Using `sed` (`d` command)**  

### **Example 5: Delete a specific line (e.g., line 2)**  
```sh
sed '2d' file.txt
```
✅ Deletes **line 2** from `file.txt`.

### **Example 6: Delete a range of lines (e.g., lines 3 to 6)**  
```sh
sed '3,6d' file.txt
```
✅ Deletes **lines 3 to 6** from `file.txt`.

### **Example 7: Delete all blank lines**  
```sh
sed '/^$/d' file.txt
```
✅ Removes **all empty lines** from `file.txt`.

## **4. Inserting and Appending Text**  

### **Example 8: Insert a line before a specific line (e.g., before line 3)**  
```sh
sed '3i\This is a new line' file.txt
```
✅ Inserts `"This is a new line"` **before line 3**.

### **Example 9: Append a line after a specific line (e.g., after line 4)**  
```sh
sed '4a\This is an appended line' file.txt
```
✅ Adds `"This is an appended line"` **after line 4**.

## **5. Printing Specific Lines Using `sed` (`p` command)**  

### **Example 10: Print only lines containing a specific word**  
```sh
sed -n '/error/p' file.txt
```
✅ Prints **only lines containing `"error"`**.

### **Example 11: Print specific lines (e.g., lines 3 to 7)**  
```sh
sed -n '3,7p' file.txt
```
✅ Prints **lines 3 to 7**.


## **6. Using `sed` with Files (In-Place Editing)**  

### **Example 12: Modify a file directly (without creating a new file)**  
```sh
sed -i 's/oldword/newword/g' file.txt
```
✅ Replaces `"oldword"` with `"newword"` in **file.txt** permanently.  
⚠️ **Warning:** This modifies the file directly! Use `-i.bak` to create a backup before making changes:
```sh
sed -i.bak 's/oldword/newword/g' file.txt
```
✅ This creates a **backup file (`file.txt.bak`)** before modifying the original file.

## **7. Removing Specific Characters Using `sed`**  

### **Example 13: Remove all digits from a file**  
```sh
sed 's/[0-9]//g' file.txt
```
✅ Removes **all numbers** from `file.txt`.

### **Example 14: Remove all spaces from a file**  
```sh
sed 's/ //g' file.txt
```
✅ Removes **all spaces** in `file.txt`.

### **Example 15: Remove a specific character (e.g., `:` from each line)**  
```sh
sed 's/://g' file.txt
```
✅ Removes **all occurrences of `:`** in `file.txt`.


## **8. Combining Multiple `sed` Commands**  

### **Example 16: Replace text, delete a line, and append new text (all in one command)**  
```sh
sed -e 's/oldword/newword/g' -e '3d' -e '5a\This is a new line' file.txt
```
✅ This command:
1. Replaces **`oldword`** with **`newword`** globally.  
2. Deletes **line 3**.  
3. Appends `"This is a new line"` **after line 5**.

## **9. Case-Insensitive Search and Replace (`I` flag)**  

### **Example 17: Replace `linux` (case-insensitive) with `UNIX`**  
```sh
sed 's/linux/UNIX/I' file.txt
```
✅ This replaces `"linux"`, `"Linux"`, `"LINUX"`, etc., with `"UNIX"`.

## **10. Removing Everything After a Specific Character**  

### **Example 18: Remove everything after `:` in each line**  
```sh
sed 's/:.*//' file.txt
```
✅ Removes everything **after and including `:`** in each line.
