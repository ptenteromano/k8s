# Boot-Dev Docker
Load balancer portion

Use a docker network running two server images and a load balancer image to distribute requests between the two servers.

```bash
docker pull caddy

docker network create caddytest

docker run --network caddytest --name caddy1 -d -p 8001:80 -v $PWD/index1.html:/usr/share/caddy/index.html caddy

docker run --network caddytest --name caddy2 -d -p 8002:80 -v $PWD/index2.html:/usr/share/caddy/index.html caddy

docker run --network caddytest -p 8080:80 -v $PWD/Caddyfile:/etc/caddy/Caddyfile caddy
```
