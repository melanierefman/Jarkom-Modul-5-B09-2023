# Praktikum Jarkom Modul 1 Kelompok B09

Anggota Kelompok B09:
| Nama | NRP |
| ---------------------- | ---------- |
| Melanie Sayyidina Sabrina Refman | 5025211029 |
| I Gusti Agung Ngurah Adhi Sanjaya | 5025211056 |

----

## Topologi
![0-topologi](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/59cdc57f-189b-443e-90f8-dc90c301391d)

### Pembagian Subnet
![1-subnet](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/ed1a27e9-3d84-4918-8776-f5db5331cf46)

### Pembagian IP

#### Tree
![2-tree](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/02da60f7-bfae-431f-a56b-4465174e1bb0)

#### Rute
![3-route](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/3a40bcfc-21a7-40e7-8b5d-5169241f885e)

### Konfigurasi Node

#### Aura
```
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
	address 10.13.14.145
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.13.14.149
	netmask 255.255.255.252

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
#### Heiter
```
auto eth0
iface eth0 inet static
	address 10.13.14.150
	netmask 255.255.255.252
	gateway 10.13.14.149

auto eth1
iface eth1 inet static
	address 10.13.8.1
	netmask 255.255.252.0

auto eth2
iface eth2 inet static
	address 10.13.0.1
	netmask 255.255.248.0

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
#### Frieren
```
auto eth0
iface eth0 inet static
	address 10.13.14.146
	netmask 255.255.255.252
	gateway 10.13.14.145

auto eth1
iface eth1 inet static
	address 10.13.14.137
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.13.14.141
	netmask 255.255.255.252

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
#### Himmel
```
auto eth0
iface eth0 inet static
	address 10.13.14.138
	netmask 255.255.255.252
	gateway 10.13.14.137

auto eth1
iface eth1 inet static
	address 10.13.14.1
	netmask 255.255.255.128

auto eth2
iface eth2 inet static
	address 10.13.12.1
	netmask 255.255.254.0

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
#### Fern
```
auto eth0
iface eth0 inet static
	address 10.13.14.3
	netmask 255.255.255.128
	gateway 10.13.14.1

auto eth1
iface eth1 inet static
	address 10.13.14.133
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.13.14.129
	netmask 255.255.255.252

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
#### Sein (Web Server)
```
auto eth0
iface eth0 inet static
	address 10.13.8.2
	netmask 255.255.255.0
	gateway 10.13.8.1

 up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
#### Stark (Web Server)
```
auto eth0
iface eth0 inet static
	address 10.13.14.142
	netmask 255.255.255.252
	gateway 10.13.14.141
 up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
#### Ritcher (DNS Server)
```
auto eth0
iface eth0 inet static
	address 10.13.14.134
	netmask 255.255.255.252
	gateway 10.13.14.133
up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
#### Revolte (DHCP Server)
```
auto eth0
iface eth0 inet static
	address 10.13.14.130
	netmask 255.255.255.252
	gateway 10.13.14.129
 up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
#### TurkRegion
```
#auto eth0
#iface eth0 inet static
#	address 10.13.0.2
#	netmask 255.255.248.0
#	gateway 10.13.0.1

auto eth0
iface eth0 inet dhcp
gateway 10.13.0.1
up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
#### GrobeForest
```
#auto eth0
#iface eth0 inet static
#	address 10.13.8.3
#	netmask 255.255.255.0
#	gateway 10.13.8.1

auto eth0
iface eth0 inet dhcp
gateway 10.13.8.1
up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
#### LaubHills
```
#auto eth0
#iface eth0 inet static
#	address 10.13.12.2
#	netmask 255.255.254.0
#	gateway 10.13.12.1

auto eth0
iface eth0 inet dhcp
gateway 10.13.12.1
up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
#### SchwerMountain
```
#auto eth0
#iface eth0 inet static
#	address 10.13.14.2
#	netmask 255.255.255.128
#      gateway 10.13.14.1

auto eth0
iface eth0 inet dhcp
 gateway 10.13.14.1
up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

### Routing

#### Aura
```
route add -net 10.12.0.0 netmask 255.255.248.0 gw 10.12.14.150
route add -net 10.12.8.0 netmask 255.255.252.0 gw 10.12.14.150
route add -net 10.12.14.140 netmask 255.255.255.252 gw 10.12.14.146
route add -net 10.12.14.136 netmask 255.255.255.252 gw 10.12.14.146
route add -net 10.12.12.0 netmask 255.255.254.0 gw 10.12.14.146
route add -net 10.12.14.0 netmask 255.255.255.128 gw 10.12.14.146
route add -net 10.12.14.132 netmask 255.255.255.252 gw 10.12.14.146
route add -net 10.12.14.128 netmask 255.255.255.252 gw 10.12.14.146
```
#### Heiter
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.12.14.149
```
#### Frieren
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.12.14.145
route add -net 10.12.12.0 netmask 255.255.254.0 gw 10.12.14.138
route add -net 10.12.14.0 netmask 255.255.255.128 gw 10.12.14.138
route add -net 10.12.14.132 netmask 255.255.255.252 gw 10.12.14.138
route add -net 10.12.14.128 netmask 255.255.255.252 gw 10.12.14.138
```
#### Himmel
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.12.14.137 
route add -net 10.12.14.132 netmask 255.255.255.252 gw 10.12.14.3
route add -net 10.12.14.128 netmask 255.255.255.252 gw 10.12.14.3
```
#### Fern
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.12.14.1
```

### Konfigurasi DHCP (dhcpd.conf)
```
#a1
subnet 10.13.14.128 netmask 255.255.255.252 { 
}

