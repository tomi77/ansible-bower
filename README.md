# ansible-bower
A Ansible role to manage Bower tool

## Parameters

| Name             | Default                   | Description |
| ---------------- | ------------------------- | ----------- |
| bower_executable | ./node_modules/.bin/bower | Location of a `bower` command |
| state            | present                   | Operation to do<br>\* present - install package(s)<br>\* absent - uninstall package(s) |
| pkg              |                           | Package(s) to install |
| chdir            | .                         | Location of a `bower.json` file |

## Examples

~~~yaml
# Install all from bower.json
- tomi77.bower

# Install using global bower
- { role: tomi77.bower, executable: bower }

# Install lodash package
- { role: tomi77.bower, pkg: lodash }

# Uninstall lodash package
- { role: tomi77.bower, pkg: lodash, state: absent }

# Specify bower.json location
- { role: tomi77.bower, chdir: /location/of/bower/json/file }

# Specify bower.json location (newer syntax)
- include_role:
    name: tomi77.bower
  vars:
    chdir: /location/of/bower/json/file
~~~
