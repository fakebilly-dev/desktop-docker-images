# Workspaces Images

Build
```
docker build -t fakebilly/ubuntu:20.04-desktop -f dockerfile-kasm-ubuntu-focal-desktop .
```

Start
```
docker run -d --restart=unless-stopped \
--name ubuntu-desktop \
-p 6901:6901 \
-e VNC_PW=dev1024 \
-e LANG=en_US.UTF-8 \
-e LANGUAGE=en_US:en \
-e LC_ALL=en_US.UTF-8 \
-v /root/tmp:/usr/local/shares \
--shm-size=512m \
fakebilly/ubuntu:20.04-desktop
```

Url
```
https://<IP>:6901
```
 - **User** : `monet`
 - **Password**: `dev1024`

Change root password
```
docker exec -u root -it ubuntu-desktop passwd
```

Stop
```
docker stop ubuntu-desktop && docker rm ubuntu-desktop
```