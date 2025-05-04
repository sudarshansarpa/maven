## ✅ **Tomcat Installation Using Ansible Role**

### 🧱 Steps Performed:

1. Create a group `tomcat`
2. Create a user `tomcat` and add it to the group
3. Download Apache Tomcat
4. Extract the tarball
5. Change ownership to the tomcat user
6. Copy `tomcat-users.xml` configuration
7. Copy `tomcat.service` systemd unit
8. Start and enable the Tomcat service

---

## 🧱 Role Directory Structure

```
roles/
└── tomcat/
    ├── defaults/
    │   └── main.yml
    ├── files/
    │   └── tomcat-users.xml
    ├── handlers/
    │   └── main.yml
    ├── tasks/
    │   └── main.yml
    ├── templates/
    │   └── tomcat.service.j2
    └── vars/
        └── main.yml
```

---

### 🔧 `defaults/main.yml`

User-overridable settings:

```yaml
tomcat_version: 9.0.85
tomcat_user: tomcat
tomcat_group: tomcat
tomcat_install_dir: /opt
tomcat_http_port: 8080
```

---

### 📦 `vars/main.yml`

Internal values derived from variables:

```yaml
tomcat_archive: apache-tomcat-{{ tomcat_version }}.tar.gz
tomcat_url: https://archive.apache.org/dist/tomcat/tomcat-9/v{{ tomcat_version }}/bin/{{ tomcat_archive }}
tomcat_home: "{{ tomcat_install_dir }}/apache-tomcat-{{ tomcat_version }}"
```

---

### 📁 `files/tomcat-users.xml`

Add secure users for `admin-gui`/`manager-gui`:

```xml
<tomcat-users>
  <user username="admin" password="StrongP@ssword" roles="manager-gui,admin-gui"/>
</tomcat-users>
```

---

### 🧾 `templates/tomcat.service.j2`

Templated systemd service file:

```ini
[Unit]
Description=Apache Tomcat
After=network.target

[Service]
Type=forking
User={{ tomcat_user }}
Group={{ tomcat_group }}
ExecStart={{ tomcat_home }}/bin/startup.sh
ExecStop={{ tomcat_home }}/bin/shutdown.sh
Restart=on-failure

[Install]
WantedBy=multi-user.target
```

---

### 🚀 `tasks/main.yml`

```yaml
---
- name: Ensure group exists
  group:
    name: "{{ tomcat_group }}"

- name: Ensure user exists
  user:
    name: "{{ tomcat_user }}"
    group: "{{ tomcat_group }}"
    shell: /bin/bash
    create_home: yes

- name: Download Tomcat
  get_url:
    url: "{{ tomcat_url }}"
    dest: "{{ tomcat_install_dir }}/"
    mode: '0644'

- name: Extract Tomcat archive
  unarchive:
    src: "{{ tomcat_install_dir }}/{{ tomcat_archive }}"
    dest: "{{ tomcat_install_dir }}"
    remote_src: yes

- name: Set ownership on Tomcat directory
  file:
    path: "{{ tomcat_home }}"
    state: directory
    recurse: yes
    owner: "{{ tomcat_user }}"
    group: "{{ tomcat_group }}"

- name: Deploy tomcat-users.xml
  copy:
    src: tomcat-users.xml
    dest: "{{ tomcat_home }}/conf/tomcat-users.xml"
    owner: "{{ tomcat_user }}"
    group: "{{ tomcat_group }}"
  notify: Restart Tomcat

- name: Deploy systemd unit file
  template:
    src: tomcat.service.j2
    dest: /etc/systemd/system/tomcat.service
    mode: '0644'
  notify: Reload Systemd

- name: Enable and start Tomcat
  service:
    name: tomcat
    state: started
    enabled: yes
```

---

### 🔁 `handlers/main.yml`

```yaml
---
- name: Reload Systemd
  systemd:
    daemon_reload: yes

- name: Restart Tomcat
  service:
    name: tomcat
    state: restarted
```

---

### ▶️ `tomcat.yml` – Main Playbook

```yaml
---
- name: Advanced Tomcat Deployment
  hosts: tomcat
  become: yes

  roles:
    - tomcat
```

---

## ✅ Key Advantages

| Feature            | Benefit                                      |
| ------------------ | -------------------------------------------- |
| Parameterized Vars | Flexible for different versions/environments |
| Templates          | Dynamic systemd service configuration        |
| Handlers           | Efficient, conditional restarts              |
| Separation         | Clean separation of config, logic, data      |
| Secure Users       | Prevents unauthorized access to manager-gui  |

