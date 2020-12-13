# MENAMBAHKAN SSL LET'S ENCRYPT

- Menginstal aplikasi certbot dengan beberapa perintah berikut pada server public
    - `sudo add-apt repository ppa:certbot/certbot`
    - `sudo apt-get update`
    - `sudo apt-get install python-certbot-nginx`

- Setelah itu jalankan perintah `sudo certbot --nginx -d recky.instructype.com` untuk mengaktifkan let's encrypt dengan bantuan certbot
  ![1](https://user-images.githubusercontent.com/45087061/102004805-acbcee00-3d46-11eb-93a2-d02d45b31638.png)
  ![2](https://user-images.githubusercontent.com/45087061/102004853-1fc66480-3d47-11eb-8c0f-5e1447281214.png)
  ![3](https://user-images.githubusercontent.com/45087061/102004861-2f45ad80-3d47-11eb-8fc5-703f22203361.png)

- Cek settingan nginx yang ada pada file `housy.conf` dalam directory `etc/nginx/sites-available`. Jika sudah terinstall ssl nya akan seperti ini
  ![4](https://user-images.githubusercontent.com/45087061/102004871-50a69980-3d47-11eb-8a6e-294ea3c4723c.png)

- Kemudian cek dengan browser komputer juga. Akan muncul icon gembok disebelah urlnya
  ![5](https://user-images.githubusercontent.com/45087061/102004911-a2e7ba80-3d47-11eb-9ce9-ecf028d61590.png)
