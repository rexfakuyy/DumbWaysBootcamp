# Setup Database

- Install mysql pada server database dengan perintah `sudo apt install mysql-client mysql-server` dan pilih mysql versi 5.7
  ![Screen Shot 2020-12-15 at 20 17 49](https://user-images.githubusercontent.com/45087061/102738443-bbc22280-437c-11eb-9b77-fb3f015d44f9.png)

- Dalam proses instalasi mysql lewat apt, saya tidak diberi kesempatan untuk membuat user baru, jadi user default sudah ada `root dan tanpa password`, untuk menambahkan user baru perlu masuk dahulu ke mysql dan jalankan perintah:\
`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'inipassword';`
  ![Screen Shot 2020-12-16 at 10 26 03](https://user-images.githubusercontent.com/45087061/102738561-152a5180-437d-11eb-9160-76753345ea71.png)

- Setelah password root diganti, coba relogin ke mysql dengan password baru, setelah berhasil, buatlah database baru bernama housy dengan perintah `create database housy;`
  ![Screen Shot 2020-12-16 at 10 30 15](https://user-images.githubusercontent.com/45087061/102738653-5e7aa100-437d-11eb-8e6c-4c397e72ca91.png)

- Buat user baru untuk mengakses server database dari server backend dan beri akses penuh dengan perintah:
  - `create user 'namauser'@'ip-server-backend' identified by 'disini-passwordnya';`
  - `grant all on *.* to 'namauser'@'ip-server-backend';`
  - `FLUSH PRIVILEGES;`
  ![Screen Shot 2020-12-16 at 10 37 47](https://user-images.githubusercontent.com/45087061/102738824-d779f880-437d-11eb-82ec-8e3fa3dd3b8d.png)

- Ubah `bind-address` yang ada pada file `mysqld.cnf` pada directory `/etc/mysql/mysql.conf.d/` dengan ip private server database
  ![Screen Shot 2020-12-16 at 10 41 28](https://user-images.githubusercontent.com/45087061/102738903-10b26880-437e-11eb-91e1-6fec50908dd5.png)
