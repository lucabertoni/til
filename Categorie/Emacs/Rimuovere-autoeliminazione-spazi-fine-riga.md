# Rimuovere l'autoeliminazione degli spazi a fine riga
Emacs a volte tende ad eliminare gli spazi a fine riga, e questo può risultare controproducente, soprattutto se si lavora utilizzando il markdown o tecnologie simili che richiedono la presenza di uno o più spazi a fine riga per determinate operazioni.  
Per evitare che ciò avvenga può risultare utile seguire questi due semplici passaggi:
```
M-:
```
`M` sta per `alt`.
`-` è solamente un separatore, non deve essere premuto.
`:` indicano i due punti.

Una volta premuta la combinazione di tasti precedenti, inserire il seguente comando
```
(remove-hook 'before-save-hook 'delete-trailing-whitespace)
```

## Riferimenti
Ulteriori informazioni possono essere trovate qui: [http://stackoverflow.com/questions/14164292/my-emacs-deletes-trailing-white-space-how-can-i-disable-this-behaviour](http://stackoverflow.com/questions/14164292/my-emacs-deletes-trailing-white-space-how-can-i-disable-this-behaviour)