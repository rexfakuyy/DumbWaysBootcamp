# INSTALL GIT AND SSH KEY

- Fork repository housy-frontend dan housy-backend milik mas sugeng, sehingga saya mendapat salinan repository tersebut tanpa perlu mengcopy secara manual, setelah berhasil duplikat repo yang sudah didapat dan jadikan private repository
  ![Screen Shot 2020-12-15 at 17 44 06](https://user-images.githubusercontent.com/45087061/102737314-af889600-4379-11eb-885a-7a731e429ddb.png)
  ![Screen Shot 2020-12-15 at 17 46 25](https://user-images.githubusercontent.com/45087061/102737352-c4fdc000-4379-11eb-8149-457cbedeae0f.png)

- Buatlah SSH keygen pada server frontend dan server backend dengan perintah `ssh-keygen` dan ikuti perintah selanjutnya.
  ![Screen Shot 2020-12-15 at 18 41 08](https://user-images.githubusercontent.com/45087061/102737478-1efe8580-437a-11eb-916f-830e66720727.png)

- Lihat isi file id_rsa.pub yang berisikan ssh key yang akan digunakan dengan perintah `cat id_rsa.pub`, kemudian tambahkan ke akun github, lalu jalankan perintah `ssh -T git@github.com` untuk menghubungkan komputer dengan akun github yang sudah terisi SSH.
  ![Screen Shot 2020-12-15 at 18 41 37](https://user-images.githubusercontent.com/45087061/102737680-a9df8000-437a-11eb-9477-709755a9ce0b.png)
  ![Screen Shot 2020-12-15 at 18 48 21](https://user-images.githubusercontent.com/45087061/102737799-f1660c00-437a-11eb-85f4-d1847f713d1f.png)
  ![Screen Shot 2020-12-15 at 19 00 51](https://user-images.githubusercontent.com/45087061/102737727-c7144e80-437a-11eb-8af4-5e775d5990a5.png)
  ![Screen Shot 2020-12-19 at 10 01 08](https://user-images.githubusercontent.com/45087061/102737846-122e6180-437b-11eb-8a05-bdc4e09f6205.png)

- Jalankan perintah `git clone git@github.com:rexfakuyy/housy-frontend.git` untuk ujicoba mengambil repository private dari akun github, lalu coba ubah script pada file README.md jalankan perintah:
  - `git add .`
  - `gt commit -m ""`
  - `git push`
  ![Screen Shot 2020-12-15 at 19 05 25](https://user-images.githubusercontent.com/45087061/102738081-ac8ea500-437b-11eb-8ff5-6c7827f40dbd.png)
