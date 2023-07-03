# Minimal Ubuntu Install
This ansible playbook aims to harden Linux while installing some useful packages (on Ubuntu) and optimizing
performance.

This README contains important information; please it in its entirety before running the playbook.


## Requirements
* `ansible`


## Task Overview
This playbook consists of two roles, `setup` and `security`.

`setup`:
1. Installs requisite packages (found in roles/setup/defaults/main.yml).
2. Makes minor tweaks to the system fstab and IO schedulers to improve performance.
3. Makes sure the system configuration is sane, and hardens where it is not.


## Usage
Run:
```sh
ansible-playbook                                \
    -i localhost                                \
    -c local                                    \
    -K main.yml                                 \
    -u $(whoami)
```

You will be prompted for your local user password (Ansible calls this the "BECOME" password as it's needed to
'become' root), after which the playbook will run.
