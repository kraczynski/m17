# M17
Dashboard reflektor M17-M17: https://m17.openquad.net<br>
Dashboard reflektor M17-POL: https://m17.hblink.network<br>
Module list M17-POL: https://m17.hblink.network/index.php?show=modules<br><br>
![m17 mode](m17_dash.png)
![m17 mode](m17_dash1.png)<br>
W ostatnim czasie wzrosło zainteresowanie cyfrowym trybem modulacji radiowej **M17** opracowanej przez kolegę Wojciecha Kaczmarskiego SP5WWP. W celu połączenia się polskim reflektorem M17-POL przygotowałem następującą instrukcję.<br>
## Połączenie z aplikacji DroidStar:<br>
Dodaj wpis w zakładce Hosts: **M17 M17-POL m17.hblink.network 17000**<br>
W zakładce Settings zaktualizuj listę Update hosts. Wyłącz, włącz aplikację.<br>
## HotSpot z Pi-Star 4.2.6 
**UWAGA! Zanim przystąpisz do zmian w Pi-Star zrób aktualną kopię:<br>
Wejdź przez przeglądarkę na adres: http://pi-star/ lub lokalny adres IP HotSpota<br> 
HostSpot oraz komputer na którym dokonujesz wpisów musi być w tej samem sieci w tej samej puli adresowej<br>
_Pi-Star Dashboard -> Configuration -> Backup/Restore -> Download Configuration._<br>**<br>
Informacje wstępne:<br>
W konfiguracji [Pi-Star](https://www.pistar.uk/) lista Relfektorów M17 pobieranych automatycznie znajduje się w następującym pliku: <br>
**/usr/local/etc/M17Hosts.txt** <br>
W celu dodania własnego reflektora np. M17-POL należy utworzyć plik: **/root/M17Hosts.txt** i dokonać wpisu:<br> "M17-POL  51.38.132.8  17000"<br><br>
Logowanie do Pi-Star SSH:
Wejdź przez przeglądarkę na adres: http://pi-star/ lub IP.<br> 
-> Configuration -> Expert -> SSH Access <br>
login: pi-star<br>
password: raspberry <br><br>
Wykonaj następujące polecenia po zalogowaniu się do SSH Pi-Star: <br>
**rpi-rw <br>
sudo -i <br>
touch M17Hosts.txt <br>
echo -e "M17-POL\t51.38.132.8\t17000" > M17Hosts.txt <br>
exit <br>
sudo pistar-update <br>**
<br> Nasz dodatkowy wpis będzie zawsze dodawany automatycznie po update na końcu pliku /usr/local/etc/M17Hosts.txt <br>
Możesz to sprawdzić komendą: **grep -r 'M17-POL'  /usr/local/etc/M17Hosts.txt**<br><br>
Konfiguracja Pi-Star 
Zaloguj się do _Pi-Star Dashboard -> Configuration_ włącz  **M17 mode** i przycisk _Apply Changes_.<br>
![m17 mode](m17_mode.png)<br>
Następnie w **M17 Configuration** wybierz z listy **M17 Startup Host: M17-POL,module D.**  zapisz zamian:  Apply Changes<br>
![m17 mode](m17_pol.png)
<br>
Jeśli chcesz zmienić suffix z R np. na H zmień wpis Suffix=R w pliku /etc/m17gateway <br>
R-Repeaters, H-Hotspots<br>
Wykonaj następujące polecenia po zalogowaniu się do SSH Pi-Star: <br>
**rpi-rw <br>
sudo -i <br>
nano /etc/m17gateway <br>**
![m17 mode](ssh.png)<br>

Po zamianie w wierszu Suffix=R na Suffix=H wciskamy przycisk **CTRL** razem z przyciskiem **X** -> następnie zapisujemy bufor literą **Y**es -> i wciskamy **Enter** by zapisać zmiany w pliku /etc/m17gateway<br>
**exit<br>
exit<br>**
Następnie należy przeprowadzić reboot hotspota _-> Dashboard -> Admin -> Power -> Reboot_<br><br>
Pamiętaj! Z tego samego zewnętrznego adresu IP co posiada HotSpot z Pi-Starem nie połączysz się z reflektorem M17_POL przez aplikację.<br>
Połącz się z innego adresu IP!<br><br>
Jestem już po pierwszych próbach transmisji M17 RF - mały krok do przodu :)
![m17 mode](m17_rf.png)<br>
_Vy 73! de SP1RAC, Kazimierz - Koszalin
