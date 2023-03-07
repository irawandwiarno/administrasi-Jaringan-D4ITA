Nama : Irawan Dwiarno Pangestu<br/>
NRP : 3121600020<br/>
Kelas : D4 IT A

<br/>
<br/>

# Apa itu Kernel?

Kernel adalah inti dari sistem operasi yang bertanggung jawab untuk mengelola sumber daya perangkat keras dan memungkinkan perangkat lunak untuk berinteraksi dengan perangkat keras. Kernel adalah program pertama yang dijalankan saat komputer dinyalakan dan bertindak sebagai jembatan antara perangkat lunak aplikasi dan perangkat keras.

## Fungsi Kernel

Beberapa fungsi utama kernel adalah sebagai berikut:

1. Manajemen memori - Kernel bertanggung jawab untuk mengalokasikan dan mengatur memori komputer untuk berbagai aplikasi.

2. Manajemen sumber daya perangkat keras - Kernel memungkinkan aplikasi untuk berkomunikasi dengan perangkat keras seperti keyboard, mouse, printer, dan kartu jaringan.

3. Penjadwalan tugas - Kernel menentukan urutan tugas apa yang harus dilakukan dan bagaimana mereka harus dikerjakan.

4. Sistem file - Kernel bertanggung jawab untuk mengelola file dan direktori di sistem operasi.

## Jenis-jenis Kernel

Terdapat beberapa jenis kernel yang umum digunakan, yaitu:

1. Monolithic kernel - Kernel monolitik berisi semua fungsi sistem operasi dalam satu unit, termasuk manajemen memori, manajemen sumber daya perangkat keras, penjadwalan tugas, dan sistem file.

2. Microkernel - Kernel mikro hanya memiliki fungsi dasar, seperti manajemen memori dan penjadwalan tugas, dan mengandalkan modul eksternal untuk menjalankan fungsi lain seperti manajemen sumber daya perangkat keras.

3. Hybrid kernel - Hybrid kernel menggabungkan elemen dari kernel monolitik dan mikro. Kernel ini berisi fungsi dasar seperti manajemen memori dan penjadwalan tugas, namun juga memiliki modul tambahan untuk manajemen sumber daya perangkat keras dan sistem file.

## Kesimpulan

Kernel adalah bagian inti dari sistem operasi yang memungkinkan perangkat lunak berinteraksi dengan perangkat keras. Kernel bertanggung jawab untuk mengelola sumber daya perangkat keras, mengatur memori, menentukan urutan tugas, dan mengelola sistem file. Terdapat beberapa jenis kernel yang umum digunakan, yaitu kernel monolitik, kernel mikro, dan kernel hibrida.
<br/><br/><br/>
![](assets/1.png)

# Identifikasi Direktori Root Pada Linux

Direktori root adalah direktori utama dalam sebuah sistem file pada sebuah komputer atau perangkat digital lainnya. Direktori ini adalah tempat di mana semua file dan direktori lainnya diorganisasikan dan disimpan.

Pada sistem operasi Linux dan Unix, direktori root biasanya dilambangkan dengan simbol "/" (forward slash) dan semua file dan direktori lainnya terletak di bawahnya. Direktori root adalah direktori tertinggi pada hierarki sistem file Linux dan Unix, dan biasanya hanya dapat diakses oleh pengguna yang memiliki hak akses administrator atau root.

<br/>
Pada linux, terdapat beberapa folder pada folder `/` atau `root`. Folder dan fungsi dari folder tersebut adalah:

1. `/bin` - aplikasi-aplikasi biner penting
2. `/boot` - file-file konfigurasi boot, kernel, dan file lain yang dibutuhkan ketika sistem booting
3. `/dev` - berisi file-file device (divais) seperti /dev/tty, /dev/input/mice
4. `/etc` - file konfigurasi, skrip startup, dll (etc)...
5. `/home` - direktori home bagi masing-masing user
6. `/initrd` - digunakan untuk mengkustomisasi initrd yang berjalan saat proses boot
7. `/lib` - pustaka-pustaka yang diperlukan oleh sistem
8. `/lost`+found - menyediakan sistem lost+found untuk file yang berada dibawah direktori root (/)
9. `/media` - partisi yang secara otomatis dimount di harddisk dan removable mediaseperti CD, kamera digital, dll.
10. `/mnt` - mounted filesistem secara manual di harddisk
11. `/opt` - menyediakan lokasi untuk aplikasi-aplikasi optional yang akan diinstal
12. `/proc` - direktori dinamis khusus yang menangani informasi mengenai kondisi sistem, termasuk proses-proses yang sedang berjalan
13. `/root` - direktori home bagi user root, diucapkan 'slash-root'. bedakan dengan /
14. `/sbin` - biner-biner sistem yang penting, biasanya aplikasi-aplikasi bagi admin
15. `/srv` - can contain files that are served to other systems
16. `/sys` - berkas sistem (system)
17. `/tmp` - berkas sementara (temporary)
18. `/usr` - aplikasi dan berkas yang tersedia untuk digunakan untuk pengguna (users)
19. `/var` - berkas variabel seperti log dan basis data

<br/>

# Perbedaan `sudo` dan `su`

