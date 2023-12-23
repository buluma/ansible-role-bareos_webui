# [Ansible role bareos_webui](#bareos_webui)

Install and configure [Bareos](https://www.bareos.com/) WebUI on your system.

|GitHub|GitLab|Downloads|Version|Issues|Pull Requests|
|------|------|-------|-------|------|-------------|
|[![github](https://github.com/buluma/ansible-role-bareos_webui/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bareos_webui/actions/workflows/molecule.yml)|[![gitlab](https://gitlab.com/shadowwalker/ansible-role-bareos_webui/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-bareos_webui)|[![downloads](https://img.shields.io/ansible/role/d/)](https://galaxy.ansible.com/buluma/bareos_webui)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bareos_webui.svg)](https://github.com/buluma/ansible-role-bareos_webui/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-bareos_webui.svg)](https://github.com/buluma/ansible-role-bareos_webui/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-bareos_webui.svg)](https://github.com/buluma/ansible-role-bareos_webui/pulls/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-bareos_webui/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: buluma.bareos_webui
      bareos_webui_directors:
        - name: localhost-dir
          enabled: yes
          diraddress: localhost
        - name: disabled-dir
          enabled: no
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-bareos_webui/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  become: yes
  gather_facts: no

  roles:
    - role: buluma.bootstrap
    - role: buluma.bareos_repository
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-bareos_webui/blob/master/defaults/main.yml):

```yaml
---
# defaults file for bareos_webui

bareos_webui_configuration:
  - section: session
    option: timeout
    value: 3600

bareos_webui_directors: []
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-bareos_webui/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.bareos_repository](https://galaxy.ansible.com/buluma/bareos_repository)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bareos_repository/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bareos_repository/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-bareos_repository/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-bareos_repository)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-bareos_webui/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Debian](https://hub.docker.com/repository/docker/buluma/debian/general)|bookworm, bullseye, buster|
|[EL](https://hub.docker.com/repository/docker/buluma/enterpriselinux/general)|8, 9|
|[Fedora](https://hub.docker.com/repository/docker/buluma/fedora/general)|38|
|[Ubuntu](https://hub.docker.com/repository/docker/buluma/ubuntu/general)|jammy, focal|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-bareos_webui/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-bareos_webui/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-bareos_webui/blob/master/LICENSE).

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)


### [Special Thanks](#special-thanks)

Template inspired by [Robert de Bock](https://github.com/robertdebock)
