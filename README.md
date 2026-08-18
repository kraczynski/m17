# m17 - konfiguracja Pi-star

rpi-rw <br>
sudo -i <br>
touch M17Hosts.txt <br>
echo -e "M17-POL\t51.38.132.8\t17000" > M17Hosts.txt <br>
exit <br>
sudo pistar-update <br>


zmiany Suffix=R <br>
rpi-rw <br>
sudo nano /etc/m17gateway <br>
