# Ansible by Shadab Akhtar 
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Ansible Ad-hoc Commands
What is EPEL ?
---------------
EPEL (Extra Packages for Enterprise Linux) is open source and free community based repository project from Fedora team which provides 100% high quality add-on software packages for Linux distribution including RHEL (Red Hat Enterprise Linux), CentOS, and Scientific Linux
Why we use EPEL repository?
----------------------------
Provides lots of open source packages to install via Yum.
Epel repo is 100% open source and free to use.
It does not provide any core duplicate packages and no compatibility issues.
All epel packages are maintained by Fedora repo.
How To Enable EPEL Repository in RHEL/CentOS 7/6/5 64 Bit ?
AWS AMI-RHEL-7.6_HVM_BETA-20180814-x86_64-0-Hourly2-GP2 - ami-006b2db4ca7e39d7d

# wget http://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm 

# rpm -ivh epel-release-latest-7.noarch.rpm

# yum install ansible

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
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
===============================================================================================================================================================================================================
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

===============================================================================================================================================================================================================
# Playbook-5: Installation of Docker
---
- name: Installation of Docker
  hosts: remote@13.233.150.29
  become: true
  tasks:
    - name: Install docker package
      yum: name=httpd state=latest
    - name: Start httpd Service
      service: name=httpd state=restarted
