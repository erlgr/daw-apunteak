### Egiaztatu web-era konektatu ahal zarela
http://192.168.73.123
edo
http://localhost/

### Apacheko direktorioak

Web orrien fitxategiak
```
/var/www/html
```

Konfigurazioak (./sites-available edo ./sites-enabled)
```
/etc/apache2
```

### Firewallean allow egiten
Firewallak arazoak eman ditzake, orduan, apache-ri pasatzeko baimena emango diogu.
```
sudo ufw allow 'Apache'
```

### ⚠ ez ikutu sites-enabled
`sites-available`-n egiten dira aldaketak.

[[000-default.conf plantilla]]
[[VirtualHost apachen]]
[[Hosts fitxategia Windowsen]]
[[SSL apachen]]

