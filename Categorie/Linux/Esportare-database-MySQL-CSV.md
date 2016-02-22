# Esportare database MySQL in formato CSV
Per esportare un database MySQL su sistemi Linux-based è presente l'utility `mysqldump`, che serve per generare backup di database.  
Per esportare un intero database in formato csv (viene generato un file in formato `txt` con un carattere separatore), eseguire questo comando:
```bash
mysqldump -u user -ppassword -t -T/tmp/ nome_database --fields-terminated-by=carattere
```
- `-u` serve per specificare un utente. Sostituire `user` con un utente appropriato per accedere al database.  
- `-p` è necessario per specificare una password per acceder al database. Sostituire `password` con una password appropriata.  
- `-t` viene utilizzato per non generare i file `.sql` (contengono i codice sql per rigenerare e popolare le tabelle). Se sono necessari togliere questa opzione.
- `nome_database` si riferisce al nome del database da esportare.  
- `-T/path` specifica il percorso in cui creare i file contenenti i dati.
- `--fields-terminated-by=carattere` specifica il carattere da usare per la separazione delle colonne delle tabelle. Sostituire `carattere` con il carattere che si vuole usare. In caso di caratteri speciali, usare il `\` per l'escape.

Per esportare una singola tabella invece dell'intero database, eseguire questo comando:
```bash
mysqldump -u user -ppassword -t -T/tmp/ nome_database nome_tabella --fields-terminated-by=carattere
```
- `nome_tabella` si riferisce al nome della tabella da esportare.

## Riferimenti
Per eventuali riferimenti: [http://www.electrictoolbox.com/using-mysqldump-to-save-data-to-csv-files/](http://www.electrictoolbox.com/using-mysqldump-to-save-data-to-csv-files/ "Guida in inglese più approfondita")

## Manuale
Il manuale di `mysqldump` è visitabile [qui](http://linux.die.net/man/1/mysqldump "Manuale mysqldump") (http://linux.die.net/man/1/mysqldump).
