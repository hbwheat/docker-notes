sudo docker run -d \
	--name pihole \
	-p 53:53/tcp -p 53:53/udp -p 80:80 \ 
	-v “home/wheat/pihole/:/etc/pihole/" \
	-v “home/wheat/pihole/dnsmasq.d/:/etc/dnsmasq.d/" \ 
	-e ServerIP=“10.0.0.8” \
	-e WEBPASSWORD=“” \
	--restart=unless-stopped \
	diginc/pi-hole:latest

sudo docker run -d \
	--name pihole \
	-p 53:53/tcp -p 53:53/udp -p 80:80 \
	-e ServerIP=“10.0.0.8” \
	-e WEBPASSWORD=“” \
	--restart=unless-stopped \
	diginc/pi-hole:latest
