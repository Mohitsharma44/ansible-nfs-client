Role Name
=========

NFS client role for mouting NFS server

Requirements
------------

N/A

Role Variables
--------------

`nfs_shares`: List of dictionaries with following variables:
- `mnt_path`: location to mount the nfs share locally
- `remote_path`: Remote NFS share path
- `nfs_mount_opts`: `comma-separated` nfs mount options

Dependencies
------------

nfs-common
> It is installed by the role

Example Playbook
----------------

``` yaml
- hosts: localhost
  connection: local
  gather_facts: no
  become: yes
  vars:
      nfs_shares:
      - mnt_path: /media/test_export
        remote_path: 10.8.10.67:/var/nfs/general
        nfs_mount_opts: auto,nofail,ro,noatime,nolock,intr,tcp,actimeo=1800

```

License
-------

MIT

Author Information
------------------

Mohit Sharma (Mohitsharma44@gmail.com)
