#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |


# **Working with `ifconfig` (Linux) and `ipconfig` (Windows)**  

Networking configuration tools differ between **Linux** and **Windows**. In Linux, `ifconfig` (now replaced by `ip` command) is used for network interface management, while in Windows, `ipconfig` helps in displaying network details.  


## **1. `ifconfig` Command (Linux)**  

The **`ifconfig`** (**interface configuration**) command is used to configure, manage, and query network interfaces in **Linux/Unix** systems.  

🔹 **Note:** `ifconfig` is **deprecated** in newer Linux versions and replaced with the `ip` command. However, you can still use it if the `net-tools` package is installed.  

### **Basic Usage:**  
```sh
ifconfig
```
✅ Displays active network interfaces and their details.  

### **Example Output:**  
```sh
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
    inet 192.168.1.100  netmask 255.255.255.0  broadcast 192.168.1.255
    inet6 fe80::1a2b:3c4d:5e6f:7890  prefixlen 64  scopeid 0x20<link>
    ether 00:1a:2b:3c:4d:5e  txqueuelen 1000  (Ethernet)
```

### **Common `ifconfig` Commands:**  

| Command | Description |
|---------|------------|
| `ifconfig eth0` | Show details of `eth0` interface. |
| `ifconfig eth0 192.168.1.200 netmask 255.255.255.0` | Assign IP address to `eth0`. |
| `ifconfig eth0 down` | Disable the network interface. |
| `ifconfig eth0 up` | Enable the network interface. |
| `ifconfig eth0 mtu 9000` | Change the MTU size. |

## **2. `ip` Command (Linux Replacement for `ifconfig`)**  

Since `ifconfig` is deprecated, the **`ip` command** is recommended for network configuration.  

| **Command** | **Equivalent `ip` Command** |
|-------------|----------------------------|
| `ifconfig` | `ip addr show` |
| `ifconfig eth0` | `ip addr show eth0` |
| `ifconfig eth0 192.168.1.200 netmask 255.255.255.0` | `ip addr add 192.168.1.200/24 dev eth0` |
| `ifconfig eth0 up` | `ip link set eth0 up` |
| `ifconfig eth0 down` | `ip link set eth0 down` |

## **3. `ipconfig` Command (Windows)**  

The **`ipconfig`** command in Windows is used to display and configure **network interface settings**. It provides details about the **IP address, subnet mask, and default gateway**.  

### **Basic Usage:**  
```powershell
ipconfig
```
✅ Displays all active network interfaces.  

### **Example Output:**  
```plaintext
Ethernet adapter Ethernet:

   Connection-specific DNS Suffix  . : example.com
   IPv4 Address. . . . . . . . . . . : 192.168.1.100
   Subnet Mask . . . . . . . . . . . : 255.255.255.0
   Default Gateway . . . . . . . . . : 192.168.1.1
```

### **Common `ipconfig` Commands:**  

| Command | Description |
|---------|------------|
| `ipconfig /all` | Show **detailed network information** (MAC address, DNS, etc.). |
| `ipconfig /release` | Release the **current IP address** from the DHCP server. |
| `ipconfig /renew` | Request a **new IP address** from the DHCP server. |
| `ipconfig /flushdns` | Clear the **DNS cache**. |


## **4. Key Differences Between `ifconfig` and `ipconfig`**  

| Feature | `ifconfig` (Linux) | `ipconfig` (Windows) |
|---------|--------------------|----------------------|
| Used in | Linux/Unix | Windows |
| Default Status | Deprecated (Use `ip` instead) | Still in use |
| Shows active network interfaces | ✅ Yes | ✅ Yes |
| Assigns IP addresses | ✅ Yes | ❌ No |
| Enables/disables interfaces | ✅ Yes | ❌ No |
| Flushes DNS cache | ❌ No | ✅ Yes (`ipconfig /flushdns`) |

