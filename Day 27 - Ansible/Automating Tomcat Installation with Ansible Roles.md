
#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |


# 🚀 Apache Tomcat Ansible Role (Beginner Friendly)

This Ansible **role** automates the installation and setup of **Apache Tomcat 9.0.104**, using best practices with a clean directory structure. It installs dependencies (Java), downloads Tomcat, sets permissions, configures users, and runs Tomcat as a service.

---

## 🗂️ Tomcat Role Directory Structure

```
tomcat/
├── defaults/
│   └── main.yml            # Default variables for the role
├── files/
│   ├── tomcat-users.xml    # Custom users/roles config for Tomcat
│   └── tomcat.service      # systemd service file to manage Tomcat
├── tasks/
│   └── main.yml            # Main logic - series of tasks to run
├── handlers/
│   └── main.yml            # Defines service restart/reload operations
├── vars/
│   └── main.yml            # Optional: higher priority variables
├── meta/
│   └── main.yml            # Optional: role metadata (author, dependencies)
```

---

## 🔧 `defaults/main.yml`

This file defines the **default variables** used throughout the role. You can override these in your playbooks.

```yaml
---
tomcat_version: "9.0.104"
tomcat_install_path: "/opt"
tomcat_user: "tomcat"
tomcat_group: "tomcat"
tomcat_dir: "{{ tomcat_install_path }}/apache-tomcat-{{ tomcat_version }}"
tomcat_tarball: "{{ tomcat_dir }}.tar.gz"
tomcat_url: "https://archive.apache.org/dist/tomcat/tomcat-9/v{{ tomcat_version }}/bin/apache-tomcat-{{ tomcat_version }}.tar.gz"
```

**Explanation for Students:**

* Variables like `tomcat_version` make the role reusable for other versions.
* `tomcat_dir` and `tomcat_tarball` are **derived variables** using other values.

---

## 📜 `tasks/main.yml`

This is the **heart of the role**. It contains a list of ordered tasks to install and configure Tomcat.

```yaml
---
- name: Verify connectivity to host
  ping:
```

Checks that the playbook can reach the host.

```yaml
- name: Install Java 11 (Amazon Corretto)
  yum:
    name: java-11-amazon-corretto-devel
    state: present
```

Installs Java, which is required for running Tomcat.

```yaml
- name: Add group "{{ tomcat_group }}"
  group:
    name: "{{ tomcat_group }}"
    state: present
```

Creates a Linux group for Tomcat.

```yaml
- name: Add user "{{ tomcat_user }}" and assign to group
  user:
    name: "{{ tomcat_user }}"
    group: "{{ tomcat_group }}"
    create_home: yes
    state: present
```

Creates a Tomcat user and assigns it to the Tomcat group.

```yaml
- name: Check if Tomcat tarball exists
  stat:
    path: "{{ tomcat_tarball }}"
  register: tomcat_tarball_stat
```

Checks if the `.tar.gz` archive has already been downloaded.

```yaml
- name: Download Apache Tomcat
  get_url:
    url: "{{ tomcat_url }}"
    dest: "{{ tomcat_tarball }}"
    mode: '0644'
  when: not tomcat_tarball_stat.stat.exists
```

Downloads Tomcat only if it isn’t already downloaded.

```yaml
- name: Check if Tomcat is already extracted
  stat:
    path: "{{ tomcat_dir }}"
  register: tomcat_extract_stat
```

Checks if Tomcat is already extracted in the destination path.

```yaml
- name: Extract Tomcat archive
  unarchive:
    src: "{{ tomcat_tarball }}"
    dest: "{{ tomcat_install_path }}"
    remote_src: yes
  when: not tomcat_extract_stat.stat.exists
```

Unzips the archive to the `/opt` directory.

```yaml
- name: Set ownership of Tomcat directory
  file:
    path: "{{ tomcat_dir }}"
    owner: "{{ tomcat_user }}"
    group: "{{ tomcat_group }}"
    state: directory
    recurse: yes
```

Ensures that all files/folders under Tomcat are owned by the right user/group.

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

Deploys the user roles configuration (`manager-gui`, etc.).

```yaml
- name: Install tomcat systemd service file
  copy:
    src: tomcat.service
    dest: /etc/systemd/system/tomcat.service
    mode: '0755'
```

Adds a custom systemd service file so Tomcat can be managed using `systemctl`.

```yaml
- name: Start and enable Tomcat service
  systemd:
    name: tomcat
    state: restarted
    enabled: true
  notify: Restart Tomcat
```

Starts Tomcat now and also ensures it starts at boot. If changes are made, it will notify the handler to restart Tomcat.

---

## 🔄 `handlers/main.yml`

Handlers are triggered when notified by a task.

```yaml
---
- name: Restart Tomcat
  systemd:
    name: tomcat
    state: restarted
```

This restarts the Tomcat service if the configuration has changed.

---

## 🧾 Sample `files/tomcat-users.xml`

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

This allows login to the Tomcat web interface using **admin/admin**.

---

## 🧾 Sample `files/tomcat.service`

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

This lets systemd manage Tomcat as a background service.

---

## 🧪 Sample `tomcat.yml` to Call This Role

```yaml
---
- name: Setup Tomcat using role
  hosts: localhost
  become: true
  roles:
    - tomcat
```

Run this with:

```bash
ansible-playbook tomcat.yml
```

---

## 🧠 Key Concepts for Students

| Concept         | Explanation                                                         |
| --------------- | ------------------------------------------------------------------- |
| **Role**        | A modular way to organize playbooks into reusable components.       |
| **Handlers**    | Special tasks triggered by other tasks (like restarting a service). |
| **Variables**   | Values that can be reused and overridden across tasks.              |
| **Idempotency** | Ensures tasks do not repeat actions unnecessarily.                  |
| **systemd**     | A system and service manager used by most modern Linux systems.     |

