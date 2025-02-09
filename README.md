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

- Ubuntu 22.04 or 24.04

## How to use this role

Add this role to your Ansible playbook file.

```yaml
- name: configure ubuntu
  role: xronos_ubuntu_common_ansible
```

## Variables

- `ubuntu_apt_upgrade` Upgrade packages? Otherwise install packages only if not present. Defaults to `"once"` to upgrade once per host. Values are `"once", "always", "no"`.
- `ubuntu_disable_unattended_upgrades` Disable unattended upgrades? Defaults to `true`.
- `ubuntu_timezone` Timezone to set. Defaults to `America/Los_Angeles`.
- `ubuntu_ntp_enable` Install and start NTP service. Defaults to `true`.
- `ubuntu_trim_motd` Trim MOTD to minimal messages? Defaults to `false`.

## Versions

- `ubuntu_snapshot` Snapshot to use for ubuntu archives. Follows `YYYYMMDDTHHMMSSZ` format, for example `20230302T030400Z` for 03:04 UTC on 2 March 2023. Defaults to empty (do not configure snapshots).
- `ubuntu_python_version` Version of Python3 package to install. Defaults to empty (latest).
