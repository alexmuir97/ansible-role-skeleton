# Ansible Role: Skeleton
A skeleton for developing Ansible roles.

## Description
This repository consists of a skeleton and guidance for templating Ansible roles.

## Installation
Install from [Github](https://github.com/alexmuir97/ansible-role-skeleton)
```
$ export ROLE_SKELETON_PATH=/path/to/skeleton
$ export ROLE_NAME=role_name
$ export ROLE_PATH=/path/to/roles

$ git clone git@github.com:alexmuir97/ansible-role-skeleton.git $ROLE_SKELETON_PATH
```
Optionally, the default role skeleton and ignoring of files can be configured with ansible.cfg.

```
[galaxy]
role_skeleton = /path/to/skeleton/role
role_skeleton_ignore = ^.git$,^.*/.git_keep$
```
More information about the configuration file can be found in the [Ansible Docs](https://docs.ansible.com/ansible/latest/reference_appendices/config.html#the-configuration-file)

## Usage
The custom role skeleton directory can be supplied as follows:

```
$ ansible-galaxy role init $ROLE_NAME --init-path=$ROLE_PATH --role-skeleton=$ROLE_SKELETON_PATH/role
```

Note: omit *--role-skeleton=* if *role_skeleton* has been configured in ansible.cfg

More information about the *ansible-galaxy role* command can be found in the [Ansible Docs](https://docs.ansible.com/ansible/latest/cli/ansible-galaxy.html#role)

When a skeleton is provided, init will:

- copy all files and directories from the skeleton to the new role
- any .j2 files found outside of a templates folder will be rendered as templates. The only useful variable at the moment is role_name
- The .git folder and any .git_keep files will not be copied

Some changes are needed to complete and document the new role.

```
# Review and Modify all "TODO" steps
$ grep -r "TODO" $ROLE_PATH/$ROLE_NAME
```

## License
MIT

## Author Information
This role was created by [Alex Muir](https://www.linkedin.com/in/alexmuir97/).