`su` (atau "switch user") digunakan untuk mengubah identitas pengguna menjadi akun superuser atau akun lain, sementara `sudo` (atau "superuser do") digunakan untuk menjalankan perintah tertentu sebagai akun superuser atau akun lain tanpa perlu masuk ke dalam akun superuser secara langsung.

Saat menggunakan perintah `su`, pengguna harus memasukkan kata sandi untuk akun superuser atau akun lain yang dituju. Namun, saat menggunakan perintah `sudo`, pengguna diminta untuk memasukkan kata sandi mereka sendiri untuk memverifikasi identitas mereka sebelum menjalankan perintah.

Penggunaan `sudo` lebih aman daripada `su` karena tidak memerlukan pengguna untuk masuk ke dalam akun superuser secara langsung. Ini membatasi potensi kerusakan atau kesalahan yang dapat terjadi saat menggunakan akses superuser. sudo su untuk folder saat ini

<br/>

# Repository

Repository adalah tempat penyimpanan kode sumber atau proyek yang dapat diakses oleh banyak orang. Biasanya repository digunakan untuk mengatur kode sumber proyek, termasuk dokumentasi dan file-file terkait lainnya.

Repositori Linux adalah lokasi penyimpanan tempat sistem Anda mengambil dan menginstal pembaruan dan aplikasi OS. Setiap repositori adalah kumpulan perangkat lunak yang di-host di server jauh dan dimaksudkan untuk digunakan untuk menginstal dan memperbarui paket perangkat lunak pada sistem Linux.

Untuk melihat repository mana saja yang digunakan pada sistem, kita bisa menggunakan perintah `cat /etc/apt/source.list`.

Ada beberapa jenis repository pada linux:

1. `deb cdrom` adalah repository dari CD/DVD instalasi Ubuntu.
2. `deb http://id.archive.ubuntu.com/ubuntu/ kinetic main restricted` adalah repository utama (main) Ubuntu, yang berisi paket-paket utama untuk sistem operasi Ubuntu.
3. `deb http://id.archive.ubuntu.com/ubuntu/ kinetic-updates main restricted` adalah repository Ubuntu untuk pembaruan (updates) dari paket-paket di repository utama.
4. `deb http://id.archive.ubuntu.com/ubuntu/ kinetic universe` adalah repository Ubuntu untuk paket-paket yang tidak disupport secara resmi oleh Ubuntu, namun tetap terbuka untuk diakses oleh pengguna.
5. `deb http://security.ubuntu.com/ubuntu kinetic-security multiverse` adalah repository Ubuntu untuk pembaruan keamanan (security) dari paket-paket di repository multiverse.
6. `deb http://security.ubuntu.com/ubuntu kinetic-security universe` Ini adalah repository Ubuntu untuk pembaruan keamanan (security) dari paket-paket di repository universe.
7. `deb http://security.ubuntu.com/ubuntu kinetic-security main restricted` Ini adalah repository Ubuntu untuk pembaruan keamanan (security) dari paket-paket di repository utama.

<br/>

# Package manager

Package management adalah sebuah aplikasi atau software pada linux yang dipakai untuk memasang / menginstal , menemukan dan menghapus software lain, secara tersentralisasi.

Pada linux ada beberapa package manager, diantaranya ada apt, yum, nix, dll. Beberapa distro biasanya sudah memiliki package manager default mereka sendiri seperti Ubuntu yang menggunakan apt dan Fedora dengan yum-nya.

Detail mengenai pacakage manager sendiri sebenenarnya bisa diakses menggunakan perintah `man [package manager]`

Untuk detail dari apt sendiri adalah:
| Perintah | Fungsi |
| -------- | ------ |
| `apt update` | Memperbarui daftar paket dan metadata yang tersedia di repository. |
| `apt upgrade` | Menginstall paket-paket baru yang tersedia dan mengupgrade paket yang sudah terinstall. |
| `apt install` | Menginstall paket baru. |
| `apt remove` | Menghapus paket yang sudah terinstall. |
| `apt autoremove` | Menghapus paket-paket yang tidak lagi dibutuhkan oleh sistem. |
| `apt search` | Mencari paket yang tersedia di repository. |
| `apt show` | Menampilkan informasi detail tentang paket yang tersedia di repository. |
| `apt list` | Menampilkan daftar paket yang sudah terinstall. |
| `apt full-upgrade` | Menginstall paket-paket baru dan mengupgrade paket-paket yang sudah terinstall dengan menyelesaikan semua ketergantungan (dependencies) yang dibutuhkan. |
| `list` | Menampilkan daftar paket berdasarkan nama paket |
| `search` | Mencari dalam deskripsi paket |
| `show` | Menampilkan detail paket |
| `install` | Menginstall paket |
| `reinstall` | Menginstall ulang paket |
| `remove` | Menghapus paket |
| `autoremove` | Menghapus otomatis semua paket yang tidak terpakai |
| `update` | Memperbarui daftar paket yang tersedia |
| `upgrade` | Mengupgrade sistem dengan menginstal/mengupgrade paket-paket |
| `full-upgrade` | Mengupgrade sistem dengan menghapus/menginstal/mengupgrade paket-paket |
| `edit-sources` | Mengedit file informasi sumber |
| `satisfy` | Memenuhi string dependensi |
