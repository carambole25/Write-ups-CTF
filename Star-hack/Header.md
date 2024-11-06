Mon image est corrompue, pouvez-vous la réparer pour moi s'il vous plaît ?

Quand on affiche le début de l'image on constate bien que le header du fichier PNG manque.
*Tout les fichiers PNG doivent commencer par ^PNG*

On récupère les premiers octet d'un png sain :
```
dd if=image_valide.png of=header_valid.png bs=1 count=8
```

Et on les rajoutes au début de l'image corrompu
```
dd if=header_valid.png of=flag.png bs=1 count=8 conv=notrunc
```