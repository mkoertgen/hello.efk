# hello.elk

Example blueprint for a minimal ELK-stack orchestrated using docker-compose.

## Getting started

### Standalone

To startup a stand-alone elasticsearch node

```shell
docker compose up -d elasticsearch kibana
```

And hit [http://localhost:5601](http://localhost:5601) to see

### Cluster

To startup a 3-node elasticsearch cluster

```shell
$ docker compose up -d es01 es02 es03
[+] Running 4/4
 - Network helloelk_default Created
 - Container es03            Started
 - Container es01            Started
 - Container es02            Started
```

And hit [http://localhost:9200](http://localhost:9200) to see

```json5
{
  name: "es01",
  cluster_name: "es-docker-cluster",
  cluster_uuid: "6EaPw16fRbykoxZp46fE8A",
  version: {
    number: "7.12.1",
    build_flavor: "default",
    build_type: "docker",
    build_hash: "3186837139b9c6b6d23c3200870651f10d3343b7",
    build_date: "2021-04-20T20:56:39.040728659Z",
    build_snapshot: false,
    lucene_version: "8.8.0",
    minimum_wire_compatibility_version: "6.8.0",
    minimum_index_compatibility_version: "6.0.0-beta1",
  },
  tagline: "You Know, for Search",
}
```

## Notes

On development machines you might need to adjust the `vm.max_map_count`-setting as described here [](https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html)

For example to adjust this on Windows using Docker Desktop on wsl2 do

```shell
wsl -d docker-desktop
sysctl -w vm.max_map_count=262144
```

## References

- [Fluentd EFK Stack Howto](https://docs.fluentd.org/container-deployment/docker-compose), [uken/fluent-plugin-elasticsearch](https://github.com/uken/fluent-plugin-elasticsearch)
