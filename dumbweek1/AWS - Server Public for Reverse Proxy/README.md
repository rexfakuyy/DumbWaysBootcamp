# REVERSE PROXY PADA SERVER PUBLIC

- Pada server public lakukan update dan upgrade OS menggunakan perintah\
  `sudo apt update && sudo apt upgrade` lalu install nginx dengan perintah `sudo apt install nginx`
  ![1](https://user-images.githubusercontent.com/45087061/102004227-6ca73c80-3d41-11eb-9edb-7cdf5a5bd789.png)
  ![2](https://user-images.githubusercontent.com/45087061/102004237-80eb3980-3d41-11eb-8388-28a727e53452.png)

- Tes akses server public dari browser komputer lokal dan curl dari terminal server public dengan perintah\
`curl localhost`
    ![4](https://user-images.githubusercontent.com/45087061/102004288-de7f8600-3d41-11eb-8d2b-61cf251031c5.png)
    ![3](https://user-images.githubusercontent.com/45087061/102004282-d58eb480-3d41-11eb-89bd-7dda3e4173c1.png)

- Kemudian buatlah file bernama `housy.conf` pada directory `etc/nginx/sites-available` untuk configurasi reverse proxynya dan di isi seperti gambar berikut

**NOTED: JANGAN GUNAKAN TOMBOL TAB UNTUK MEMBERI JARAK PADA SAAT PENULISAN SCRIPT KARENA AKAN MENIMBULKAN ERROR! GUNAKANLAH TOMBOL SPASI**
  ![5](https://user-images.githubusercontent.com/45087061/102004311-1e466d80-3d42-11eb-8fb2-1d6b98e8d3d6.png)

- Hubungkan file `housy.conf` yang ada dalam directory `etc/nginx/sites-available` ke directory `etc/nginx/sites-enabled` menggunakan perintah `sudo ln -s /etc/nginx/sites-available/housy.conf /etc/nginx/sites-enabled/housy.conf` agar tidak perlu mengganti(include sites-available) file di nginx.conf karena secara default sudah ada include `etc/nginx/sites-enabled/*` dan kemudian restart service nginx nya.\
`sudo systemctl restart nginx` dan `sudo systemctl status nginx`
    ![8](https://user-images.githubusercontent.com/45087061/102004544-459e3a00-3d44-11eb-8ed8-930b1432c662.png)
    ![6](https://user-images.githubusercontent.com/45087061/102004404-ec81d680-3d42-11eb-8ac8-18e9a1049785.png)

- Tes akses website yang ada pada server private dari browser komputer lokal mengguakan ip server public
    ![7](https://user-images.githubusercontent.com/45087061/102004427-12a77680-3d43-11eb-8ebf-630e29a9d389.png)
