# Ansible role for common Ubuntu maintenance and configuration

This role is a standard configuration for Ubuntu systems used at Xronos.

- apt updates and package management
- pip updates
- timezone configuration
- prerequisites for common Ansible modules

## Requirements

Provisioning host:

- ansible 2.15 or later

Host that will be configured:

- Ubuntu 22.04 or later

## How to use this role

Add this role to your Ansible playbook file.

```yaml
- name: configure ubuntu
  role: xronos_ubuntu_common_ansible
```

## Variables

- `ubuntu_apt_upgrade` Upgrade packages? Otherwise install packages only if not present. Defaults to `"once"` to upgrade once per host, after which only `present` is checked.
- `ubuntu_disable_unattended_upgrades` Disable unattended upgrades? Defaults to `true`.
- `ubuntu_timezone` Timezone to set. Defaults to `America/Los_Angeles`
- `ubuntu_ntp_enable` Install and start NTP service. Defaults to `true`
- `ubuntu_trim_motd` Trim MOTD to minimal messages? Defaults to `false`
