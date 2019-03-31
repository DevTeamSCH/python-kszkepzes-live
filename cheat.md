Hello world

mindenki feltelepítette otthon a pythont?
python3 --version windows python --version
aki nem majd workshop előtt szünetben

### Változók

nézzük meg milyrn változok vannak pythonban
először is a számok (integer, float, complex)

a = 2 #int
print(a)
b = 3.2 #float
print(b)
d = 2 + 4j #komplex
print(d)

print(a ** 3)
print(b / a)
print(d * 2)

- boolean
x = False
y = True
print(x, y) #Bármenyi paraméter, space elválasztva kiírja nekunk

- string

str = "string" # '' vagy ""
print(str)
str2 = str + 'abc' # konkatenálni
print(str2)
str3 = str * 2 
print(str3)

Vannak összetettebb adattipusaink is:

### List  = lista

- Ez áll legközelebb a C tömbhöz
- Bármilyen típust tartalmazhat (általában egyforma)
- Módosítható(mutable)
- Indexelhető

list = ["a", "b", "c", 1, 2, 3] kapcsoszárójel, vesszővel elválasztva
print(list) # python okos, szinte bármit kiír nekünk, object -> to_string
list[4] = 22 # lehet indexelni 2->22
print(list)
list.append(50) tudonk hozzáfűzni
del list[3] del kitörli a változót mintha nem is inicializáltuk volna, itt a lista egy elemét

print(list[2:5]) intervallumot is tudunk indexelni, mettől (még benne van), meddig (már nincs benne)

print(list[2:]) megadhatjuk csak az egyiket is
print(list[:4])

# Mit ír ki!!

### Kövi adatszerkezet a Tuple

- jelentése: véges lista
- Ugyanaz, mint egy lista
- De nem módosítható(immutable)

tuple = ("a", "b", 3, 4) zárójelben adjuk meg az elemeket
print(tuple) irassuk ki
print(tuple[2]) indexelhető
tuple[2] = 22 hibát fog dobni, nem modosítható
a, b, c, d = tuple pythonban ha felsorolunk annyi változót amenyit a tuple taralmaz akkor kibontja nekunk

print(c) ez mukodi a tobbi adatszerkezetre is

tuple2 = (34, 56, "d")
tuple3 = tuple + tuple2 konkatenálni lehet
print(tuple3)

print(len(tuple3)) len ki tudjuk íratni a lista, tuple, hosszát

### Dictionary - szótár

- Kulcs érték pár
- Kulcs csak string, egyedi érték
- Érték bármilyen típusú lehet
- Kulcsal indexelhető
- Mutable

dict = {"Name": "Zara", "Age": 10} kapcsoszárojel, kulcs érték : elválasztva
print(dict)

dict["Pet"] = "Dog" tudunk hozzáadni elemet, ha indexbe beírjuk a kulcsot és egyenlővé tesszük az értékkel
print(dict["Pet"])

del dict["Name"] törölhetjük az elemet
print( "Name" in dict) mit csinal az in, ha az érték benne van a objectbe akkor true, amugy false

### Set jelentése halmaz

- minden érték egyszer szerepelhet benne
- Nem indexelhető
- Nem biztos, hogy sorban tárolja az elemeket
- Lehet hozzáadni elemeket

```python
set = {1, 3, 1, 5} kapcsoszárojelben, vesszővel elválasztva
print(set)

set[2] hibát fog dobni

print(1 in set) in ugyan ugy megnezhetjuk benne van e egy elem
print(2 in set)

set.add(2) vannak fgv
set.update([6, 4, 1]) adhatunk hozzá több elemet is egyszerre, pl egy listat
print(set)

set2 = {2, 6, 10, 11}
union = set.union(set2) halmaz, vannak alap halmazmuveletek, uunio, metszet, stb
print(union)

## Ciklusok
nanoba --> exit()
nem csak interpreterbe hanem fileba is irhatjuk a programot, igy maradando lesz.
nano while.py


While, FOR mint c++ ban

a while az ugyan olyan min C ben

i = 1
while i < 6: adunk neki egy feltételt és addig megy amig igaz
    print(i) behuzasra figyelni
    i += 1

### For(each) 
eltér a c++-tol
nincs neki megadva egy feltétel
mindig egy iterelhato dolog osszes elemen megy végig, pl list
a = [1, 2, 3]
for x in a: végig megy x az A osszes elemen
    print(x)

Intervallumot bejarni a range segítségével tudunk

ls = list(range(5))  range fgv, egy iterelható elemet ad vissza
print(ls)

for x in range(1, 6, 2):  # for (int i = 1; i < 6; i += 2)
    print(x)
```

