# Tema 1 Introducció i Python

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

````