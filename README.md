Ansible role for chrony setup.

This role is developed with Ansible 2.9.6 and tesed on Ubuntu 20.04 LTS.

## Role Variables

| Variable | Required | Default | Comments |
| -------- | -------- | ------- | -------- |
| `chrony_pkg_state` | No | `present` | Set pkg `enabled`, `disabled`, `latest` |
| `chrony_service_state` | No | `started` | Set service state, started, enabled or disabled |
| `chrony_service_enabled` | No | `yes` | A list of NTP servers to use.                   |
| `chrony_config_server` | No | `["0.cz.pool.ntp.org","1.cz.pool.ntp.org","2.cz.pool.ntp.org", "3.cz.pool.ntp.org"]` | A list of NTP servers to use. |
| `chrony_config_logdir` | No | `/var/log/chrony` | A list of NTP servers to use. |
| `chrony_config_extra_options` | No | `{}` | A dict of extra config options. |

## Requirements

None

## Install chrony with default settings
```yaml
  roles:
     - ansible-chrony
```

## Install chrony with some custom variables
```yaml
  roles:
     - ansible-chrony
  vars:
     - chrony_config_server:
        - 0.pool.ntp.org
        - 1.pool.ntp.org
```
