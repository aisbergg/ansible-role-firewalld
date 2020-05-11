# Ansible Role: `aisbergg.firewalld`

This Ansible role is used to install and configure firewalld on Debian, Arch Linux and Redhat Linux distributions.

## Requirements

None.

## Role Variables

| Variable |  Default | Comments |
|----------|----------|----------|
| `firewalld_enabled` | `true` | Enable the firewalld service. |
| `firewalld_state` | `started` | Manage the state of the firewalld service</br>Choices: <ul><li>reloaded</li><li>restarted</li><li>started</li><li>stopped</li></ul> |
| `firewalld_rules` | `[]` | List of firewall rules. The parameters can be looked up [here](https://docs.ansible.com/ansible/latest/modules/firewalld_module.html).* |
| `firewalld_config` | `{}` | A dict (key-value pairs) of firewalld base configuration options. |
| `firewalld_config.DefaultZone` | `public` | See [official firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |
| `firewalld_config.CleanupOnExit` | `true` | See [official firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |
| `firewalld_config.Lockdown` | `true` | See [official firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |
| `firewalld_config.IPv6_rpfilter` | `true` | See [official firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |
| `firewalld_config.IndividualCalls` | `false` | See [official firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |
| `firewalld_config.LogDenied` | `off` | See [official firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |
| `firewalld_config.FirewallBackend` | `nftables` | See [official firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |
| `firewalld_config.FlushAllOnReload` | `true` | See [official firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |
| `firewalld_config.RFC3964_IPv4` | `true` | See [official firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |
| `firewalld_config.AllowZoneDrifting` | `false` | See [official firewalld documentation](https://firewalld.org/documentation/configuration/firewalld-conf.html). |

> *If not specified otherwise, the rules will be added permanently and applied immediately after the role finishes. Except from that, the defaults are the same as the defaults of the official [firewalld module](https://docs.ansible.com/ansible/latest/modules/firewalld_module.html).

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  roles:
    - role: aisbergg.firewalld
      vars:
        firewalld_enabled: true
        firewalld_state: started
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
```

## Author Information

Andre Lehmann (aisberg@posteo.de)
