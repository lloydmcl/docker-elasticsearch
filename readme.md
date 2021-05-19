## Elasticsearch
### Description
This role is designed to install elasticsearch on a cluster of VMs running docker.

### Warnings
It is recommended that this role is run with a serial value of one to prevent any downtime.

### Testing
This role was tested on the below versions
- Ubuntu 20.04

### Variables
Below are the variables used by this role;  

- **docker_network_name**  
The name of the docker network that will be associated with your elastic cluster.

- **docker_volume_name**
The name of your docker volume specific to the elastic cluster.

- **container_elastic_hostname**
The name of your container.

- **elastic_image**
The image and version of Elastic you want to deploy.

- **minimum_java_heap_size**
The minimum java heap size you want to configure. See additional docco.

- **maximum_java_heap_size**
The maximum java heap size you want to configure. See additional docco.

- **kibana_username**
The Kibana username to connect with.

- **kibana_password**
The kibana password to connect with.

- **elastic_backup_dir**
The persistent data directory for backups on the VM to map to the container.

- **docker_log_max_size**
The maximum json file size before the log is rolled.

- **docker_log_max_file**
The maximum number of log files that can be present.

- **elastic_node_name**
Elasticsearch uses this variable as a human-readable identifier for a particular instance of Elasticsearch.

- **elastic_node_master**
True/False value required. However this variable is not used in a basic stack and has been hashed out for now.
 # TODO: Add if statement for master node variable in template.

### Tags
- elastic
This tag will target all tasks related to this role.

### Additional Resources
https://www.elastic.co/guide/en/elasticsearch/reference/6.8/heap-size.html
https://docs.docker.com/config/containers/logging/local/
https://docs.ansible.com/ansible/latest/collections/community/docker/docker_network_module.html
https://docs.ansible.com/ansible/latest/collections/community/docker/docker_volume_module.html
https://docs.ansible.com/ansible/latest/collections/ansible/builtin/file_module.html
https://docs.ansible.com/ansible/latest/collections/ansible/builtin/template_module.html
https://docs.ansible.com/ansible/latest/collections/ansible/builtin/copy_module.html
https://docs.ansible.com/ansible/latest/collections/ansible/posix/sysctl_module.html
https://docs.ansible.com/ansible/latest/collections/community/docker/docker_container_module.html