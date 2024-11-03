My little brother's laptop seems to have a problem. Can you find out what's wrong and find the right information inside?

---

On liste tout les processus de la mémoire :
```
5068	7964	Discord.exe	0xae03bd9dc0c0	53	-	1	False	2024-09-17 13:50:20.000000 UTC	N/A	\Device\HarddiskVolume2\Users\bipbop\AppData\Local\Discord\app-1.0.9163\Discord.exe	"C:\Users\bipbop\AppData\Local\Discord\app-1.0.9163\Discord.exe" 	C:\Users\bipbop\AppData\Local\Discord\app-1.0.9163\Discord.exe
* 8128	5068	Discord.exe	0xae03bd994080	9	-	1	False	2024-09-17 13:50:22.000000 UTC	N/A	\Device\HarddiskVolume2\Users\bipbop\AppData\Local\Discord\app-1.0.9163\Discord.exe	C:\Users\bipbop\AppData\Local\Discord\app-1.0.9163\Discord.exe --type=crashpad-handler --user-data-dir=C:\Users\bipbop\AppData\Roaming\discord /prefetch:4 --no-rate-limit --monitor-self-annotation=ptype=crashpad-handler --database=C:\Users\bipbop\AppData\Roaming\discord\Crashpad --url=https://f.a.k/e --annotation=_productName=discord --annotation=_version=1.0.9163 --annotation=plat=Win64 --annotation=prod=Electron --annotation=ver=30.2.0 --initial-client-data=0x518,0x51c,0x520,0x514,0x524,0x7ff6f3cdf218,0x7ff6f3cdf224,0x7ff6f3cdf230	C:\Users\bipbop\AppData\Local\Discord\app-1.0.9163\Discord.exe
* 8800	5068	Discord.exe	0xae03bd9aa0c0	9	-	1	False	2024-09-17 13:50:40.000000 UTC	N/A	\Device\HarddiskVolume2\Users\bipbop\AppData\Local\Discord\app-1.0.9163\Discord.exe	"C:\Users\bipbop\AppData\Local\Discord\app-1.0.9163\Discord.exe" --type=utility --utility-sub-type=audio.mojom.AudioService --lang=fr --service-sandbox-type=audio --user-data-dir="C:\Users\bipbop\AppData\Roaming\discord" --secure-schemes=disclip,sentry-ipc --bypasscsp-schemes=sentry-ipc --cors-schemes=sentry-ipc --fetch-schemes=disclip,sentry-ipc --field-trial-handle=3864,i,4552412188950616898,8316196853737537629,262144 --enable-features=kWebSQLAccess --disable-features=AllowAggressiveThrottlingWithWebSocket,HardwareMediaKeyHandling,IntensiveWakeUpThrottling,MediaSessionService,SpareRendererForSitePerProcess,UseEcoQoSForBackgroundProcess,WinDelaySpellcheckServiceInit,WinRetrieveSuggestionsOnlyOnDemand --variations-seed-version --mojo-platform-channel-handle=3912 /prefetch:8	C:\Users\bipbop\AppData\Local\Discord\app-1.0.9163\Discord.exe
* 7280	5068	Discord.exe	0xae03b66c00c0	17	-	1	False	2024-09-17 13:50:23.000000 UTC	N/A	\Device\HarddiskVolume2\Users\bipbop\AppData\Local\Discord\app-1.0.9163\Discord.exe	"C:\Users\bipbop\AppData\Local\Discord\app-1.0.9163\Discord.exe" --type=utility --utility-sub-type=network.mojom.NetworkService --lang=fr --service-sandbox-type=none --user-data-dir="C:\Users\bipbop\AppData\Roaming\discord" --secure-schemes=disclip,sentry-ipc --bypasscsp-schemes=sentry-ipc --cors-schemes=sentry-ipc --fetch-schemes=disclip,sentry-ipc --field-trial-handle=2096,i,4552412188950616898,8316196853737537629,262144 --enable-features=kWebSQLAccess --disable-features=AllowAggressiveThrottlingWithWebSocket,HardwareMediaKeyHandling,IntensiveWakeUpThrottling,MediaSessionService,SpareRendererForSitePerProcess,UseEcoQoSForBackgroundProcess,WinDelaySpellcheckServiceInit,WinRetrieveSuggestionsOnlyOnDemand --variations-seed-version --mojo-platform-channel-handle=2092 /prefetch:3	C:\Users\bipbop\AppData\Local\Discord\app-1.0.9163\Discord.exe
* 7256	5068	Discord.exe	0xae03bd9990c0	21	-	1	False	2024-09-17 13:50:23.000000 UTC	N/A	\Device\HarddiskVolume2\Users\bipbop\AppData\Local\Discord\app-1.0.9163\Discord.exe	"C:\Users\bipbop\AppData\Local\Discord\app-1.0.9163\Discord.exe" --type=gpu-process --user-data-dir="C:\Users\bipbop\AppData\Roaming\discord" --gpu-preferences=WAAAAAAAAADgAAAMAAAAAAAAAAAAAAAAAABgAAEAAAA4AAAAAAAAAAAAAAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAGAAAAAAAAAAYAAAAAAAAAAgAAAAAAAAACAAAAAAAAAAIAAAAAAAAAA== --field-trial-handle=1864,i,4552412188950616898,8316196853737537629,262144 --enable-features=kWebSQLAccess --disable-features=AllowAggressiveThrottlingWithWebSocket,HardwareMediaKeyHandling,IntensiveWakeUpThrottling,MediaSessionService,SpareRendererForSitePerProcess,UseEcoQoSForBackgroundProcess,WinDelaySpellcheckServiceInit,WinRetrieveSuggestionsOnlyOnDemand --variations-seed-version --mojo-platform-channel-handle=1844 /prefetch:2	C:\Users\bipbop\AppData\Local\Discord\app-1.0.9163\Discord.exe
* 8508	5068	Discord.exe	0xae03bba08080	35	-	1	False	2024-09-17 13:50:32.000000 UTC	N/A	\Device\HarddiskVolume2\Users\bipbop\AppData\Local\Discord\app-1.0.9163\Discord.exe	"C:\Users\bipbop\AppData\Local\Discord\app-1.0.9163\Discord.exe" --type=renderer --user-data-dir="C:\Users\bipbop\AppData\Roaming\discord" --secure-schemes=disclip,sentry-ipc --bypasscsp-schemes=sentry-ipc --cors-schemes=sentry-ipc --fetch-schemes=disclip,sentry-ipc --app-user-model-id=com.squirrel.Discord.Discord --app-path="C:\Users\bipbop\AppData\Local\Discord\app-1.0.9163\resources\app.asar" --no-sandbox --no-zygote --autoplay-policy=no-user-gesture-required --disable-background-timer-throttling --disable-gpu-compositing --lang=fr --device-scale-factor=1 --num-raster-threads=3 --enable-main-frame-before-activation --renderer-client-id=7 --time-ticks-at-unix-epoch=-1726580918614612 --launch-time-ticks=112488765 --field-trial-handle=3888,i,4552412188950616898,8316196853737537629,262144 --enable-features=kWebSQLAccess --disable-features=AllowAggressiveThrottlingWithWebSocket,HardwareMediaKeyHandling,IntensiveWakeUpThrottling,MediaSessionService,SpareRendererForSitePerProcess,UseEcoQoSForBackgroundProcess,WinDelaySpellcheckServiceInit,WinRetrieveSuggestionsOnlyOnDemand --variations-seed-version --mojo-platform-channel-handle=3892 --enable-node-leakage-in-renderers /prefetch:1	C:\Users\bipbop\AppData\Local\Discord\app-1.0.9163\Discord.exe
6088	5080	free-robux.exe	0xae03bb594080	1	-	1	False	2024-09-17 13:52:58.000000 UTC	N/A	\Device\HarddiskVolume2\Users\bipbop\Downloads\free-robux.exe	"C:\Users\bipbop\Downloads\free-robux.exe" C:\Users\bipbop\AppData\Local\Temp\_MEI79202\phanpy.py	C:\Users\bipbop\Downloads\free-robux.exe
* 8792	6088	free-robux.exe	0xae03bb0b8340	1	-	1	False	2024-09-17 13:52:59.000000 UTC	N/A	\Device\HarddiskVolume2\Users\bipbop\Downloads\free-robux.exe	"C:\Users\bipbop\Downloads\free-robux.exe" C:\Users\bipbop\AppData\Local\Temp\_MEI79202\phanpy.py	C:\Users\bipbop\Downloads\free-robux.exe
```

