## Hướng Dẫn
Artifactory được deploy bằng docker-compose kèm theo nginx để sử dụng domain https://jfrog.vtdc.local kèm Cert SSl wildcard .vtdc.local

## Clone folder Artifactory để deploy
```

mkdir -p /opt/artifactory && cd /opt/artifactory && \
git init && \
git remote add -f origin https://git.vtdc.local/devops/docker.git && \
git config core.sparsecheckout true && \
echo artifactory >> .git/info/sparse-checkout && \
git pull origin master

```

## Sau khi clone xong, tiến hành deploy Artifactory bằng file docker-compose.yaml
```
cd /opt/artifactory
mkdir -p var
mkdir -p var/data
mkdir -p var/data/nginx
mkdir -p var/data/postgres
mkdir -p var/etc
chown -R 1030:1030 var
chown -R 1030:1030 var/data
chown -R 1030:1030 var/etc
chown -R 104:107 var/data/nginx
chown -R 999:999 var/data/postgres

# docker-compose v1
docker-compose up -d
docker-compose logs
# docker compose v2
docker compose up -d
docker compose logs
```
## Truy cập https://jfrog.vtdc.local
User: admin\
Pass: password
