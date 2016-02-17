# Scansione porte con Nmap
[Nmap](https://it.wikipedia.org/wiki/Nmap "Nmap Wikipedia") è un tool per la scansione delle porte (port scanner).  
Per eseguire una scansione basilare dei servizi in ascolto sulle porte di un dispositivo è sufifficiente eseguire il seguente comando:  
```bash
nmap -A -T4 indirizzo_ip
```

## Analisi comando
`nmap` invoca il software.  
`-A` abilita la scansione del sistema operativo e della versione in uso sul dispositivo.
`-T4` impedisce al ritardo dinamico per una scansione di andare al di sotto della soglia dei 10 millisecondi per le porte TCP.

## Manuale
E' possibile leggere il manuale di Nmap qui: [man](http://linux.die.net/man/1/nmap "Manuale di nmap").