# Ansible playbook - creating openstack resources


## Setting the project

clouds.yaml is a configuration file that contains everything needed to connect to one or more clouds. It may contain private information and is generally considered private to a user.

OpenStackClient looks for a file called clouds.yaml in the following locations:

- current directory
- ~/.config/openstack
- /etc/openstack

It is advisable putting the clouds.yml file in the `~/.config/openstack` location.

Example:
```
clouds:
  ormuco:
    auth:
      auth_url: https://api.example.com:5000/v3
      username: {your_user}
      password: {your_password}
      tenant_id: {projectID}
    region_name: {region}
    identity_api_version: 3
```
In the above example, there is a cloud called "ormuco". This name will be reference from playbook in the `site.yml`

```
- hosts: localhost
  remote_user: root
  roles:
    - ormuco
```

## Run the playbook

1. Clone the repository
```
git clone 
```

3. run docker-compose in the root directory project: 
```
$ docker-compose up -d
```
