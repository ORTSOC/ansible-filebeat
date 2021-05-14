# ansible-filebeat
=========

Deploys Filebeat, a log collector.

Requirements
------------

- Debian 10
- sudo
- ssh

Role Variables
--------------
- filebeat_download_path: the path to download filebeat to.
- logstash_lb_host: the logstash host to send logs to. Note: Needs to be a Wireguard address.
- kibana_host: the host to connect to for Kibana. Note: Needs to be a Wireguard address.
- kibana_username: a username to log in to Kibana with.
- kibana_password: a password to log in to Kibana with.


Example Playbook
----------------

Read traffic over 10.0.0.0/24 and 192.168.0.0/24 using the eth0 interface.

```yaml
- filebeat_download_path: /tmp/filebeat.deb
- logstash_lb_host: 10.100.0.30:4141
- kibana_host: 10.100.0.31:4000
- kibana_username: my_username
- kibana_password: my_password
```
License
-------

GPL3

Author Information
------------------

ORTSOC, Oregon State University
