LAPORAN MINGGU-7 Instalasi DNS

## 1. **Update dan upgrade paket**

```console
sudo apt update && apt upgrade
```

Dengan menggunakan perintah apt update dan apt upgrade akan mengupdate dan memperbarui daftar paket pada system

## 2. **Ubah Hostname**

```console
hostnamecli set-hostname kampus-5.takehome.com
```

Ubah nama hostname sesuai topologi, karena kami kelompok 5 maka nama hostnamenya yaitu : kampus-5.takehome.com

## 3. **Install Bind9**

Gunakan command berikut :

```console
sudo apt install bind9 -y
```

Kita menginstal bind9 yang digunakan pada sistem Debian untuk mengelola dan menyediakan layanan DNS pada jaringan lokal atau internet.

## 4. **Install bind9utils**

Gunakan command berikut :

```console
sudo apt install bind9utils
```

Kita menginstal bind9utils untuk bisa menggunakan utilitas yang terkait dengan server DNS BIND9 seperti : dig, nslookup, rndc, dnssec-keygen dll.

## 5. **Konvigurasi DNS Server**

Untuk konfigurasi DNS ada beberapa file yang perlu kita ubah. kita perlu mengubah Zone saat konfirgurasi DNS server.

Zone editor adalah fitur yang memungkinkan untuk membuat, edit, dan hapus DNS, dan ini adalah zone recordnya

Zone sendiri adalah suatu wilayah atau domain yang dikelola oleh sebuah server DNS tertentu. Setiap zona DNS dapat berisi informasi mengenai nama domain, alamat IP, atau informasi lainnya yang terkait dengan domain tersebut.

## 6. **Setting file forward**

Ada beberapa singkatan yang ada pada file forward :

| TTL                | Time To Life adalah parameter yang menentukan berapa lama suatu catatan DNS (DNS record) akan di-cache oleh DNS resolver atau server yang meminta informasi tersebut.                                                                                                                                                                                  |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| IN                 | singkatan dari "Internet" yang menandakan kelas jaringan untuk catatan DNS. Nilai IN digunakan untuk semua catatan DNS dalam file forward DNS Debian.                                                                                                                                                                                                  |
| SOA                | singkatan dari "Start of Authority" yang digunakan untuk menentukan server DNS utama untuk domain dan informasi lainnya seperti email administrator DNS, serial number, dan parameter lainnya.                                                                                                                                                         |
| A                  | singkatan dari "Address" yang digunakan untuk menentukan alamat IPv4 untuk sebuah nama domain. Catatan A menghubungkan sebuah nama domain dengan alamat IPv4.                                                                                                                                                                                          |
| AAAA               | singkatan dari "IPv6 Address" yang digunakan untuk menentukan alamat IPv6 untuk sebuah nama domain. Catatan AAAA menghubungkan sebuah nama domain dengan alamat IPv6.                                                                                                                                                                                  |
| NS                 | singkatan dari "Name Server" yang digunakan untuk menentukan server DNS yang bertanggung jawab untuk domain tertentu.                                                                                                                                                                                                                                  |
| PTR                | singkatan dari "Pointer" yang digunakan untuk menentukan sebuah nama domain berdasarkan alamat IP.                                                                                                                                                                                                                                                     |
| Serial             | Parameter serial digunakan untuk menandai perubahan pada DNS zone. Setiap kali ada perubahan pada zone file, misalnya menambah, menghapus, atau mengubah catatan DNS, nilai serial harus ditingkatkan untuk menandakan perubahan tersebut. Nilai serial harus berupa bilangan bulat positif dan meningkat setiap kali terjadi perubahan pada DNS zone. |
| Refresh            | Parameter refresh menentukan waktu dalam detik antara server DNS utama melakukan refresh pada zone file dan server DNS sekunder meminta pembaruan terbaru dari server utama. Jadi, refresh menandakan seberapa sering server sekunder meminta pembaruan dari server utama.                                                                             |
| Retry              | Parameter retry menentukan waktu dalam detik antara server DNS sekunder meminta pembaruan dari server DNS utama jika upaya pertama tidak berhasil. Jadi, retry menandakan berapa sering server sekunder mencoba memperbarui data dari server utama jika gagal pada upaya pertama.                                                                      |
| Expire             | Parameter expire menentukan waktu dalam detik setelah server sekunder harus menganggap data yang tersimpan dalam cache tidak valid lagi jika server DNS utama tidak tersedia. Jadi, expire menandakan seberapa lama data DNS yang disimpan dalam cache akan berlaku jika server utama tidak tersedia.                                                  |
| Negative Cache TTL | Parameter ini menentukan waktu dalam detik bahwa server DNS akan menyimpan hasil pencarian DNS yang gagal (misalnya, ketika domain tidak ada). Hal ini memungkinkan server DNS untuk menampung sementara informasi negatif dalam cache dan menghindari melakukan permintaan DNS yang berlebihan.                                                       |

Ubah localhost menjadi nama hostname yang sudah di setting sebelumnya

Replace semua localhost menjadi berikut :

```console
kampus-5.takehome.com
```

## 7. **Buat file Reserve**

Lakukan perintah berikut :

```console
cp /etc/bind/db.127 /etc/bind/reverse
```

Kemudian inputkan perintah berikut :

```console
gedit /etc/bind/reverse
```

Buat file reserve dengan mengcopy file db.127 pada direktori yang sama dengan forward

Sama seperti sebelumnya ubah localhost menjadi hostname yang telah di setting dan juga ganti ip menjadi 249 sesuai dengan ip sebelumnya

## 8. **Tambahkan name server**

```console
nano /etc/resolv.conf
```

tuliskan code berikut :

```console
search takehome.com
nameserver 202.9.85.3
nameserver 192.168.5.249
```

Daftarkan IP dari Debian kedalam file resolv.conf

## 9. **Restart layanan DNS**

Gunakan command berikut untuk merestart service dari bind9 :

```console
systemcli restart bind9.service
```

Kemudian gunakan command berikut untuk melihat service dari bind9 :

```console
systemcli status bind9.service
```

Setelah setting selesai lakukan restart untuk mengupdate setting yang telah di ubah

## 10. **Pindahkan file**

Sebelumnya kita menaruh file bind di etc, pindahkan kedalam folder chace yang berlokasi di computer/var/cache/bind, file yang dipindah yairu forward dan reverse

```console
mv forward /var/cache/bind/
```

Dan

```console
mv reverse /var/cache/bind/
```

## 11. **Pengecekan nslookup dan service**

Untuk melakukan pengecekan domain anda dapat menggunakan perintah berikut.

```console
nslookup kampus-5.takehome.com
```

Maka akan muncul Name server dan Address dari DNS yang kita ingin lihat tadi. Jika Name server dan Address sudah muncul maka instalasi dns sudah selesai.
