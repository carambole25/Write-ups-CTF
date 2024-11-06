Une vulnérabilité a été détectée, et comme nous faisons partie de l'équipe de Forensics, nous avons besoin d'un rapport pour l'équipe.
Nous avons obtenu une capture Wireshark, et nous devons maintenant répondre aux questions suivantes :

Quel est le nom d'utilisateur compromis ?

Quel est le domaine ? YOGO.CORP

Quel est le mot de passe en clair ?

Format du flag : StarHack{username@DOMAIN_MotDePasseUtilisateurCompromis}

---

On télécharge une capture réseau contenant des communications liées à Kerberos pour le domaine YOGO.CORP.

Filtrage des paquets Kerberos
On a appliqué un filtre sur les paquets Kerberos pour isoler les tentatives de connexion réussies.
```
kerberos.CNameString && kerberos.msg_type == 11
```

Identification de l'utilisateur
En analysant le flux TCP 3, on a identifié l’utilisateur lampard.frank comme étant compromis.

Extraction du mot de passe
```
451e9ed23580ec12803285da1e6f63a22e96b27e5117c8a12b8a75ff4ca7363c5a4e82910a95ec7357b236fd3168fddebbcb3495b19290a586dfced257a721f2943d5af23b2bc7ebf4d770437ca2f88bba4a6f03104e3f20ed5b34c22bacd2b2f3f1bf3bdedf269e3d4eaa63fd62619c984a130b57e9d884d74b46663124de8396edf3c8c8ba7f06217d1881801bc916e33a8adddb3799fbd1b8553ff3bac29ca02cf2940f72d1d98a177f763ef1c20fa21d354f3c84a3b23110756547d5bcf93d43f8d93d4084723c5e5cd185b1e0ae01738850f8bacfcc92ea8cd56ddcca89d69aff430e8bb45405e1ac49ee073ffe3c9380119b9c
```

On utilise hashcat pour retrouver le mdp en clair :
```
hashcat -m 18200 -a 0 hash.txt rockyou.txt
```
le mdp est Number12rocks

---

Le flag est :

StarHack{lampard.frank@YOGO.CORP_km81088}