On peu repérer un très suspect "free-robuxe.exe".

Lorsqu'on liste les fichier avec filescan on obtient une adresse qui permet de le dumper :
```
0xae03bd23adb0	\LOCAL\mojo.636.6420.14289963232246045839
0xae03bd23b0d0	\Users\bipbop\Downloads
0xae03bd23b260	\Users\bipbop\Downloads\free-robux.exe <---------- ici
0xae03bd23b580	\Users\bipbop\AppData\Local\Microsoft\Edge\User Data\Default\Code Cache\js\787a12ac394738eb_0
0xae03bd23b8a0	\Users\bipbop\AppData\Local\Microsoft\Edge\User Data\Default\Code Cache\js\a717a6674e05f3f5_0
0xae03bd23ba30	\LOCAL\mojo.636.6420.14289963232246045839
```

Après avoir faire une commande strings dessus et également grâce au nom du challenge on ce doute qu'il s'agit d'un programme en python :
```
carambole@debian:~/Documents/ctf/ecw/[OK] ECW2024-phanpyware$ strings free-robux.exe | grep .py
%s%c%s.py
_pyi_main_co
pyi-python-flag
Failed to copy file %s from %s
etc...
```

On peu le unpacke de cette manière : 
```
git clone https://github.com/countercept/python-exe-unpacker.git
cd python-exe-unpacker
python pyinstxtractor.py free-robuxe.exe
```

A l'intérieur on voit beaucoup de chose en lien des lib de crypto en python.

Mais on remarque également un fichier phanpy :
```
$ file phanpy 
phanpy: data
```

Peu d'info mais un peu plus avec la commande strings:
```
....
Ph4nPy.readme.txtu
    Wow... You found the readme.txt... But can you see the wallpaper ?
    Sometimes you need to follow the water before to jump in.
    and BTW : This Pokemon lives and nests on a riverbank. After playing in the mud, it won
t be able to settle down unless it washes its body.
....
```

Au passage je me fait avoir par un false flag.

On à une grande chaine de base64 dans le fichier, je l'a prend est la convertie avec cyberchef qui me permet de l'enregistrer en tant qu'image .jpg

On récupère le fameux wallapaper et le flag !
