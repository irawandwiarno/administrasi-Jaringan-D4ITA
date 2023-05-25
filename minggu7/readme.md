# LAPORAN MINGGU-7 Flow DNS

![](blob/Flow%20DNS.jpg)

Flow DNS recursive sebagai berikut:

1. Client ingin mengakses sebuah website dengan nama domain "kompas.com".
2. Client mengirim permintaan (DNS query) ke nameserver lokal (NSL) yang terhubung ke jaringan.
3. NSL memeriksa apakah ia memiliki cache untuk lokasi domain "kompas.com". Jika tidak ada, NSL melanjutkan permintaan ke langkah berikutnya.
4. NSL mengirim permintaan (DNS query) ke root server, yang merupakan server tingkat tertinggi dalam hierarki DNS.
5. Root server memberikan respons (DNS response) dengan memberikan informasi tentang nameserver otoritatif untuk domain top-level "com".
6. NSL melakukan permintaan (DNS query) kepada nameserver otoritatif untuk domain "com" yang diberikan oleh root server.
7. Nameserver otoritatif untuk domain "com" memberikan respons (DNS response) dengan memberikan informasi tentang nameserver otoritatif untuk domain "kompas.com".
8. NSL melakukan permintaan (DNS query) kepada nameserver otoritatif untuk domain "kompas.com" yang diberikan oleh nameserver otoritatif untuk domain "com".
9. Nameserver otoritatif untuk domain "kompas.com" memberikan respons (DNS response) dengan memberikan alamat IP yang terkait dengan domain "kompas.com".
10. NSL menerima respons tersebut dari nameserver otoritatif untuk domain "kompas.com".
11. NSL mengirimkan respons (DNS response) kepada komputer client yang awalnya mengajukan permintaan.
12. Client menerima respons tersebut dan dapat mengakses website "kompas.com" dengan menggunakan alamat IP yang diberikan dalam respons.

## **Penjelasan Dari forward**

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
