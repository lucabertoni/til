# Cancellare testo in Emacs
In Emacs esistono diversi shortcut per la cancellazione veloce del testo. Di seguito ne vengono elencati alcuni.

Cancellare una regione precedentemente selezionata(il testo viene tagliato, è quindi possibile incollarlo altrove usando C-y):
```
C-wn
``` 
- `C` identifica il tasto `ctrl` sulla tastiera.
- `-` non deve essere premuto, è solo un separatore.

Cancellare la parola successiva al cursore(il testo viene tagliato, è quindi possibile incollarlo altrove usando C-y):
```
M-d
```
- `M` identifica il tasto `alt` sulla tastiera.

Cancellare la parola precedente al cursore(il testo viene tagliato, è quindi possibile incollarlo altrove usando C-y):
```
M-DEL
```

Cancellare dall'inizio della riga fino alla posizione del cursore(il testo viene tagliato, è quindi possibile incollarlo altrove usando C-y):
```
C-x DEL
```

Cancellare dalla posizione del cursore fino alla fine della riga(il testo viene tagliato, è quindi possibile incollarlo altrove usando C-y):
```
M-k
```

# Riferimenti
Le guide originali si trovano: [qui](https://www.gnu.org/software/emacs/manual/html_node/emacs/Other-Kill-Commands.html) e [qui](https://www.gnu.org/software/emacs/manual/html_node/emacs/Erasing.html).