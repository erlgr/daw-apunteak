### SSL aktibatzen
Hasteko, `mod_ssl` aktibatu komando honekin
```
sudo a2enmod ssl
```

eta berrabiarazi apache
```
sudo systemctl reload apache2
```

### TLS ziurtagiria sortzen
Exekutatu komando hau eta bere formularioa
```
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/apache-selfsigned.key -out /etc/ssl/certs/apache-selfsigned.crt
```
### ⚠️ Gogoratu Common Name barruan zure domeinua sartzea!

### Konfigurazioa aldatzen
Orain goazen Apache-ko konfigurazio fitxategietara berriz
```
sudo vim /etc/apache2/sites-available/nireweb1.conf
```

eta aldaketa hauek egin (**ez guztiak!** aldatu portua 443ra, gehitu SSLEngine, etab.)
### ⚠️ Ez ahaztu! Common name == ServerName
```
<VirtualHost *:443>
   ServerName nireweb1.com
   DocumentRoot /var/www/nireweb1

   SSLEngine on
   SSLCertificateFile /etc/ssl/certs/apache-selfsigned.crt
   SSLCertificateKeyFile /etc/ssl/private/apache-selfsigned.key
</VirtualHost>
```

(nota pertsonalak, hau ondo iteko - nik nireweb1-en kopia bat in det ta nireweb2 bihurtu det, CONFIG ETA /VAR/WWW, gero diferentziau in ditut web orrien diseinuak, eta nireweb1ei SSL jarri diot, nireweb2-ri ez). GOGORAU
- nireweb1.conf KOPIA IN nireweb2.conf
- nireweb2 EDITAU nireweb2 jartzeko danian
- nireweb1 EDITAU ssl gehitzeko
- /var/www/ ra jun ta IN KOPIA BAT
- IN DISEÑO DIFERENTIAK (iual jarri baten "nireweb1 sslkin" ta bestian "nireweb2 insegurua")
- windowsen HOSTS FITXATEGIYA ALDAU!!!!!! [[Hosts fitxategia Windowsen]]
- ta ez ahaztu ping batekin konprobatzia ta flushdns itia
- A2ENSITE IN!!!!!!!!!! TA RELOAD!!!!!!


### HTTP/HTTPS redirect
Kasu honetan:
- NireWeb1 HTTPSn dago
- NireWeb2 HTTPn dago
- http(://)nireweb1.com -> https(://)nireweb1.com
- https(://)nireweb2.com -> http(://)nireweb2.com

Horretarako aldaketa hauek egingo ditugu:

#### Nireweb1.conf (http -> https)
Gehitu hau hasieran
```
<VirtualHost *:80>
	ServerName nireweb1.com
	Redirect / https://nireweb1.com/
</VirtualHost>
```

#### Nireweb2.conf (https -> http)
Gehitu hau hasieran
```
<VirtualHost *:443>
	ServerName nireweb2.com
	Redirect / http://nireweb2.com/
</VirtualHost>
```

Aldaketak egin ondoren, berrabiarazi apache
```
sudo systemctl reload apache2
```
