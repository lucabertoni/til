# Gestire le funzioni per la shell fish
La shell `fish` mette a disposizione la gestione degli alias, ma da come si può leggere nella documentazione ufficiale sono "deprecati" e vengono utilizzati solo per retrocompatibilità. Come sostituti degli alias utilizziamo le funzioni.  
Per creare una funzione eseguire il seguente comando:
```bash
function nome_funzione ; corpo ; end
```
- `function` è l'utility per la gestione delle funzioni.
- `nome_funzione` è il nome da associare alla funzione.
- `corpo` è il corpo, quello che deve eseguire la funzione richiamata.
- `end` identifica che la definizione della funzione è terminata.

Un esempio:
```bash
function ll ; ls -l $argv ; end 
```
- `$argv` è la variabile di sistema che immagazzina gli eventuali parametri passati (in questo caso potrebbe essere il pattern, es: "*.txt").

Per salvare una funzione appena creata usare il seguente comando:
```bash
funcsave nome_funzione
```
- `nome_funzione` è il nome da associare alla funzione.

Per cancellare una funzione si utilizza invece `functions`, in questo modo:
```bash
functions -e nome_funzione
```
- `-e` è l'equivalente di `--erase` e serve per cancellare una funzione
- `nome_funzione` è il nome da associare alla funzione.

Per mostrare la lista delle funzioni:
```bash
functions -a
```

## Manuale
Il manuale per la gestione delle funzioni della shell `fish` può essere letto: [qui](http://fishshell.com/docs/current/commands.html#function) e [qui](http://fishshell.com/docs/current/commands.html#functions).