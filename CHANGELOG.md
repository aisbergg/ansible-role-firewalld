# Changelog

All notable changes to this project will be documented in this file.

- [2.0.0 (2021-10-11)](#200-2021-10-11)
- [1.2.2 (2020-11-01)](#122-2020-11-01)
- [1.2.1 (2020-08-26)](#121-2020-08-26)
- [1.2.0 (2020-08-22)](#120-2020-08-22)
- [1.1.0 (2020-06-13)](#110-2020-06-13)
- [1.0.1 (2020-05-28)](#101-2020-05-28)
- [1.0.0 (2020-05-11)](#100-2020-05-11)

---

<a name="2.0.0"></a>
## [2.0.0](https://github.com/aisbergg/ansible-role-firewalld/compare/v1.2.2...v2.0.0) (2021-10-11)

### CI Configuration

- add Github action for automatic releases

### Chores

- update changelog
- update development configs
- **.pre-commit-config.yaml:** bump pre-commit hook versions
- **CHANGELOG.tpl.md:** update changelog template

### Code Refactoring

- rename options firewalld_enabled and firewalld_state
- drop support for Ansible < 2.10

### Documentation

- **README.md:** update readme


<a name="1.2.2"></a>
## [1.2.2](https://github.com/aisbergg/ansible-role-firewalld/compare/v1.2.1...v1.2.2) (2020-11-01)

### Chores

- update changelog

### Code Refactoring

- use macro for boolean values
- reformat conditions and other minor changes

### Documentation

- **README.md:** update readme


<a name="1.2.1"></a>
## [1.2.1](https://github.com/aisbergg/ansible-role-firewalld/compare/v1.2.0...v1.2.1) (2020-08-26)

### Bug Fixes

- syntax errors

### Chores

- update changelog


<a name="1.2.0"></a>
## [1.2.0](https://github.com/aisbergg/ansible-role-firewalld/compare/v1.1.0...v1.2.0) (2020-08-22)

### Chores

- update changelog

### Features

- split tasks and add option firewalld_redhat_enablerepo


<a name="1.1.0"></a>
## [1.1.0](https://github.com/aisbergg/ansible-role-firewalld/compare/v1.0.1...v1.1.0) (2020-06-13)

### Bug Fixes

- type of default variable

### Chores

- update changelog

### Features

- add option 'firewalld_debian_repo'


<a name="1.0.1"></a>
## [1.0.1](https://github.com/aisbergg/ansible-role-firewalld/compare/v1.0.0...v1.0.1) (2020-05-28)

### Code Refactoring

- clean up repo


<a name="1.0.0"></a>
## [1.0.0]() (2020-05-11)

- Initial Release
