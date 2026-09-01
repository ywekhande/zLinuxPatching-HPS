# zLinuxPatching-HPS

An Ansible playbook for patching RHEL 9 servers with specific kernel versions on IBM Z (s390x) architecture.

## Overview

This playbook performs kernel patching on RHEL 9 servers while:
- Skipping systems with GPFS installed
- Managing DNF package locks and exclusions
- Safely rebooting servers with kernel updates
- Verifying kernel installation post-reboot

## Directory Structure

```
playbooks/          # Ansible playbooks
roles/              # Ansible roles
group_vars/         # Group-level variables
host_vars/          # Host-level variables
inventory/          # Inventory files
```

## Usage

```bash
ansible-playbook playbooks/patch_rhel9.yml -i inventory/hosts
```

## Features

- Pre-check for GPFS installation (skips patching if present)
- DNF cache cleanup
- Kernel exclusion management
- Linux firmware updates
- System reboots with timeout handling
- Post-reboot kernel verification

## Requirements

- Ansible 2.9+
- RHEL 9 target systems
- SSH access with sudo privileges

## Author

Created for HPS infrastructure patching
