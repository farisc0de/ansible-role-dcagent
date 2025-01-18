# Ansible Role: Desktop Central Agent

This Ansible role installs and configures the ManageEngine Desktop Central Agent on Linux systems.

## Supported Platforms

- RedHat/CentOS 7, 8, 9
- Ubuntu 20.04 (Focal), 22.04 (Jammy)
- Debian 11 (Bullseye), 12 (Bookworm)

## Requirements

- Ansible 2.9 or higher
- Valid Desktop Central Agent download URL

## Role Variables

```yaml
# Required
dc_agent_url: ""  # URL to download the agent package

# Optional
dc_agent_username: "{{ ansible_user }}"  # User to run the agent as
dc_agent_install_dir: "/home/{{ dc_agent_username }}"  # Installation directory
dc_force_install: false  # Force reinstallation if already installed
```

## Example Playbook

```yaml
- hosts: servers
  vars:
    dc_agent_url: "https://your-dc-server:8040/agent/Linux/LinuxAgent.zip"
  roles:
    - dcagent
```

## Role Structure

```
dcagent/
├── defaults/
│   └── main.yml         # Default variables
├── meta/
│   └── main.yml         # Role metadata and dependencies
├── tasks/
│   ├── main.yml         # Main tasks file
│   ├── RedHat.yml       # RedHat family specific tasks
│   ├── Debian.yml       # Debian family specific tasks
│   └── install.yml      # Common installation tasks
└── README.md
```

## License

MIT

## Author Information

Your Name
