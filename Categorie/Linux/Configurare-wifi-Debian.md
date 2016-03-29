# Configurare WiFi su Debian
Per configurare un'interfaccia di rete che si appoggia su un WiFi è necessario aggiungere al file `/etc/network/interfaces` la seguente porzione di testo:
```
iface wlan0 inet dhcp
    wpa-ssid SSID
    wpa-psk PASSWORD
```
- `wlan0` è il nome dell'interfaccia.
- `SSID` deve essere sostituito con l'SSID della rete alla quale ci si vuole connettere (es: "mia-wifi").
- `PASSWORD` deve essere sostituita con l'eventuale password necessaria per accedere alla rete. 

Dopo aver modificato il file è necessario avviare l'interfaccia di rete con il seguente comando:
```bash
ifup wlan0
```
Sostituire `wlan0` con il nome assegnato all'interfaccia di rete.

Per verificare poi il corretto funzionamento eseguire un ping:
```bash
ping indirizzo
```
- `indirizzo` identifica l'indirizzo da pingare, es: `libero.it` o `google.com`.

# Riferimenti
Per la guida originale seguire il seguente link: [http://www.cyberciti.biz/faq/debian-linux-wpa-wpa2-wireless-wifi-networking/](http://www.cyberciti.biz/faq/debian-linux-wpa-wpa2-wireless-wifi-networking/)

# Manuale
Il manuale di `ifup` può essere letto qui: [manuale](http://linux.die.net/man/8/ifup).
Il manuale di `ping` può essere letto qui: [manuale](http://linux.die.net/man/8/ping).