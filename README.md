# Webarchitects JC Ansible role 

[![pipeline status](https://git.coop/webarch/jc/badges/main/pipeline.svg)](https://git.coop/webarch/jc/-/commits/main)

Ansible role to install [JC (JSON Convert)](https://github.com/kellyjonbrazil/jc) on Debian and Ubuntu using [apt](https://github.com/kellyjonbrazil/jc/releases), [pip](https://pypi.org/project/jc/) or [git](https://github.com/kellyjonbrazil/jc). 

## Usage

This role can be run using `become` or as `root` to install `jc` server-wide or as regular user for `git` and `pip` installs into `~/.local/bin`, you might need to update your `$PATH` environmental variable if `~/.local/bin` is not included.

This role can be used via the [localhost repo](https://git.coop/webarch/localhost) to install `jc` locally.

Note that if you wish to use the [community.general.jc](https://blog.kellybrazil.com/2020/08/30/parsing-command-output-in-ansible-with-jc/) Ansible filter plugin then you need to install `jc` using `pip3`.

## Role variables

There are four [default variables](defaults/main.yml):

| Variable name        | Default value    | Comment                                                                                                                                                                                                                           |
|----------------------|------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `jc`                 | `true`           | Run the tasks in this role, set to `false` for all tasks to be skipped                                                                                                                                                            |
| `jc_bash`            | `true`           | Install Bash completion if `jc_version` is `>= 1.20.1` and not the .`deb` package, unless `jc_version` is `<= 1.20.1`                                                                                                     |
| `jc_install`         | `deb`            | Install method, set to `deb`, `git` or `pip`                                                                                                                                                                                      |
| `jc_version`         | `latest`         | Version for `deb` and `pip` installs, or branch (`dev` or `master`) for a `git` install, set to `latest` for the [latest version](https://github.com/kellyjonbrazil/jc/releases/latest) or a version number, for example `1.20.1` |

## Repository

The primary URL of this repo is [`https://git.coop/webarch/jc`](https://git.coop/webarch/jc) however it is also [mirrored to GitHub](https://github.com/webarch-coop/ansible-role-jc) and [available via Ansible Galaxy](https://galaxy.ansible.com/chriscroome/jc).

If you use this role please use a tagged release, see [the release notes](https://git.coop/webarch/jc/-/releases).

## Copyright

Copyright 2022-2023 Chris Croome, &lt;[chris@webarchitects.co.uk](mailto:chris@webarchitects.co.uk)&gt;.

This role is released under [the same terms as Ansible itself](https://github.com/ansible/ansible/blob/devel/COPYING), the [GNU GPLv3](LICENSE).
