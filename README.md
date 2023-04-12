# Ansible Role: systemd-service

Role for configuring a systemd service with a local service file.

## Requirements

N/A

## Role Variables

### Defaults

| Variable Name | Required | Description | Default Value | Type |
| - | :-: | - | :-: | :-: |
| systemd_service_file   | no  | Path with file to the local service file to copy | "" | string |
| systemd_service_name   | yes | Name of the created systemd service | "" | string |
| systemd_service_enable | no  | If the service should be enabled or disabled | true | bool |
| systemd_service_state  | no  | State of the systemd service, can be one of `started`, `stopped`, `restarted`, `absent`. When `absent` the service will be stopped, disabled and removed. | "started" | string |

## Dependencies

N/A

## Example Playbook

```yaml
- hosts: all
  roles:
    - role: tinyblargon.systemd_service
      vars:
        systemd_service_file: "path/to/test.service"
        systemd_service_name: "testing-service"
        systemd_service_enable: false
        systemd_service_state: "started"
```

## License

MIT
