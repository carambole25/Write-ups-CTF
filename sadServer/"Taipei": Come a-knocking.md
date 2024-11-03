## "Taipei": Come a-knocking

---

There is a web server on port :80 protected with Port Knocking. Find the one "knock" needed (sending a SYN to a single port, not a sequence) so you can curl localhost.

---

Le port knocking est une technique de sécurité réseau où l’accès à un service est conditionné par une séquence de tentatives de connexion sur des ports spécifiques. Lorsque la bonne séquence est exécutée, le firewall ouvre le port souhaité pour l'IP du client. Cela permet de masquer les services en bloquant leur accès jusqu'à ce qu'une "clé" (la séquence) soit fournie.

Ici la séquence est composé d'un seul port on peu donc tous les tester de 0 à 9999, en espérant que ça soit pas le 65000 par exemple :)

```
for i in {1..9999}; do
    nc localhost "$i"
    curl localhost
done
```
Le problème c'est que le script s'arretait sur certain port qui était utilisé par le serveur (22, 6767) et ça le faisait planter.

Finalement celui-ci à fonctionné :
```
for i in {6768..9999}; do
    nc localhost "$i"
    curl localhost
done
```
