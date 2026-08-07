# zhan9san.java

Install an OpenJDK GA build from [jdk.java.net](https://jdk.java.net/archive/)
on Linux, macOS and Windows.

## Requirements

- Ansible 2.4+
- Windows targets: `ansible.windows` and `community.windows` collections

## Role Variables

- `jdk_version` (default `25.0.2`) — one of `17.0.2`, `21.0.2`, `25.0.2`
- `install_jdk_in_user_dir_on_linux` (default `false`) — install under the
  user's home dir instead of `/opt`

Add more versions via `download_urls` in `vars/main.yml`.

## Example Playbook

```yaml
- name: Install JDK
  hosts: all
  roles:
    - role: zhan9san.java
      vars:
        jdk_version: 25.0.2
```

## Testing

```bash
molecule test              # linux
molecule test -s macos
molecule test -s windows
```

## License

MIT
