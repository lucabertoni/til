# Estrarre la dimensione di un file da scaricare con `wget` prima di scaricarlo
`wget` è un utility per il download di file dal web.  
Per estrarre la dimensione di un file da scaricare, prima di scaricarlo, usare il seguente comando:
```bash
wget --spider link
```
- `--spider` invocando questa funzione `wget` si comporta come un web-spider, il che significa che non scaricherà il file ma controllerà che sono presenti restituendo determinate informazioni, tra le quali è presente la dimensione del file stesso.
- `link` è il link al file/pagina da scaricare.

## Riferimenti
Per la spiegazione originale clicca sul seguente link: (http://stackoverflow.com/questions/6986085/get-file-size-of-a-file-to-wget-before-wget-ing-it)[http://stackoverflow.com/questions/6986085/get-file-size-of-a-file-to-wget-before-wget-ing-it]

## Manuale
Il manuale di wget può essere letto: [qui](http://linux.die.net/man/1/wget).