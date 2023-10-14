Hasteko, joan `C:\inetpub\wwwroot\` direktoriora eta sortu zure hainbat web orriak. Horretarako, sortu direktorio bat hauetako bakoitzarentzat eta barruan sortu index.html fitxategi bat.
![[ws-vhost-1.png]]
(issstart horiek defaultak dira, ahal dira ezabatu.)

### IIS panela
IIS panelera sartzeko, joan Administrador del servidor>Herramientas>Administrador de IIS. Hor barruan **Conexiones** panela izango duzu ezkerrean.
Zabaldu zure zerbitzariaren izena. Hor barruan, sitios izeneko karpeta bat ikusiko duzu. Egin eskuineko klik gainean eta Agregar sitio web sakatu.
![[ws-vhost-2.png]]
Eta bete formularioa.
![[ws-vhosts-3.png]]

### Konektatu baino lehen
Ez ahaztu [[Hosts fitxategia Windowsen|hosts fitxategia]] editatzea! gehitu zure erregistro berriak.
```
	127.0.0.1    www.nireweb1.com
	127.0.0.1    www.nireweb2.com
```

Eta orain egiaztatu funtzionatzen duela. Funtzionatzen badu, jarraitu.
### [[SSL IISn|SSL ->]]