# Ansible
Ansible-Practice

# Launch Nginx on worker using master node
Launch three ec2 instance rename them as master and worker
![image](https://github.com/ashishramesh9/Ansible/assets/144009382/fbb35a6c-88ca-424e-b5ca-4831ed019377)

# Login to the master
update the packages using command : "sudo apt update"

# Install ansible
Run command : "sudo apt install ansible"

# Create a directory or use the default path where ansible files are present to update the host file
Default path "/etc/ansible/host"
or create inventory file
command touch inventory

# Update the ip address of worker is inventory
Using command: vim inventory or vim /etc/ansible/host

# Create a Playbook
touch "filename.yml"

# Playbook
---
- name: Install and start Nginx
  host: all
  become: yes ## yes to become root user
  task:
    -name: Install Nginx
     apt:
     name: Nginx
     state: latest

    -name: start Nginx
     service: Nginx
     state: started
     enable: yes
  esc:wq!  #to write and quit your playbook

  # Execute playbook
  Command: ansible-playbook "playbookname.yml"

  # Copy the public ip of worker and search on web browser to see Nginx running
    
