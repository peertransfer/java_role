# JAVA Ansible role

This role installs JAVA from Oracle or OpenJDK in a Debian Stretch environment.

There is optiontal setups for:
- Database
- Okta SSO integration
- Datacenter

All built with CircleCI: [![CircleCI](https://circleci.com/gh/peertransfer/java_role.svg?style=svg)](https://circleci.com/gh/peertransfer/java_role)

![Flywire Engineering](flywire_engineering.png)

<!-- TOC -->
- [JAVA Ansible role](#java-ansible-role)
- [Getting Started](#getting-started)
	- [Prerequisities](#prerequisities)
	- [Installing](#installing)
- [Testing](#testing)
- [Developing](#developing)
	- [Built With](#built-with)
	- [Contributing](#contributing)
	- [Versioning](#versioning)
- [Authors](#authors)
- [License](#license)

<!-- /TOC -->

## Getting Started

### Prerequisities

Ansible 2.8.3.0 version installed, or a Docker environment to develop.

### Installing

Add role dependecy to your requirements file ([Installing roles from file](https://docs.ansible.com/ansible/latest/reference_appendices/galaxy.html#installing-multiple-roles-from-a-file)).

Use the following example as a guide for specifying roles in *requirements.yml*:

```yaml
- src: flywire.java_role
  version: 0.1.0
```
Use the following command to install roles included in requirements.yml:

```sh
ansible-galaxy install -r requirements.yml
```

Then you'll be able to use the role in your playbooks:

```yaml
- hosts: linux-server
  become: yes
  roles:
    - { role: flywire.java_role }

```

## Testing

For testing we've used [Molecule](https://molecule.readthedocs.io/) with [Docker](https://www.docker.com/) as driver, and [Testinfra](https://testinfra.readthedocs.io/en/latest/) as verifier.

In order to run the tests you can:

```sh
$ pipenv install -r test-requirements.txt
$ pipenv run molecule test
```

Also you can play each stage of __Molecule__ separated from this matrix, *test* will do all the steps:

```
└── default
    ├── lint
    ├── cleanup
    ├── destroy
    ├── dependency
    ├── syntax
    ├── create
    ├── prepare
    ├── converge
    ├── idempotence
    ├── side_effect
    ├── verify
    ├── cleanup
    └── destroy
```

## Developing

### Built With

![Ansible](https://img.shields.io/badge/ansible-2.8.3-green.svg)
![Python](https://img.shields.io/pypi/pyversions/3)
![Molecule](https://img.shields.io/static/v1?label=molecule&message=2.20.2&color=green)
![Testinfra](https://img.shields.io/static/v1?label=testinfra&message=3.0.6&color=orange)

### Contributing

You can check in [CONTRIBUTING](.github/CONTRIBUTING.md)

### Versioning

We use the semver system to version all of our ansible roles, https://semver.org/

The current version is kept in plain text in a .semver file Ej: v1.2.5

## Authors

* **Flywire** - [flywire](https://github.com/peertransfer)

## License

![Apache 2.0 License](https://img.shields.io/hexpm/l/plug.svg)

This project is licensed under the [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) license - see the [LICENSE](.github/LICENSE) file for details.
