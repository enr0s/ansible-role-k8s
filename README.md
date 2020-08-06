[![Build Status](https://travis-ci.com/enr0s/ansible-role-docker.svg?branch=master)](https://travis-ci.com/enr0s/ansible-role-docker)
![.github/workflows/molecule.yml](https://github.com/enr0s/ansible-role-docker/workflows/.github/workflows/molecule.yml/badge.svg)
[![quality](https://img.shields.io/ansible/quality/49709)](https://galaxy.ansible.com/enr0s/ansible-role-docker)
![LICENSE](https://img.shields.io/github/license/enr0s/ansible-role-docker)

Ansible Role Docker
=========

Install k8s on your Raspberry (64 bit architecture).


Role Variables
--------------

```

```
Docker installation options
```
docker_apt_release_channel: stable
docker_apt_repository: "deb [arch={{ ansible_architecture | replace('x86_64','amd64') | replace ('aarch64','arm64') }}] https://download.docker.com/linux/{{ ansible_distribution | lower }} {{ ansible_distribution_release }} {{ docker_apt_release_channel }}"
docker_apt_gpg_key: https://download.docker.com/linux/{{ ansible_distribution | lower }}/gpg
```
Docker users
```
docker_users: ['ubuntu']
```

Dependencies
------------

```
ansible-galaxy install -r molecule/default/requirements.yml
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
  ---
  - hosts: all
    roles:
      - {role: ansible-role-k8s, run_not_in_container: True }
```

License
-------

Apache-2.0


Author Information
------------------

[https://blog.enros.me]
