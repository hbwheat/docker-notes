# unifi-docker-notes
These are notes used to create a container based off the jacobalberty/unifi:stable image from Docker hub. 

docker create \
  --name=unifi \
  -p 8080:8080 \
  -p 8443:8443 \
  -p 8843:8843 \
  -p 3478:3478/udp \
  -p 10001:10001/udp \
  -p 6789:6789 \
  -p 465:465 \
  -p 587:587 \
  -e TZ='America\New_York' \
  -e PGID=1002 -e PUID=1001  \
  -v ~/unifi:/unifi \
  --restart unless-stopped \
  jacobalberty/unifi:stable

sudo docker container run unifi

docker run --rm --init -p 8080:8080 -p 8443:8443 -p 3478:3478/udp -p 10001:10001/udp -e TZ='Africa/Johannesburg' -v ~/unifi:/unifi --name unifi jacobalberty/unifi:stable

___________________________________________________________
other docker image from linuxserver/unifi

docker create \
  --name=unifi2 \
  -v ~/unifi/data:/var/lib/unifi \
  -v ~/unifi/logs:/var/log/unifi \
  -v ~/unifi/config:/config \
  -e PGID=1002 -e PUID=1001  \
  -p 8080:8080 \
  -p 8443:8443 \
  -p 8843:8843 \
  -p 8880:8880 \
  -p 6789:6789 \
  -p 3478:3478 \
  -p 465:465 \
  -p 587:587 \
  --restart unless-stopped \
  linuxserver/unifi

