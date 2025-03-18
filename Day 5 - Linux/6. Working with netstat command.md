#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

# **Working with `netstat` Command in Linux**  

The `netstat` (**Network Statistics**) command is used to monitor **network connections, routing tables, interface statistics, masquerade connections, and more** in Linux. It helps system administrators analyze network performance and troubleshoot network issues.

⚠️ **Note:** `netstat` is deprecated in modern Linux distributions and replaced by the `ss` and `ip` commands.

## **1. Display All Network Connections**  
```sh
netstat -a
```
✅ Shows **all active and listening** network connections.

## **2. Display Only TCP Connections**  
```sh
netstat -at
```
✅ Displays **only TCP** connections.

## **3. Display Only UDP Connections**  
```sh
netstat -au
```
✅ Displays **only UDP** connections.

## **4. Display Listening Ports**  
```sh
netstat -l
```
✅ Shows **only listening** sockets.

### **4.1. Show Only Listening TCP Ports**
```sh
netstat -lt
```
✅ Lists **only listening TCP** ports.

### **4.2. Show Only Listening UDP Ports**
```sh
netstat -lu
```
✅ Lists **only listening UDP** ports.

### **4.3. Show Listening UNIX Domain Sockets**
```sh
netstat -lx
```
✅ Lists **listening UNIX domain sockets**.

## **5. Show Network Statistics**  
```sh
netstat -s
```
✅ Displays **network statistics** (packets received, errors, dropped packets, etc.).

### **5.1. Show Only TCP Statistics**
```sh
netstat -st
```
✅ Displays **only TCP statistics**.

### **5.2. Show Only UDP Statistics**
```sh
netstat -su
```
✅ Displays **only UDP statistics**.

## **6. Continuously Monitor Network Connections**  
```sh
netstat -c
```
✅ Continuously updates **network statistics every second**.

## **7. Display More Verbose Output**  
```sh
netstat --verbose
```
✅ Provides **detailed information** about the network status.

## **8. Show Kernel Routing Table (Similar to `route -n`)**  
```sh
netstat -r
```
✅ Displays the **routing table** (like `route -n`).

## **9. Find Processes Using a Specific Port**  
```sh
netstat -an | grep 8080
```
✅ Checks which process is **using port 8080**.


## **Alternative to `netstat` (`ss` Command in Modern Linux Versions)**  
Since `netstat` is deprecated, use the **`ss` (socket statistics)** command instead:

### **Show All TCP Connections**  
```sh
ss -t
```

### **Show All UDP Connections**  
```sh
ss -u
```

### **Show Listening TCP Ports**  
```sh
ss -lt
```

### **Show Listening UDP Ports**  
```sh
ss -lu
```
