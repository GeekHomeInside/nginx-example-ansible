# NGINX installer

This installer use ansible to setup Nginx on a Linux environment using Docker 18.03.1

## Playbooks

- `install.yml`

> Install Nginx on the machine


## Install from an Artifactory release

For each install do:
- Generate an ssh key
```ssh-keygen```
- copy the private key to the remote server
``` ssh-copy-id -i ssh/id_rsa <your user>@<hostname.domainename>```

for example:
```ssh-copy-id -i ~/.ssh/id_rsa admin_devops@localhost```

- Edit the file `artifactory/group_vars/all.yml` of this project
  - Change the `allspark_root_domain` to use your domain name
    (each component will be exposed as a subdomain).
  - Change the `allspark_hostname` to use your hostname

- `ansible-playbook -i hosts install.yml`

## Components

| Components    | Usage                                                       |
| ------------- | ----------------------------------------------------------- |
| Nginx         | High Performance Load Balancer, Web Server, & Reverse Proxy |

## OS Compatibility

Nginx is compatible with:
  - CentOS 7 or above
  - RedHat 7 or above
  - Fedora Server/Atomic 28 or above
  - Ubuntu 14.04 or above
  - Debian 8 or above

## Requirements

- Linux using Docker 18.03.1
