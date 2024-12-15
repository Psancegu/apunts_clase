# TEMA 6 FITXERS I REGEX

## 6.2 ÚS D'EXCPETIONS AMB FITXERS

Es diuq eu són excpecions checkejades (**checked**) perquè java ens obliga a indicar les:

- Opció 1: Indicar-ho al mètode (throws IOException)
- Opció 2: Esciure un bloc try catch on capturar i tractar l'excepció.

## 6.4 SORTIDA DE DADES A FITXER

- Per escriure ddades al fitxer obert:
    - Es pot fer ús dels mètodes print o println() o write() de la classe PrintWriter.

- Per a afegir dades al final de fitxer l'obrim amb un paràmetre establer a true.

### Exemple de Sortida de Fitxer (Classe PrintWriter)

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.io.PrintWriter;

public class G_EscripturaDadesFitxerAmbPrintln {
    public static void main(String[] args) {
        File fitxer = new File("notes1.txt");
        PrintWriter salida = null;

        try {
            // Creem el PrintWriter. Si el path no existeix, es llança excepció
            salida = new PrintWriter(fitxer);

            // Escriurem les dades al fitxer. Si ja existeix, el sobreescribim
            salida.print("Maria ");
            salida.println("9.5");
            salida.print("Joan ");
            salida.println("5.5");

            System.out.println("Dades escrites a " + fitxer.getName());
        } catch (FileNotFoundException e) {
            System.out.println("No s'ha pogut escriure: " + e.getMessage());
        } finally {
            if (salida != null) {
                salida.close();
            }
        }
    }
}
```

Altra alternativa:

```java
import java.io.*;

public class AfegirDadesFitxer {
    public static void main(String[] args) throws IOException {
        // Obrim el fitxer en mode "append" (true)
        // Si el fitxer existeix, afegeix dades al final
        // Si no existeix, el crea i escriu les dades
        FileWriter fitxer = new FileWriter("notes1.txt", true);
        PrintWriter salida = new PrintWriter(fitxer);
        float nota;

        // Afegim dades al fitxer "notes1.txt"
        salida.print("Pep ");
        nota = 6.9f;
        salida.println(nota);

        salida.print("Joana ");
        nota = 9.2f;
        salida.println(nota);

        System.out.println("Dades afegides al final del fitxer");

        // Tanquem el flux
        salida.close();
    }
}
```

## 6.5 ENTRADA DE DADES DES DEL FITXER

- Per a llegir dades des del fitxer obert:
    - Es pot fer ús de next(), nextInt().
    - Es pot fer ús dels mètode read() de la classe FileReader.


## Exemple d'entrada amb file reader i mètodes de la classe Scanner.

```java
import java.io.*;

public class AfegirDadesFitxer {
    public static void main(String[] args) throws IOException {
        // Obrim el fitxer en mode "append" (true)
        // Si el fitxer existeix, afegeix dades al final
        // Si no existeix, el crea i escriu les dades
        FileWriter fitxer = new FileWriter("notes1.txt", true);
        PrintWriter salida = new PrintWriter(fitxer);
        float nota;

        // Afegim dades al fitxer "notes1.txt"
        salida.print("Pep ");
        nota = 6.9f;
        salida.println(nota);

        salida.print("Joana ");
        nota = 9.2f;
        salida.println(nota);

        System.out.println("Dades afegides al final del fitxer");

        // Tanquem el flux
        salida.close();
    }
}
```

## Exemple d'entrada (read() de la Classe FileReader)

```java
import java.io.*;

public class LecturaDadesFitxerSenseScanner {
    public static void main(String[] args) throws IOException {
        // Si el fitxer no existeix, es produeix l'excepció FileNotFoundException
        FileReader fitxer = new FileReader("notes.txt");

        int dato;

        // read() llegeix un caràcter i retorna el seu codi int, -1 si és fi de fitxer
        // També es podrien llegir un conjunt de caràcters (veure informació a l'API)
        dato = fitxer.read();

        while (dato != -1) {
            // Convertim el codi int a caràcter i el mostrem per pantalla
            System.out.print((char) dato);

            // Llegim el següent caràcter
            dato = fitxer.read();
        }

        // Tanquem el fitxer
        fitxer.close();
    }
}
```

