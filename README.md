Ansible Role: Git Credential Manager
====================================

[![Build Status](https://travis-ci.com/gantsign/ansible_role_git_credential_manager.svg?branch=master)](https://travis-ci.com/gantsign/ansible_role_git_credential_manager)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-gantsign.git__credential__manager-blue.svg)](https://galaxy.ansible.com/gantsign/git_credential_manager)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/gantsign/ansible_role_git_credential_manager/master/LICENSE)

Role to install Microsoft's [Git Credential Manager for Mac and Linux](https://github.com/Microsoft/Git-Credential-Manager-for-Mac-and-Linux).

**Important:** while Microsoft's Git Credential Manager works on macOS this
Ansible role is presently for Linux only.

Requirements
------------

* Ansible >= 2.4

* Linux Distribution

    * Debian Family

        * Debian

            * Jessie (8)
            * Stretch (9)

        * Ubuntu

            * Trusty (14.04)
            * Xenial (16.04)
            * Bionic (18.04)

    * RedHat Family

        * CentOS

            * 7

        * Fedora

            * 28

    * SUSE Family

        * OpenSUSE

            * 42.2

    * Note: other versions are likely to work but have not been tested.

Role Variables
--------------

The following variables will change the behavior of this role:

```yaml
# Git Credential Manager version number
git_credential_manager_version: '2.0.3'

# The SHA256 of the Git Credential Manager JAR
git_credential_manager_jar_sha256sum: 'ee7a11486dffbea366c79500395d9f1384fe4dd3f91b49e09e6bc2ed8ab5f65a'

# The major version of the JRE
git_credential_manager_jre_major_version: '8'

# The full version of the JRE (from AdoptOpenJDK)
git_credential_manager_jre_version: 'jdk8u162-b12_openj9-0.8.0'

# The SHA256 of the JRE
git_credential_manager_jre_sha256sum: '4a90944fbe96cb6452391e952cc7c9b5136fb042a445eb205e31a029fd72fd7c'

# Base installation directory the Git Credential Manager
git_credential_manager_install_dir: '/opt/git-credential-manager/{{ git_credential_manager_version }}'

# Directory to store files downloaded for the Git Credential Manager
git_credential_manager_download_dir: "{{ x_ansible_download_dir | default(ansible_env.HOME + '/.ansible/tmp/downloads') }}"
```

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: gantsign.git_credential_manager
```

More Roles From GantSign
------------------------

You can find more roles from GantSign on
[Ansible Galaxy](https://galaxy.ansible.com/gantsign).

Development & Testing
---------------------

This project uses [Molecule](http://molecule.readthedocs.io/) to aid in the
development and testing; the role is unit tested using
[Testinfra](http://testinfra.readthedocs.io/) and
[pytest](http://docs.pytest.org/).

To develop or test you'll need to have installed the following:

* Linux (e.g. [Ubuntu](http://www.ubuntu.com/))
* [Docker](https://www.docker.com/)
* [Python](https://www.python.org/) (including python-pip)
* [Ansible](https://www.ansible.com/)
* [Molecule](http://molecule.readthedocs.io/)

To test this role run the following command from the project root:

```bash
molecule test
```

License
-------

MIT

Author Information
------------------

John Freeman

GantSign Ltd.
Company No. 06109112 (registered in England)