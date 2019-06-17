# Ansible playbook - creating openstack resources


## Setting the project

clouds.yaml is a configuration file that contains everything needed to connect to one or more clouds. It may contain private information and is generally considered private to a user.

OpenStackClient looks for a file called clouds.yaml in the following locations:

- current directory
- ~/.config/openstack
- /etc/openstack

It recomend putting the clouds.yml file in the `~/.config/openstack`

```
git clone https://github.com/carrenolg/wordpress-nginx-mysql.git 
```

2. Download wordpress files run following command in the root directory project
```
git clone https://github.com/WordPress/WordPress.git wordpress
```

3. run docker-compose in the root directory project: 
```
$ docker-compose up -d
```
