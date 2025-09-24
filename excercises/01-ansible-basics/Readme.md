# Ansible Basics

This chapter covers the basics of ansible. After reviewing the material, you will learn to execute selected commands on remote systems using the `ansible` command.

## About Ansible

Ansible is a great IaC tool designed to automate software installation and configuration tasks across many target systems.

One of the main advantages of Ansible is the low requirements for managed systems. There is no need to install Ansible on them. It is sufficient to have Python installed and a user account created that can be accessed via SSH.

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
mail.example.com

[webservers]
foo.example.com
bar.example.com

[dbservers]
one.example.com
two.example.com
three.example.com
```

YAML example:
```yaml
ungrouped:
  hosts:
    mail.example.com:
webservers:
  hosts:
    foo.example.com:
    bar.example.com:
dbservers:
  hosts:
    one.example.com:
    two.example.com:
    three.example.com:
```

## Ansible Installation

<!--
* Wymagania control node
* Wymagania managed node
-->

## Configuration Files

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
