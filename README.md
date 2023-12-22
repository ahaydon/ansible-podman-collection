# Ansible Collection for rootless Podman

This collection includes Ansible roles for enabling users to run rootless Podman containers and managing containers with systemd service units.

## Roles

Roles included in this collection:

- [Podman systemd service](roles/podman_systemd)
- [Podman user](roles/podman_user)

## Installation

The collection can be installed with `ansible-galaxy`:

```sh
ansible-galaxy collection install git+https://github.com/ahaydon/ansible-podman-collection.git
```

## Usage

The roles can be used to enable a user to run rootless containers and to create a systemd service to run containers as that user.

```yaml
- role: ahaydon.podman.podman_user
  podman_user_name: hass
  become: yes

- role: ahaydon.podman.podman_systemd
  podman_systemd_name: homeassistant
  podman_systemd_image: ghcr.io/home-assistant/home-assistant:stable
  podman_systemd_user: hass
  podman_systemd_network: host
```

## License

This Ansible collection is [MIT licensed](LICENSE)
