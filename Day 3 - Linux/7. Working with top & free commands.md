#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

# **Working with `top` and `free` Commands in Linux**

In Linux, the `top` and `free` commands are essential tools for monitoring system performance, particularly the processes running and memory usage.

## **1. `top` Command in Linux**

The `top` command is a dynamic tool that displays real-time information about the system's processes, memory usage, CPU activity, and more. It is typically used to monitor system performance and track resource usage by processes.

### **Syntax:**  
```sh
top
```

#### **Example Output:**

```sh
[root@ip-10-70-10-192 ~]# top
top - 01:00:21 up 25 min,  2 users,  load average: 0.00, 0.00, 0.00
Tasks: 102 total,   1 running, 101 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni, 94.3 id,  0.0 wa,  0.0 hi,  0.0 si,  5.7 st
MiB Mem :    949.5 total,    618.8 free,    127.0 used,    203.6 buff/cache
MiB Swap:      0.0 total,      0.0 free,      0.0 used.    685.1 avail Mem

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
      1 root      20   0  105720  16832  10468 S   0.0   1.7   0:00.77 systemd
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kthreadd
      3 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 rcu_gp
```

### **Breaking Down the Output:**

1. **System Information:**
   - **`01:00:21`** → Current system time.
   - **`up 25 min`** → The system has been running for 25 minutes since the last reboot.
   - **`2 users`** → There are 2 users currently logged into the system.
   - **`load average: 0.00, 0.00, 0.00`** → The load average over the last 1, 5, and 15 minutes. A low load average indicates the system is idle.

2. **Tasks Information:**
   - **`Tasks: 102 total`** → There are 102 processes in total.
   - **`1 running, 101 sleeping`** → 1 process is actively running, and 101 are in a sleeping (idle) state.
   - **`0 stopped, 0 zombie`** → No processes are stopped or in a zombie state.

3. **CPU Usage:**
   - **`%Cpu(s): 0.0 us, 0.0 sy, 0.0 ni, 94.3 id, 0.0 wa, 0.0 hi, 0.0 si, 5.7 st`**
     - **`us`** (user): The percentage of CPU used by user processes (0.0%).
     - **`sy`** (system): The percentage of CPU used by system processes (0.0%).
     - **`ni`** (nice): The percentage of CPU used by user processes with altered priority (0.0%).
     - **`id`** (idle): The percentage of CPU time spent idle (94.3%).
     - **`wa`** (I/O wait): The percentage of CPU time spent waiting for I/O operations (0.0%).
     - **`hi`** (hardware interrupts): The percentage of CPU time spent handling hardware interrupts (0.0%).
     - **`si`** (software interrupts): The percentage of CPU time spent handling software interrupts (0.0%).
     - **`st`** (steal): The percentage of CPU time stolen from virtual machines (5.7%).

4. **Memory Information:**
   - **`MiB Mem: 949.5 total`** → The total memory is 949.5 MB.
   - **`618.8 free`** → 618.8 MB of memory is free.
   - **`127.0 used`** → 127.0 MB of memory is used.
   - **`203.6 buff/cache`** → 203.6 MB of memory is used for buffers/cache.
   - **`MiB Swap: 0.0 total`** → There is no swap space configured (0.0 MB).
   - **`685.1 avail Mem`** → 685.1 MB of memory is available for use.

### **Process List:**

- The list shows information about each running process on the system.
- **PID:** The process ID.
- **USER:** The user who owns the process.
- **PR (Priority):** The priority of the process.
- **NI (Nice value):** The priority value altered by the user.
- **VIRT (Virtual memory):** The total virtual memory used by the process.
- **RES (Resident memory):** The portion of the process’s memory that is held in RAM.
- **SHR (Shared memory):** Memory shared with other processes.
- **S:** The current status of the process (e.g., Sleeping, Running).
- **%CPU:** Percentage of CPU usage by the process.
- **%MEM:** Percentage of memory usage by the process.
- **TIME+:** Total CPU time consumed by the process.
- **COMMAND:** The name of the process (e.g., `systemd`).

### **Key Shortcuts in `top`:**

- **`q`** → Quit the `top` command.
- **`P`** → Sort processes by CPU usage.
- **`M`** → Sort processes by memory usage.
- **`N`** → Sort processes by PID.
- **`1`** → Show CPU usage per core.
- **`u`** → Filter processes by a specific user.

## **2. `free` Command in Linux**

The `free` command shows memory usage statistics, providing information about the total, used, free, and swap memory. It is a great tool for getting a quick overview of system memory resources.

### **Syntax:**  
```sh
free
```

#### **Example:**  
```sh
free
```
✅ This will display the memory usage in **kilobytes (KB)** by default.

### **Example Output of `free`:**

```sh
              total        used        free      shared  buff/cache   available
Mem:          16280084     2766540     12107692       54232      932852      13493696
Swap:         4095996           0      4095996
```

- **Mem:** Displays the total memory, used memory, free memory, memory used by shared memory, cache/buffer memory, and memory available for use.
- **Swap:** Shows the swap memory statistics.
### **Using the `-h` Option for Human-Readable Output:**

To display memory in a more readable format, such as megabytes (MB) or gigabytes (GB), use the `-h` flag.

### **Syntax:**  
```sh
free -h
```

#### **Example:**  
```sh
free -h
```
✅ This will display the memory statistics in a **human-readable format** (e.g., GB, MB).

### **Key Columns in `free`:**

- **total:** Total amount of memory.
- **used:** Memory currently used by processes.
- **free:** Memory that is completely unused.
- **shared:** Memory used by multiple processes.
- **buffers/cache:** Memory used by the system for buffers and caches (can be reclaimed).
- **available:** Memory available for starting new applications.

## **Summary Table for `top` and `free`**

| Command        | Description                                                | Example Command      |
|----------------|------------------------------------------------------------|----------------------|
| `top`          | Displays a dynamic, real-time view of system processes.    | `top`                |
| `free`         | Displays memory usage (total, used, free, swap, etc.).     | `free`               |
| `free -h`      | Displays memory usage in a human-readable format.          | `free -h`            |
| `top -u user`  | Show processes for a specific user.                        | `top -u root`        |
| `top -p PID`   | Display information for a specific process ID (PID).      | `top -p 1234`        |
