# Ansible Role: EPEL Repository

Installs the EPEL repository (Extra Packages for Enterprise Linux) for RHEL/CentOS.

## Requirements

This role only is needed/runs on RHEL and its derivatives.

## Role Variables

Available variables are listed below, optional parameters for overriding yum_repository defaults from (see tasks/main.yml for provided defaults):
https://docs.ansible.com/ansible/yum_repository_module.html#options

    repo_epel
    repo_epel_debuginfo
    repo_epel_source
    repo_epel_testing
    repo_epel_testing_debuginfo
    repo_epel_testing_source

Every aspect of the yum repository definition can be changed with the above params variables. For example, you can remove the mirrorlist by setting it to null and use baseurl to set a local mirror repository of your choice.

## Dependencies

None.

## Example Playbook : defaults

    - hosts: servers
      roles:
        - erenfro.repo-epel

## Example Playbook : variables

```
- hosts: all
  vars:
    - repo_epel_debuginfo: { enabled: yes }
    - repo_epel_testing: { enabled: yes }
  roles:
    - erenfro.repo-epel
```

Will set overide the default (dissabled) and enable the `epel-debuginfo` and the `epel-testing` repo 

## License

MIT / BSD

## Author Information

This role was created in 2016 by [Eric Renfro](https://linux-help.org/).

