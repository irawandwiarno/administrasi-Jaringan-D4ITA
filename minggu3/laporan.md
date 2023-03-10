# Minggu Ke 3

## Reset Router

Pertama kita melakukan reset router untuk menghapus setingan yang sudah ada agar tidak terjadi crash saat melakukan configurasi dengan cara menulisakan command berikut di console.

```console
/system
reset-configuration no-defaults=yes skip-backup=yes
```

setelah mengetikan command di atas router otomatis akan teriset seperti awal tanpa ada configurasi.

## Configure IP Local

Selanjutnya melakukan konfigurasi pada IP local dengan menggunakan Gui yang di sediakan di opsi _IP > Addresses_ kemudian tekan tombol **"+"** lalu masukan Ip = "192.168.5.0/24" untuk eth2

Atau bisa dengan mengetikan perintah berikut di console.

```console
/ip address
add address=192.168.5.1/24 interface=ether2 network=192.168.5.0
```

## Configure IP Public

Selanjutnya melakukan konfigurasi pada IP Public dengan menggunakan Gui yang di sediakan di opsi _IP > Addresses_ kemudian tekan tombol **"+"** lalu masukan Ip = "10.252.108.15/24" untuk eth1

Atau bisa dengan mengetikan di console command berikut.

```console
/ip address
add address=10.252.108.15/24 interface=ether1 network=10.252.108.0
```

## Configuration Default Route

Disini kita akan menyeting Default Route dengan IP address 10.252.108.212. kita dapat mengetikannya menggunakan console dengan command berikut.

```console
/ip route
add distance=1 gateway=10.252.108.212
```

## Configuration DNS

mengkonfigurasi DNS untuk dapat menghubungi router main dengan mengetikan command berikut.

```console
/ip dns
set servers=202.9.85.3
```

## Internet client Configuration

Untuk agar client bisa mendapatkan IP secara otomatis dari router. caranya dengan mengetikan command berikut pada console.

```console
/ip dhcp-server network
add address=192.168.5.0/24 gateway=192.168.5.1
```

## Kesimpulan

Kesimpulan untuk minggu ini adalah kami mengkonfigurasi rourter dengan topology yang sudah di sediakan. setelah konfigure kami melakukan backup pada file untuk bisa di simpan di device mandiri
