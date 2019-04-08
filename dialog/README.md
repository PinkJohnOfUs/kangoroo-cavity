# Was ist hier los?

Dialog texte werden auf dem Interplanetary File System [IPFS](https://ipfs.io/) abgelegt. 
Dialoge können über ein beliebiges IPFS Gateway hochgeladen werden. Wir verwenden in diesem Beispiel das [Infura](https://infura.io/) Gateway:

Einen Dialog kannst du folgendermaßen mit [curl](https://curl.haxx.se/docs/manual.html) oder einem beliebigem [REST](https://install.advancedrestclient.com/install) hochladen. 

```
kangoroo-cavity/dialog $ curl -F file=@./quantityland-beschreibung.txt "https://ipfs.infura.io:5001/api/v0/add"
```

Du erhälst Hashwert und Dateiname zurück.
```
{"Name":"quantityland-beschreibung.txt","Hash":"QmRJNGsGu2Pu2P7VG3t1S8gbPMHnFSHiuknGdg7AzGcwps","Size":"866"}
```
Dieser Wert kann verwendet werden, um den Inhalt der Datei auszulesen:

```
curl "https://ipfs.infura.io:5001/api/v0/get?arg=QmRJNGsGu2Pu2P7VG3t1S8gbPMHnFSHiuknGdg7AzGcwps"
```