# Mit ír ki 2

### Elágazások

-C if, else, while
- if, elsif, else, nincs while

nano if.py

hozzunk letre két változót
b = False 
x = 3
if not b and x <= 6: nincsennek külön logikai operátor jelölések, ki írjuk őket
! -> not
&& -> end
|| -> or
    print("Hello")
elif b or x > 5:
   print("World!")
else:
   print("Hello World!")

futtasuk

---

### Függvények


- Hasonlít a C, C++ fügvényekre
- Nem kell megadni a visszatérési értéket, változók tipusát

(- pass = null operation, mikor végrehalytodik nem torténik semmi
- nem lehet üres fgv megadni)

def kulcsoszóval készítunk fgv
fgv név
paraméterek

def fibonacci(n): olyan fgv ami fisszaadja az n fibonacci szamot 
    if n == 0: orfeltétel
        return 0
    elif n == 1: orfeltétel
        return 1
    else:
        return fibonacci(n - 1) + fibonacci(n - 2) rekurziv hvás


print(fibonacci(10)) hívjuk meg


### Opcionális paraméter

def fibonacci(n=10):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    else:
        return fibonacci(n - 1) + fibonacci(n - 2)


print(fibonacci())


### Névszerinti paraméterátadás

def fibonacci(n=10):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    else:
        return fibonacci(n - 1) + fibonacci(n - 2)


print(fibonacci(n = 8))


### Tetszőlegesen sok paraméter, list

készítsünk egy minimum fgv

def minimum(first, *args): *válozónév egy lista, amibe azok a paraméterek kerülnek amik kimaradtak
    acc = first
    for x in args:
        if x < acc:
            acc = x
    return acc

print(minimum(3, 4, 2, -8, 6)) first 3, args a többi


- miért kell a first paraméter ha args ugyis megkapja az összeset?
- mert a min fgv 0 paraméterrel nem értelmes

---

### Tetszőlegesen sok paraméter, dictionary-szótár

-** válozonév egy szótár, ide pakolja be a név szerint átadott elemek, amik nem szerepelnek a fgv változói közt

def bar(**kwargs): 
    for key, value in kwargs.items():
        print(key, value)


bar(Kutya="vau", Cica="miaaau") változó név kulcs, értéke az érték
 
### Beépített fgv-ek

értelmezőbe:

print(dir(__builtins__)) kiírja az összeset

- print()
- len() Returns the length of an object
- input() Allowing user input
- abs() Returns the absolute value of a number
- diában lesz egy link az összesre
- https://www.w3schools.com/python/python_ref_functions.asp

---

### Osztályok

- Hasonló mint C, C++-ban
- Minden public

class A:
    __b = "fa" igy tudjuk jelolni a private, más ne piszkálja

    def __init__(self): konstruktor
        self.a = 1 inicializalunk egy a, selfen keresztul globalisan elerjuk

    def print(self, str): csináljunk egy print fgv
        for x in range(self.a): irassuk ki annyiszor amennyi az a
            print(str + self.__b)

class B(A): örököl a A-bol, minden fgv, minden parametert
    def __init__(self, a):
        self.a = a

a = A() hozzunk letre egy A
a.print("Alma") Irassuk ki valamit
b = B(5) hozzunk letre egy B
b.print("Körte") irassunk ki valamit

szerntetek mit fog kiirni?

 ( - Többszörös öröklés
  - Operator overloading)

vissza a diasorra