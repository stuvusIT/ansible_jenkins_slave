# jenkins-slave

This role installs a Jenkins JNLP slave and configures the start parameters to connect it to the master.
The slave is run under an own user `jenkins-slave`.

## Requirements

Debian

## Role Variables

| Name                      | Default / Mandatory | Description                         |
|:--------------------------|:-------------------:|:------------------------------------|
| `jenkins_slave_master`    | :heavy_check_mark:  | URL to the master installation      |
| `jenkins_slave_node_name` | :heavy_check_mark:  | The name of this Jenkins node       |
| `jenkins_slave_secret`    | :heavy_check_mark:  | The Secret to connect to the master |

## Example Playbook

```yml
- hosts: slaves
  roles:
    - role: jenkins-slave
      jenkins_slave_master: https://jenkins.example.com
      jenkins_slave_node_name: "{{ inventory_hostname }}"
      jenkins_slave_secret: eae68e1e30f8659224ac5d0d32884ab0814284aa43d18d700a4df41d3e298962
      jenkins_port: 8081
```

## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).

## Author Information

- [Janne Heß](https://github.com/dasJ)
