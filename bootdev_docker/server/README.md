# Docker

```bash
GOOS=linux GOARCH=amd64 go build -o goserver
docker build . -t goserver:latest
docker run -p 8080:8080 goserver:latest
```

Build and push for all tags, example below:

```bash
docker build -t ptenteromano/goserver:0.2.0 -t ptenteromano/goserver:latest .
docker push ptenteromano/goserver --all-tags
```
