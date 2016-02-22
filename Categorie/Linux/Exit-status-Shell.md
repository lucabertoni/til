# Valore di ritorno (exit status) dei programmi
Per stampare il valore di ritorno dei programmi eseguiti dalla shell di Linux è necessario eseguire uno dei comandi proposti di seguito.

Bash:
```bash
echo $?
```
La variabile `$?` contiene l'exit status dell'ultimo programma eseguito nella shell.

Fish-shell:
```
echo $status
```
La variabile `status` contiene l'exit status dell'ultimo programma eseguito nella shell.