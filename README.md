# ManageEngine Desktop Central Agent Role

This Ansible role installs and configures the **ManageEngine Desktop Central Agent** on Linux systems.

## Features

- Installs required dependencies.
- Downloads and extracts the agent from a user-provided URL.
- Configures the agent using a template.
- Validates the installation.

## Requirements

- Supported on any Linux distribution compatible with ManageEngine Desktop Central Agent.
- Ansible 2.9+.
- Python on the target system.

## Role Variables

| Variable Name                    | Description                                  | Default Value                                             |
| -------------------------------- | -------------------------------------------- | --------------------------------------------------------- |
| `manageengine_agent_url`         | URL to download the agent. **Required.**     | None                                                      |
| `manageengine_agent_version`     | Agent version for configuration.             | `"10.1.2228.19.L"`                                        |
| `manageengine_agent_install_dir` | Directory to install the agent.              | `"/usr/local/desktopcentralagent"`                        |
| `manageengine_agent_work_dir`    | Working directory for installation.          | `"/home/{{ ansible_user }}/manageengine_agent"`           |
| `manageengine_agent_zip_path`    | Path to store the downloaded agent ZIP file. | `"{{ manageengine_agent_work_dir }}/dccentral_linux.zip"` |
| `manageengine_agent_executable`  | Path to the agent executable.                | `"{{ manageengine_agent_work_dir }}/UEMS_LinuxAgent.bin"` |
| `manageengine_required_packages` | List of packages required for installation.  | `["unzip"]`                                               |

## Usage

Define the `manageengine_agent_url` in your playbook and include this role:

### Example Playbook

```yaml
---
- name: Install ManageEngine Desktop Central Agent
  hosts: all
  vars:
    manageengine_agent_url: ""
    manageengine_agent_version: ""
  roles:
    - role: farisc0de.dcagent
```

## Tags

Use tags for selective task execution:

- `manageengine_agent_dependencies`: Install dependencies.
- `manageengine_agent_download`: Download the agent.
- `manageengine_agent_config`: Configure the agent.
- `manageengine_agent_validate`: Validate the installation.

---

## License

MIT

## Author Information

(c) 2025 Faris Alotaibi
