# Bookinfo Rating Service

Rating service has been developed on NodeJS

## How to run with Docker

```bash
docker run -d --name mongodb -p 27017:27017 \
  -v $(pwd)/databases:/docker-entrypoint-initdb.d bitnami/mongodb:4.4.4-debian-10-r5
docker run -d --name ratings -p 8080:8080 --link mongodb:mongodb \
  -e SERVICE_VERSION=v2 -e 'MONGO_DB_URL=mongodb://mongodb:27017/ratings' ratings
```

* Test with path `/ratings/1`