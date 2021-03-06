# Ansible Role: Files 

A wrapper for the Official File Module of Ansible.

With the role you can easily use all options of the Ansible File module in variables.

Folders, symlinks, file permissions, owner and group can be easily managed via variables.

All available options can be found here: https://docs.ansible.com/ansible/latest/collections/ansible/builtin/file_module.html

## Example Playbook

```
- hosts: all
  tasks:
  - name: files
    import_role:
      name: files
    tags:
      - files
```

*Inside `group_vars/all.yml`*:
```
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
