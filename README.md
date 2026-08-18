# m17 - konfiguracja Pi-Star

UWAGA! Zanim przystąpisz do zmian w Pi-Star zrób aktualną kopię:<br> _Pi-Star Dashboard -> Configuration -> Backup/Restore -> Download Configuration._<br>

W konfiguracji [Pi-Star](https://www.pistar.uk/) lista Relfektorów M17 pobieranych automatycznie znajduje się w następującym pliku: <br>
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
Zaloguj się do Pi-Star D_ashboard -> Configuration_ włącz** M17 mode** i przycisk _Apply Changes_.<br>
Następnie w **M17 Configuration** wybierz z listy **M17 Startup Host: M17-POL,module D. ** zapisz zamian:  Apply Changes<br>
<br>
Jeśli chcesz zmienić suffix z R np. na H zmień wpis Suffix=R w pliku /etc/m17gateway <br>

**rpi-rw <br>
sudo nano /etc/m17gateway <br>**

Pamiętaj! Z tego samego zewnętrznego adresu IP co posiada HotSpot z Pi-Starem nie połączysz się z aplikacją QSO One.<br>
Połącz się z innego adresu IP. 
