# Algorismes Numèrics I

## Bases i Nombres

Una base representa la cardinalitat d'un conjunt:

642 és 600 + 40 + 2

Aquesta fòrmula seria:

$ d_n · R^{n-1} + ... + d_2 · R + d_1$

D'aquí surt que:

$ 642 = 6_3·10^2 + 4_2·10¹ + 2_1 * 10⁰  $

Les bases importants en informàtica:
- Decimal
- Binària
- Hexadecimal

## Algorisme Definitiu de Fibonacci

```python
def fib3(n):
    a,b = 0,1
    for i in range(1, n+1):
        a,b = b, a+b
    return a

fib3(10)
55
```

Notació O Gran:

    Constant, O(1), com f(n) = min(n,1), que no depenen de n.
    Logarítmic, O(log(n)).
    Lineals, O(n).
    Super-lineals, O(nlog(n)).
    Quadràtics, O(n^2).
    Cúbics, O(n^3).
    Exponencials, O(c^n) per c>1.
    Factorials, O(n!)

