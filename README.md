# Ansible Role: Icinga 2

![Build Status](https://github.com/transitiv/ansible-role-icinga2/workflows/CI/badge.svg)

This role installs Icinga 2 from the [official package repositories](https://packages.icinga.com/) on systems running Debian/Ubuntu and RHEL/CentOS.

## Requirements

Root accesss is required for installing packages, so you must run it in a playbook with global root privileges or define `become: yes` when the role is included:

```yaml
- hosts: icinga2_servers
  roles:
    - role: transitiv.icinga2
      become: yes
```

Note that the EPEL repository must be enabled on CentOS/RHEL.

## Dependencies

This role has no dependencies.

## Variables

```yaml
icinga2_packages:
  - icinga2
icinga2_group_packages:
  - icinga2-ido-mysql
icinga_host_packages: []
```

Defines the package(s) installed by the role. The variables are combined and flattened before being used so can contain nested lists if desired.

```yaml
icinga2_service_state: started
```

Sets the state of the service whenever the role is invoked (refer to the `state` parameter of the service module for valid values).

```yaml
icinga2_service_enabled: true
```

Defines whether Icinga 2 is started on boot.

## License

This role is available under the terms of the MIT license.

## Author

This role was created by [Transitiv Technologes Ltd](https://www.transitiv.co.uk).
