# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.2.2] - 2020-11-01
### Changed
- Reformat install condition
- Update task naming

## [1.2.1] - 2020-08-26
### Fixed
- Fix syntax errors

## [1.2.0] - 2020-08-22
### Added
- Add option `firewalld_redhat_enablerepo` to control the repository, which shall be used to install the requirements.

## [1.1.0] - 2020-06-13
### Added
- Add option `firewalld_debian_repo` to install reasonable up to date version of firewalld on Debian systems.

### Fixed
- Fix type of default variable `firewalld_config.LogDenied`

## [1.0.1] - 2020-05-28
### Changed
- Clean up repo

## [1.0.0] - 2020-05-11
### Added
- First version of the role
