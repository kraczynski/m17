# m17 - konfiguracja Pi-star

rpi-rw
sudo -i
touch M17Hosts.txt
echo -e "M17-POL\t51.38.132.8\t17000" > M17Hosts.txt
exit
sudo pistar-update


zmiany Suffix=R
rpi-rw
sudo nano /etc/m17gateway
