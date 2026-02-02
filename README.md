uds_cli
=======

Installs the Defense Unicorns **UDS CLI** (`uds`).

Currently implemented:
- macOS (Darwin): installs via Homebrew (using the published Galaxy role `moltimersmith.brew`)
- Linux: placeholder only (fails with a clear message)

Requirements
------------

- macOS targets require Homebrew installed on the target host.
- Controller needs the `community.general` collection (containerized-ansible includes it).

Role Variables
--------------

```yaml
# macOS/Homebrew behavior
uds_cli_brew_update: false
uds_cli_brew_taps:
  - defenseunicorns/tap
uds_cli_brew_formulae:
  - uds
```

Dependencies
------------

This role depends on the Galaxy role:
- `moltimersmith.brew`

Pin it in your playbook repo’s `roles/requirements.yml` (recommended). Latest release from last night:
- `moltimersmith.brew`, version `v0.0.3`

Example Playbook
----------------

```yaml
- hosts: macos
  roles:
    - role: moltimersmith.uds_cli
      vars:
        uds_cli_brew_update: false
```

If you vendor roles via `roles/requirements.yml` (recommended):

```yaml
# roles/requirements.yml
- name: moltimersmith.brew
  version: v0.0.3

- name: moltimersmith.uds_cli
  src: git+ssh://git@github.com/moltimersmith/ansible-role-uds-cli.git
  version: main
```
