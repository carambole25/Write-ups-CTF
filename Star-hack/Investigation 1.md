Dans ce challenge, on a un fichier challenge.pcapng qui contient des captures réseau. L'objectif est d'analyser ce fichier pour trouver des informations sensibles et potentiellement identifier une vulnérabilité exploitable.

On image que la machine à était scanné par nmap, car il y a beaucoup de tentative de connexion sur plein de port et la plus par échoue.

On peu récupérer les résultats du scan avec cette commande tshark (généré par chatgpt)
```
tshark -r challenge.pcapng -Y "tcp.flags.syn == 1 && tcp.flags.ack == 1" -T fields -e tcp.dstport -e ip.dst -e tcp.srcport
36092   192.168.1.22    80
36108   192.168.1.22    80
48890   192.168.1.22    22
48532   192.168.1.22    21
39180   192.168.1.22    80
39188   192.168.1.22    80
55062   192.168.1.22    21
```

Voici les ports ouvert :
```
80 (HTTP)
22 (SSH)
21 (FTP)
```

Étape 2 : Identification de la version du service FTP

En analysant les connexions vers le port FTP (port 21), nous avons identifié la version du serveur FTP utilisée : ProFTPD 1.3.5.

Une recherche rapide sur Google pour ProFTPD 1.3.5 nous mène à une vulnérabilité bien connue : CVE-2015-3306. Cette vulnérabilité permet un accès non autorisé et un détournement des permissions utilisateur, ce qui peut être exploité pour des élévations de privilèges et des accès non autorisés aux fichiers.

Le flag pour ce challenge est :

StarHack{3_CVE-2015-3306}