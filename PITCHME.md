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
- De mi is ez?
- Python tervezési filozófiája, igy irjuk a python kódunkat
- Kiemeltem párat nektek, amit fontosnak tartok

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

### Mit ír ki?

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

- egy csomagból csak egy lehet fent globálisan
- van két programunk egyik a régi, másik az újabb verzióját használja az edott csomagnak, egyszerre csak ez egyik fog működni

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
  - ha betartjuk 
  - átláthatóbb
  - egységes kód --> pl: kevesebb merge conflict
- PEP (Python Enháncment Propózolsz), Bővítési javaslatok indexe
- nayon sok van

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
