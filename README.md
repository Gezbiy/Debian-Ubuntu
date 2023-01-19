# Remote Debian / Ubuntu Server 

## Download DVD Debian 10.10.0
```
https://cdimage.debian.org/cdimage/archive/10.10.0/amd64/iso-dvd/debian-10.10.0-amd64-DVD-1.iso
https://cdimage.debian.org/cdimage/archive/10.10.0/amd64/iso-dvd/debian-10.10.0-amd64-DVD-2.iso
https://cdimage.debian.org/cdimage/archive/10.10.0/amd64/iso-dvd/debian-10.10.0-amd64-DVD-3.iso
```

## Install Open SSH
```
sudo apt-get install openssh-server
```
untuk Debian, harap masukkan DVD 1 terlebih dahulu

## Konfigurasi sshd_config
```
nano /etc/ssh/sshd_config
```

```
# Port and ListenAddress options are not used when sshd is socket-activated,
# which is now the default in Ubuntu.  See sshd_config(5) and
# /usr/share/doc/openssh-server/README.Debian.gz for details.
Port 22
#AddressFamily any
#ListenAddress 0.0.0.0
#ListenAddress ::

#HostKey /etc/ssh/ssh_host_rsa_key
#HostKey /etc/ssh/ssh_host_ecdsa_key
#HostKey /etc/ssh/ssh_host_ed25519_key

# Ciphers and keying
#RekeyLimit default none

# Logging
#SyslogFacility AUTH
#LogLevel INFO

# Authentication:

#LoginGraceTime 2m
#PermitRootLogin prohibit-password
PermitRootLogin yes
#StrictModes yes
#MaxAuthTries 6
#MaxSessions 10

#PubkeyAuthentication yes
```
"hapus pagar port 22 & tambahkan PermitRootLogin yes, dibawah PermitRootLogin prohibition-password" 

## Restart konfigurasi
```
/etc/init.d/ssh restart
```
## periksa IP Address (enp0s3)
```
ifconfig
```

## Login SSH menggunakan Putty / CMD
Link Download Putty : https://www.putty.org
jika menggunakan putty, cukup input ip enp0s3, dan login seperti biasa

Jika menggunakan CMD
cukup ketikkan
```
ssh user@ipaddress
contoh
ssh gezbiy@105.64.xx.xx
```
