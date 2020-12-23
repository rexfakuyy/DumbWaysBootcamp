# SSL CONFIGURATION

- Karena pada Reverse Proxy housy-frontend.conf saya sudah ada certbot, maka saya hanya perlu mengaktifkan let's encrypt atau SSL pada Reverse Proxy housy-backend.conf melalui certbot di server public
  ![Screen Shot 2020-12-17 at 14 42 19](https://user-images.githubusercontent.com/45087061/102962715-fdd49b00-4519-11eb-9cd2-9bb3886e46f9.png)

- Ubah configurasi api pada server frontend dalam directory housy-frontend/src/config/
  ![Screen Shot 2020-12-17 at 15 13 00](https://user-images.githubusercontent.com/45087061/102962961-88b59580-451a-11eb-830a-9da463c654ec.png)

- Tes akses ke website https://api.reckypramana.instructype.com dan cek SSl certificate
  ![Screen Shot 2020-12-19 at 11 09 38](https://user-images.githubusercontent.com/45087061/102962922-6d4a8a80-451a-11eb-90a8-eeae62352548.png)

- Tes login dari https://reckypramana.instructype.com menggunakan user yang sudah dibuat tadi menggunakan Postman
  ![Screen Shot 2020-12-19 at 11 15 16](https://user-images.githubusercontent.com/45087061/102963006-a1be4680-451a-11eb-85f2-508ccf827dda.png)\
  ![Screen Shot 2020-12-19 at 11 16 14](https://user-images.githubusercontent.com/45087061/102963272-3aed5d00-451b-11eb-9f59-70a491564ad1.png)
