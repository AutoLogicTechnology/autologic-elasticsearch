# Autologic ElasticSearch

Manage ElasticSearch on your RedHat based systems.

## Version

1.1.0

## Variables

The role is split into three sections: software, configuration, and service. You can choose to have this role manage one or all of them.

```yaml
autologic_elasticsearch_manage_software: true 
autologic_elasticsearch_manage_configuration: true 
autologic_elasticsearch_manage_service: true 
```

You can also define two basic hashes which will be pushed out to the ```elasticsearch.yml``` and ```logging.yml``` configuration files.

```yaml
autologic_elasticsearch_configuration: []
autologic_elasticsearch_logging: []
```

These hashes should follow the namespaced pattern, like this:

```yaml
valid.configuration.item: true
valid.memory.setting: 1.4
```

You can also defne where the ElasticSearch RPM is downloaded and installed from, as well as what dependencies are installed to support ElasticSearch:

```yaml
autologic_elasticsearch_rpm_url: "https://download.elasticsearch.org/elasticsearch/elasticsearch/elasticsearch-1.5.0.noarch.rpm"
autologic_elasticsearch_dependencies:
  - "java-1.8.0-openjdk"
```

A Java runtime is needed for run ElasticSearch.

## Tests

The tests folder allows for an isolated testing environment using Vagrant and VirtualBox. You're free to edit the Vagrantfile to suit your needs, or ignore it completely. To test:

```shell
$ vagrant up
```

To provision the VM again after changes to the Role:

```shell
$ vagrant provision
````

## License

MIT.

## Author Information

- Michael Crilly
- Autologic Technology Ltd
- http://www.mcrilly.me/
