# Mostrare il peso di uno o più file da riga di comando
Per mostrare il peso di un file da riga di comando in sistemi Linux-based esistono due modi. Il primo:
```bash
ls -lh nome_file
```
- `-l` mostra una lista in formato più dettagliato.
- `h` stampa i valori del peso in un formato leggibile (es: 10M). Equivalente a `--human-readable`.
- `nome_file` è il nome del file da analizzare. Sostiuirlo con il percorso del file o di una cartella.  
Purtroppo con l'utilizzo di ls si ottengono anche informazioni non necessarie (proprietari, data di creazione e modifica, ...). Usando invece `du` con le opzioni descritte qui sotto verranno visualizzati unicamente il file e il suo peso:
```bash
du -bh nome_file
```
- `-b` serve per specificare su che scala mostrare il peso del file (scale size). Equivalente a `--apparent-size --block-size=1`.
- `h` stampa i valori del peso in un formato leggibile (es: 10M). Equivalente a `--human-readable`.
- `nome_file` è il nome del file da analizzare. Sostiuirlo con il percorso del file o di una cartella.

## Manuale
Il manuale di `du` si trova al seguente indirizzo: [http://linux.die.net/man/1/du](http://linux.die.net/man/1/du)