# docker_verysync
versync的docker镜像

## docker命令启动
```bash
docker run -d --restart=unless-stopped --name verysync -v /your_data:/data -p 8886:8886 babyfenei:verysync:latest
```

## docker-compose启动
```yml
version: "3"

services:
  versync:
    image: babyfenei:verysync:latest
    ports:
      - "8886:8886"
      - "22330:22330"
    volumes:
      - "/your_data:/data"
      - "/etc/localtime:/etc/localtime:ro"
    restart: unless-stopped
```
