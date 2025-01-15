# Node Exporter Ansible Role

This repository provides an Ansible role for deploying and configuring **Node Exporter**, a monitoring agent for Prometheus. Node Exporter exposes machine-level metrics like CPU usage, memory usage, disk I/O, and network statistics, which Prometheus can scrape for monitoring purposes.

## Table of Contents

- [Requirements](#requirements)
- [Role Variables](#role-variables)
- [Dependencies](#dependencies)
- [Installation](#installation)
- [Usage](#usage)
- [Example Playbook](#example-playbook)
- [Contributing](#contributing)
- [License](#license)

## Requirements

- Ansible 2.10 or higher
- Linux-based system (Ubuntu 20.04 recommended)

## Role Variables

Here are the configurable variables used by this role:

```yaml
node_exporter_version: "1.3.1"       # Version of Node Exporter to install
node_exporter_user: node_exporter    # User to run Node Exporter
node_exporter_port: 9100             # Port on which Node Exporter will listen
node_exporter_install_dir: /usr/local/bin  # Directory where the Node Exporter binary will be installed
node_exporter_service_name: node_exporter  # Name of the systemd service
node_exporter_release_url: https://github.com/prometheus/node_exporter/releases/latest  # URL for the latest release of Node Exporter
node_exporter_enable_tls: false      # Enable TLS for Node Exporter (default: false)
node_exporter_enable_basic_auth: false # Enable basic authentication for Node Exporter (default: false)
node_exporter_cert_path: /etc/ssl/certs/node_exporter  # Path to the TLS certificate
node_exporter_key_path: /etc/ssl/private/node_exporter  # Path to the TLS key
node_exporter_basic_auth_user: admin  # User for basic authentication
node_exporter_basic_auth_password: secret  # Password for basic authentication
```

## Dependencies

This role has no external dependencies. It can be used directly in your playbook.

## Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/your-username/ansible-node-exporter.git
   cd ansible-node-exporter
   ```

2. Install the role in your Ansible playbook:

   ```bash
   ansible-galaxy install ./roles/node_exporter
   ```

## Usage

To use the role in your Ansible playbook, include it as follows:

```yaml
- hosts: all
  become: yes
  roles:
    - node_exporter
```

You can customize the role's behavior by setting the appropriate variables in your playbook or group_vars. For example, to enable TLS and basic authentication:

```yaml
node_exporter_enable_tls: true
node_exporter_enable_basic_auth: true
node_exporter_basic_auth_user: "myuser"
node_exporter_basic_auth_password: "mypassword"
```


## Contributing

Contributions are welcome! If you'd like to contribute, please fork the repository, make your changes, and create a pull request.


---

Let me know if you need further adjustments!
