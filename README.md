# m17 - konfiguracja Pi-star

W konfiguracji P-Star lista Relfektorów M17 pobieranych automatycznie znajduje się w następującym pliku: <br>
**/usr/local/etc/M17Hosts.txt** <br>
W celu dodania własnego reflektora np. M17-POL należy utworzyć plik: **/root/M17Hosts.txt** i dokonać wpisu według formatu: reflector<TAB>host<TAB>port <br>
<br>
Wykonaj następujące polecenia po zalogowaniu się do SSH Pi-star
rpi-rw <br>
sudo -i <br>
touch M17Hosts.txt <br>
echo -e "M17-POL\t51.38.132.8\t17000" > M17Hosts.txt <br>
exit <br>
sudo pistar-update <br>


zmiany Suffix=R <br>
rpi-rw <br>
sudo nano /etc/m17gateway <br>
