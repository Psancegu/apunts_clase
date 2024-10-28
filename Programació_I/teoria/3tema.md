# TEMA 3 - MÈTODES

- API: Application programming interface.

Els mètodes es defineixen i es criden.

A la definicio'els paràmtetre es diuen paràmetres formals.

A la crida es dien paràmetres actuals.


## 2 Tipus de Mètodes:

- Mêtodes de clase:
```java
static void m1 (int x){
}
```
Exemple: Math.sqrt();


-Mètodes d'objecte:
```java
s1.length();
```
Exemple: ratoli1.move()


## Pas de paràmtetres per valor/copia:
```java
main{
    int a = 3,
    //print(a)
    incr(a); // Paràmtetre actual
    //print(a)
}

static void incr(int x  ){ // Paràmetres Formals
    //print x
    x++;
    //print x
}
```

- A java tot es passa per valor.

Paso por parámtetros poro copia de una refenrcia se modifica el paramétro actual dentro del método.
