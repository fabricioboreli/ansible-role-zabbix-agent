Zabbix Agent
============
Ansible Role that install and configure [zabbix-agent](https://www.zabbix.com/ "The Enterprise-class Monitoring Solution for Everyone").  

This role add a new repository to the system containing the 3.4 version of Zabbix then install the zabbix-agent package and transfer the configuration file (_zabbix_agentd.conf_) to the host.

Requirements
------------
Debian 7, 8 or 9  
CentOS 7  

Role Variables
--------------
The IP address in which the agent will listen on, if you want it to listen on all IP addresses available on the host then use '0.0.0.0':
```yaml
zabbix_agent_listen_ip: "0.0.0.0"
```

The IP address of the Zabbix Server for [passive checks](https://www.zabbix.com/documentation/3.4/manual/appendix/items/activepassive):
```yaml
zabbix_agent_server_passive: "192.168.10.10"
```

The IP address of the Zabbix Server for [active checks](https://www.zabbix.com/documentation/3.4/manual/appendix/items/activepassive):
```yaml
zabbix_agent_server_active: "192.168.10.10"
```

Dependencies
------------

None.

Example Playbook
----------------
```yaml
---
- name: Install and configure Zabbix Agent
  hosts: firewall-01
  become: true
  gather_facts: true

  roles:
    - role: ansible-role-zabbix-agent
      zabbix_agent_listen_ip: "0.0.0.0"
      zabbix_agent_server_passive: "192.168.10.10"
      zabbix_agent_server_active: '{{ zabbix_agent_server_passive }}'
```

License
-------

MIT

Author Information
------------------

Fabricio Boreli  
fabricioboreli at openmailbox dot org
