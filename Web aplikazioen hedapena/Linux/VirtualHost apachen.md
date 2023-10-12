### Web orria sortzen
Hasteko, web orria sortzeko direktoriora sartu
```
cd /var/www
```

eta hor karpeta berri bat sortuko dugu.
```
sudo mkdir nireweb1
```

Apachek hau irakurri ahal izateko, baimenak emango dizkiogu
```
sudo chmod 755 nireweb1
```
↑ Honek apacheri irakurtzeko eta exekutatzeko baimenak emango dizkio.

`nireweb1` karpetan sartu zaitez eta sortu zure fitxategiak. Adibidez:
```
cd nireweb1
sudo touch index.html
```

### Web-a editatzen
Linuxetik editatu nahi badugu
```
sudo vim index.html
```

### Konfigurazioa sortzen
Apache-ren konfigurazio fitxategiak sortzeko edo aldatzeko, direktorio egokira joan behar gara
```
cd /etc/apache2/sites-available
```

eta `000-default.conf`-en kopia bat egingo dugu
```
sudo cp 000-default.conf nireweb1.conf
```

 > 000-default galdu duzu? [[000-default.conf plantilla]]
 
 Aldatu parametro hauek zuk nahi duzunarekin
 ```
 ServerName nireweb1.com
 ServerAlias www.nireweb1.com
 DocumentRoot /var/www/nireweb1
 ```

### Web-a hosteatzen
Hau dena amaitutakoan, default web orria desaktibatuko dugu eta berria aktibatuko dugu
```
sudo a2dissite 000-default.conf
```

```
sudo a2ensite nireweb1.conf
```

eta apache berrabiaraziko dugu
```
sudo systemctl reload apache2
```

### Egiaztatzen funtzionatzen duela
Windows-en egiaztatu nahi? Gogoratu [[Hosts fitxategia Windowsen|hosts fitxategia]] editatzea zure web berrian sartu baino lehen. Orri horrek konponbide batzuk ere ekartzen ditu ez badizu ondo funtzionatzen.

## Funtzionatzen du? [[SSL apachen||Jarraitu SSL-rekin ->]]
