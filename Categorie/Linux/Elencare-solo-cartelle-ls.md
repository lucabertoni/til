# Elencare solo le cartelle e non i file con ls
Esistono diversi modi per elencare le cartelle presenti in un percorso. Di seguito ne vengono elencati alcuni.
Essendo che le cartelle terminano con il carattere `/` è possibile eseguire il seguente comando:
```bash
ls -d */
```
`-d` indica di mostrare solo le cartelle che rispettano il pattern `*/`

Per avere una lista dettagliata:
```bash
ls -ld */
```

Un altro metodo è il seguente:
```bash
ls -l | grep "^d"
```
- `grep` esegue una ricerca di un patter in un testo/file.
- `"^d"` è la regex che indica di mostrare tutte le righe di `ls -l` che iniziano con il carattere `d` (indica che il file è una directory) 

# Riferimenti
Per la guida originale seguire il seguente link: [http://stackoverflow.com/questions/14352290/listing-only-directories-using-ls-in-bash-an-examination](http://stackoverflow.com/questions/14352290/listing-only-directories-using-ls-in-bash-an-examination)

# Manuale
Il manuale di ls può essere letto: [qui](http://linux.die.net/man/1/ls "Manuale di ls").  
Il manuale di grep può essere letto: [qui](http://linux.die.net/man/1/grep "Manuale di ls").