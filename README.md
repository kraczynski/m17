# m17 - konfiguracja Pi-star

W konfiguracji P-Star lista Relfektorów M17 pobieranych automatycznie znajduje się w następującym pliku: <br>
**/usr/local/etc/M17Hosts.txt** <br><br>
W celu dodania własnego reflektora np. M17-POL należy utworzyć plik: **/root/M17Hosts.txt** i dokonać wpisu "M17-POL  51.38.132.8  17000"<br><br>
Wykonaj następujące polecenia po zalogowaniu się do SSH Pi-star: <br><br>
**rpi-rw <br>
sudo -i <br>
touch M17Hosts.txt <br>
echo -e "M17-POL\t51.38.132.8\t17000" > M17Hosts.txt <br>
exit <br>
sudo pistar-update <br>**
<br> Nasz dodatkowy wpis będzie zawsze dodawany po update na końcu pliku. <br>
<br>
Jeśli chcesz zmienić suffix z R np. na H zmień wpis Suffix=R w pliku /etc/m17gateway <br>

**rpi-rw <br>
sudo nano /etc/m17gateway <br>**
