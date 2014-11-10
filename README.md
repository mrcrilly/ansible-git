# Role Name

Installs (or updates) the Git SCM software suite on the target system. This can be installed from source or from the local package management system.

## Requirements

None.

## Role Variables

All variables use "mrcrilly_" as a namespace.

### mrcrilly_git_from_source
Default: true.

Installs Git using the source, which is obtained from the official source repository at kernel.org. This is default because Git RPM packages are few and far between or from untrusted, third party sources. The option to install from package management exists, of course.

### mrcrilly_git_version
Default: "2.1.3"

The version of Git to install.

### mrcrilly_git_prefix
Default: "/usr"

This is where the Git binaries will be installed. This module is *brutal* in its approach. That is, it will wipte out any package management based install (see below) and replace it with the compiled/installed version we use.

### mrcrilly_git_remove_system_install
Default: true

Remove the current installation before proceeding. This only uses the local package manager to remove the software - any custom or compiled setups aren't taken into account.

## Dependencies

None.

## Example Playbook

Use of this module is very straight forward:

    - hosts: servers
      roles:
        - mrcrilly.git

## License

BSD

## Author Information

- Michael Crilly
- http://mrcrilly.github.io/
