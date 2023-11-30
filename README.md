# Workshop Pytest

Hello ! Ce workshop a pour but de vous faire decouvrir comment tester vos fonctions en python ! Et plus encore.

Dans ce workshop, je pars du principe que vous connaissez assez le python pour faire des fonctions classiques de lib type piscine C.

## Installation

Tout d'abord, vous devez verifier si vous avez Python3 déjà installer:

```
python3 —version
```

Si ce n'est pas le cas vous pouvez faire cette commande (Sur Fedora):

```
sudo dnf install python3
```

Une fois que c'est fait, vous installer Pytest grace a pip install !

```
pip install -U pytest
```

Et normalement si c'est bien installer, vous pourrez tester avec cette commande pour verifier si l'installation est bon.

```
pytest --version
```

# Exercices
Maintenant que tout est pret, on peut passer au but du workshop...: Faire des tests en python. :D

### Exercice 1: Faire un test basique
Nous avons une fonction en python qui calcule la taille de ma string. Comment la tester ?

Je veux que vous trouver comment comparer le retour de la fonction si pour "Hello World" elle me retourne 9 ou non.

(On attend qu'il soit dans un fichier appeler test_my_lib.py)

La fonction en question:
```py
def my_strlen(string: str) -> int:
    length = 0
    for char in string:
        length += 1
    return length
```

Une fois le test ecrit, ecrivez dans votre terminal:
```
pytest
```
C'est normal si vous avez des erreurs ! :)

Normalement vous avez une erreur comme ceci:

```
============================= test session starts ==============================
platform linux -- Python 3.11.6, pytest-7.2.2, pluggy-1.0.0
rootdir: /home/(votre nom de session)/(path jusqu'a la ou vous etes)/TU-Python-Workshop
collected 1 item

test_my_lib.py F                                                                                                                                                                                 [100%]

=================================== FAILURES ===================================
_________________________________ test_answer _________________________________

    def test_my_lib():
>       (Details de vos erreurs)

test_my_lib.py:9: AssertionError
============================ short test summary info ===========================
FAILED test_my_lib.py::test_answer - AssertionError: assert 11 == 9
=============================== 1 failed in 0.10s ==============================
```

### Exercice 2: Fixer l'erreur de votre test

Reprenez l'exercice 1 et faites en sorte que le test marche pour "Hello World".

Une fois que c'est bon, vous pouvez refaire la commande:
```
pytest
```

### Exercice 3: Un test c'est cool, plusieurs c'est mieux !

Vous avez une fonction tester, c'est bien ! Mais le principe c'est tester tous les cas possible. Pour un strlen c'est compliquer il est vrai mais je vais vous demander de tester plusieurs fonctions dans le meme fichier.

Ajouter et tester les fonctions suivantes ! (Recouvrez tous les cas qu'il pourrait avoir....)

```py
def my_list_append(my_list: list, string: str) -> list:
    my_list.append(string)
    return my_list

def is_pair(number: int) -> bool:
    if number % 2 == 0:
        return True
    else:
        return False
```

### Exercice 4: Tester son exception
Pour cette exercice soit vous savez c'est quoi une exception en python et vous etes un chad, soit c'est sadge mais faudra apprendre c'est quoi ici aussi.... (C'est important pour faire de la belle gestion d'erreur en python !)

Imaginons j'ai fais ce programme:
```py
def my_div(num: int, div: int) -> int:
    return num // div
```

Je veux que vous fassiez un test en python qui est capable de tester et voir catch l'erreur `ZeroDivisionError` (Pro tips, dans vos projets vous ferrez des beaux try except.... Ce test est juste la pour vous faire tester les cas d'erreur qui arriveront)

Je vous laisse chercher par vous meme c'est quoi les exceptions en python !

### Exercice 5: Tester mes classes.... ?
Pour cette exercice, vous aurez deux reactions. Soit vous etes content et vous savez c'est quoi des classes ! Et youpi pour vous. Soit vous savez pas et aucun soucis. Renseignez vous sur la documentation python ou bien faites le workshop [(cliquer ici :D)](https://github.com/Chasfory/Workshop-Python-Ruby) 👀

Bref, imaginons j'ai ma class lib ! (decidement....)
```py
class lib:
    def __init__(self):
        self.my_list = []

    def my_strlen(self, string: str) -> int:
        length = 0
        for u in string:
            length += 1
        return length

    def my_list_append(self, string: str) -> list:
        my_list.append(string)
        return my_list

    def is_pair(self, number: int) -> bool:
        if number % 2 == 0:
            return True
        else:
            return False

    def my_div(self, num: int, div: int) -> int:
        return num // div
```

Tester tous les cas comme les autres exo mais avec la class !

### Exercice 6: Toujours plus propre... !
Vous avez surement remarquer mais.... bah vous avez tout mis dans le meme fichier....

Hors ! On veut avoir un jolie petit dossier `/tests/` ou seront tester toutes mes fonctions/class...

Faites en sorte d'avoir le meme tree (votre pycache aura pas forcement les meme nom de fichier c'est normal):
```
.
├── __pycache__
│   ├── test_my_strlen.cpython-311-pytest-7.2.2.pyc
│   └── test_sample.cpython-311-pytest-7.2.2.pyc
├── src
│   └── my_lib.py
└── tests
    └── test_my_lib.py

4 directories, 4 files
```

Faites en sorte que vos fonctions peuvent toujours etre tester....

### Exercice 7: Toujours plus loin !

Ca avance bien dites-donc ! L'avant derniere etape est de maintenant tester si vos prints sont bien bons.... Ca serait dommage de faire faute de frappe et pas passer la moulinette....

Votre fonction test:
```py
def say_hello(name: str):
    print("Hello", name, "!")
```

On veut tester si on test: `say_hello("Tom")` si elle ressort bien: `Hello Tom !\n`

### Exercice 8: A vous de jouer

C'est super ! Vous avez fait le tour de tous ce qu'on pouvait faire.... (Plus ou moins evidemment)
Vous pouvez toujours developper vos tests en python...

Maintenant, si vous avez fait des projets en maths en python je vous invite a tester des maintenant votre projet par vous meme.

Vous pouvez aussi automatiser la creation de test unitaire avec un json 👀. Je vous laisse chercher par vous meme et demander pendant le workshop c'est quoi....

Bravo a vous pour avoir fini ce workshop, en esperant voir des beaux code python bien tester prochainement. ✨
