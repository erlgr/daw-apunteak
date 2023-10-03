### ⚠ Gida hau debian-en oinarrituta dago, interfaze grafiko gabe

### kredentzialak
`erlantz:admin`
`root:Admin123`

### apt pakete batzuk (root)

```
apt install nala
```

```
nala install vim sudo
```

### sare konfigurazioa (root)
```
vim /etc/network/interfaces
```

```
auto lo
iface lo inet loopback

auto-hotplug enp0s3
iface enp0s3 inet static
    address 192.168.73.123
    netmask 255.255.255.0 
    gateway 192.168.73.254
```

### aplikatzeko, berrabiarazi networking
```
systemctl restart networking
```
edo
```
reboot
```

### erabiltzailea sudo taldean sartu (root)
```
usermod -aG sudo erlantz
```

### Hasi saioa zure erabiltzaile normalarekin eta egiaztatu sudo duzula
### sartu windowsetik
```
ssh erlantz@192.168.73.123
```

### instalatu apache
```
sudo nala install apache2
```

### pakete gehiago instalatu (omz nahi baduzu)
```
sudo nala install zsh curl git
```
### instalatu oh-my-zsh
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### (aukerakoa) eman root sarrera ssh-ri
ireki hurrengo fitxategi hau
```
/etc/ssh/sshd_config
```
eta aldatu lerro hau
`#PermitRootLogin without-password`
hona (gogoratu # -a kentzea!)
`PermitRootLogin yes`