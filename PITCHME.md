# Python3 alapok  

```python
import this

```

Note:

- Ki ismeri a Pythont?
- Ki tudja mit csinál a kód?
- Nézzük meg mit is csinál.
---

### The Zen of Python, by Tim Peters

<div class="half left">
  <ol>
  @size[24px](<li><b>Beautiful is better than ugly.</b></li>)
  @size[24px](<li>Explicit is better than implicit.</li>)
  @size[24px](<li><b>Simple is better than complex.</b></li>)
  @size[24px](<li><b>Complex is better than complicated.</b></li>)
  @size[24px](<li>Flat is better than nested.</li>)
  @size[24px](<li>Sparse is better than dense.</li>)
  @size[24px](<li><b>Readability counts.</b></li>)
  @size[24px](<li>Special cases aren't special enough to break the rules.</li>)
  @size[24px](<li>Although practicality beats purity.</li>)
  @size[24px](<li>Errors should never pass silently.</li>)
  @size[24px](<li>Unless explicitly silenced.</li>)
  @size[24px](<li>In the face of ambiguity, refuse the temptation to guess.</li>)
  </ol>
</div>

<div class="half right">
  <ol start="13">
  @size[24px](<li>There should be one-- and preferably only one --obvious way to do it.</li>)
  @size[24px](<li>Although that way may not be obvious at first unless you're Dutch.</li>)
  @size[24px](<li>Now is better than never.</li>)
  @size[24px](<li>Although never is often better than <i>right</i> now.</li>)
  @size[24px](<li><b>If the implementation is hard to explain, it's a bad idea.</b></li>)
  @size[24px](<li><b>If the implementation is easy to explain, it may be a good idea.</b></li>)
  @size[24px](<li>Namespaces are one honking great idea -- let's do more of those!</li>)
  </ol>
</div>

Note:

- Kiírja a Zen of Pythont
- Kiemeltem párat nektek, amit fontosnak tartok
- De mi is ez?
- Python tervezési filozófiája, igy irjuk a python kódunkat

---

### Története

- Guido van Rossum
- 1991 Python 1
- Magas szintű programozási nyelv

Note:

- 89 karácsonya előtt
- 1 hét szünete -> Ír egy programnyelvet, amit egyszerű használni
- Kedven sorozatárol a Monty Python
- 1991 első verzió
- Magas szintű jellemzői:
  - könnyen olvasható, tanulható, gyors fejlesztés
  - lassú
- (BDFL (Benevolent dictator for life))

---

### Interpretált

- A kódot egy értelmező dolgozza fel
- Platformfüggetlen
- Sok féle megvalósítás(CPython, PyPy, ...)

Note:

- Python interpretált nyelv
- Az interpreter dolgozz fel és futtatja a kódot
- Mivel nem a rendszer futatja a kódot, hanem az értelmező
- nincs platformhoz kötve, értelmezőnek kell lennie
- Sok féle megvalósítás -> alap: Cpython
- PyPy (C, CLI, JVM), 5x gyorsabb
- Létezik java és dotnet alapú is

---

### Miért szeretjük a pythont?

Note:

- Magasszintű:
  - Könnyen tanulható, gyors fejlesztés
- Interpretált:
  - Bárhol lefut, nem kell lefordítani
- Mindent is lehet benne csinálni
- Vicc : Bármit akarunk a második legjobb választás 

---

![Python is awsome!](https://cdn-images-1.medium.com/max/800/0*_e09A-2xg4x7PG_A.)


Note:

- csomagkezelés, mindenre is van csomag

---

### Tökéletes?!

---

### Tökéletes?!

NEM!

---

### Tökéletes?!

- Viszonylag lassú
- Nagy memóriaigény

Note:

- alacsonyszintű nyelvekhez képest, c, c++
- pl: nem kell memoria teruletet foglalni

---

![C++ vs Python3](https://raw.githubusercontent.com/DevTeamSCH/python-kszkepzes/master/media/c%2B%2B_vs_python.png)

Note:

- Mint láthatjuk sokkal lasabb

Mandelbrot:

- Fraktál 

N-body

- dinamikus rendszer
- fizikai erőkkel szimulálva
- pl Bolygók egymásra hatását

---

### Hello World

Note:

- Kezdjük is el írni az első programunkat
- Mint minden nyelven a Hello Worldot

---

### Szintaxis

```python
"""This is the start of the program """
while 1:
    print("Spam")
    answer = input("Press 'y' for large fries ")
    if answer == "y":
        print('Large fries with spam, mmmm, yummy ')
        continue
    answer = input('Had enough yet? ')
    if answer == "y":
        break
print("Have a ")
print("nice day!")  # Bye bye

```

Note:

- Pythonak eltérő a szintaxisa a C C++ képest
- Nincs pontosvessző a sor végén
- A kód blokkokként indentálva vannak, nincs kapcsoszárójel
  - AMi ugyananyira van behuzva az egy blokk
  - 4 space
- '' vagy ""
- komment sorvége: #, hosszú:  '''alam'''

---

### Mit ír ki?

```python
list = ["SCH", "ujonc", "KSZK", "105", ["Kocka", "u."], 69.69, []]
print(list[-5:-3])

```

---

```python
list = ["SCH", "ujonc", "KSZK", "105", ["Kocka", "u."], 69.69, []]
print(list[-5:-3])

```

Output:

```python
['KSZK', '105']
```

---

### Mit ír ki?

```python
sum = 0
for i in range(12, 2, -2):
    sum += i
print(sum)

```

---

### Mit ír ki?

```python
sum = 0
for i in range(12, 2, -2):
    sum += i
print(list(range(12, 2, -2)))
print(sum)

```

Output

```python
[12, 10, 8, 6, 4]
40
```

---

### Modul

- Python forráskódot tartalmazó fájlok
- Segítségükkel több fájlra tudjuk bontani a kódunkat

fruite.py

```python
from apple import print_apple

print_apple()

```

apple.py

```python
def print_apple():
    print("Apple")
```

Note:

- Előnyei
  - Egyszerűbb, átlátható kód
  - Könnyebben karbantartható, összefüggő programrészek egy helyen
  - Egy modul egy feladat --> újrahasznosítható
  - Namespce-ekre osztja a kódot, pl: két modulban lehet ugyan olyan nevű fgv

---

### Csomag

- Hierarchikus szerkezet modulok tárolására
- Egy mappa ami tartalmaz egy \_\_init\_\_.py-t és modulokat vagy további csomagokat

```python
sound/                          Top-level package
      __init__.py               Initialize the sound package
      formats/                  Subpackage
              __init__.py
              wavread.py
              wavwrite.py
              ...
      effects/                  Subpackage
              __init__.py
              echo.py
              surround.py
              ...
```

---

### Pip

- Csomagkezelő
  - Egy helyen van minden
  - Könnyen használható

```bash
pip3 install <package>
```

Note:

- könnyen használható
  - C++ ban jóval nehezebb lib import

---

### Virtualenv

- Saját környezet minden projekthez
- Ide kerülnek a projekt csomagjai

Note:

- Dependency, egy csomag több verzió

---

- Windows:

```cmd
python -m venv venv
```

```cmd
venv\Scripts\activate.bat
```

---

- Linux:

```bash
python3 -m venv venv
```

```bash
source venv/bin/activate
```

---

### Flake8

- Linter
- pep8(Style Guide)
- Segít jobb kódot írni:
  - Syntax error
  - Typo
  - Rossz formázás

```cmd
pip3 install flake8
```

```cmd
python3 -m flake8 <filename>
```

Note:

- Style Guide
  - átlátható
  - egységes --> kevesebb merge conflict
-PEP (Python Enháncment Propózolsz) index, Bővítési javaslatok

---

### Black

- Atomatikusan formázza a kódot

```cmd
pip3 install black
```

```cmd
python3 -m black <filename>
```

Note:

- flake8 megfelel

---

### Csomagok

- Webfejlesztés:
  - Django
  - Flask
  - Requests

Note:

- Hasznos csomagok, témakörönként

---

- IT Security:
  - Scapy
  - Nmap

---

- AI:
  - TensorFlow
  - Keras

---

- Data Science:
  - Pandas
  - StatsModels
  - NumPy

Note:

- Miért ha a python lassú, miért nem c++?
- Pythont prototipus készítésre használjuk, élesben(producton) C++

---

- GUI:
  - PyQt
  - Tkinter
  - Flexx

---

- Data visualization
  - matplotlib
  - Plotly
  - geoplotlib
Note:

---

### Workshop

---

### HF

---

### Változók

- number (integer, floating point, complex)
- boolean
- string
- list, tuple, dictionary, ...

Note:

- Mint láthatjátok vannak számok, boolok, stringek
- egyébb adattípusok: list, tuple

---

```python
a = 2
b = 3.2
d = 2 + 4j

print(a ** 3)
print(b / 2)
print(d * 2)
```

Output

```python
8
1.6
(4+8j)
```

Note:

- d komplex

---

```python
x = False
str = "string"
str2 = str * 2
str3 = str2 + 'abc'

print(x)
print(str)
print(str2)
print(str3)
```

output

```python
False
string
stringstring
stringstringabc
```

Note:

-Konkatenálni

---

### List

```python
list = ["a", "b", "c", 1, 2, 3]
```

- Bármilyen típust tartalmazhat (általában egyforma)
- Módosítható(mutable)
- Indexelhető

Note:

- Ez áll legközelebb a C tömbhöz

---

```python
list = ["a", "b", "c", 1, 2, 3]
print(list)
list[4] = 22
list.append(50)
del list[3]
print(list[2:5])
print(list[2:])
print(list[:4])

```

Output:

```python
['a', 'b', 'c', 1, 2, 3]
['c', 22, 3]
['c', 22, 3, 50]
['a', 'b', 'c', 22]
```

Note:
- Hozzunk ltre egy listát
- print bármit megeszik
- indexelhető, 2 -> 22
- hozzáfuzhetünk a lista végére
- del törli a vátozót, minhta nem inicializátuk volna
- többféleképpen indexelhető, adhatunk meg intervallumot
- mettől
- meddig

---

### Tuple

```python
tuple = ("a", "b", 3, 4)
```

- Ugyanaz, mint egy lista
- De nem módosítható(immutable)

Note:

- jelentése: véges lista
- zárojelben adjuk meg

---

```python
tuple = ("a", "b", 3, 4)
item = tuple[2]
print(tuple)

a, b, c, d = tuple
print(c)

tuple2 = (34, 56, "d")
tuple3 = tuple + tuple2
print(tuple3)

length = len(tuple3)
print(length)

```

Output:

```python
('a', 'b', 3, 4)
3
('a', 'b', 3, 4, 34, 56, 'd')
7
```

Note:

- Létrehozzuk
- indexelunk mint a listánál
- kiíratjuk
- python okos, ha ugyanannyi a változo mint ami a tupleben van akkor átrakja
- lehet konkatenálni
- len kiiírja egy tuple, lista, string..  hosszát

---

### Dictionary

```python
dict = {"Name": "Zara", "Age": 10, "Class": "First"}
```

- Kulcs érték pár
- Kulcs csak string, egyedi érték
- Érték bármilyen típusú lehet
- Kulcsal indexelhető
- Mutable

Note:

- szótár

---

```python
dict = {"Name": "Zara", "Age": 10, "Class": "First"}
print(dict)

dict["Pet"] = "Dog"
print(dict["Pet"])

del dict["Name"]
bool = "Name" in dict
print(bool)

```

Output:

```python
{'Name': 'Zara', 'Age': 10, 'Class': 'First'}

Dog

False
```

---

### Set

```python
set = {1, 3, 5}
```

- Mint a lista, csak minden érték egyszer szerepelhet benne
- Nem indexelhető
- Nem biztos, hogy sorban tárolja az elemeket
- Mutable

Note: halmaz

---

```python
set = {1, 3, 5}
print(set)

print(1 in set)
print(2 in set)

set.add(2)
set.update([6, 4, 1])
print(set)

set2 = {2, 6, 10, 11}
union = set.union(set2)
print(union)

```

Output:

```python
{1, 3, 5}
True
False
{1, 2, 3, 4, 5, 6}
{1, 2, 3, 4, 5, 6, 10, 11}
```

---

## Ciklusok

---

### While

```python
i = 1
while i < 6:
    print(i)
    i += 1

```

Output:

```python
1
2
3
4
5
```

---

### For(each)

```python
a = [1, 2, 3]
for x in a:
    print(x)
ls = list(range(5))
print(ls)
for x in range(1, 6, 2):  # for (int i = 1; i < 6; i += 2)
    print(x)
```

Output:

```python
1
2
3

[0, 1, 2, 3, 4]

1
3
5
```

Note:

- C eltérő
- a for egy iterálható elemen megy végig
- pl: list, string
- range fgv, egy iterelható elemet ad vissza

---

### Elágazások

Note:

-C if, else, while
- if, elsif, else

---

```python
b = False
x = 3
if not b and x <= 6:
    print("Hello")
elif b or x > 5:
   print("World!")
else:
   print("Hello World!")

```

Output:

```python
Hello
```

Note:

- logikai jelek helyett kiírjuk
- ! = not, && = and, || = or

---

### Függvények

```python
def function(): # void function() {}
    pass
```

- Hasonlít a C, C++ fügvényekre
- Nem kell megadni a visszatérési értéket, változók tipusát

Note:

- pass = null operation, mikor végrehalytodik nem torténik semmi
- nem lehet üres fgv megadni

---

```python
def fibonacci(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    else:
        return fibonacci(n - 1) + fibonacci(n - 2)


print(fibonacci(10))
```

Output:

```python
55
```

Note:

- rkurziv
- orfeltetel

---

### Opcionális paraméter

```python
def fibonacci(n=10):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    else:
        return fibonacci(n - 1) + fibonacci(n - 2)


print(fibonacci())

```

Output:

```python
55
```

---

### Névszerinti paraméterátadás

```python
def print_rectangle(w=0, h=0, x=0, y=0):
    print("Rectangle")
    print("- size: {}×{}".format(w, h))
    print("- position: ({};{})".format(x, y))


print_rectangle(20, 30, 40, 50)
print_rectangle(x=10, w=19, h=25)

```

Output:

```python
Rectangle
- size: 20×30
- position: (40;50)
Rectangle
- size: 19×25
- position: (10;0)
```

---

### Tetszőlegesen sok paraméter, list

```python
def minimum(first, *args):
    acc = first
    for x in args:
        if x < acc:
            acc = x
    return acc


print(minimum(3, 4, 2, -8, 6))

```

Output:

```python
-8
```

Note:

- *válozó lista
- ide pakolja be a python a maradék elemeket
- miért van a first paraméter?
- mert a min fgv 0 paraméterrel nem értelmes

---

### Tetszőlegesen sok paraméter, dictionary

```python
def bar(**kwargs):
    for key, value in kwargs.items():
        print(key, value)


bar(Kutya="vau", Cica="miaaau")

```

Output:

```python
Kutya vau
Cica miaaau
```

Note:

 -** válozonév egy dict, ide pakolja be a név szerint átadott elemek, amik nem szerepelnek a fgv változói közt
 -változónév kulcs

---

### Beépített fgv-ek

```python
print(dir(__builtins__))

```

- input() Allowing user input
- len() Returns the length of an object
- abs() Returns the absolute value of a number
- ...
- https://www.w3schools.com/python/python_ref_functions.asp

---

### Osztályok

- Hasonló mint C, C++-ban
  - Többszörös öröklés
  - Operator overloading
- Minden public

---

```python
class A:
    __b = "Foo"

    def __init__(self):
        self.a = 1

    def print(self, str):
        for x in range(self.a):
            print(self.__b, str)

class B(A):
    def __init__(self, a):
        self.a = a

a = A()
a.print("Fighters")
b = B(5)
b.print(u"\u03C1" + " Fej")

```

---

Output:

```python
Foo Fighters
Foo ρ Fej
Foo ρ Fej
Foo ρ Fej
Foo ρ Fej
Foo ρ Fej
```

---

```bash
pip3 install colorama
```

```python
from colorama import init
from colorama import Fore, Back, Style

init()
print(Fore.RED + "some red text")
print(Back.GREEN + "and with a green background")
print(Style.DIM + "and in dim text")
print(Style.RESET_ALL)
print("back to normal now")

```

---

### Dekorátor

```python
def my_decorator(func):
    def wrapper():
       print("Before")
       func()
       print("After")

    return wrapper

@my_decorator
def hello():
    print("Hello")

```

Output:

```python
Before
Hello
After
```

---

--
- Jython bármilyen Java class használhatunk vele, mintha Python modul lenne
- PythonNet

 Jupiter, Saturn, Uranus and Neptune
- https://en.wikipedia.org/wiki/N-body_simulation
