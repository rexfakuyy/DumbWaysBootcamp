# DEPLOY PHP APPLICATION IN CPANEL

## Berikut beberapa platform yang saya gunakan untuk deploy php application:


#### CMS yang akan dideploy adalah [WordPress CMS](https://wordpress.org/)
#### cPanel  yang digunakan adalah [Infinity free](https://infinityfree.net/)
#### SSL yang dipakai adalah [GoGetSSL](https://www.gogetssl.com/)
#### FTP yang digunakan adalah [FileZilla](https://filezilla-project.org/) tapi saya menggunakan FTP/File Manager Online bawaan cPanelnya
#### Domain cPanel saya adalah [reckywp](https://reckywp.rf.gd/)


Langkah - langkah yang dilakukan untuk deploy aplikasi pada cPanel adalah sebagai berikut: 

- Download cms yang akan dideploy, dan ekstrak pada komputer lokal agar mempercepat proses deploy sehingga tidak perlu ekstrak didalam folder cPanel

- Daftar ke cPanel dan pilih domain dan subdomain yang akan dipakai untuk mengakses CMS, pada kolom yang ada dikanan terdapat info yang bisa digunakan untuk mengakses ftp dan database


![Screen Shot 2021-01-10 at 15 44 32](https://user-images.githubusercontent.com/45087061/105947009-e3eb2280-609a-11eb-819c-98c9fa9d421b.png)


- Transfer cms yang sudah di ekstrak pada komputer lokal ke folder cPanel, bisa langsung dari website atau menggunakan ftp. Utuk kasus ini karena file cms Vanilla Forum ada lebih dari 4.000 file, menggunakan website akan membebani komputer lokal dan proses akan sangat lama, karnanya menggunakan frp adalah jalan keluar terbaik karna dirasa lebih ringan dan proses cukup cepat.


![Screen Shot 2021-01-10 at 16 06 36](https://user-images.githubusercontent.com/45087061/105947045-f7968900-609a-11eb-9ab8-2658c1feb6e5.png)


- Install CMS melalui domain yang sudah dibuat saat proses registrasi cPanel dan masukan data yang sudah didapat


![Screen Shot 2021-01-10 at 16 56 58](https://user-images.githubusercontent.com/45087061/105947089-11d06700-609b-11eb-9442-fe5a5a8ee1ca.png)

- Pada cPanel infinityfree sudah disediakan **SSl Gratis** yang berlaku selama 60 hari dan bisa diperbaharui. Untuk mendapatkan ssl cukup mengisi data yang dibutuhkan dan tunggu sampai proses selesai.


![Screen Shot 2021-01-10 at 17 17 28](https://user-images.githubusercontent.com/45087061/105947150-2f053580-609b-11eb-9945-c8cc4dc66e7f.png)

![Screen Shot 2021-01-10 at 19 13 05](https://user-images.githubusercontent.com/45087061/105947219-56f49900-609b-11eb-9d10-2b653cb615fc.png)

![Screen Shot 2021-01-10 at 19 13 38](https://user-images.githubusercontent.com/45087061/105947287-71c70d80-609b-11eb-9715-72e9ae269920.png)


![Screen Shot 2021-01-10 at 19 11 38](https://user-images.githubusercontent.com/45087061/105947484-c10d3e00-609b-11eb-8ce3-3988aacb4a0d.png)


- Setelah proses selesai, akan mendapat private key dan certificate yang bisa dimasukkan dalam menu SSL pada dashboard cPanel dan website dapat diakses menggunakan https://


![Screen Shot 2021-01-10 at 19 25 52](https://user-images.githubusercontent.com/45087061/105947520-d5513b00-609b-11eb-9b3d-be7a0fc8b2dc.png)

![Screen Shot 2021-01-11 at 11 41 52](https://user-images.githubusercontent.com/45087061/105947587-f2860980-609b-11eb-97ae-f7021e66aa04.png)