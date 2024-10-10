J'ai fait ce petit site web, regarde le code ! T'aimes bien ?

Essaie de récupérer le contenu de mon fichier flag.txt si t'es un chad 😼
http://intro.ctfrei.fr:6004 

--------------

```
from flask import Flask, request, render_template_string

app = Flask(__name__)

@app.route('/')
def index():
    name = request.args.get('name', 'meow')
    template = f"<h1>cc {name}</h1>"
    return render_template_string(template)

if __name__ == "__main__":
    app.run(debug=True)
```

-------------

On voit que le get de l'utilisateur n'est pas dutout filter par le code. En plus de nous donner une xss classique, comme le programme utilise Flask on a une Server Side Template Injection (SSTI).
On peu s'en assurer avec le classique 7*7 http://intro.ctfrei.fr:6004/?name={{7*7}} qui est interprété par le site:

```
cc 49
```
