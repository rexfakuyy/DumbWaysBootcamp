# SETUP MONITORING SERVER

- Install prometheus dan grafana pada server monitoring menggunakan docker yang dijalankan oleh ansible-playbook, berikut konfigurasinya dan hasil runing:


![Screen Shot 2021-01-07 at 23 01 01](https://user-images.githubusercontent.com/45087061/105947792-56103700-609c-11eb-8770-23b2b75372a6.png)

![Screen Shot 2021-01-07 at 23 03 07](https://user-images.githubusercontent.com/45087061/105947813-61636280-609c-11eb-83b8-245ff48e3978.png)


- Membuat reverse proxy untuk server frontend(0), grafana(1), backend(2), dan jenkins(3). lalu copy semua file yang sudah dibuat ke server nginx menggunakan ansible-playbook. 


![Screen Shot 2021-01-07 at 23 24 46](https://user-images.githubusercontent.com/45087061/105947869-87890280-609c-11eb-8e2a-14751acf13d5.png)
![Screen Shot 2021-01-07 at 23 25 16](https://user-images.githubusercontent.com/45087061/105947877-89eb5c80-609c-11eb-8d54-75d2844f862e.png)
![Screen Shot 2021-01-07 at 23 27 09](https://user-images.githubusercontent.com/45087061/105947880-8b1c8980-609c-11eb-9dc3-0b322436d18b.png)
![Screen Shot 2021-01-07 at 23 28 03](https://user-images.githubusercontent.com/45087061/105947883-8c4db680-609c-11eb-8d47-d1d161fe43c8.png)

![Screen Shot 2021-01-08 at 00 07 38](https://user-images.githubusercontent.com/45087061/105947940-a8515800-609c-11eb-8bf1-4795abc207ef.png)

![Screen Shot 2021-01-08 at 00 07 07](https://user-images.githubusercontent.com/45087061/105947962-b606dd80-609c-11eb-8fa0-0a84e93bc60f.png)


- Untuk SSL lets encrypt digunakan bantuan certbot yang dijalankan melalui ansible-playbook dengan konfigurasi sebagai berikut


![Screen Shot 2021-01-10 at 14 42 55](https://user-images.githubusercontent.com/45087061/105948048-d8006000-609c-11eb-9caf-0db95f6966f8.png)

![Screen Shot 2021-01-10 at 14 43 59](https://user-images.githubusercontent.com/45087061/105948051-d9318d00-609c-11eb-9859-21e68e873dec.png)

![Screen Shot 2021-01-08 at 14 53 06](https://user-images.githubusercontent.com/45087061/105948038-d46cd900-609c-11eb-8a71-24ddf3d716ff.png)