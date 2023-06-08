### Daftar Isi

- [Instalasi Debian Server](#instalasi-debian-server)
- [Instalasi NTP Server Debian](#instalasi-ntp-server-debian)
- [Konfigurasi NTP Client Mikrotik ke Server Debian](#konfigurasi-ntp-client-mikrotik-ke-server-debian)
  - [Membuka file konfigurasi ntp server](#membuka-file-konfigurasi-ntp-server)
  - [Menjalankan ntp](#menjalankan-ntp)
  - [ntp client](#ntp-client)
- [Hasil](#hasil)

<br>

# Instalasi Debian Server

Pertama yang harus yang dilakukan adalah instalasi OS yang digunakan pada server, kali ini saya menggunakan Debian server. Untuk tutorial lengkap instalasi, sudah banyak tersebar di google.

[Cara instalasi Debian Server di virtualbox](https://virgiawan.id/tutorial-install-debian-server-di-virtualbox/)

[Cara instal Debian Server](https://idelinux.com/tutorial-install-debian-11-minimal-server-di-virtualbox)

setelah instalasi, pastikan bahwa OS bisa dijalankan.

![debian.jpeg](blob/debian.jpeg)

# Instalasi NTP Server Debian

Selanjutnya adalah instalasi ntp servernya, masukkan perintah dibawah untuk melakukan instalasi

```console
sudo apt install ntp
```

Kemudian tunggu proses instalasi sampai berhasil, dan ntp berhasil ter-_install_ di perangkat.

![ntp_instalation.png](blob/1.%20instalasi%20ntp%20server.png)

# Konfigurasi NTP Client Mikrotik ke Server Debian

## Membuka file konfigurasi ntp server

Untuk membuka file konfigurasi ntp, gunakan perintah

```console
sudo vim /etc/ntp.conf
```

kemudian masukkan konfigurasi berikut kedalam file nya

```console
pool 0.debian.pool.ntp.org iburst
pool 1.debian.pool.ntp.org iburst
pool 2.debian.pool.ntp.org iburst
pool 3.debian.pool.ntp.org iburst
```

kemudian simpan konfigurasi.

## Menjalankan ntp

Selanjutnya pastikan bahwa ntp sudah dijalankan menggunakan perintah `sudo service ntp status`. Jika ntp sudah berjalan maka akan tampil seerti berikut

![status_ntp_server.png](blob/4.%20status%20ntp%20server.png)

![status_ntp_server.png](blob/5.%20status%20ntp%20server.png)

atau kita bisa mengecek tanggal pada terminal kita menggunakan perintah `date`.

![status_date.png](blob/6.%20status%20date.png)

## ntp client

selanjutnya kita akan mengkonfigurasi ntp client pada mikrotik kita bisa mengaturnya seperti berikut pada bagian `System -> SNTP Client`, kemudian simpan.

![ntp_client.png](blob/7.%20ntp%20client.png)

# Hasil

Setelah semua konfigurasi dilakukan, kita bisa mengecek waktu pada mikrotik, jika berhasil maka waktu di mikrotik dan server akan sama.

![hasil.png](blob/8.%20hasil%20konfigurasi%20ntp%20client.png)

[def]: #daftar-isi
