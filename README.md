avahi
==========
- [Introduction](#introduction)
- [Requirements](#requirements)
- [Variables](#variables)
- [Usage](#usage)

# Introduction
Manage Avahi deamon on RHEL based systems

# Requirements

- Ansible 1.9

# Variables

| Name | Description | Default |
|:-----|:------------|:--------|
| avahi_package_name | Package name | avahi |
| avahi_package_state | Package state | present |
| avahi_service_names | List of service | depends on __ansible_os_family__ and __ansible_distribution_major_version__ |
| avahi_service_state | Service(s) state | running |
| avahi_service_enabled | Service enabled | true |

# Usage
Example to ensure Avahi daemon is stopped and not started at boot time
```yaml
---
- hosts: server
  become: true
  become_method: sudo
  become_user: true
  vars:
    avahi_service_state: stopped
    avahi_service_enabled: false
  roles:
  - role: avahi
```
