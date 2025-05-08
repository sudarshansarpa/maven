
#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

# 🚀 Apache Tomcat Installation and Setup using Ansible Playbook

This Ansible playbook automates the installation and configuration of **Apache Tomcat 9.0.104** on a Linux server (such as Amazon Linux 2 or CentOS). It installs Java, downloads and extracts Tomcat, sets the right permissions, and configures it as a systemd service.

---

## 📁 Folder Structure

```bash
.
├── tomcat-install.yml          # The main Ansible playbook
├── tomcat-users.xml           # Tomcat user configuration file
└── tomcat.service             # Systemd service unit file for Tomcat
```

---

## 📌 Prerequisites

* Ansible installed on your local machine.
* A Linux host (e.g., Amazon EC2) where the playbook will be run.
* Internet access to download Java and Tomcat.

---

## ▶️ How to Run

```bash
ansible-playbook tomcat-install.yml
```

---

## 📜 Playbook Explanation

```yaml
- name: Apache Tomcat Installation and Setup
  hosts: localhost
  become: true
```

* **name**: Just a descriptive name for the play.
* **hosts: localhost**: This playbook runs on the local machine (can be modified to target remote servers).
* **become: true**: Runs the tasks with sudo privileges (admin access).

---

### 🔧 Variables

```yaml
vars:
  tomcat_version: "9.0.104"
  tomcat_install_path: "/opt"
  tomcat_user: "tomcat"
  tomcat_group: "tomcat"
  tomcat_dir: "{{ tomcat_install_path }}/apache-tomcat-{{ tomcat_version }}"
  tomcat_tarball: "{{ tomcat_dir }}.tar.gz"
  tomcat_url: "https://archive.apache.org/dist/tomcat/tomcat-9/v{{ tomcat_version }}/bin/apache-tomcat-{{ tomcat_version }}.tar.gz"
```

These are configuration settings:

* Tomcat version and install path.
* User/group for managing the service.
* URL to download the specific Tomcat version.

---

### ✅ Tasks Explained

#### 1. Check Host Connectivity

```yaml
- name: Verify connectivity to host
  ping:
```

Sends a ping to confirm the host is reachable.

---

#### 2. Install Java (Dependency for Tomcat)

```yaml
- name: Install Java 11 (Amazon Corretto)
  yum:
    name: java-11-amazon-corretto-devel
    state: present
```

Tomcat runs on Java. This installs Amazon Corretto 11 using the `yum` package manager.

---

#### 3. Create Group and User for Tomcat

```yaml
- name: Add group "{{ tomcat_group }}"
  group:
    name: "{{ tomcat_group }}"
    state: present
```

Creates a Linux group called `tomcat`.

```yaml
- name: Add user "{{ tomcat_user }}" and assign to group
  user:
    name: "{{ tomcat_user }}"
    group: "{{ tomcat_group }}"
    create_home: yes
    state: present
```

Creates a new user named `tomcat` and adds it to the `tomcat` group.

---

#### 4. Download Tomcat

```yaml
- name: Check if Tomcat tarball exists
  stat:
    path: "{{ tomcat_tarball }}"
  register: tomcat_tarball_stat
```

Checks if the Tomcat archive file is already downloaded.

#### `stat`

* This is an Ansible **module**.
* It is used to **retrieve information** about a file or directory on the remote machine (like whether it exists, its size, permissions, etc.).
* In this example, it's checking the **file metadata** of the Tomcat tarball at the path `{{ tomcat_tarball }}`.

#### `register: tomcat_tarball_stat`

* This stores the **result** of the `stat` module in a **variable** named `tomcat_tarball_stat`.
* This variable will now contain a dictionary of facts like:

  * `tomcat_tarball_stat.stat.exists` (boolean indicating if the file exists),
  * `tomcat_tarball_stat.stat.size` (file size in bytes),
  * `tomcat_tarball_stat.stat.mode` (permissions),
  * and more.
  * 
```yaml
- name: Download Apache Tomcat
  get_url:
    url: "{{ tomcat_url }}"
    dest: "{{ tomcat_tarball }}"
    mode: '0644'
  when: not tomcat_tarball_stat.stat.exists
```

Downloads Tomcat only if it doesn't already exist.

---

#### 5. Extract Tomcat

```yaml
- name: Check if Tomcat is already extracted
  stat:
    path: "{{ tomcat_dir }}"
  register: tomcat_extract_stat
```

Checks if the Tomcat archive has already been extracted.

```yaml
- name: Extract Tomcat archive
  unarchive:
    src: "{{ tomcat_tarball }}"
    dest: "{{ tomcat_install_path }}"
    remote_src: yes
  when: not tomcat_extract_stat.stat.exists
```

Extracts the downloaded `.tar.gz` archive.

---

#### 6. Set Permissions

```yaml
- name: Set ownership of Tomcat directory
  file:
    path: "{{ tomcat_dir }}"
    owner: "{{ tomcat_user }}"
    group: "{{ tomcat_group }}"
    state: directory
    recurse: yes
```

Changes ownership of the entire Tomcat directory to the `tomcat` user and group.

---

#### 7. Configure Tomcat Users

```yaml
- name: Deploy tomcat-users.xml configuration
  copy:
    src: tomcat-users.xml
    dest: "{{ tomcat_dir }}/conf/"
    owner: "{{ tomcat_user }}"
    group: "{{ tomcat_group }}"
    mode: '0644'
    backup: yes
```

Copies the custom `tomcat-users.xml` file which defines roles and credentials for accessing the Tomcat Manager UI.

---

#### 8. Create Tomcat Service

```yaml
- name: Install tomcat systemd service file
  copy:
    src: tomcat.service
    dest: /etc/systemd/system/tomcat.service
    mode: '0755'
```

Adds a systemd service unit so you can start/stop Tomcat using `systemctl`.

---

#### 9. Start and Enable the Service

```yaml
- name: Start and enable Tomcat service
  systemd:
    name: tomcat
    state: restarted
    enabled: true
```

Starts Tomcat immediately and ensures it starts automatically on boot.

---

## 🎓 Summary for Students

| Concept              | Description                                                                               |
| -------------------- | ----------------------------------------------------------------------------------------- |
| **Ansible Playbook** | A YAML script that defines tasks to automate system administration.                       |
| **Variables**        | Used to define reusable values like version, paths, and usernames.                        |
| **Modules Used**     | `ping`, `yum`, `group`, `user`, `stat`, `get_url`, `unarchive`, `file`, `copy`, `systemd` |
| **Idempotency**      | Ensures the playbook can be run multiple times without breaking or duplicating things.    |
| **Systemd**          | Linux service manager used to run Tomcat as a background service.                         |

---

## 🧪 Example: tomcat-users.xml

```xml
<tomcat-users>
<role rolename="manager-gui" />
<role rolename="manager-status" />
<role rolename="manager-script" />
<role rolename="manager-jmx" />
<role rolename="admin-gui" />
<role rolename="admin-script" />

<user username="tomcat" password="tomcat" roles="manager-gui,admin-script, admin-gui,manager-status,manager-script,manager-jmx"/>

</tomcat-users>
```

---

## 🧪 Example: tomcat.service

```ini
[Unit]
Description=Apache Tomcat
After=network.target

[Service]
Type=forking
User=tomcat
Group=tomcat
ExecStart=/opt/apache-tomcat-9.0.104/bin/startup.sh
ExecStop=/opt/apache-tomcat-9.0.104/bin/shutdown.sh
Restart=always

[Install]
WantedBy=multi-user.target
```
