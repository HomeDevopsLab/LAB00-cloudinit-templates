# Ansible Basics

This chapter covers the basics of ansible. After reviewing the material, you will learn to execute selected commands on remote systems using the `ansible` command.

## About Ansible

Ansible is a great IaC tool designed to automate software installation and configuration tasks across many target systems.

One of the main advantages of Ansible is the low requirements for managed systems. There is no need to install Ansible on them. It is sufficient to have Python installed and a user account created that can be accessed via SSH.

> [!TIP]
> Ansible is able to authenticate with managed node with interactive password prompt and ssh keys.

## Ansible concepts

### Playbooks

Playbooks are YAML format files that contain instructions for executing various operations on target systems. These can include software installation instructions, service configuration, and more.

### Control Node

The system from which playbooks are executed.
<picture>
  <source srcset="/assets/img/ansible-diagram.png" />
  <img src="/assets/img/ansible-diagram.png" />
</picture>

### Managed Node

A system managed by Ansible (server, VM) on which configuration is automatically deployed from the control node.

### Inventory
Inventory can be static or dynamic. Static inventory is a file in `ini` or `yaml` format. It contains information that allows Ansible to locate managed nodes in order to execute commands and configurations on them.

INI example:
```ini
[foo_hosts]
foo  ansible_host=10.0.0.1          another_var=another_value

[foo_hosts:vars]
ansible_connection=ssh
ansible_user=ansible
```

YAML example:
```yaml
foo_hosts:
  hosts:
    foo:
      ansible_host: 10.0.0.1
      another_var: another_value
  vars:
    ansible_connection: ssh
    ansible_user: ansible
```

> [!TIP]
> `ansible_host` and `ansible_user` are connection variables. They are available by default. `ansible_host` can be used to provide IP address of the target, when no DNS name is configured yet.

## Ansible Installation

The only environment where ansible needs to be installed is control node.

### Control node

```bash
sudo apt install ansible
```

### Managed Node

There's no need to install ansible on managed node, only python package is required.

## Configuration File

Ansible's configuration file is `ansible.cfg`. Changes can be made and used in a configuration file which will be searched for in the following order:
* `ANSIBLE_CONFIG` (environment variable if set)
* `ansible.cfg` (in the current directory)
* `~/.ansible.cfg` (in the home directory)
* `/etc/ansible/ansible.cfg`

```ini
[defaults]
host_key_checking = False
enable_plugins = host_list
force_color = True
```

In this file, you can have many configuration options that define how Ansible should behave or what resources it can use. In the example above, we set Ansible not to verify host keys and to produce colored output. We also want to use only the host_list inventory plugin.

## Running Commands Using Ansible

<!-- Ad-hoc tasks.
Use cases -->

<!-- https://docs.ansible.com/ansible/latest/command_guide/intro_adhoc.html#why-use-ad-hoc-commands -->

<!--
NOTATKI:

W 02-ansible playbook
* Ćwiczenia z yaml
*
-->
