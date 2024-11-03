You have successfully infiltrated a dangerous group planning to attack submarine communications cables. Gain access to their secret project and gather all the information you can !

Username : User
Password : P@ssw0rd

---


je comprend pas trop le git lab à l'air vide de chez vide. A part un projet laissé avec les trucs par defaut de gitlab. J'ai crue que l'email user@ecw-challenge.com pouvait être une piste mais je trouve rien avec epios. Peut-être le token est une piste... NON lol


Mais avec la pipeline on peu executer des commandes sur leur serveur :
```
ls /builds
ls /builds/JvjXygUzr
ls /home/gitlab-runner
```

Et avoir le résultat lors des tests CI/CD :
```
$ ls /builds
JvjXygUzr
$ ls /builds/JvjXygUzr
0
$ ls /home/gitlab-runner
```

Il y a toujours qu'une seul build...
```
ls /builds/JvjXygUzr/0/root/secret-project
ls /builds/JvjXygUzr/0/root/secret-project.tmp
cat /builds/JvjXygUzr/0/root/secret-project/index.html
cat /builds/JvjXygUzr/0/root/secret-project/readme.md
ls /builds/JvjXygUzr/0/root/secret-project/data
ls /builds/JvjXygUzr/0/root/secret-project/pdfs
ls /builds/JvjXygUzr/0/root/secret-project/src
ls /builds/JvjXygUzr/0/root/secret-project.tmp/git-template
ls /builds/JvjXygUzr/0/root/secret-project.tmp/gitlab-runner-env
```

On a plein d'information sur leur potentielles attaques :
```
$ cat /builds/JvjXygUzr/0/root/secret-project/readme.md
```

Le flag est dans le readme ! ECW{B3_c4reFU11_WiTh_Th053_Sh4rr3d_RunN3r5}
