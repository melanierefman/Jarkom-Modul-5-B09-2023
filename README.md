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

## No.2
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

![5-no 2](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/d5e89294-7576-430e-89a1-819b399af793)
![6-no 2](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/6ca41303-8da9-4e19-b171-fc14c338e45c)
- Testing kecuali port 8080 pada TCP (tidak berhasil)

![7-no 2](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/237aee22-f6f5-47f4-a773-057b9731df0f)
![8-no 2](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/6323bad8-2852-4858-b443-dc5b2123980a)
- Testing pada UDP (tidak berhasil)

![10-no 2](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/3b656d56-341a-4cff-818c-8481551c5277)
![9-no 2](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/2e388181-3983-4aaa-b371-a38e2adbc263)

## No.3
Kepala Suku North Area meminta kalian untuk membatasi DHCP dan DNS Server hanya dapat dilakukan ping oleh maksimal 3 device secara bersamaan, selebihnya akan di drop.

### Penyelesaian
Berikut adalah syntax pada DNS dan DHCP Server agar DHCP dan DNS Server hanya dapat dilakukan ping oleh maksimal 3 device secara bersamaan, selebihnya akan di drop
```
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
iptables -A INPUT -p icmp -m connlimit --connlimit-above 3 --connlimit-mask 0 -j DROP
```

#### Penjelasan
- `iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT`: Menambahkan aturan ke chain INPUT untuk mengizinkan koneksi yang terkait dengan koneksi yang sudah ada (`ESTABLISHED`) atau terkait dengan koneksi yang masih berlangsung (`RELATED`).
- `iptables -A INPUT -p icmp -m connlimit --connlimit-above 3 --connlimit-mask 0 -j DROP`: Menambahkan aturan ke chain INPUT untuk membatasi jumlah koneksi ICMP (ping) yang diterima. Aturan ini akan menolak paket ICMP jika jumlah koneksi dari satu alamat IP melebihi 3 secara bersamaan

#### Pembuktian
- Berikut pembuktian pada DHCP Server (Revolte)
![14-no 3](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/f3c3300d-967c-4125-9770-2637f35ce826)
![13-no 3](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/0b791bcc-3227-4b9a-8a39-1a8bd3b0bb5d)
![12-no 3](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/c4ce0c90-813a-4ac6-9f41-889203327f25)
![11-no 3](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/bebc4624-c89b-42c6-8201-50b377bd89ff)
- Berikut pembuktian pada DNS Server (Ritcher)
![16-no 3](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/4614f584-3bda-46f7-8c59-f5e86cccc2aa)
![15-no 3](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/e4ba6671-22fc-4093-962e-4ab842fc6b1d)
![18-no 3](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/9271f6b8-d0e6-44f0-a9ef-f80836b61a75)
![17-no 3](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/1a7bdd93-565a-4817-99e8-bb200758844e)

Dari kumpulan gambar diatas dapat diketahui bahwa hanya 3 node saja yang berhasil ngeping ke DHCP dan DNS Server (Laubhills, GrobeForest, dan TurkRegion), sedangkan node ke 4 yaitu SchewerMountain tidak bisa.

## No.4
Lakukan pembatasan sehingga koneksi SSH pada Web Server hanya dapat dilakukan oleh masyarakat yang berada pada GrobeForest.

### Penyelesaian
Berikut adalah syntax pada WebServer agar koneksi SSH terbatas.
```
iptables -A INPUT -p tcp --dport 22 -m iprange --src-range 10.13.8.3-10.13.11.254 -j ACCEPT
iptables -A INPUT -p tcp --dport 22 -j DROP
```

#### Penjelasan
- `iptables -A INPUT -p tcp --dport 22 -m iprange --src-range 10.13.8.3-10.13.11.254 -j ACCEPT`: Menambahkan aturan ke chain INPUT untuk mengizinkan koneksi TCP dengan tujuan port 22 (SSH) dari rentang alamat IP 10.13.8.3 hingga 10.13.11.254. Aturan ini memungkinkan akses SSH dari alamat IP yang sesuai dengan rentang yang ditentukan.
- `iptables -A INPUT -p tcp --dport 22 -j DROP`: Menambahkan aturan ke chain INPUT untuk menolak koneksi TCP dengan tujuan port 22 (SSH). Aturan ini bersifat umum dan akan menolak akses SSH dari semua alamat IP yang tidak sesuai dengan aturan sebelumnya. Sebaiknya aturan ini ditempatkan setelah aturan yang lebih spesifik.

