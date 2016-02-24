# Mostrare gli upgrade disponibili con `apt-get`
`apt` è uno strumento per la gestione dei pacchetti. Solitamente si trova in distribuzioni Linux Debian-based, ma lo si può trovare anche in altre.
Per mostrare gli upgrade disponibili all'installazione eseguire il seguente comando:
```bash
apt-get -u upgrade
```
`-u` equivalente a `--show-upgrade` serve appunto per stampare la lista dei pacchetti con disponibili degli aggiornamenti.

## Riferimenti
Per ulteriori riferimenti: [clicca qui](http://unix.stackexchange.com/questions/19470/list-available-updates-but-do-not-install-them).

## Manuale
Il manuale di `apt-get` può essere trovato: [qui](http://linux.die.net/man/8/apt-get).