# Webarchitects JC Ansible role

[![pipeline status](https://git.coop/webarch/jc/badges/main/pipeline.svg)](https://git.coop/webarch/jc/-/commits/main)

Ansible role to install [JC (JSON Convert)](https://github.com/kellyjonbrazil/jc) on Debian and Ubuntu using [apt](https://github.com/kellyjonbrazil/jc/releases), [pipx](https://pypi.org/project/jc/) or [git](https://github.com/kellyjonbrazil/jc).

## Usage

This role can be run using `become` or as `root` to install `jc` server-wide or as regular user for `git` installs, usig `pipx` into `~/.local/bin`, you might need to update your `$PATH` environmental variable if `~/.local/bin` is not includedn in it already.

This role can be used via the [localhost repo](https://git.coop/webarch/localhost) to install `jc` locally.

## Role variables

Set `jc` to `true` for the tasks in this role to be run, see [default variables](defaults/main.yml) for all the variables.

The following documentation has been generated from the [meta/argument_specs.yml](meta/argument_specs.yml).

### Entrypoint: main

The main entry point for the JC role.

|Option|Description|Type|Required|
|---|---|---|---|
| jc | Run the tasks in this role. | bool | yes |
| jc_bash | Install Bash completion if the jc version is >= 1.20.1 and not the .deb package, unless the jc version is <= 1.20.1. | bool | yes |
| jc_home | Generated variable for the HOME directory of the Ansible user that JC is to be present for. | str | yes |
| jc_install | Install method for JC. | str | yes |
| jc_jmespath_queries | JMESPath queries. | dict | yes |
| jc_pipx_root_env | The pipx environment variables for the root user. | dict of 'jc_pipx_root_env' options | no |
| jc_pipx_user_env | The pipx environment variables for a regular user. | dict of 'jc_pipx_user_env' options | no |
| jc_verify | Verify variables that start with jc_ using the argument specification. | bool | yes |
| jc_version | JC version number, branch name or latest. | str | yes |

#### Options for main > jc_pipx_root_env

|Option|Description|Type|Required|
|---|---|---|---|
| PIPX_HOME | The PIPX_HOME environment variable value for pipx when run as root. | str | no |
| PIPX_BIN_DIR | The PIPX_BIN_DIR environment variable value for pipx when run as root. | str | no |

#### Options for main > jc_pipx_user_env

|Option|Description|Type|Required|
|---|---|---|---|
| PIPX_HOME | The PIPX_HOME environment variable value for pipx when run as a regular user. | str | no |
| PIPX_BIN_DIR | The PIPX_BIN_DIR environment variable value for pipx when run as a regular user. | str | no |

#### Choices for main > jc_install

|Choice|
|---|
| deb |
| git |
| pipx |

## Repository

The primary URL of this repo is [`https://git.coop/webarch/jc`](https://git.coop/webarch/jc) however it is also [mirrored to GitHub](https://github.com/webarch-coop/ansible-role-jc) and [available via Ansible Galaxy](https://galaxy.ansible.com/chriscroome/jc).

If you use this role please use a tagged release, see [the release notes](https://git.coop/webarch/jc/-/releases).

## Copyright

Copyright 2022-2024 Chris Croome, &lt;[chris@webarchitects.co.uk](mailto:chris@webarchitects.co.uk)&gt;.

This role is released under [the same terms as Ansible itself](https://github.com/ansible/ansible/blob/devel/COPYING), the [GNU GPLv3](LICENSE).