#### Pembuktian
- Stark
![19-no 4](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/ae863202-9ad0-482d-9f92-d6cb87bd9b1e)
- GrobeForest
![20-no 4](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/21aba1f3-e78c-4f50-a9cf-619a2ffbb28d)

## No.5
Selain itu, akses menuju WebServer hanya diperbolehkan saat jam kerja yaitu Senin-Jumat pada pukul 08.00-16.00.

### Penyelesaian
Berikut adalah syntax pada WebServer agar akses yang menuju WebServer dibatasi saat jam kerja pukul 08.00-16.00.
```
iptables -A INPUT -p tcp --dport 80 -m time --timestart 08:00 --timestop 16:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT
iptables -A INPUT -p tcp --dport 80 -j DROP
```

#### Penjelasan
- `iptables -A INPUT -p tcp --dport 80 -m time --timestart 08:00 --timestop 16:00 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT`: Menambahkan aturan ke chain INPUT untuk mengizinkan koneksi TCP dengan tujuan port 80 pada hari Senin hingga Jumat antara pukul 08:00 dan 16:00. Ini bertujuan untuk membolehkan akses ke layanan web selama jam kerja pada hari kerja.
- `iptables -A INPUT -p tcp --dport 80 -j DROP`: Menambahkan aturan ke chain INPUT untuk menolak semua koneksi TCP dengan tujuan port 80. Ini dilakukan setelah aturan pertama agar memastikan bahwa setelah jam kerja pada hari kerja, akses ke layanan web pada port 80 akan ditolak.

#### Pembuktian
Jam Malam `date 121319002023.00`
- Sein
![21 no 5](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/2f68a375-0a35-4215-bade-ad72bfcdc1dc)
- TurkRegion
![22 no 5](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/60f3a756-0c4f-47d9-a92f-0434e94f242a)

Jam Siang `date 121313002023.00`
- Sein
![23 no 6](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/72e07282-02bf-43f8-babd-a9d0d9cfbedd)
- TurkRegion
![24 no 7](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87106838/8a4b15d3-62ff-4997-9166-ae6bc8c9c52f)


## No.6
Lalu, karena ternyata terdapat beberapa waktu di mana network administrator dari WebServer tidak bisa stand by, sehingga perlu ditambahkan rule bahwa akses pada hari Senin - Kamis pada jam 12.00 - 13.00 dilarang (istirahat maksi cuy) dan akses di hari Jumat pada jam 11.00 - 13.00 juga dilarang (maklum, Jumatan rek).

### Penyelesaian
Berikut adalah penyelesaian agar WebServer tidak bisa akses pada hari Senin - Kamis pada jam 12.00 - 13.00 dan di hari Jumat pada jam 11.00 - 13.00
```
iptables -A INPUT -p tcp --dport 22 -j ACCEPT
iptables -A INPUT -p tcp --dport 80 -m time --timestart 13:01 --timestop 10:59 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT
iptables -A INPUT -p tcp --dport 80 -m time --timestart 12:00 --timestop 13:00 --weekdays Mon,Tue,Wed,Thu -j DROP
iptables -A INPUT -p tcp --dport 80 -m time --timestart 11:00 --timestop 13:00 --weekdays Fri -j DROP
iptables -A INPUT -p tcp --dport 80 -j DROP

```
Codingan diatas akan membuat WebServer tidak bisa mengakses pada jam tersebut.

#### Pembuktian
Untuk pembuktian dapat dilakukan pada salah satu WebServer (TurkRegion) dengan menggunakan 
```
nc -l -p 80
```

Lalu pada sisi client (SEIN) juga lakukan dengan menggunakan
```
nc 10.13.8.2 80
```

## Jumat Jam 11
![image](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87845735/e5077634-bf67-4c02-9866-e4b3dbc4a128)
![image](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87845735/47957689-48aa-4456-8bfa-f67ad434c8db)
dilihat bahwa keduanya tidak bisa saling akses

## Jumat Jam 10
![image](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87845735/bc12f8ce-4759-4d70-a3bd-0ad733096f84)
![image](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87845735/d56fde2b-b1f9-4575-8a34-9c3992633a2e)
dilihat bahwa keduanya bisa saling akses

## No.7
Karena terdapat 2 WebServer, kalian diminta agar setiap client yang mengakses Sein dengan Port 80 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan dan request dari client yang mengakses Stark dengan port 443 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan.

