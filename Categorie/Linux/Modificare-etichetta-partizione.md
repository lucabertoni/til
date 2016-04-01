# Modificare etichetta di una partizione
Per modificare l'etichetta di una partizione è necessario usare uno dei seguenti tool (variano in base al filesystem):
```
mtools
ntfsprogs
e2fsprogs
jfsutils
reiserfsprogs
xfsprogs
```

### FAT16 FAT32
Per i filesystem FAT16 e FAT32 il tool richiesto è `mlabel`.  
Per modificare l'etichetta di una partizione eseguire il seguente comando:
```bash
mlabel -i <device> ::<label>
```
- `device` è il percorso che identifica la partizione, es: `/dev/sdb1`.
- `label` è l'etichetta da assegnare alla partizione.

### NTFS
Per il filesystem NTFS il tool richiesto è `ntfslabel`.  
Per modificare l'etichetta di una partizione eseguire il seguente comando:
```bash
ntfslabel <device> <label>
```
- `device` è il percorso che identifica la partizione, es: `/dev/sdb1`.
- `label` è l'etichetta da assegnare alla partizione.

### ext2 ext3 ext4
Per i filesystem ext2, ext3 ed ext4  il tool richiesto è `e2label`.  
Per modificare l'etichetta di una partizione eseguire il seguente comando:
```bash
e2label <device> <label>
```
- `device` è il percorso che identifica la partizione, es: `/dev/sdb1`.
- `label` è l'etichetta da assegnare alla partizione.

### JFS
Per il filesystem JFS il tool richiesto è `jfs_tune`.  
Per modificare l'etichetta di una partizione eseguire il seguente comando:
```bash
jfs_tune -L <label> <device>
```
- `device` è il percorso che identifica la partizione, es: `/dev/sdb1`.
- `label` è l'etichetta da assegnare alla partizione.

### ReiserFS(v3)
Per il filesystem FAT16 e FAT32 il tool richiesto è `reiserfstune`.  
Per modificare l'etichetta di una partizione eseguire il seguente comando:
```bash
reiserfstune -l <label> <device>
```
- `device` è il percorso che identifica la partizione, es: `/dev/sdb1`.
- `label` è l'etichetta da assegnare alla partizione.

### XFS
Per il filesystem XFS il tool richiesto è `xfs_admin`.  
Per modificare l'etichetta di una partizione eseguire il seguente comando:
```bash
xfs_admin -L <label> <device>
```
- `device` è il percorso che identifica la partizione, es: `/dev/sdb1`.
- `label` è l'etichetta da assegnare alla partizione.

N.B. I Comandi devono essere eseguiti da un utente con i privilegi di amministratore (utente `root` o comandi eseguiti con `sudo`).  
Il dispositivo non deve essere montato durante l'esecuzione di tali comandi.  
I vari tool possono essere installati usando il package manager a disposizione (apt-get, yum, ...)

## Riferimenti
Per leggere la guida originale, cliccare [qui](https://help.ubuntu.com/community/RenameUSBDrive)

## Manuali
Il manuale di `mlabel` può essere letto al seguente link: [http://linux.die.net/man/1/mlabel](http://linux.die.net/man/1/mlabel).  
Il manuale di `ntfslabel` può essere letto al seguente link: [http://linux.die.net/man/8/ntfslabel](http://linux.die.net/man/8/ntfslabel).  
Il manuale di `e2label` può essere letto al seguente link: [http://linux.die.net/man/8/e2label](http://linux.die.net/man/8/e2label).  
Il manuale di `jfs_tune` può essere letto al seguente link: [http://man.he.net/man8/jfs_tune](http://man.he.net/man8/jfs_tune).  
Il manuale di `ReiserFS` può essere letto al seguente link: [http://man.he.net/man8/reiserfstune](http://man.he.net/man8/reiserfstune).  
Il manuale di `mtools` può essere letto al seguente link: [http://linux.die.net/man/8/xfs_admin](http://linux.die.net/man/8/xfs_admin).