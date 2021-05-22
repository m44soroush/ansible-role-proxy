# Ansible role: Setup-Proxy

An ansible role to setup proxy on linux package managers and docker service.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

Decide to set proxy on package manager or docker service:

    set_proxy_on_package_manager: true
    set_proxy_on_docker: true

Proxy url which will be set:

    proxy_url: "http://Proxy.Docker.ir:5555"

Docker service config path and file name:


    docker_service_config_dir: /etc/systemd/system/docker.service.d
    docker_service_proxy_config_file: http-proxy.conf

This role will restart docker service if service status is active and installed. It is not necessary to have docker-cli installed on you system:

    docker_service_name: docker

Config file name for each package manager:
    
    apt_config_file_path: /etc/apt/apt.conf.d/99proxy
    yum_config_file_path: /etc/yum.conf


## Example Playbooks

```yaml
- hosts: all
  roles:
    - setup-proxy
```

## License

MIT


## Author Information

This role was created in 2021 by Mohammad Soroushzadeh.
