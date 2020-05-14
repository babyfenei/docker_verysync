# docker_verysync
versync的docker镜像

## docker命令启动
```bash
docker run -d --restart=unless-stopped --name verysync -v /your_data:/data -p 8886:8886 -p 3000:3000 -p 22027:22027/udp -p 22037:22037/udp babyfenei/verysync
```

## docker-compose启动
```yml
version: "3"

services:
  versync:
    image: babyfenei/verysync
    ports:
      - "8886:8886"
      - "22330:22330"
      - "3000:3000"
      - "22027:22027/udp"
      - "22037:22037/udp"
    volumes:
      - "/your_data:/data"
      - "/etc/localtime:/etc/localtime:ro"
    restart: unless-stopped
```