#a2
subnet 10.13.14.132 netmask 255.255.255.252 { 
}

#a5
subnet 10.13.14.136 netmask 255.255.255.252 { 
}

#a6
subnet 10.13.14.140 netmask 255.255.255.252 { 
}

#a7
subnet 10.13.14.144 netmask 255.255.255.252 { 
}

#a8
subnet 10.13.14.148 netmask 255.255.255.252 { 
}

#schewermountain a3
NID yang ada rangenya
subnet 10.13.14.0 netmask 255.255.255.128 { 
    range 10.13.14.4 10.13.14.126; bukan broadcast, router, dan nid
    option routers 10.13.14.1;
    option broadcast-address 10.13.14.127;
    option domain-name-servers 10.13.14.134;
    default-lease-time 180;
    max-lease-time 5760;
}

#laubhills a4
subnet 10.13.12.0 netmask 255.255.254.0 { 
    range 10.13.12.4 10.13.13.254;
    option routers 10.13.12.1;
    option broadcast-address 10.13.13.255;
    option domain-name-servers 10.13.14.134;
    default-lease-time 180;
    max-lease-time 5760;
}

#turkregion a9
subnet 10.13.0.0 netmask 255.255.248.0 { 
    range 10.13.0.2 10.13.7.254;
    option routers 10.13.0.1;
    option broadcast-address 10.13.7.255;
    option domain-name-servers 10.13.14.134;
    default-lease-time 180;
    max-lease-time 5760;
}

#grobeforest a10
subnet 10.13.8.0 netmask 255.255.252.0 { 
    range 10.13.8.3 10.13.11.254;
    option routers 10.13.8.1;
    option broadcast-address 10.13.11.255;
    option domain-name-servers 10.13.14.134;
    default-lease-time 180;
    max-lease-time 5760;
}
```
### Konfigurasi DHCP Relay (isc-dhcp-relay)
```
SERVERS="10.13.14.130"

# On what interfaces should the DHCP relay (dhrelay) serve DHCP requests?
INTERFACES="eth0 eth1 eth2"

# Additional options that are passed to the DHCP relay daemon?
OPTIONS=""
```

## No.1
Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Aura menggunakan iptables, tetapi tidak ingin menggunakan MASQUERADE.

### Penyelesaian
Berikut adalah konfigurasi iptables pada Aura yang mencakup pengaturan agar topologi dapat mengakses keluar tanpa menggunakan MASQUERADE
```
ETH0_IP=$(ip -4 addr show eth0 | grep -oP '(?<=inet\s)\d+(\.\d+){3}')
iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source $ETH0_IP
```

#### Penjelasan
- `ETH0_IP=$(ip -4 addr show eth0 | grep -oP '(?<=inet\s)\d+(\.\d+){3}')`: Perintah ini mengambil alamat IP dari antarmuka `eth0` dan menyimpannya dalam variabel `$ETH0_IP`.
- `iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source $ETH0_IP`: Perintah ini menambahkan aturan ke tabel NAT untuk melakukan SNAT (Source NAT) pada koneksi keluar melalui antarmuka `eth0`. Ini memastikan bahwa paket yang keluar memiliki alamat sumber yang sesuai dengan alamat IP antarmuka `eth0`.

#### Pembuktian
Tiap route dapat melakukan ping keluar.
![4-no 1](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/38ce7ea6-7974-48b9-ba8b-0ddc22ec45da)
Gambar diatas terbukti dapat `ping google.com` pada server Sein.

# No.2
Kalian diminta untuk melakukan drop semua TCP dan UDP kecuali port 8080 pada TCP.

### Penyelesaian
Berikut adalah syntax pada GrobeForest(client) untuk melakukan drop semua TCP dan UDP kecuali port 8080 pada TCP
```
# Izinkan koneksi ke port 8080
iptables -A INPUT -p tcp --dport 8080 -j ACCEPT
iptables -A INPUT -p tcp ! --dport 8080 -j DROP

# Tolak semua koneksi yang tidak diizinkan
iptables -A INPUT -p udp -j DROP
```

### Pembuktian
- Testing port 8080 pada TCP (berhasil)
(gambar)
- Testing kecuali port 8080 pada TCP (tidak berhasil)
(gambar)
- Testing pada UDP (tidak berhasil)
(gambar)


