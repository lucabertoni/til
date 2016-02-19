# Significato dei numeri di `man`
`man` è un'interfaccia per leggere i manuali di riferimento presenti nel sistema o generati altrove.
Capita spesso di trovare alla fine la dicitura `see also getopt(3)`.
Il numero racchiuso tra le parentesi assume un valore diverso sulla base di cosa il manuale sta ad indicare (sezione di cui fa parte il manuale). Qui la lista:
```
1 -> Comandi utente
2 -> Chiamate di sistema (syscall)
3 -> Funzioni di librerie C
4 -> Devices e file speciali
5 -> Formati di file e convenzioni
6 -> Giochi
7 -> Miscellanea
8 -> Demoni e tool per l'amministrazione del sistema
```

Essendo che una risorsa può esistere in più sezioni, qui di seguito sono elencati alcuni comandi per un utilizzo più approfondito.
Accedere ad una sezione N di una risorsa:
```bash
Sintassi:
	man N nome_risorsa
	
Esempio:
	man 1 printf
```

Mostrare in successione tutti i manuali collegati ad una risorsa:
```bash
Sintassi:
	man -a nome_risorsa

Esempio:
	man -a printf
```

Elencare tutti i manuali associati ad una risorsa:
```bash
Sintassi:
	man -k 'regexp'

Esempio:
	man -k '^printf'
```
`N.B.: Nell'esempio precedente è necessario usare ^ per evitare ricerche di *printf (sprintf, vsprintf, ...)`.  

Spiegazione trovata: [qui](http://unix.stackexchange.com/questions/3586/what-do-the-numbers-in-a-man-page-mean "Spiegazione stackexchange").

## Manuale
Il manuale per `man` è reperibile al seguente indirizzo: [http://linux.die.net/man/1/man](http://linux.die.net/man/1/man "Manuale di man").