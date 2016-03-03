# Limitare velocità di download di `wget`
`wget` è un utility per il download di file dal web.  
Per limitare la velocità di download con la quale vengono scaricate le pagine/file è sufficiente eseguire il seguente comando:
```bash
wget link --limit-rate=500K
```
- `link` è il il percorso web dal quale scaricare il file.
- `--limit-rate` è l'opzione che indica che il paramentro successivo sarà la velocità massima di download del file. Di default il valore è espresso in bytes per secondo. Aggiungendo i vari suffissi, come `K` nell'esempio, è possibile cambiare l'unità di misura.

## Riferimenti
[Stackexchange](http://unix.stackexchange.com/questions/39218/throttle-the-download-speed-of-wget-or-curl-while-downloading)

## Manuale
Il manuale di wget può essere letto: [qui](http://linux.die.net/man/1/wget).