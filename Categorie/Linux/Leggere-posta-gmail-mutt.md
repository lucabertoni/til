# Gestire email da riga di comando con mutt
Per leggere le email da riga di comando su Linux esiste un tool chiamato `mutt`.  
Per installare `mutt` è sufficiente usare un package manager (in questo caso verrà utilizzato apt):

```bash
apt-get install mutt
```

Dopo aver installato il pacchetto è necessario configurarlo. Seguire i seguenti passaggi:  
  
  * Creare il file `.muttrc` nella home dell'utente (`~/`)
  ```bash
  touch ~/.muttrc
  ```
  
  * Inserire all'interno del file il seguente testo
  ```
  set from = 'email_address@domain.com'
  set realname = 'Your Name'
  set imap_user = ''email_address@domain.com'
  set imap_pass = 'your_password'
  set folder = 'imaps://imap.gmail.com:993'
  set spoolfile = '+INBOX'
  set postponed ='+[Google Mail]/Drafts'
  set trash = '+[Google Mail]/Trash'
  set header_cache =~/.mutt/cache/headers
  set message_cachedir =~/.mutt/cache/bodies
  set certificate_file =~/.mutt/certificates
  set smtp_url = 'smtp://username@smtp.gmail.com:587/'
  set smtp_pass = 'your_password'
  set move = no
  set imap_keepalive = 900
  set tmpdir="directory_file_temporanei"
  set editor ="/usr/bin/emacs %s"
  ```
  Sostituire `directory_file_temporanei` con la directory da usare per i file temporanei (es: /home/luca/tmp/).  
  L'ultima riga è opzionale e serve a specificare quale editor usare per la scrittura e modifica di messaggi.

  * Creare ora le seguenti cartelle
  ```bash
  mkdir ~/.mutt
  mkdir ~/.mutt/cache
  ```
  
  * Eseguire poi il seguente comando per cambiare l'accessibilità del file
  ```bash
  chmod 700 ~/.muttrc 
  ```

## Riferimenti
Per leggere la guida originale clicca sul seguente link: [https://blog.bartbania.com/raspberry_pi/consolify-your-gmail-with-mutt/](https://blog.bartbania.com/raspberry_pi/consolify-your-gmail-with-mutt/)

## Manuale
Il manuale di `mutt` può essere letto: [qui](http://linux.die.net/man/1/mutt "Manuale di mutt")
