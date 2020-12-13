# DEPLOY APPLIKASI MENGGUNAKAN PM2 DI SERVER PRIVATE

- Setelah menjalankan SSH dari Server Private yang saya lakukan ialah:
  - Menjalankan perintah `sudo su` agar menjadi super user sehingga tidak perlu lagi menambahkan perintah sudo disetiap perintah.
  - Mengupdate dan upgrade apt dengan perintah `apt update && apt upgrade`
    ![1](https://user-images.githubusercontent.com/45087061/102002976-6bbbde00-3d34-11eb-919b-8ea06afab085.png)
    ![2](https://user-images.githubusercontent.com/45087061/102003002-a756a800-3d34-11eb-8431-f71d681198d7.png)
  - Install nodejs dengan perintah\
  `curl -sL https://deb.nodesource.com/setup_10.x | bash -
 apt-get install -y nodejs`
    ![3](https://user-images.githubusercontent.com/45087061/102003012-d0773880-3d34-11eb-994a-cf9452ceb766.png)

- Setelah proses instalasi selesai, jalankan perintah berikut untuk clone repository applikasi\
`git clone https://github.com/DumbwaysDotId/DW15WDTPH_housy`
    ![4](https://user-images.githubusercontent.com/45087061/102003496-ceb07380-3d3a-11eb-8bd5-777a70fcd92b.png)

- CD ke `DW15WDTPH_housy` dan buat file baru bernama `ecosystem.config.js` dan isi dengan configurasi PM2
    ![7](https://user-images.githubusercontent.com/45087061/102003566-89407600-3d3b-11eb-9b4d-5eee1c70685d.png)

- Install PM2 dengan perintah `npm install -g pm2` kemudian `npm install` dan jalankan perintah `pm2 start ecosystem.config.js` setelah instalasi selesai
    ![5](https://user-images.githubusercontent.com/45087061/102003603-eb997680-3d3b-11eb-8961-f9392e92e4d7.png)
    ![8](https://user-images.githubusercontent.com/45087061/102003636-2a2f3100-3d3c-11eb-9711-a66eff124ce3.png)

---

# ALLOW PORT 3000 (PORT DEFAULT NODEJS) UNTUK CEK RUNNING DARI SERVER PUBLIC

Pada settingan `Security Group` di instance server private, aturlah seperti ini dibagian `Inbound Rules` lalu save.
    ![9](https://user-images.githubusercontent.com/45087061/102004092-2dc4b700-3d40-11eb-92c0-2d5281cb35be.png)
    ![10](https://user-images.githubusercontent.com/45087061/102004122-7c725100-3d40-11eb-9b80-a75ec87d8c72.png)

Setelah itu cek hasil deploynya dari server public dengan perintah\
`curl ipprivate-serverprivate:3000`
    ![6](https://user-images.githubusercontent.com/45087061/102004162-cbb88180-3d40-11eb-8238-9f7220c66ee1.png)
