The ship is drifting! The flag is the IP that has cut the helm.

---

Dans la mesure ou l'on recherche une coupure de communication on peu aller chercher des RST (reset), FIN (finish) ou des erreurs ICMP.

Voici les filtres correspondant dans wireshark :

```
RST tcp.flags == 0x04
FIN tcp.flags.fin == 1
ICMP error icmp.type == 3
```

du premier coup on tombe sur un RST
src = 192.168.101.21
dst = 192.168.101.68

J'ais d'abord essayé l'ip source croyant que c'était elle qui était à l'origine de la coupure. Mais finalement c'était l'ip destination 192.168.101.68
