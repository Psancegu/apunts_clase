# TEMA 5 EXCEPCIONS

```java
catch (ArrayIndexOutOfBoundsException e){
    System.out.println("Algo");
    e.getMessage();
}
```

Output:
```txt
algo
ArrayIndexOutOfBoundsException
```

Exemple:
[1,100]
```java
int n = 0;
while( n < 1 || n > 100){
    System.out.println("introdueix un nombre");
    try{
        n = sc.nextInt();
    }
    catch (InputMismatchExcpetion e){
        System.out.println("Solo números porfavor");
    }
}
```
