# CREATE JENKINS JOB

- Pertama yang saya lakukan adalah membuat token github agar bisa diakses oleh jenkins, token yang saya generate hanya membolehkan akses workflow repo dan read/write

![Screen Shot 2020-12-26 at 09 56 17](https://user-images.githubusercontent.com/45087061/105942729-63282880-6092-11eb-8f05-d6ce94d41cb5.png)

![Screen Shot 2020-12-26 at 12 36 49](https://user-images.githubusercontent.com/45087061/105942952-d5990880-6092-11eb-9304-a80ae89401ec.png)

- Token yang sudah dibuat ditambahkan pada konfigurasi guthub yang ada pada jenkins gui 

![Screen Shot 2020-12-26 at 12 36 29](https://user-images.githubusercontent.com/45087061/105942906-bb5f2a80-6092-11eb-9e05-d15947c7094b.png)

- Membuat jobs baru dengan menambahkan ssh repository github dan branch yang saya gunakan adalah master

![Screen Shot 2020-12-27 at 09 36 25](https://user-images.githubusercontent.com/45087061/105943056-08430100-6093-11eb-93b6-1ecec8a2003b.png)

- Credential yang digunakan untuk mengakses github menggunakan ssh key server yang ingin dihubungkan. Disini saya menggunakan Username & Password dari server saya bukan ssh key.

![Screen Shot 2020-12-27 at 09 17 53](https://user-images.githubusercontent.com/45087061/105943178-4dffc980-6093-11eb-88e0-b1d86bc153e4.png)

- Menambahkan informasi server remote yang ingin dihubungkan dengan publish over ssh. Pada kasus ini, saya tidak menggunakan ssh key dan mencoba menggunakan password server, hasilnya pun sama saja.

- Pengaturan build menggunakan publish over ssh, nama didapat dari proses sebelumnya yang sudah berhasil konek ke remote server. untuk remote directorynya pastikan sudah masuk /home/user dan exec command berisi perintah yang akan dijalankan pada server remote

Untuk build saya lakukan setelah terjadi perubahan pada repo github

![Screen Shot 2020-12-27 at 09 43 11](https://user-images.githubusercontent.com/45087061/105943340-a6cf6200-6093-11eb-9e0e-daaf59beecf8.png)

- Cek log github yang ada pada gui jenkins

![Screen Shot 2020-12-27 at 10 37 27](https://user-images.githubusercontent.com/45087061/105943407-c1a1d680-6093-11eb-91ae-00f787601b33.png)

- Consol log dari server yang terhubung dengan jenkins. Lingkaran berubah warna menjadi biru jika proses berhasil 

![Screen Shot 2020-12-27 at 12 59 05](https://user-images.githubusercontent.com/45087061/105943591-28bf8b00-6094-11eb-894e-716bb8c9bc92.png)


- Untuk push image ke docker saya menggunakan fitur yang sudah disediakan oleh docker, yaitu docker build yang terintegrasi dengan akun github, jadi docker akan secara otomatis melakukan build dan push setelah ada perubahan pada repo github.

![Screen Shot 2020-12-27 at 12 41 24](https://user-images.githubusercontent.com/45087061/105943658-4ab90d80-6094-11eb-860e-2f26b122c23d.png)

- Setelah proses build berhasil akan ada keterangan kapan proses selesai dan di push, dipojok kanan bawah ada keterangan siapa yang melakukan build

![Screen Shot 2020-12-27 at 12 41 49](https://user-images.githubusercontent.com/45087061/105943684-57d5fc80-6094-11eb-96c0-a0ac8c0f6832.png)

- Untuk notifikasi build saya menggunakan Discord notif

![Screen Shot 2020-12-27 at 12 17 55](https://user-images.githubusercontent.com/45087061/105943716-74723480-6094-11eb-9527-c6dfade3e03a.png)

