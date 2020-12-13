# SERVER PUBLIC FOR REVERSE PROXY

- Pada tampilan seperti ini, pilih `Launch a virtual machine`
  ![1](https://user-images.githubusercontent.com/45087061/101750801-16988600-3b02-11eb-9da7-b8720bf531d9.png)

- Pilih OS yang akan digunakan untuk server, disini saya menggunakan Ubuntu server 18.04
  ![2](https://user-images.githubusercontent.com/45087061/101751756-39776a00-3b03-11eb-9025-b2a114ca3d32.png)

- Pilih spesifikasi ram pada server, tidak perlu terlalu besar karena hanya akan digunakan untuk mendeploy aplikasi sederhana
  ![3](https://user-images.githubusercontent.com/45087061/101752619-4e083200-3b04-11eb-807c-6b5283ddf28f.png)

- Konfigurasi koneksi yang akan digunakan oleh server, pastikan memilih opsi `Disable` pada `Auto-assign Public IP` agar ip menjadi static dan tidak akan berubah-ubah setelah server di restart
  ![4](https://user-images.githubusercontent.com/45087061/101783212-92a7c380-3b2c-11eb-9239-e578b4a6316f.png)

- Atur storage yang akan digunakan, disini yang saya ganti hanya bagian Size dari default 8GB menjadi 15GB.
  ![5](https://user-images.githubusercontent.com/45087061/101784452-1b732f00-3b2e-11eb-8170-718a05310e29.png)

- `Configurasi security group` agar user hanya bisa mengakses beberapa port yang sudah di sediakan, dalam hal ini yang dibutuhkan adalah:

    SSH : agar server bisa diakses lewat komputer lokal\
    HTTP : agar website bisa diakses public\
    HTTPS : agar website bisa dipasang SSL
  ![6](https://user-images.githubusercontent.com/45087061/101784581-48274680-3b2e-11eb-8bea-cff7c50e7174.png)

- Klik `Launch`, lalu buat key pair baru yang nantinya akan digunakan untuk login ke server menggunakan SSH. Beri nama untuk `Key pair name`, setelah itu `Download Key Pair`, lalu `Launch Instances`
  ![7](https://user-images.githubusercontent.com/45087061/101785162-00ed8580-3b2f-11eb-87de-48d6a6d815ad.png)

- Setelah proses instalasi server selesai akan terlihat tampilan seperti ini pada AWS Console bagian Instances.\
Tapi server yang telah dibuat tidak memiliki public ip, jadi harus ditambahkan Elastic IP terlebih dahulu agar server bisa diakses dari komputer lokal
  ![8](https://user-images.githubusercontent.com/45087061/101785591-8709cc00-3b2f-11eb-9f5f-f734847ea194.png)

- Pada Dashboard sebelah kiri geser kebawah untuk pilih `Elastic IPs` lalu `Allocate Elastic IP address`
  ![9](https://user-images.githubusercontent.com/45087061/101786020-01d2e700-3b30-11eb-9c72-dd5675d0f01b.png)

- Klik `Allocate`
  ![10](https://user-images.githubusercontent.com/45087061/101786659-c258ca80-3b30-11eb-9f1e-6bf5bf1ec3e0.png)

- Tambahkan Elastic IP yang sudah didapat ke server public dengan cara klik pada bagian `Actions` lalu pilih `Associate Elastic IP address`
  ![11](https://user-images.githubusercontent.com/45087061/101786886-0fd53780-3b31-11eb-86cd-5fe4eb998f66.png)

- Pada bagian `Instance` pilih instance yang telah dibuat lalu klik `Associate`
  ![12](https://user-images.githubusercontent.com/45087061/101787180-63478580-3b31-11eb-8348-b477b9621ba3.png)

- Setelah selesai akan tampil seperti ini
  ![13](https://user-images.githubusercontent.com/45087061/101787431-a7d32100-3b31-11eb-817d-0e3a80b514d4.png)

---

# SERVER PRIVATE FOR APPLICATION

Untuk konfigurasi server Private cara konfigurasinya kurang lebih sama, hanya pada `Configure Security Group` cukup menggunakan `All trafic`, kemudian pada bagian `Source` diganti menjadi `My IP` untuk IP Private milik Server Public. Server ini juga tidak memerlukan Elastic IP.
![14](https://user-images.githubusercontent.com/45087061/101787847-1f08b500-3b32-11eb-9bc3-35b2f8e67c85.png)

Setelah selesai maka akan jadi seperti ini yang akan diberi nama\
`recky-private-srv`
![15](https://user-images.githubusercontent.com/45087061/101788361-963e4900-3b32-11eb-80fd-ecc76bd9b85d.png)

---

# SSH KE SERVER PUBLIC

Cara berikut saya lakukan pada kedua server untuk menghilangkan key-pair saat login:
- Buka terminal pada komputer lalu ubah permission pada file key-pair yang telah di download tadi dengan perintah `chmod 400 key-pair.pem`

![16](https://user-images.githubusercontent.com/45087061/101788871-2f6d5f80-3b33-11eb-92c5-b1d0a5ba6ad8.png)

- Kemudian login ssh dari terminal komputer menggunakan perintah `ssh -1 key-pair ubuntu@ip-public`, gunakan IP Public pada instance yang telah dibuat

![17](https://user-images.githubusercontent.com/45087061/101789491-f1247000-3b33-11eb-8209-dc090656f6eb.png)

- Setelah berhasil masuk akan seperti ini
![18](https://user-images.githubusercontent.com/45087061/101789922-714ad580-3b34-11eb-8fc9-4acf262c026a.png)

- Tambahkan user baru dengan perintah `sudo adduser nama-user` kemudian beri akses sudo pada user tersebut menggunakan `sudo usermod -aG sudo nama-user`.
![19](https://user-images.githubusercontent.com/45087061/101790375-f635ef00-3b34-11eb-855a-ad476584ffcb.png)
![20](https://user-images.githubusercontent.com/45087061/101790754-65134800-3b35-11eb-844b-5382a688a511.png)

- Kemudian edit file yang ada dalam `/etc/ssh/sshd_config` dan ganti `PasswordAuthentication` dari `No` ke `Yes`
![21](https://user-images.githubusercontent.com/45087061/101790990-9f7ce500-3b35-11eb-931f-8f1ee5f6ec5b.png)

- Restart service sshd nya dengan perintah `sudo systemctl restart sshd` dan cek jika sudah running dengan `sudo systemctl status sshd`
![22](https://user-images.githubusercontent.com/45087061/101791043-ac99d400-3b35-11eb-9f8d-46b6895f92d6.png)

- Test login menggunakan user baru
![23](https://user-images.githubusercontent.com/45087061/101791422-16b27900-3b36-11eb-9372-5cf23aad9989.png)

---

# SSH KE SERVER PRIVATE

Untuk masuk ke server private kita harus masuk terlebih dahulu ke instance server public setelah itu baru bisa login ssh menggunakan IP Privatenya server private:
- Buka terminal di komputer lokal anda kemudian jalankan perintah\
`ssh namauser@ippublic-serverpublic-anda`
![24](https://user-images.githubusercontent.com/45087061/102003203-b8081d80-3d36-11eb-972e-a4bedc08e3bf.png)

- Kemudian jalankan perintah berikut untuk masuk ke server private\
`sudo ssh -i key-pair namauser@ipprivate-serverprivate-anda` dan masukkan password user dari server public kita
![25](https://user-images.githubusercontent.com/45087061/102003267-b7bc5200-3d37-11eb-96f4-b9d57ef15d3a.png)

- Buat nama user baru seperti pada server public untuk memudahkan login ssh pada server private. Jalankan perintah `sudo adduser nama-user` dan beri password loginnya beserta keterangan kemudian beri akses sudo pada user tersebut menggunakan `sudo usermod -aG sudo nama-user`.
![26](https://user-images.githubusercontent.com/45087061/102003343-acb5f180-3d38-11eb-84cf-29d3fa9533df.png)

- Kemudian edit file yang ada dalam `/etc/ssh/sshd_config` dan ganti `PasswordAuthentication` dari `No` ke `Yes`
![27](https://user-images.githubusercontent.com/45087061/102003423-e0dde200-3d39-11eb-974a-303a9266998b.png)

- Restart service sshd nya dengan perintah `sudo systemctl restart sshd` dan cek jika sudah running dengan `sudo systemctl status sshd`
![28](https://user-images.githubusercontent.com/45087061/102003444-1256ad80-3d3a-11eb-9afc-9c0401cb7427.png)

- Test login menggunakan user baru
![29](https://user-images.githubusercontent.com/45087061/102003475-8e50f580-3d3a-11eb-847d-28b28a57353e.png)
