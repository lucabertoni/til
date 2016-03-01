# Eliminare file con delle esclusioni usando `rm`
Il tool usato solitamente in ambienti Linux-based per eliminare dei file è `rm`.  
Può capitare a volte che sia necessario eliminare tutti i file presenti in una cartella (questo può essere fatto con il carattere `*`) ma con delle eccezioni.  
Supponiamo di voler eliminare tutti i file presenti nella cartella `/tmp/` tranne il file `file.txt`. Questo può essere fatto con il seguente comando:
```bash
find /tmp/ ! -name 'file.txt' -type f -exec sh -c 'rm {}' \;
```
Qui non viene usato direttamente il comando `rm` con delle sue opzioni, ma viene applicato un "filtro" usando `find`.  
`find`, come si deduce dal nome, viene utilizzato per trovare dei file all'interno di una "gerarchia di cartelle".  
Analizziamo il comando:
- `/tmp/` è il percorso della cartella che vogliamo analizzare (posizione dei file da eliminare).  
- `!` serve per escludere un determinato pattern.  
- `-name` è l'opzione che permette di specificare il pattern di ricerca, in questo caso il nome intero del file (da escludere, essendo che è presente il `!`).  
- `'file.txt'` è il pattern.  
- `-type` indica il tipo di ricerca da effettuare (basata sui file, sulle directory, ecc). Per una definizione maggiore su quali sono i valori che questa opzione può assumere fare riferimento al [manuale](http://linux.die.net/man/1/find "Manuale di find").  
- `f` indica che la ricerca deve limitarsi ai soli file.  
- `-exec` esegue un altro programma, nel nostro caso `sh -c`.
- `sh -c` è necessario per poter eseguire a sua volta il programma `rm -f`. Senza di esso non funziona. L'opzione `-c` specifica al comando `sh` che deve prendere il comando da eseguire da un stringa e non dallo stdin (standard input).  
- `rm -f` richiama il programma `rm` passando l'opzione `-f` che indica di forzare l'eliminazione dei file/directory.  
- `{}` servono per indicare a `find` di passare ogni valore che estrae (la lista dei file trovati, escluso il pattern) al programma `rm`. Esempio: `rm -f file1.txt`, `rm -f file2.txt`.  
- `\;` specifica a `find` che si deve passare la lista estratta come "più parametri" richiamando quindi `rm` più volte. Esempio: `rm -f file1.txt`, `rm -f file2.txt`. Esiste la variante `+` che serve per eseguire il comando una sola volta, ma sul sistema attualmente utilizzato (Debian + fish shell) non funziona (probabilmente perchè viene richiamato `sh -c` al posto di `rm` direttamente).   

Se i file da escludere dall'eliminazione sono molteplici, si può usare il comando nel seguente modo:
```bash
find /tmp/ ! -name 'file1.txt' ! -name 'file2.txt' -type f -exec sh -c 'rm {}' \;
```
`N.B.:` Il comando `find . !\(-name 'file1.txt' -a -name 'file2.txt'\) -type f -exec sh -c 'rm {}' \;` non funziona sull'ambiente utilizzato (Debian + fish shell), per questo motivo è necessario concatenare più `-name` negati (`! -name`).

## Riferimenti
- [Stackexchange](http://unix.stackexchange.com/questions/153862/remove-all-files-directories-except-for-one-file)
- [Cyberciti](http://www.cyberciti.biz/faq/linux-bash-delete-all-files-in-directory-except-few/)

## Manuale
Manuale di find: [clicca qui](http://linux.die.net/man/1/find).  
Manuale di rm: [clicca qui](http://linux.die.net/man/1/rm).  
Manuale di sh: [clicca qui](http://linux.die.net/man/1/sh).  