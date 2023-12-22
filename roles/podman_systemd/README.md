Ansible Role: Podman systemd service
=========

An Ansible role that creates a systemd service for managing a Podman container.

Requirements
------------

The Podman package must be installed as the CLI is used in the exec command for the service.

Role Variables
--------------

```yaml
podman_systemd_name: homeassistant
podman_systemd_image: ghcr.io/home-assistant/home-assistant:stable
podman_systemd_user: hass
podman_systemd_network: host
podman_systemd_unit_path: /usr/local/lib/systemd/system
podman_systemd_file: "container-{{ podman_systemd_name }}.service"
podman_systemd_comment: "{{ podman_systemd_file }}"
podman_systemd_description: Podman {{ podman_systemd_file }}
podman_systemd_readonly: false
podman_systemd_ports: []
podman_systemd_volumes: []
```

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: ahaydon.podman.podman_systemd
      podman_systemd_name: homeassistant
      podman_systemd_image: ghcr.io/home-assistant/home-assistant:stable
      podman_systemd_user: hass
      podman_systemd_network: host
```

License
-------

MIT

Author Information
------------------

This role was created by [Adam Haydon](https://github.com/ahaydon)
