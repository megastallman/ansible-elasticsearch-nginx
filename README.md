# ansible-elasticsearch-nginx
Ansible playbook to setup an elasticsearch cluster with nginx load-balancer

Supported OS: Ubuntu 14.04
User: ubuntu, with passwordless sudo

1) Create necessary host groups in your ansible inventory file
	/etc/ansible/hosts
	[es-balancer]
	192.168.66.1

	[es-node]
	192.168.66.2
	192.168.66.3
	192.168.66.4
2) Start the playbook as:
ansible-playbook ES.yml


Many necessary defaults are predefined. Such as:
- Oracle java 8
- Cluster name test-elasticsearch (elasticsearch.yml.j2: cluster.name: test-elasticsearch)
- Separate ES data directory (you can just remove: 
		elasticsearch.yml.j2: path.data: /mnt/elasticsearch
		ES-1.4: task 4)

