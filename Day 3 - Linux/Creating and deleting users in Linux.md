#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |


## **1. Creating and Deleting Users in Linux**

In Linux, creating and deleting users can be done using commands such as `useradd`, `userdel`, and checking user details with the `id` or `cat /etc/passwd` command.


### **Creating a User**

To create a new user on your system, you can use either of the following commands:

#### **1. `useradd` Command:**
```sh
useradd username
```

#### **2. `adduser` Command:**
In some Linux distributions (like Debian-based systems), `adduser` is a more user-friendly script for creating users.
```sh
adduser username
```

#### **Explanation:**
- **`username`** → This is the name of the user you want to create.

Both commands create a new user, but `adduser` is typically more interactive and sets up additional configuration like password and home directory automatically.


### **Check If the User is Created**

To verify if the user has been created successfully, you can use the following commands:

#### **1. `id` Command:**
```sh
id username
```
This command will display the user ID (UID), group ID (GID), and the groups the user belongs to.

#### **2. `/etc/passwd` File:**
```sh
cat /etc/passwd | grep username
```
This command checks the `/etc/passwd` file, which stores information about all users on the system. If the user exists, you will see an entry for them.

### **Deleting a User**

To remove a user, you can use the `userdel` command.

#### **1. `userdel` Command:**
```sh
userdel username
```

This deletes the user but **does not** remove their home directory.

#### **2. `userdel -r` Command:**
```sh
userdel -r username
```

#### **Explanation:**
- **`-r`** → Removes the user's home directory and mail spool along with the user. This is useful to clean up all user-specific files.

### **Example Usage:**

#### **Create a User:**
```sh
useradd john
```

#### **Verify User Creation:**
```sh
id john
```

#### **Delete a User:**
```sh
userdel -r john
```

### **Note:**
- The `userdel` command will not remove files or directories owned by the user if they are elsewhere on the system. Use with caution, and always double-check before removing user accounts.
- **`-r`** is crucial if you want to remove all files associated with the user, including their home directory and mail spool.

### **Summary:**

| Command | Action |
|---------|--------|
| `useradd username` | Creates a user without additional options. |
| `adduser username` | Creates a user with additional prompts (interactive). |
| `id username` | Verifies user creation and shows UID, GID, and groups. |
| `cat /etc/passwd | grep username` | Checks the `/etc/passwd` file for the user entry. |
| `userdel username` | Deletes the user (but keeps the home directory). |
| `userdel -r username` | Deletes the user and removes their home directory and mail spool. |
