On va rechercher cette fois-ci un fichier. J'étais en train d'écrire dans un document Word.

Peux-tu me le récupérer ? Ce dernier contient le flag.

Il te faudra un outil adapté à l'analyse mémoire pour y arriver.

Note : Le fichier est le même pour les 4 étapes

sha1: c91d17b27d8bf5df0830bd6104801b065cca6ee9
http://files.ctfrei.fr/memory.7z 

----------------------------------------------------------

Les fichiers sont chargé dans la mémoire lors de leur utilisation.

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
Parmis les processus on repère WINWORD qui est le nom de l'application Word.

On va donc dumper tout les fichiers lié à ce processus:

```
carambole@debian:~/volatility3$ python3 vol.py -f memory/memory.vmem windows.dumpfiles.DumpFiles --pid 5300
```

Parmis les fichiers on obtient une image de cadeaux avec le flag : CTFREI{F1l3s_Ar3_Lo@deD_iN_mEm0RY}
