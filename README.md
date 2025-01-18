# Ansible Role: ManageEngine Desktop Central Agent

This Ansible role installs the ManageEngine Desktop Central Agent on Linux systems.

## Requirements

- Ansible 2.9 or higher
- A supported Linux distribution
- Internet connectivity to download the agent

## Role Variables

### Required Variables

```yaml
# Agent download URL (required)
dc_agent_url: "https://your-server/agent-download-url"
```

### Optional Variables

```yaml
# Agent username (defaults to ansible_user)
dc_agent_username: "username"

# Installation directory
dc_directory: "/usr/local/manageengine/uems_agent"

# Force installation
dc_force_install: true
```

## Example Playbook

```yaml
- hosts: servers
  roles:
    - role: farisc0de.dcagent
      vars:
        dc_agent_url: "https://your-server/agent-download-url"
        dc_agent_username: "username"  # Optional
```

## License

MIT
