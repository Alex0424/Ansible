# Ansible

Beginner installation guide about Ansible https://youtu.be/-Q4T9wLsvOQ?list=PLT98CRl2KxKEUHie1m24-wkyHpEsa4Y70

# What is Ansible?

Ansible® is an open source, command-line IT automation software application written in Python

# Start Here

Distro: "Ubuntu"

install ansible: https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html#installing-ansible-on-ubuntu

create a YAML file `sudo apt install openssh-server`

create a YAML file `vim guide.yml`
```
- name: Install packages and write file
  hosts: localhost
  tasks:
    - name: Install vim and curl
      become: true
      community.general.pacman:
        name:
          - curl
          - vim
        state: latest
    - name: Add file with line in it
      ansible.builtin.lineinfile:
        path: /tmp/ansible.done
        line: 'Woohoo, this is done!'
        create: yes
```
run ansible file
```
$ ansible-playbook guide.yml --ask-become-pass
```
