# Ansible

Information gathered from
- [Wolfgang](https://www.youtube.com/watch?v=Z7p9-m4cimg&list=PLkxWXio1KmRoZd88WbrnSnQM5MJY5PjH2)
- [Learn Linux TV (06)](https://youtu.be/VANub3AhZpI)


### Project Structure and inventory

#### A Hosts File
A file that containers the location of all the hosts or nodes you will interacting with

## SSH
*How to copy a ssh file to the host*
`ssh-copy-id -i ~/location username@host`

#### Ansible.cfg

The File should attribute inventory to the hosts and enable pipelining
### Variables
- Places to use variables
    - group_vars
    - host_vars

Like this !(image)[/home/ivan/Documents/projects/ansible/vars.png]