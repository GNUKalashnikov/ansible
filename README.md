# Ansible

Information gathered from
- [Wolfgang](https://www.youtube.com/watch?v=Z7p9-m4cimg&list=PLkxWXio1KmRoZd88WbrnSnQM5MJY5PjH2)
- [Learn Linux TV (06)](https://youtu.be/VANub3AhZpI)


### Project Structure and inventory

### How to use ansible generally

`ansible-playbook main.yml --ask-become-pass`
this will run the main.yml file

`ansible all --key-file ~/.ssh/sshfile -i inventory -m ping`
Will ping the hosts using the sshfile provided

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

Accessing varriables within playbooks is done like this:

`"{{ variable_name }}"`

Like this:
```
ansible
|
├── group_vars
│       |── all
│       |   └── vars.yml
|       |── group1
|       └── group2
└── host_vars
        |── all
        |── group1
        └── group2
```

**Secret Values**
Keys, passwords, api-keys can be stored and accessed a number of ways.
One way is creating some hardcoded values within a directory; or using ansible-vault

1.  `ansible-vault create secret.yml` 
This will prompt for a password and once createad, looking into will show a encrypted file.
To access the files content once more use:
2. `ansible-vault edit secret.yml`


### Injecting vallues from ansible secrets to a file for docker to pickup
We want to create a way where we specify secrets and anonymously send them to our docker-compose file location into a made `.env`, where we replace the values with the attributes assigned from our ansible-vault.