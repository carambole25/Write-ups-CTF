Celui ci était très marrant.
L'application génère une code secret et les but est de le trouver.
Le code change à chaque tentative ce qui empêche toute tentative de brut-force.

Ce qui se passe c'est que la seed utilisé pour générer de l'aléatoire dépend d'un paramêtre que l'utilisateur peu manipuler.

Voici le code de l'appplication pour générer l'aléatoire qui nous est donné :
```
@app.route('/check_password', methods=['POST'])
def check_password():
    data = request.json  
    guess = data.get('guess')  
    random.seed(guess)
    generated_random = random.randint(0, 9999)
    return jsonify({'status': 'success', 'generated_random': generated_random, 'guess': guess})
```

Et le code de vérification :
```
@app.route('/check_guess', methods=['POST'])
def check_guess():
    data = request.get_json()
    guess = data.get('guess')

    n = ["6", "k", "8", "t", "d", "r", "c", "4", "7", "q", "w", "m", "x", "3"]
    random.shuffle(n)
    
    if guess == ''.join(n):
        print("This is your flag: StarHack{Fake_Flag}")
        return jsonify({"message": "Flag obtained", "flag": "StarHack{Fake_Flag}"}), 200
    else:
        return jsonify({"message": "Guess does not match the flag."}), 400

if __name__ == '__main__':
    app.run()
```

On a cas générer un code à partie de la seed 1234 que l'on va pouvoir envoyer par la suite :
```
import random

random.seed('1234')
generated_random = random.randint(0, 9999)


def check_guess():

    n = ["6", "k", "8", "t", "d", "r", "c", "4", "7", "q", "w", "m", "x", "3"]
    random.shuffle(n)
    
    res = ''.join(n)
    print(res)

check_guess()
```
```
$ python3 script.py 
c87r3ktx64qdwm
```

Pour le guess c87r3ktx64qdwm le code serra donc 1234.