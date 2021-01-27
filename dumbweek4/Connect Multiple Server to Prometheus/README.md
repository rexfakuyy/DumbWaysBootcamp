# CONNECT MULTIPLE SERVER TO PROMETHEUS

- Menambahkan konfigurasi prometheus untuk mendapatkan informasi dari server yang akan dipantau. File bernama `prometheus.yml` akan dimasukkan kedalam folder /etc/prometheus yang sudah dilakukan pada proses instalasi prometheus seperti sebelumnya. berikut isi dari konfigurasi prometheus dan tampilan website prometheus yang diakses dari komputer lokal:


![Screen Shot 2021-01-09 at 14 28 34](https://user-images.githubusercontent.com/45087061/105946109-2875be80-6099-11eb-8947-65db2b732e26.png)

![Screen Shot 2021-01-09 at 16 29 01](https://user-images.githubusercontent.com/45087061/105946133-3297bd00-6099-11eb-87e1-db8d50803c13.png)


- Cara prometheus mendapatkan data dari server yang lain adalah dengan meminta informasi node expoter yang sudah terinstall pada server remote. Proses instalasi node expoter juga dilakukan secara masal dan otomatis menggunakan ansible-playbook bersamaan dengan proses instalasi docker karena melibatkan semua server, jadi bisa dirasa lebih menghemat waktu. 


![Screen Shot 2021-01-27 at 12 18 03](https://user-images.githubusercontent.com/45087061/105946374-ba7dc700-6099-11eb-8789-373e4d975fbe.png)


NB: untuk hasil run tidak sempat diambil karena proses yang cukup panjang dan melibatkan semua server

- Setelah prometheus berhasil mendapatkan semua data dari server remote giliran grafana yang akan di reverse proxy pada file monitoring.conf, jadi domain https://monitoring.recky.instructype.com yang sebelumnya menampilkan halaman prometheus akan diubah menjadi grafana supaya tampilan lebih enak dilihat dan informasi lebih jelas. Grafana akan mengambil data source dari prometheus dan menampilkan informasi berdasarkan host yang dipilih.


![Screen Shot 2021-01-09 at 16 43 41](https://user-images.githubusercontent.com/45087061/105946490-f31da080-6099-11eb-80af-036532ce4c3e.png)


![Screen Shot 2021-01-09 at 18 58 23](https://user-images.githubusercontent.com/45087061/105946603-25c79900-609a-11eb-8345-30226fd73199.png)
![Screen Shot 2021-01-09 at 19 11 19](https://user-images.githubusercontent.com/45087061/105946610-29f3b680-609a-11eb-8389-4fc4abfc5d89.png)