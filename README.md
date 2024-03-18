# Ansible

Beginner installation guide about Ansible

# What is Ansible?

Ansible® is an open source, command-line IT automation software application written in Python

# Start Here

install ansible: https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html#installing-ansible-on-ubuntu

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
```
$ ansible-playbook test.yml --ask-become-pass
```
