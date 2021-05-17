ansible-filebeat
=========

Deploys Filebeat, a log collector.

Requirements
------------

- Debian 10
- sudo
- ssh

Role Variables
--------------
- `filebeat_download_path`: the path to download filebeat to.
  - NOTE: This is defined in the role to save in /tmp, optional to set and override
- `logstash_lb_host`: the logstash host to send logs to. Note: Needs to be a Wireguard address.
- `kibana_host`: the host to connect to for Kibana. Note: Needs to be a Wireguard address.
- `kibana_username`: a username to log in to Kibana with.
- `kibana_password`: a password to log in to Kibana with.
- `es_hosts`: an array of elasticsearch hosts to write to (only used when configuring the pipeline).
- `filebeat_modules`: a list of modules to be enabled (valid options: `suricata`, `zeek`, `wireguard`).
- `es_creds.beats_system`: the password for the `beats_system` user.

Example Playbook
----------------

Move zeek logs and suricata logs to Logstash over the specified address, and add kibana dashboards using specified kibana credentials

```yaml
filebeat_download_path: /tmp/filebeat.deb
logstash_lb_host: 10.100.0.30:4141
kibana_host: 10.100.0.31:4000
kibana_username: my_username
kibana_password: my_password
es_hosts:
  - https://es1.local:9200
  - https://es2.local:9200
filebeat_modules:
  - zeek
  - suricata
```
License
-------

GPL3

Author Information
------------------

ORTSOC, Oregon State University
