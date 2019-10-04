# Setup WSL

- https://medium.com/@sebagomez/installing-the-docker-client-on-ubuntus-windows-subsystem-for-linux-612b392a44c4
- https://nickjanetakis.com/blog/setting-up-docker-for-windows-and-wsl-to-work-flawlessly#ensure-volume-mounts-work

# Start Container

```
docker-compose up -d
```

## Information & Configuration

https://hub.docker.com/_/couchbase

## Create Cluster

https://medium.com/@kungwang/couchbase-cluster-using-docker-f17f0e04f83e
https://blog.couchbase.com/couchbase-using-docker-compose/

## access gui

http://localhost:8091/ui/index.html

## Load Data

```
 docker exec -d couchbase1 cbimport csv -c couchbase://127.0.0.1  -u Administrator -p Password1234 \
            -b memonly  -d file:///mnt/data/AllstarFull.csv -g allstarfull::%playerID%  --omit-empty --field-separator ','
```

```
 docker exec -d couchbase1  cbimport csv -c couchbase://127.0.0.1  -u Administrator -p Password1234 \
            -b memonly  -d file:///mnt/data/Appearances.csv -g appearances::#MONO_INCR#  --omit-empty --field-separator ','
```

## Bash in Container

```
docker exec -i -t couchbase1 /bin/bash
```

## Kuberentes Cluster

- https://blog.couchbase.com/deploy-self-healing-highly-available-couchbase-cluster-on-kubernetes-using-persistent-volumes/
- https://docs.couchbase.com/operator/current/install-kubernetes.html

### EKS couchbase Cluster

- https://github.com/couchbaselabs/cboperator-hol/tree/master/eks
