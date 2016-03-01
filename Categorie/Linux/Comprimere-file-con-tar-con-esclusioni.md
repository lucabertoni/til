# Comprimere file e cartelle con `tar` escludendo alcuni file o cartelle
`tar` è un utility per la creazione ed estrazione di archivi.
Per generare un archivio compresso usando `gzip` usare il seguente comando:
```bash
tar -czf nome_archivio.tar.gz files
```
- `-c` indica di creare un nuovo archivio.
- `-z` imposta la compressione usando `gzip`.
- `-f` indica che verrà specificato il nome dell'archivio da generare
- `nome_archivio.tar.gz` è il nome dell'archivio da generare. Solitamente per i file generati con `tar` e compressi con `gzip` si usa l'estensione `.tar.gz`
- `files` è la lista di file e directory da comprimere

Per inserire delle esclusioni (file o cartelle che non devono essere incluse nell'archivio) usare il seguente comando:
```bash
tar -czf nome_archivio.tar.gz files --exclude=file
```
- `--exclude=file` indica il file/cartella da escludere. Per escludere più file è necessario ripetere più volte la direttiva `--exclude`.

## Manuale
Il manuale di tar può essere letto: [qui](http://linux.die.net/man/1/tar "Manuale di tar").