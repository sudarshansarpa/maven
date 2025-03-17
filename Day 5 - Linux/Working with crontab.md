#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

# **Working with `crontab` Command in Linux**  

The **`crontab`** command is used to schedule and automate tasks (cron jobs) in Linux. It allows users to execute scripts or commands at specified intervals.  

## **1. Understanding `crontab` Syntax**  

A cron job consists of **five time fields** followed by the **command** to execute:  

```plaintext
MIN HOUR DOM MON DOW CMD
```

| Field  | Description          | Allowed Values |
|--------|----------------------|---------------|
| **MIN**  | Minute field         | `0-59`        |
| **HOUR** | Hour field           | `0-23`        |
| **DOM**  | Day of the Month     | `1-31`        |
| **MON**  | Month field          | `1-12` (or `JAN-DEC`) |
| **DOW**  | Day of the Week      | `0-6` (`0=Sunday`, `1=Monday`, etc.) |
| **CMD**  | Command to execute   | Any valid shell command |

✅ **Example:**  
```sh
15 * * * * /opt/script.sh
```
🔹 Runs `/opt/script.sh` at **minute 15** of **every hour**.  

## **2. Common `crontab` Scheduling Examples**  

| Schedule | Cron Expression | Description |
|----------|----------------|-------------|
| Every minute | `* * * * *` | Runs every minute |
| Every 5 minutes | `*/5 * * * *` | Runs every 5 minutes |
| Every hour | `0 * * * *` | Runs at the beginning of every hour |
| Every day at midnight | `0 0 * * *` | Runs daily at **00:00** |
| Every Sunday at 3 AM | `0 3 * * 0` | Runs every Sunday at 3:00 AM |
| On 1st of every month | `0 0 1 * *` | Runs on **1st of every month** at midnight |
| Every Monday and Wednesday at 6 PM | `0 18 * * 1,3` | Runs on Mondays & Wednesdays at **18:00** |
| Every 6 hours | `0 */6 * * *` | Runs every **6 hours** |
| At 9:30 AM on March 15 | `30 9 15 3 *` | Runs on **March 15 at 9:30 AM** |

## **3. Managing Crontab Entries**  

### **Check Existing Cron Jobs**  
```sh
crontab -l
```
✅ Lists current user's cron jobs.  

### **Edit Crontab Entries**  
```sh
crontab -e
```
✅ Opens the crontab file in an editor.  

### **Remove All Cron Jobs**  
```sh
crontab -r
```
⚠️ **Warning:** This will delete all scheduled jobs!  

### **Remove a Specific User's Crontab (as root)**  
```sh
crontab -u username -r
```
✅ Removes the crontab for the specified user.  

## **4. Special Strings in `crontab`**  

Instead of numbers, **special strings** can be used for common schedules:  

| Special String | Equivalent Cron Expression | Description |
|---------------|--------------------------|-------------|
| `@reboot` | Runs once after system reboot | Run script on startup |
| `@yearly` | `0 0 1 1 *` | Run once a year |
| `@monthly` | `0 0 1 * *` | Run once a month |
| `@weekly` | `0 0 * * 0` | Run once a week |
| `@daily` | `0 0 * * *` | Run once a day |
| `@hourly` | `0 * * * *` | Run once an hour |

✅ **Example using `@reboot`**  
```sh
@reboot /opt/startup.sh
```
Runs `/opt/startup.sh` **every time the system reboots**.  

## **5. Logging & Debugging Crontab Jobs**  

### **Check Cron Logs**
```sh
cat /var/log/cron
```
✅ View logs for cron job execution.  

### **Redirect Cron Output to a Log File**  
```sh
* * * * * /opt/script.sh >> /var/log/myscript.log 2>&1
```
✅ Logs both **output** and **errors** to `/var/log/myscript.log`.  
