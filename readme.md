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

## Versioning

In order to have a verioning in place and working, create leightweight tags that point to the appropriate minor release versions.

Creating a new minor release:

```bash
git tag v1
git push --tags
```

Replacing an already existing minor release:

```bash
git tag -d v1
git push origin :refs/tags/v1
git tag v1
git push --tags
```
