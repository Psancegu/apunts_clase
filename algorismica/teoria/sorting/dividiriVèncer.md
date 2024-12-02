# ALGORISMES DE DIVIDIR I VÈNCER

## Exemple de Suma Dividida en 2 cada cop

```python
def sum2(a):
    if len(a) == 2:
        return a[0]+a[1]
    return sum2(a[0:int(len(a)/2)]) + sum2(a[int(len(a)/2):len(a)])
```

## TEOREMA MASTER

El teorema master diu la complexitat dels algorismes subdividits.

Si tenim un problema de mida n