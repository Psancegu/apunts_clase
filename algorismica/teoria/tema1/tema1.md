# Tema 1 Introducció i Python

## Funcions Python

Sintaxi de funciona a Python:
```python
## Crear una funció
def hola():
    print("hola")

## Cridar una funció
hola()

## Amb paràmteres 
def hola(persona):
    print("Hola", persona )

hola("Pol")
> Hola Pol
```

## Un Programa a Python

### Sortides
```python
print(value1, value2, sep=" ", end="\n")
```
### Assignacions
```python
a = eval(input("Entrada: "))
> Entrada: 3+4+5
a
> 12
```
### Assignacions Simultànies
Intercanvi de valors a python:
```python
x = 3
y = 4
x,y = y,x
print(x,y)

> 4 3
```

### Iteracions
Bucle For:
```python
for i in range(10):
    print(i, end=" ")
> 0 1 2 3 4 5 6 7 8 9 

for j in [0,1,2,3]:
    print(j*j)
> 0 
> 1 
> 4 
> 9
```

## Les dades i python
### Tipus de dades i operadors a Python
```python
  type(3)
  > int 

  type(3.14)
  > float 
  
  x = -32
  type(x)
  > int
  
  print(3+4, 3+4.0)
  > 7 7.0
  
  print(10.0/3, 10/3)
  > 3.3333333333335  3.3333333333335
```
Els operadors bàsics són: +, -, *, /, **, %, abs().


### Els Nombres i Python
Python ens dona funciona matemàtiues dins del mòdul math que s'ha d'importar.
```python
  import math
  def main(a,b,c):
      x = (-b+math.sqrt(b**2-4*a*c))/2*a
      print(x)
```
range(start, stop, step)
```python
  list(range(10))
  > [0,1,2,3,4,5,6,7,8,9]
  list(range(0,10,3))
  > [0,3,6,9]
  list(range(0,-4,-1))
  > [0,-1,-2,-3]
```

## Estructures de control (if)
Formen part de l'estructura condicional.
```python
if a==0:
    print("valor neutre")
elif a < 0:
    print("valor negatiu")
elif a == 1:
    print("valor unitat")
else: 
    print("altres valors")
```

## Exemple explicat: El Factorial d'un Nombre:
```python
def factorial(num):   
# definim la funció factorial amb un paràmetre
  factorial = 1
  if num < 0:         
  # condicional
    print("Entra un enter positiu! ")   
    # només s'executa si es compleix la condició
  elif num == 0:            
  # condicional
    print("El factorial de 0 és 1")          
    # només s'executa si es compleix la condició
  else:                  
  # alternativa als condicionals
    for i in range(1,num+1):             
    # 1,2,3...num
        factorial *= i              
        # factorial = factorial * i
    print("El factorial de ", num, "és", factorial)
```

## Cadenes de Caràcters(Strings)
És un seqüència de caràcters que pots emmagatzemar en variables:
```python
a = 'Hola'
b = "Mireia"
print(a,b)
> Hola Mireia

type(a)
> str
```

Strings des del teclat:
```python
nom = input("Quin és el teu nom?")

edat = eval(input("Quin és la teva edat?"))
```

Per treballar amb cadenes:
```python
print(s[0:3], s[6:9], s[:3], s[3:], s[:])
> Hel, Bob, Hel, lo Bob, Hello Bob
```

Exemple d'ús:
```python
def mes():
    mesos = "GenFebMarAbrMaiJunJulAgoSetOctNovDes"
    n = eval(input("Quin mes vols?"))
    pos = (n-1) * 3
    m = mesos[pos:pos+3]
    print("L'abreviatura és: ", m)
```

Funció split:
```python
cadena = "El gos i el gat, menjàven plegats"
llista = cadena.split()
> ['El', 'gos', 'i', 'el', 'gat,', 'menjàven', 'plegats']
```

Mètode .join() i .strip():
```python
llista = ['El', 'gos,', 'i', 'el', 'gat,', 'menjàven', 'plegats.']
cadena=" ".join(llista)  # l'espai farà de separador
print(cadena)
> El gos, i el gat, menjàven plegats.
```

```python
"introducció a Python".strip('nio')
> 'troducció a Pyth‘
" introducció   ".strip()
> 'introducció‘
```

També hi ha les funcions .islower(), .isupper(), .isalpha() i .isnumeric: Verifiquen si la cadena és majúscules, minúscules, tota de lletres o tota de números  respectivament.

També .lower() i .upper(): Converteixen la cadena de majúscules a minúscules i de minúscules a majúscules respectivament.


## Funcions
- Tot ok.

## Col·leccions de dades
```python

list(range(10))
# > [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

a = "ABCD"
a.split()
# > [A, B, C, D]
```

- Les llistes són mutables, és a dir que poden canviar els valors de dins.
- A la vegada són dina`miques perquè poden canviar la mida.
- **Inhomogènies** 

### Funcions aplicades a les llistes

```python

