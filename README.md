# certbot

Installs certbot on Debian, Ubuntu, RHEL, CentOS, and using pip if needed.

## Requirements

### RHEL/CentOS:
  - EPEL

### Pypi aka pip
  - python-pip

## Role Variables
| Variable | Required | Default | Options | Comments |
|----------|----------|---------|---------|----------|
| `certbot_pkg_mgr` | No | {{ ansible_pkg_mgr }} | `apt`, `yum`, `pip` | The package manager used to install certbot |
| `certbot_pip_version` | No | 0.27.1 | Any Valid Version | The version of the certbot pip packages |
| `certbot_plugins` | No | `omit` | `apache`, `dns-cloudflare`, `digitalocean`, `dns-dnsimple`, `dns-rfc2136`, `dns-route53`, `nginx` | Specified as a list allows installation of certbot plugins |

## Example Playbook

### Basic Installation
```

  - hosts: server
    roles:
      - role: certbot
```   

### Installation w/Route53 Plugin
```

  - hosts: server
    roles:
      - role: certbot
        certbot_pkg_mgr: pip
        certbot_plugins:
          - dns-route53
```          

## License

Apache 2.0

## Author Information

Eric Anderson  
Avi Networks
