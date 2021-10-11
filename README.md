# Ansible Role: `aisbergg.firewalld`

This Ansible role is used to install and configure Firewalld on Debian, Arch Linux and RedHat Linux distributions.

## Requirements

None.

## Role Variables

| Variable |  Default | Comments |
|----------|----------|----------|
| `firewalld_debian_repo` | `{{ ansible_distribution_release }}-backports` | The repository to install Firewalld from. Applies only to Debian systems. |
| `firewalld_redhat_enablerepo` |  | Repository to enable while installing Firewalld. Applies only to RedHat systems. |
| `firewalld_service_enabled` | `true` | Enable the Firewalld service. |
| `firewalld_service_state` | `started` | Manage the state of the Firewalld service</br>Choices: <ul><li>reloaded</li><li>restarted</li><li>started</li><li>stopped</li></ul> |
| `firewalld_service_restart_on_change` | `true` | Restart Firewalld service on configuration changes. |
| `firewalld_rules` | `[]` | List of firewall rules. The parameters can be looked up [here](https://docs.ansible.com/ansible/latest/modules/firewalld_module.html).* |
| `firewalld_config` | `{}` | A dict (key-value pairs) of Firewalld base configuration options. |
| `firewalld_config.DefaultZone` | `public` | See the [official Firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |
| `firewalld_config.CleanupOnExit` | `true` | See the [official Firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |
| `firewalld_config.Lockdown` | `true` | See the [official Firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |
| `firewalld_config.IPv6_rpfilter` | `true` | See the [official Firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |
| `firewalld_config.IndividualCalls` | `false` | See the [official Firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |
| `firewalld_config.LogDenied` | `off` | See the [official Firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |
| `firewalld_config.FirewallBackend` | `nftables` | See the [official Firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |
| `firewalld_config.FlushAllOnReload` | `true` | See the [official Firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |
| `firewalld_config.RFC3964_IPv4` | `true` | See the [official Firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |
| `firewalld_config.AllowZoneDrifting` | `false` | See the [official Firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |

> *If not specified otherwise, the rules will be added permanently and applied immediately after the role finishes. Except from that, the defaults are the same as the defaults of the official [firewalld module](https://docs.ansible.com/ansible/latest/modules/firewalld_module.html).

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  vars:
    firewalld_service_enabled: true
    firewalld_service_state: started
    firewalld_config:
      FirewallBackend: nftables
    firewalld_rules:
      # permanent rules
      - service: ssh
        zone: public
      - service: https
        zone: public
      - service: http
        zone: public

      # temporary rule
      - port: 222/tcp
        zone: trusted
        permanent: false
        state: enabled

      # disable rule
      - service: ftp
        zone: public
        state: disabled
  roles:
    - aisbergg.firewalld
```

## License

MIT

## Author Information

Andre Lehmann (aisberg@posteo.de)
