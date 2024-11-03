## "Saskatoon": counting IPs.
----

Description: There's a web server access log file at /home/admin/access.log. The file consists of one line per HTTP request, with the requester's IP address at the beginning of each line. Find what's the IP address that has the most requests in this file (there's no tie; the IP is unique). Write the solution into a file /home/admin/highestip.txt. For example, if your solution is "1.2.3.4", you can do echo "1.2.3.4" > /home/admin/highestip.txt

Test: The SHA1 checksum of the IP address sha1sum /home/admin/highestip.txt is 6ef426c40652babc0d081d438b9f353709008e93 (just a way to verify the solution without giving it away.)

----

Pour ce genre d'oppération il vaut mieux utiliser un script bash :

```bash                                                                          
res=$(cut -d " " -f 1 access.log | sort -u)
max=0
ipmax=0
for ip in $res
do
        nb=$(cat access.log | grep $ip | wc -l)
        if [ $nb -gt $max ]
        then
          max=$nb
          ipmax=$ip
        fi
done
echo $max $ipmax
````
*-gt est l'équivalent d'un > dans d'autres langages de programmation, ça m'a fait perdre pas mal de temps.*

On obtient un résultat pour une ip ayant effecuté 482 requêtes :
```
admin@ip-172-31-27-155:~$ ./script.sh 
482 66.249.73.135
admin@ip-172-31-27-155:~$ echo "66.249.73.135" > highestip.txt
```

On vérifie le résultat :
```
admin@ip-172-31-27-155:~$ sha1sum highestip.txt 
6ef426c40652babc0d081d438b9f353709008e93  highestip.txt
```

Et c'est validé !