l.append: # afegeix elements al final.
l.sort: # ordena els elements.
l.reverse # inverteix la llista.
l.index(x) # retorna l'índex del primer element igual a x.
l.count(x) # retorna el nombre de vegades que apareix x.
l.remove(x) # elimina la primera ocurrència de x.
l.pop(i) # elimina l'ièssim element de la llista i retorna el seu valor.
x in l # retorna una valor booleà en funció de si x és a la llista o no.

```

Exemple:
```python
def getNumbers():
    nums = []
    xStr = eval(input("Entra un nombre (<Enter> per acabar): "))
    while xStr != "":
        x = eval(xStr) 
        nums.append(x)
        xStr = eval(input("Entra un nombre (<Enter> per acabar): "))
    return nums
def m(nums):
    suma = 0.0
    for num in nums:
        suma += num
    return suma/len(nums)
def stdDev(nums, mean):
    import math
    sumDev = 0.0
    for num in nums:
        dev = mean - num
        sumDev += dev * dev
    return math.sqrt(sumDev/len(nums)-1)
data = getNumbers()
print("Mitja: ", mean(data), " | Desviació: ", stdDev(data, mean(data)))

```

## Matrius a Python

```python
m = [[1,2,3],[4,5,6],[7,8,9]]

print(m[0][0])

```

## Diccionari
Característiques dels Diccionaris a python:
```python
passwd = {'bill':'clinton', 'barack':'obama'}

passwd['bill']
> clinton

passwd['bill'] = 'gates'
```

Accedir als diferents tipus dades dins del diccionari:
```python
p = {'a':'A', 'b':'B', 'c':'C', 'd':'D'}
for i in p.keys():
    print(i,end=',')
> a,b,c,d
for i in p.values():
    print(i,end=',')
> A,B,C,D
for i in p.items():
    print(i,end=',')
> ('a','A'),('b','B'),('c','C'),('d','D')
list(p.values())
> ['A','B','C','D']
'a' in p
> True
```

## Tuples
És semblant a la llista però immutable.
```python
t = ('a','b','c','d')

t = ('a',)
type(t)
> tuple
t = ('a')
type(t)
> str
```

## Referències

Amb strings tot va per referència a python.

```python
a = "banana"
b = "banana"

id(a)
> 135044008
id(b)
> 135044008
```

Amb llistes van amb objectes pero si una variable fa referència a una altra tenim un problema perquè si canviem una canvia l'altra.
Això es pot veure amb l'snippet 1 o 2.

```python
a = [1,2,3]
b = [1,2,3]
print(id(a),id(b))
> 238870816, 245363636
```

```python
a = [1,2,3]
b = a
print(id(a),id(b))
> 238870856, 238870856
```
Per clonar dos llistes, s'ha de fer així:
```python
a = [1,2,3]
b = a[:]
b[0] = 5
print(a,b)
> [1,2,3] [5,2,3]
```

### Omplir un diccionari des d'un fitxer
```python
passwords = {}
f = open('passwords.txt','r')
for line in f.readlines():
    usr, passw = line.split()
    passwords[usr] = passw
f.close()
```

# Funció .join per a una llista de Int
```python
# Llista d'enters
numeros = [1, 2, 3, 4, 5]

# Convertir els enters a cadenes i unir-los amb un separador (per exemple, una coma i un espai)
resultat = ", ".join(map(str, numeros))

# Imprimir el resultat
print(resultat)
> 1, 2, 3, 4, 5
```

# Funció Map
Sintaxi de Map:
```python
map(funció, iterable)
```
1. Funció que s'aplica a l'iterable.
2. Un iterable és qualsevol objecte sobre el qual es pot iterar. Llistes, tuples, strings...

Exemple bàsic de funció que multiplica per dos:
```python
# Definim una llista de números
numeros = [1, 2, 3, 4, 5]

# Definim una funció que s'aplicarà a cada element de la llista
def multiplicar_per_dos(x):
    return x * 2

# Utilitzem map() per aplicar la funció a cada número de la llista
resultat = map(multiplicar_per_dos, numeros)

# Convertim el resultat a una llista per veure'l
print(list(resultat))
> [2, 4, 6, 8, 10]
```

En aquest cas podem utilitzar lambda per no haver de declarar la funció.:
```python
numeros = [1, 2, 3, 4, 5]

# Utilitzem una funció lambda en lloc de definir una funció separada
resultat = map(lambda x: x * 2, numeros)

print(list(resultat))
> [2, 4, 6, 8, 10]
```

Un altre exemple amb lamda pero amb dos valors entrants:
```python
llista1 = [1, 2, 3]
llista2 = [4, 5, 6]

resultat = []

for x, y in zip(llista1, llista2):
    resultat.append(x + y)

print(resultat)

```


consulta_llibre = "https://lectura-unebook-es.sire.ub.edu/viewer/9788491687719/105"
