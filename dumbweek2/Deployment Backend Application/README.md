# DEPLOYMENT BACKEND

- Clone repo housy dengan perintah `git clone git@github.com:rexfakuyy/housy-backend.git` dan masuk ke directory repo yang sudah di clone lalu jalankan perintah `npm install`

- Install library pendukung seperti nodejs, npm dan pm2 seperti [minggu pertama](https://github.com/rexfakuyy/DumbWaysBootcamp/tree/master/dumbweek1) ditambah install sequelize dengan perintah `sudo npm install -g sequelize-cli` untuk migrasi database
  ![Screen Shot 2020-12-16 at 10 48 08](https://user-images.githubusercontent.com/45087061/102739795-ac44d880-4380-11eb-9501-9dd594c484d1.png)

- Edit file `config.json` pada directory `housy-backend/config/config.json` dan isi username, password serta host sesuai seperti yang sudah dibuat pada sesi instalasi database
  ![Screen Shot 2020-12-16 at 10 50 38](https://user-images.githubusercontent.com/45087061/102739967-21b0a900-4381-11eb-8a9f-4344b3b2f3be.png)

- Sebelum melakukan migrasi, saya mencoba dulu masuk ke mysql pada server database di server backend dengan menginstall `mysql-client` untuk mysql versi 5.7
  ![Screen Shot 2020-12-16 at 10 31 49](https://user-images.githubusercontent.com/45087061/102740054-64728100-4381-11eb-9d3f-c8a7d07adc33.png)

- Masuk ke mysql server database dengan perintah `mysql -u 'username' -h 'ip-server-db' -p` dan coba lihat database yang ada dengan perintah `show databases;`
  ![Screen Shot 2020-12-16 at 11 28 21](https://user-images.githubusercontent.com/45087061/102740114-98e63d00-4381-11eb-95ec-4e17c93ceefd.png)

- Jalankan migrasi database dengan perintah `sequelize db:migrate all`, pastikan berada pada directory `housy-backend`
  ![Screen Shot 2020-12-16 at 11 29 19](https://user-images.githubusercontent.com/45087061/102740194-d0ed8000-4381-11eb-8adf-b56a1e3a35d6.png)\
  **NB: jika proses migrasi gagal coba install mysql2 dengan perintah `sudo npm install -g mysql2`**

- Aktifkan `pm2` untuk backend agar nodejs terus berjalan walaupun ssh terputus
  ![Screen Shot 2020-12-19 at 10 36 49](https://user-images.githubusercontent.com/45087061/102740352-23c73780-4382-11eb-98ca-156847a23682.png)
