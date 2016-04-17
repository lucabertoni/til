# Aggiungere font al sistema
Per aggiungere un font al sistema (individuabile anche da software di terze parti (es: gimp)) è sufficiente copiare il file (.otf o .ttf) all'interno delle cartelle `/usr/share/fonts/opentype` o `/usr/share/fonts/truetype`:
```bash
cp nome_file_font destinazione
```
- `nome_file_font`, inserire il nome del file (es: miofont.otf).
- `destinazione`, sostituire con `/usr/share/fonts/opentype` o `/usr/share/fonts/truetype`.

Per poter utilizzare il font è necessario eseguire il seguente comando:
```bash
fc-cache -f
```

## Riferimenti
Per leggere la guida originale vai [qui](http://askubuntu.com/questions/18357/how-to-install-otf-fonts).

## Manuale
Il manuale di `fc-cache` può essere letto [qui](http://linux.die.net/man/1/fc-cache).