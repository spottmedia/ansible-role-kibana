# Ansible Role: Kibana

An Ansible Role that installs Kibana on Debian/Ubuntu. CentOS might come in future if requested/PRed
Uses *.deb to install kibana and has full `molecule` coverage.

### Why not install via yum/apt ?

It turned out to be frekishly hard (if not impossible) to install and maintain the library
via repos, so all had to be hacked 

## Requirements

None.

## Testing

All testing via molecule

* Download https://artifacts.elastic.co/downloads/kibana/kibana-6.3.1-amd64.deb and 
put into `files` folder of the project
*  Run `molecule test`

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):


* Kibana listen IP/port combination:

    ```
    kibana_server_port: 5601
    kibana_server_host: "0.0.0.0"
    ```

* ES search address:

    `kibana_elasticsearch_url: "http://localhost:9200"`

The URL (including port) over which Kibana will connect to Elasticsearch.

## Dependencies

None.

## Example Playbook (if pulled from github)

    - hosts: kibana
      roles:
        - ansible-role-kibana
