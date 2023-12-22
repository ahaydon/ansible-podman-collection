Role Name
=========

An Ansible role to enable a user to run Podman rootless containers.

Requirements
------------

None.

Role Variables
--------------

```yaml
podman_user_name: ansible
podman_user_group: "{{ podman_user_name }}"
```

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: ahaydon.podman.podman_user
      podman_user_name: hass
      become: yes
```

License
-------

MIT

Author Information
------------------

This role was created by [Adam Haydon](https://github.com/ahaydon)
