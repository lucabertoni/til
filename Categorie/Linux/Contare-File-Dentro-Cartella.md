# Contare i file presenti in una cartella
Per estrarre il numero di file (e directory) presenti in una cartella è necessario eseguire il seguente frammento di codice.
Per la shell `bash`:
```bash
numero_file=$(ls -l | wc -l) ; echo $numero_file - 1 | bc
```

Per la shell `fish`:
```bash
set numero_file (ls -l | wc -l) ; echo $numero_file - 1 | bc
```

La prima porzione di codice assegna il valore alla variabile `numero_file`. La seconda stampa a schermo il numero dei file concatenando la stringa `- 1`. `bc` esegue la sottrazione.  
La sottrazione è necessaria perchè `wc -l` conta i ritorni a capo, ed è necessario escludere il primo (contiene la scritta `totale X,XM`).
L'opzione `-l` di `ls` serve per stampare riga per riga la lista dei file con annesse varie informazioni (peso, proprietario, permessi, ...). L'opzione `-l` di `wc` invece serve per indicare che si vogliono contare i ritorni a capo. `wc` serve per stampare alcuni conteggi o caratteri presenti in un file (anche lo stdin è considerato come file).

## Manuale
Manuale di ls: [man](http://linux.die.net/man/1/ls "Manuale di ls")
Manuale di wc: [man](http://linux.die.net/man/1/wc "Manuale di wc")
Manuale di bc: [man](http://linux.die.net/man/1/bc "Manuale di bc")