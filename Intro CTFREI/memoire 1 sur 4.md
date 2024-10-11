Ceci est un exercice d'analyse de mémoire vive. J'ai récupéré la mémoire de mon ordinateur Windows à un moment donné, et pleins d'informations utiles s'y cachent.

On va commencer par rechercher quelque chose de simple : le nom de l'ordinateur

C'est simple, il porte le mot CTFREI dedans. Le flag sera alors les mots qui suivent.

Format : CTFREI{Mots-trouvés}
NB : Le hostname est composé de 3 mots, CTFREI ne compte pas

Note : Le fichier est le même pour les 4 étapes

sha1: c91d17b27d8bf5df0830bd6104801b065cca6ee9
http://files.ctfrei.fr/memory.7z 

--------------------------------------------------------------

Comme expliquer dans l'indice le hostname commence par CTFREI. Pour ce challenge on a juste à utiliser strings :

```
strings memory/memory/memory.vmem | grep CTFREI
....
CTFREI-Nice-Hostname-buddy
...
```
