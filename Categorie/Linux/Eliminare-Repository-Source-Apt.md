# Eliminare una repository e la sua key da apt
`apt-key` è uno strumento della suite `apt` utilizzato per la gestione delle chiavi usate da `apt` per l'autenticazione dei pacchetti. I pacchetti che sono stati autenticati usando le chiavi sono considerati fidati.  
Quando viene aggiunta una repository viene creato un file all'interno di `/etc/apt/sources.list.d/`.  
Per eliminare una repository è necessario eliminare il file della repository da `/etc/apt/sources.list.d/`.  
Dopo aver eliminato il file si deve cancellare anche la chiave presente nel file `/etc/apt/sources.list`. Per estrarre la chiave usare il seguente comando:  
```bash
apt-key list
```

Per cancellarla:
```bash
apt-key del $id_chiave_repository
```

Dare poi un:
```bash
apt-get update
```

Tutti i comandi devono essere eseguiti come utente `root`.

## Manuale
Il manuale di `apt-key` si trova: [qui](http://manpages.ubuntu.com/manpages/precise/man8/apt-key.8.html "Manuale apt-key")