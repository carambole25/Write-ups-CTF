Description

En parlant de document Word, il semble que le mien ait exécuté un processus... Comportement assez étrange.

Peux-tu me trouver :

Le PID du processus exécuté par Word

La commande utilisée (pas toute la chaîne, juste la commande effective et ses arguments)

Format : CTFREI{1234_ipconfig-/all}

Note : Le fichier est le même pour les 4 étapes

sha1: c91d17b27d8bf5df0830bd6104801b065cca6ee9

----

On va d'abord lister les processus :

```
carambole@debian:~/volatility3$ python3 vol.py -f memory/memory.vmem windows.pstree
Volatility 3 Framework 2.10.0
[...]
****** 5300	2560	WINWORD.EXE	0x96035674a080	32	-	1	False	2024-09-12 10:50:09.000000 UTC	N/A	\Device\HarddiskVolume3\Program Files\Microsoft Office\root\Office16\WINWORD.EXE	"C:\Program Files\Microsoft Office\Root\Office16\WINWORD.EXE" /n "C:\Users\Aramis\Documents\Portos.docm	C:\Program Files\Microsoft Office\Root\Office16\WINWORD.EXE
******* 3016	5300	cmd.exe	0x960356325340	1	-	1	False	2024-09-12 10:50:37.000000 UTC	N/A	\Device\HarddiskVolume3\Windows\System32\cmd.exe	C:\Windows\System32\cmd.exe /c net user /add admin_user 123password & pause	C:\Windows\System32\cmd.exe
******** 8120	3016	conhost.exe	0x960353fa0080	5	-	1	False	2024-09-12 10:50:38.000000 UTC	N/A	\Device\HarddiskVolume3\Windows\System32\conhost.exe	\??\C:\Windows\system32\conhost.exe 0x4	C:\Windows\system32\conhost.exe
******* 7576	5300	ai.exe	0x960356565340	11	-	1	False	2024-09-12 10:50:39.000000 UTC	N/A	\Device\HarddiskVolume3\Program Files\Microsoft Office\root\vfs\ProgramFilesCommonX64\Microsoft Shared\Office16\ai.exe	-	-
[...]
```

On voit que le PID du WINWORD 5300 mais également que celui ci lance cmd.exe ce qui est assez inatendu (surtout vu la commande en question).

proc 3016
```
cmd.exe /c net user /add admin_user 123password & pause	C:\Windows\System32\cmd.exe
```

Avec ces informations on peu reconstruire le flag !

3016_net-user-/add
