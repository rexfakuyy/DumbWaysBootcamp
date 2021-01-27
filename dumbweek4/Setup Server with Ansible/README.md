# SETUP SERVER WITH ANSIBLE

- Install ansible secara manual tanpa bantuan docker
```
apt install python
sudo apt-add-repository ppa:ansible/ansible
apt update
apt install ansible
```

- Setelah ansible terinstal, buat list inventory yang berisikan informasi host server remote


![Screen Shot 2021-01-06 at 18 36 52](https://user-images.githubusercontent.com/45087061/105948236-33325280-609d-11eb-9166-0ac589a63728.png)


NB: pada awalnya ansible_user tidak ada dan untuk melakukan ssh ke server remote ansible menggunakan user root dan ssh keys yang ada pada file `ansible.cfg` berikut


![Screen Shot 2021-01-27 at 12 43 56](https://user-images.githubusercontent.com/45087061/105948346-5a891f80-609d-11eb-91e4-a53ddb9d0749.png)

![Screen Shot 2021-01-06 at 18 39 51](https://user-images.githubusercontent.com/45087061/105948534-ad62d700-609d-11eb-9ca9-db75ed8af249.png)


- Install NGINX pada server public dengan bantuan ansible-playbook.


![Screen Shot 2021-01-07 at 12 08 54](https://user-images.githubusercontent.com/45087061/105948656-e438ed00-609d-11eb-8d05-ef44cfa968b7.png)

![Screen Shot 2021-01-07 at 12 09 17](https://user-images.githubusercontent.com/45087061/105948611-ce2b2c80-609d-11eb-965f-4bfce89cbcf2.png)


- Setelah beberapa proses diatas, saya juga melakukan beebrapa eksperimen seperti melakukan git clone dan running Docker menggunakan ansible-playbook


Proses clone repository private menggunakan ssh:


![Screen Shot 2021-01-07 at 12 26 59](https://user-images.githubusercontent.com/45087061/105948803-3a0d9500-609e-11eb-8910-cddd17a862a8.png)

![Screen Shot 2021-01-07 at 12 34 59](https://user-images.githubusercontent.com/45087061/105948862-4eea2880-609e-11eb-8398-0e89a1e1d237.png)

NB: Untuk menambahkan ssh key ke github masih dilakukan secara manual


- Run docker untuk mengambil data dumbplay backend dan frontend, sehingga tidak perlu melakukan npm install maupun migrasi database. Serta mengambil data jenkins yang akan digunakan untuk melakukan build secara otomatis. Untuk proses instalasi jenkins sama persis dengan [minggu ke tiga](../../dumbweek3), hanya saja berbeda dalam proses otomatisasi dimana pada task ini dilakukan scheduling agar server tidak terbebani oleh proses build berulang kali.


![Screen Shot 2021-01-07 at 13 36 10](https://user-images.githubusercontent.com/45087061/105949068-b1432900-609e-11eb-98dc-bac0189fa256.png)