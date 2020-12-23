# REVERSE PROXY

- Pada server nginx buatlah file baru bernama `housy-frontend.conf dan housy-backend.conf` dan masukkan konfigurasi seperti berikut
  ![Screen Shot 2020-12-19 at 10 59 19](https://user-images.githubusercontent.com/45087061/102740905-748b6000-4383-11eb-9f07-baeb7ca2ddea.png)
  ![Screen Shot 2020-12-19 at 10 59 56](https://user-images.githubusercontent.com/45087061/102740914-7f45f500-4383-11eb-8cea-54bf7d8bf5e8.png)\
  **NOTED: konfigurasi bisa dilakukan pada 1 file saja dan digabungkan dengan konfigurasi frontend, tapi menurut saya jika dipisah akan jauh lebih mudah untuk melakukan debugging bila ada suatu kesalahan**

- Kemudian hubungkan konfigurasi tersebut dengan perintah `sudo ln -s /etc/nginx/sites-available/housy-frontend.conf housy-backend.conf /etc/nginx/sites-enabled/housy-frontend.conf housy-backend.conf` lalu restart service nginx nya

- Setelah itu buka aplikasi `Postman`, buatlah user baru untuk login https://reckypramana.instructype.com (aplikasi frontend) nantinya dari api backend melalui `Postman`. Gunakan method `POST` dan isi datanya sebagai berikut
  ![Screen Shot 2020-12-17 at 12 48 06](https://user-images.githubusercontent.com/45087061/102741594-5f173580-4385-11eb-9102-15ed319ad4be.png)\
  **NOTED: jika berhasil akan muncul sebuah token dibagian bawah**

- Pada Reverse proxy frontend saya tambahkan upstream untuk loadbalancing, sehingga jika 1 server frontend mati maka server frontend yang lain bisa langsung menggantikan
  ![Screen Shot 2020-12-19 at 10 59 19](https://user-images.githubusercontent.com/45087061/102740905-748b6000-4383-11eb-9f07-baeb7ca2ddea.png)

- Restart service nginx nya dengan perintah `sudo systemctl restart nginx`
