# Ansible Firewall Role

Firewall installation role.

## Role Variables

- `firewall_ssh_port`: The SSH port that should allowed
- `firewall_rules`: A list of additional rules that can be configured

## Example Playbook

```yaml
- hosts: all
  tasks:
    - ansible.builtin.include_role:
        name: ansible-firewall
      vars:
        firewall_rules:
          - port: 80
            protocol: tcp
            rule: allow
          - port: 443
            protocol: tcp
            rule: allow
          - port: 1234
            protocol: udp
            from: 10.1.0.0/24
            rule: allow
```

## Build & Publish

To build and publish the role, visit the GitHub Actions page of the repository and trigger the workflow "Release Package" manually.
