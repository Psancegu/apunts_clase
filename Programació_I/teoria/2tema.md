# Tema 2 - SENTÈNCIES SEQÜENCIALS, ALTERNATIVES I ITERATIVES

## 2.3 Sentències Iteratives

### While

```java
Si (Sentències inicials)
while ( condició_booleana ){
    <S (Sentències)>
}
Sf (Sentències finals)
```
S'executa quan una condició boleana es certa.

Exemple d'iterativa Simple:
```java
public class Escriu100Enters {
    public static void main (String[] args) {
        int num;
        num = 1;
        while (num <= 100) {
            System.out.println(" "+num+" ");
            num = num + 1;
        }
    }
}
```

### For

```java
Si (Sentències inicials)
for ( int idx=0; idx < n ; idx++ ){
    <S ( Sentències)>
}
Sf (Sentències finals)
```
La sentència es repteix n vegades.

Exemple:
```java
int num = 2;
for (int i = 1; i <= 10; i++)
    System.out.println(num + " x " + i + " =" + num*i);

```

### Iteratives aniuades

```java
public class TablasMultiplicar {
    public static void main(String[] args) {
        for (int i = 1; i <= 10; i++) {
            System.out.println("Tabla de multiplicar del " + i);
            for (int j = 1; j <= 10; j++)
            System.out.println(i + " x " + j + " =" + i*j);
        }
    }
}
```
Sortida: Les taules de mulitplicar de  l'1 al 10.


### Do while (bucle)
```java
Si (Sentències inicials)
do {
    < S (Sentències) >
} while (condició_booleana)
Sf (Sentències finals)
```

### OBO (Off by one Error)
S'han de comprovar les condicions exactament, que si es un menor esticte o un menor igual.

## Seqüència (Concepte per evitar OBO)

La caracterització d’una seqüència es fa indicant:
 - Identificació de la seqüència: és una descripció que indica quins element formen part de la seqüència.
 - Primer ( ): S0 //Primer element de la seqüència.
 - Següent (Si): Si+1 //Regla per a calcular el següent element.
 - FinalSeq ( Si): (condició_booleà) //Regla o propietat per saber si podem continuar avançant en la seqüència. Identifica el primer element que NO és de la seqüència.

 El final sequüència és un element que no pertany a la seqüència, com podria ser perfectament un -1.

 ▸ Exemple 1: caracterització de la seqüència [1 - 100]:
1. Identificació de la seqüència: enters de l’1 al 100
2. Primer (): 1
3. Següent (x): x+1
4. FinalSeq (x): (x > 100)

Exemple Usuari entre entrades fins que la entrada sigui sortir:

```java
import java.util.Scanner;
public class Sortir {
    public static void main (String [] args) {
    String cmd;
    Scanner sc;
    /*  Identificació de la seqüència: Seqüència de
        Strings/Comandes entrats pel teclat.
        Primer()= sc.nextLine();
        Següent(x)= sc.nextLine();
        FinalSeq(x)= (x.equals("sortir"))
        Esquema: recorregut
*/ 
    sc = new Scanner(System.in);
    System.out.println("Comanda?");
    cmd = sc.nextLine();
    while (!cmd.equals("sortir")) {
        System.out.println("Processant comanda "+cmd);
        System.out.println("Comanda?");
        cmd = sc.nextLine();
        }
    }
}
```

## Esquemes de programació de Seqüències:

- Recorregut: Recorre tots els elements de la cerca.

- Cerca: Recorre la seqüència fins a trobar un determinat element o fins que es complieixi un condició booleana.

L'objectiu és evitar l'ús del break i el continue i formalització l'utilització de bucles for.


Exemple de càlcul de la mitjana dels quadrats dels 100 primers naturals.

```java
public class MitjanaQ {
    public static void main (String[] args) {
    int x; 
    int suma;
    float mitjana;
    suma = 0; // Inicialitzacions
    x = 1; // Primer Element
    while (x <= 100) { // while (!FinalSeq)
        suma = suma + x*x; // Tractament
        x = x + 1; // Seguent Element
    }
    mitjana = suma / 100.0f;
    System.out.println ("La mitjana és " + mitjana);
    }
}
```

Exemple de programa que compta les paraules:

1. Identificació de la seqûència: paraules de la frase.
    Primer() = next(),
    Següent() = next(),
    FinalSeq() = paraula.endsWith(".")
2. Idenitificació de l'esquema: Recorregut,

```java
import java.util.*;
    public class ComptarParaules{
        public static void main (String[] args) {
            int nParaules = 0; String paraula; Scanner teclat = new Scanner(System.in);
            paraula = teclat.next(); // Primer Element
            if (paraula.equals(".")) // Condició seq. buida
                System.out.println("El nombre de paraules és: 0");
            else{
                while (!paraula.endsWith(".")) {// while (!FinalSeq)
                nParaules++; // Tractament
                paraula = teclat.next(); // Seguent Element
                }
                nParaules++; // Finalitzacions: tractament últim element
                System.out.println ("El nombre de paraules és: " + nParaules);
            }
        }
    }       
```

Els recorreguts amb el nombre d'elements conegut s'utilza un for.

## Esquemes de Cerca

Exemple 1 de cerca:

```java
import java.util.Scanner; Esquema 1 de cerca

public class Cerca {
    public static final int CLAU_SECRETA=725;
    public static void main (String[] args) {
        int clau; // clau entrada per l'usuari
        Scanner sc;
        /*
            Identificacio de la sequencia: sequencia d'enters (claus) entrats per teclat,acabada en 0.
            Primer: clau = sc.nextInt();
            Seguent(): clau = sc.nextInt();
            FinalSeq(): clau == 0
            Esquema: Cerca. Condicio: clau == CLAU_SECRETA
        */
        sc = new Scanner(System.in);
        System.out.println("Clau secreta?");    
        clau = sc.nextInt();
        while ( (clau != 0) && (clau!=CLAU_SECRETA)) {
            System.out.println("Clau secreta?");
            clau = sc.nextInt();
        }
        if ( clau!=0 ) {
            System.out.println("Acces obert");
        }
        else {
            System.out.println("No ho has encertat!");
        }
    }
}
```

Exemple 2 de Cerca:
```java
import java.util.Scanner;

public class Cerca2 {
    public static final int CLAU_SECRETA=725;
    public static void main (String[] args) {
        int clau; // clau entrada per l'usuari
        boolean atura; // indica si s'ha encertat la clau
        Scanner sc;
        sc = new Scanner(System.in);
        System.out.println("Clau secreta?");
        clau = sc.nextInt();
        atura = false;
        while ( (clau != 0) && !atura) {
            if ( clau == CLAU_SECRETA ) {
                atura = true;
            } else {
                System.out.println("Clau secreta?");
                clau = sc.nextInt();
            }
        }
        if ( atura ) {
            System.out.println("Acces obert");
        } else {
            System.out.println("No ho has encertat!");
        }
    }
}
```




