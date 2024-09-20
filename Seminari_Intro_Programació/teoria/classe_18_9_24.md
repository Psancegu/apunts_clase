# Conceptes Bàsics
## Debug
- Definició actual, rastrejar error que fan que el programa tingui errors.

### Logs
- Missatges que indiquen que el programa està arribant allà.

### Traces
- Forma part del codi i indica tot el que va passant pel programa.
	- Diferents nivells:
		- **Error**: S'ha arribat a una situació d'error
		- **Warning**: S'ha detectat una situació que pot indicar un erro fora del funcionament desitjat.
		- **Info**: Missatge informatiu
		- **Debug** Missatge que permet fer un seguiment detallat de l'execució.

- Permet filtrar per gravetat.
Exemple:
```java
public Formiga(){
	// Creem l'objecte Logger
	logger = Logger.getLogger(Formiga.class.getName());
	// Assignem un nivell de Log
	logger.serLevel(Level.All);
}
```
```java
// Exemple de Log
logger.Log(Wanring.INfO);

```

## Execució en Modes Diferents
- Existeixen dos modes el mode release i el mode debug.
	- **Release:** Compilació que aplica optimitzacions dirigides a millorar el rendiment i la mida del programa.
				- S'eliminen els comentaris
				- Noms mètodes i variables es reescriuen.
				- Mode destinat a la distribució de l'aplicació.
	- **Debug:** Compilació que guarda l'estructura incial. peremtent posar en correspondència el codi compilat i el codi font.
				- Codi no optimitzat
				- Es manté una base de dades de símbols amb els noms originals
	
## Execució pas a pas
### Punt de parada(Breakpoint): Punt en el codi en el que l'execució s'aturarà.
- Permet examinar què passa en una prt del programa.
- Inspecció de memòria, per exemple les variables i els seus valors .


 ### Habitualment hi ha tres opcions:
 - **Continuar**: Un cop examinat el codi demanem que continuï l'execució.
 - **Executar per sobre(Step)**:Executa la següent seqüència al nivell on estem. (no entrem dins).
 - **Executar  entrant (Step in )**: Executa la següent seqüència, però si és composta, entrem dins,
 
 
# Repositori de Codi



