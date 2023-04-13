# Ansible Role: systemd

Role for configuring a systemd service/timer from a local file.

## Requirements

N/A

## Role Variables

### Defaults

| Variable Name | Required | Description | Default Value | Type |
| - | :-: | - | :-: | :-: |
| systemd_file   | no  | Path with file to the local service/timer file to copy | "" | string |
| systemd_name   | yes | Name of the created systemd service/timer | "" | string |
| systemd_enable | no  | If the service/timer should be enabled or disabled | true | bool |
| systemd_state  | no  | State of the systemd service/timer, can be one of `started`, `stopped`, `restarted`, `absent`. When `absent` the service/timer will be stopped, disabled and removed. | "started" | string |
| systemd_type   | no  | If systemd should create it as a `service` or `timer` | "service" | string |

## Dependencies

N/A

## Example Playbook

```yaml
- hosts: all
  roles:
    - role: tinyblargon.systemd
      vars:
        systemd_file: "path/to/test.service"
        systemd_name: "testing-service"
        systemd_enable: false
        systemd_state: "started"
        systemd_type: "service"
```

## License

MIT
