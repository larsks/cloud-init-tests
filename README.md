This is a suite of tests to validate that cloud-init is operating
correctly.  Create an Ansible inventory with a `cloudinit` group
containing any hosts you wish to validate, and then run the included
`playbook.yml` against that inventory.

## Configuration

### verify_root_fs_size

- `cloudinit_expected_fs_size` -- the tests will verify that the root
  filesystem size is *at least* this many bytes.  Use this to verify
  that cloud-init is growing the root filesystem when the system
  boots.

  Default: 20000000000 bytes (20GB or slightly less depending on how
  you count)

### verify_userdata

The `verify_userdata` test is meant to verify that cloud-init
correctly processed a user-data blob.  It makes use of the following
variables:

- `cloudinit_expected_files` -- a list of files that are expected to
  exist on the target system. This is meant to verify the behavior of
  modules such as `write_files`, `runcmd`, `bootcmd`, etc.

- `cloudinit_expected_users` and `cloudinit_expected_groups` -- these
  contains lists of users and groups that should exist on the target
  system.

## License

cloud-init-tests: a suite of anisble roles for verifying the behavior
of cloud-init  
Copyright (C) 2017 Lars Kellogg-Stedman

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
