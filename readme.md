# Ansible Firewall Role

Firewall installation role.

## Role Variables

- `firewall_ports`: The password that should be set for the default postgres user

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
```

## Versioning

In order to have a verioning in place and working, create leightweight tags that point to the appropriate minor release versions.

Creating a new minor release:

```bash
git tag 1.0
git push --tags
```

Replacing an already existing minor release:

```bash
git tag -d 1.0
git push origin :refs/tags/1.0
git tag 1.0
git push --tags
```
