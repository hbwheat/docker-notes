sudo docker run -d \
    --name pihole \
    -p 53:53/tcp -p 53:53/udp \
    -p 67:67/udp \
    -p 80:80 \
    -v '/home/wheat/pihole/:/etc/pihole/' \
    -v '/home/wheat/pihole/dnsmasq.d/:/etc/dnsmasq.d/' \
    -e ServerIP='10.0.0.8'	\
    --restart=unless-stopped \
    -e WEBPASSWORD='' \
    --cap-add=NET_ADMIN \
    --dns=127.0.0.1 --dns=1.1.1.1 \
    pihole/pihole:latest
