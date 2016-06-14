### Creare disco condiviso su più VMs in VMware ###

Per creare un disco condiviso su “VMware ESXi Server”, ovvero un disco che sia accessibile contemporaneamente a due o più macchine virtuali contemporaneamente, occorre seguire un paio di punti.  

Innanzitutto consiglio prima di creare o avere già le macchine virtuali e solo in un secondo tempo aggiungere il disco condiviso onde rischiare di formattare tale disco in fase di installazione.  

Da una macchina virtuale ( spenta possibilmente ) andiamo a editarne la configurazione e aggiungiamo un hard disk facendo attenzione di impostarlo come “Persitent” e facendogli usare un controller diverso ( se il disco principale è ad esempio su SCSI 0:0 questo lo mettiamo su SCSI 1:0 ) operazione che andrà ad installare un controller aggiuntivo.  

Il controller appena aggiunto andiamo a vederne le proprietà e andiamo a controllare ed eventualmente a dirgli che è di tipo “Virtual” ovvero che permette la condivisione a macchine virtuali sullo stesso server.  

Ora a seconda della dimensione del disco il server impiegherà più o meno tempo a creare il disco virtuale.  

aggiunta: tale procedimento non serve se si procede a creare il disco a mano tramite la shell usando il comando vmkfstools  

```bash
vmkfstools -c 40G -d eagerzeroedthick /vmfs/volumes/datastore/shared.vmdk
```

Operazione che crea un disco da 40G di tipo thick e ovviamente rende obsoleta la parte di rinomina descritta sotto.  

A questo punto possiamo già usarlo così ma il disco avrà il nome della macchina virtuale che l’ha creato, per rinominarlo visto che il client “VMware vSphere Client” non lo permette attualmente ( almeno la versione che ho io ) occorre entrare in shell sul server e cambiarlo a mano.  

Quindi innanzi tutto occorre togliere i disco appena creato dalla macchina virtuale facendo attenzione a non cancellarlo dal disco e abilitare la gestione via shell ( locale o remota che sia ).  

Dalla console sulla macchina server passare al pannello di configurazione tramite F2 ( “System Customization” ) e selezionare l’opzione “Troubleshooting Options”.  

Le voci interessate sono: 

- “Enable/Disable Local Tech Support”

- “Enable/Disable Remote Tech Support (SSH)”

Entrare via shell tramite l’accesso root solito e spostarsi nel path del datastore  

```bash
cd /vmfs/volumes/datastore
```

A questo spostare il disco virtuale in un posto a parte e rinominarlo  

```bash
mkdir shared

mv vmguest/vmguest_1* shared

mv vmguest_1.vmdk shared.vmdk

mv vmguest_1-flat.vmdk shared-flat.vmdk

```

Ora serve editare il file di configurazione del disco e assegnargli il nuovo nome del file dei dati ( usando vi come editor che ne vim ne nano sono presenti nella versione che ho io )  

```bash
vi shared.vmdk[/bash]
```

Premere il tasto “i” sulla tastiera per entrare in modalità modifica, cercare la riga dove c’è il vecchio nome “vmguest_1-flat.vmdk” e mettere il nuovo “shared-flat.vmdk”  

Per uscire e salvare le modifiche premere in sequenza: “ESC”, “:”, “w”, “q”, “INVIO”  

Invece se avete sbagliato qualcosa per uscire senza salvare le modifiche premere in sequenza: “ESC”, “:”, “q”, “!”, “INVIO”  

Ora basta tornare sul client “VMware vSphere Client” e aggiungere di nuovo il disco alle macchine virtuali interessate, facendo sempre attenzione che sia su un controller a parte e che sia di tipo “Virtual”.  
