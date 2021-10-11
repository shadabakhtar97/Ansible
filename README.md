# Shadab-Ansible

# Playbook-1: Copy Tasks
---
 - hosts: remote@172.31.38.247
   vars:
    welcome_msg: 'In 20 minutes i want to reboot servers'
   tasks:
   - name: copy_task
     copy:
      dest: /home/remote/deepak/file1.py
      content: "{{welcome_msg}}"

Hands-on: Success

=====================================================================================================================================
# Playbook-2: Creating new users
---
- name: New User is Created
  hosts: remote@13.233.150.29
  become: true
  tasks:
    - name: User Gets Created
      user:
        name: test
        state: present

Hands-on: Success
=====================================================================================================================================
# Playbook-3: Installation of Apache-Tomcat
---
- name: Installation of Apache-Tomcat
  hosts: remote@13.233.150.29
  become: true
  tasks:
    - name: Install httpd package
      yum: name=httpd state=latest
    - name: Start httpd Service
      service: name=httpd state=restarted
Hands-on: Success
