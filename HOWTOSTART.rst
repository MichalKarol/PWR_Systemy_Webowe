**Jak zacząć na Windowsie**
---------------------------
 1) Otwórz `docker.com <docker.com>`_ > resources > Community > Get started    
 2) Download for Windows > Link: Docker Toolbox
 3) Zainstaluj Docker Toolbox
 4) Uruchom Kinematic > Use Virtualbox > Poczekaj > Pomiń logowanie do DockerHub
 5) Otwórz `docker-compose releases <https://github.com/docker/compose/releases>`_ i pobierz ostatnie wydanie
 6) Zainstaluj docker-compose
 7) Sklonuj lub ściągnij repo
 8) Uruchom Docker Quickstart Terminal > Przejdz do folderu np. z0 > docker-compose.exe up
 9) Otwórz Docker Quickstart Terminal
 10) | `docker run -it --rm --network z$(nr_zadania)_squid_net appropriate/curl sh`
     | eg. w zadaniu 0: `docker run -it --rm --network z0_squid_net appropriate/curl sh`
 11) | `curl -x 10.0.$(nr_zadania).$(nr_maszyny):3128 pics4learning.com`
     | eg. w zadaniu 0: `curl -x 10.0.0.2:3128 pics4learning.com`
 12) I powinna się pojawić zawartość strony pics4learning.com

**Jak zacząć na Linuxie**
---------------------------
 1) Zainstaluj dockera
 2) sudo pip install docker-compose
 3) Sklonuj lub ściągnij repo
 4) Przejdz do katalogu z zadaniem np. z0 > docker-compose up
 5) | Ze względu na brak wirtualizacji nie trzeba tworzyć klienta, można połączyć się bezpośrednio:
    | `curl -x 10.0.$(nr_zadania).$(nr_maszyny):3128 pics4learning.com`
 6) I powinna się pojawić zawartość strony pics4learning.com


Dodatkowo
---------

Aby dostać się do kontenerów należy:
 | `docker exec -it z$(nr_zadania)_x$(nr_maszyny)_1 bash`
 | eg. w zadaniu 0 do maszyny x1: `docker exec -it z0_x1_1 bash`

I z tej konsoli możemy zobaczyć np.:
 * czy squid działa -  `service squid status`
 * przeładować squid -  `service squid reload`
 * zobaczyć logi dostępu -  `tail -f /var/log/squid/access.log`
 * zobaczyć katalog cachowania -  `ls /var/spool/squid/`
