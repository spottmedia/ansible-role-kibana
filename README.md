# Ansible Role: Kibana


An Ansible Role that installs Kibana on RedHat/CentOS or Debian/Ubuntu.

## Requirements

None.

## Testing

* Download https://artifacts.elastic.co/downloads/kibana/kibana-6.3.1-amd64.deb and 
put into `files` folder of the project
*  Run `molecule test`

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

(for sub 5.x)

    kibana_version: "4.6"
    
(for >= 5.x)    

    kibana_version: "5.x"    
    kibana_version: "6.x"

The version of kibana to install (major and minor only).

    kibana_server_port: 5601
    kibana_server_host: "0.0.0.0"

The FQDN or IP address and port Kibana should use.

    kibana_elasticsearch_url: "http://localhost:9200"

The URL (including port) over which Kibana will connect to Elasticsearch.

## Dependencies

None.

## Example Playbook

    - hosts: kibana
      roles:
        - spottmedia.kibana
