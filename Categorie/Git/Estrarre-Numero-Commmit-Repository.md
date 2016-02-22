# Estrarre il numero di commit di una repository
`git` offre tra le sue innumerevoli funzionalità anche quella per la stampa dei commit appartenenti ad un branch. L'utility che svolge questo lavoro è `git rev-list`, che come da manuale stampa i commit in un ordine cronologico inverso: dal più recente al meno recente.  
Per visualizzare i commit di un branch, usare il seguente comando:  
```bash
git rev-list nome_del_branch
```
_Sostituire ```nome_del_branch``` con il branch che si vuole analizzare, es: `master`_

Per estrarre il totale dei commit relativi ad un branch è sufficiente aggiungere l'opzione `--count`:
```bash
git rev-list --count nome_del_branch
```
_Sostituire ```nome_del_branch``` con il branch che si vuole analizzare, es: `master`_

Per elencare il count dei commit di tutti i branch:
```bash
git rev-list --count --all
```

## Riferimenti
Per eventuali riferimenti: [http://stackoverflow.com/questions/677436/how-to-get-the-git-commit-count](http://stackoverflow.com/questions/677436/how-to-get-the-git-commit-count "Stackoverflow")

## Manuale
Il manuale di `git rev-list` può essere letto: [qui](https://www.kernel.org/pub/software/scm/git/docs/git-rev-list.html "Manuale git rev-list").