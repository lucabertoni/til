# Controllare i settori danneggiati dell'HardDisk
Per controllare i settori danneggiati di un HardDisk da sistemi basati su Linux (Debian, CentOs,..) è possibile eseguire il seguente comando:
```bash
badblocks device
```
- `device` identifica il dispositivo da controllare (potrebbe essere un HardDisk come una chiavetta usb). Su ambienti Linux solitamente è simile a `/dev/hdc1`.

`badblocks` analizzerà l'intera memoria e mostrerà un report con eventuali errori.

## Manuale
Il manuale di `badblocks` può essere letto qui: [http://linux.die.net/man/8/badblocks](http://linux.die.net/man/8/badblocks)