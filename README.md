# Ansible Role: Files 

A wrapper for the Official File Module of Ansible.

With the role you can easily use all options of the Ansible module in variables.

Folders, symlinks, file permissions, owner and group can be easily managed via variables.


## Example Playbook

    - hosts: all
      roles:
        - { role: files }

```
*Inside `group_vars/all.yml`*:
    files:
      '/tmp/testfile':
        state: absent
        owner: root
        group: root
        mode:  644
      '/tmp/directory':
        state: directory
        owner: foo
        group: foo
        mode:  775
      '/tmp/foooo':
        state: link
        src: "/var/log"
```
