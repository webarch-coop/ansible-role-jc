# Webarchitects jc Ansible role 

[![pipeline status](https://git.coop/webarch/jc/badges/main/pipeline.svg)](https://git.coop/webarch/jc/-/commits/main)

Ansible role to install `jc` on Debian and Ubuntu using [deb packages](https://github.com/kellyjonbrazil/jc/releases) from [the GitHub repo](https://github.com/kellyjonbrazil/jc), [pip3](https://pypi.org/project/jc/) or [git](https://github.com/kellyjonbrazil/jc). 

There are three [default variables](defaults/main.yml):

| Variable name        | Default value    | Comment                                                                                                                                                                                                       |
|----------------------|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `jc`                 | `true`           | Run the tasks in this role, set to `false` for all tasks to be skipped                                                                                                                                        |
| `jc_install`         | `deb`            | Install method, set to `deb`, `git` or `pip`                                                                                                                                                                  |
| `jc_version`         | `latest`         | Version for `deb` and `pip` installs, or branch for a `git` install, set to `latest` for the [latest version](https://github.com/kellyjonbrazil/jc/releases/latest) or a version number, for example `1.18.6` |


The primary URL of this repo is [`https://git.coop/webarch/jc`](https://git.coop/webarch/jc) however it is also [mirrored to GitHub](https://github.com/webarch-coop/ansible-role-jc) and [available via Ansible Galaxy](https://galaxy.ansible.com/chriscroome/jc).

If you use this role please use a tagged release, see [the release notes](https://git.coop/webarch/jc/-/releases).

This role can also be used with the [localhost repo](https://git.coop/webarch/localhost) to install `jc` locally.
