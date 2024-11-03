## "Saint John": what is writing to this log file?
---

Description: A developer created a testing program that is continuously writing to a log file /var/log/bad.log and filling up disk. You can check for example with tail -f /var/log/bad.log.
This program is no longer needed. Find it and terminate it.

----

On constate qu'effectivement un programme écrit toute les secondes dans le fichier bad.log
```bash
tail -f /var/log/bad.log
2024-11-03 13:46:57.234496 token: 1384205605
2024-11-03 13:46:57.534966 token: 1369625930
2024-11-03 13:46:57.835469 token: 1883301313
```

La commande lsof permet de retrouver quel utilisateur ou quel programme utilise quels fichiers :
```bash
admin@i-05d95b9b1f4648578:~$ lsof | grep bad.log
badlog.py 588                    admin    3w      REG              259,1    40289 265802 /var/log/bad.log
```

Grâce au nom du programme on peu retrouver le processus :
```bash
admin@i-05d95b9b1f4648578:~$ ps -e | grep badlog.py
    588 ?        00:00:00 badlog.py
```

Et l'arreter !
```
admin@i-05d95b9b1f4648578:~$ kill 588
```
