Role Name
=========

Role installs autossh and systemd unit for it


Role Variables
--------------
See [defaults](defaults/main.yml)


Example Playbook
----------------

```
- hosts:
    - jump-server
  become: yes
  roles:
     - role: ussrlongbow.autossh
       autossh_profiles:
         - name: test
           user: someuser
           host: "10.10.10.10"
           ssh_key: "/root/.ssh/id_rsa"
           systemd_state: started
           systemd_enabled: yes
           systemd_masked: no
           forwards_local:
             - "127.0.0.1:8080:10.20.30.40:8080"
```

License
-------

MIT