### Penyelesaian
```
iptables -A PREROUTING -t nat -p tcp --dport 80 -d 10.13.8.2 -m statistic --mode nth --every 2 --packet 1 -j DNAT --to-destination 10.13.8.2
iptables -A PREROUTING -t nat -p tcp --dport 80 -d 10.13.8.2 -j DNAT --to-destination 10.13.14.142
iptables -A PREROUTING -t nat -p tcp --dport 443 -d 10.13.14.142 -m statistic --mode nth --every 2 --packet 1 -j DNAT --to-destination 10.13.14.142
iptables -A PREROUTING -t nat -p tcp --dport 443 -d 10.13.14.142 -j DNAT --to-destination 10.13.8.2
```
#### Pembuktian
masing2 stark dan sein di test menggunakan port 80 dan 443.

### Port 80
```
while true; do nc -l -p 80 -c 'echo "sein"'; done
while true; do nc -l -p 80 -c 'echo "stark"'; done
```
### Port 443
```
while true; do nc -l -p 443 -c 'echo "sein"'; done
while true; do nc -l -p 443 -c 'echo "stark"'; done
```

setelah itu testing di turkregion pada port 80 dan 443 : 

```
nc 10.13.8.2 80
```
![image](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87845735/908ab208-845d-4a81-91d9-b231364497cb)

```
nc 10.13.14.142 443
```
![image](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87845735/76640bf2-0dee-4bfb-807d-b02fe2c6d9cd)
dilihat bahwa output yg di hasilkan berhasil berganti ganti

## No.8
Karena berbeda koalisi politik, maka subnet dengan masyarakat yang berada pada Revolte dilarang keras mengakses WebServer hingga masa pencoblosan pemilu kepala suku 2024 berakhir. Masa pemilu (hingga pemungutan dan penghitungan suara selesai) kepala suku bersamaan dengan masa pemilu Presiden dan Wakil Presiden Indonesia 2024.

### Penyelesaian
```
nc -l -p 80
nc 10.13.8.2 80
```

#### Pembuktian
date 121313002023.00 (gabisa)
date 021613002024.00 (bisa)


kita coba di revolte dimana waktu sekarang masih ada pada rentang pemilu yg sudah di define akan tidak bisa menerima input dari sein
![image](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87845735/76f38622-345d-43e8-a019-4ebac71f2ee3)
![image](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87845735/a1610c9f-013c-4e06-8ad7-3693b500cc33)

Lalu kita coba ganti tanggalnya jadi diluar batasan pemilu (16 feb 24)
![image](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87845735/e2016db4-e79f-4e48-b99b-8a34cd943e4e)
![image](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87845735/b847a7b3-ea80-4455-896a-a7db7902f91c)


## No.9
Sadar akan adanya potensial saling serang antar kubu politik, maka WebServer harus dapat secara otomatis memblokir  alamat IP yang melakukan scanning port dalam jumlah banyak (maksimal 20 scan port) di dalam selang waktu 10 menit. 
(clue: test dengan nmap)

#### Penyelesaian
```
iptables -N scan_port

iptables -A INPUT -m recent --name scan_port --update --seconds 600 --hitcount 20 -j DROP
iptables -A FORWARD -m recent --name scan_port --update --seconds 600 --hitcount 20 -j DROP

iptables -A INPUT -m recent --name scan_port --set -j ACCEPT
iptables -A FORWARD -m recent --name scan_port --set -j ACCEPT

```
#### Pembuktian
![image](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87845735/08060d1e-6b46-416a-b603-0d3c3376791c)
![image](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87845735/486f9faa-6bf8-4e82-813f-685e4fccf7eb)

dilihat bahwa ping maximal pada 20 scan port

## No.10
Karena kepala suku ingin tau paket apa saja yang di-drop, maka di setiap node server dan router ditambahkan logging paket yang di-drop dengan standard syslog level. 

### Penyelesaian
```
iptables -A INPUT  -j LOG --log-level debug --log-prefix 'Dropped Packet' -m limit --limit 1/second --limit-burst 10
```

### Pemnbuktian
![image](https://github.com/melanierefman/Jarkom-Modul-5-B09-2023/assets/87845735/92d3556c-f7d6-4171-a9bb-b13f75e31051)

Pada list iptables tersebut terdapat rules untuk membuat log maka dari itu paket telah didrop




