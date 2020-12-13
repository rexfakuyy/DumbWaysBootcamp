# Custom Domain

- Buka Cloudflare lalu tambahkan DNS dari cloudflare dengan memasukkan nama sub-domain dan elastic-ip/ip-public dari Server Public
  ![1](https://user-images.githubusercontent.com/45087061/102004729-d1649600-3d45-11eb-977b-65ecd2209c4b.png)

- Edit file housy.conf pada directory etc/nginx/sites-available dan ganti server_name menjadi recky.instructype.com kemudian restart service nginx nya dengan\
`sudo systemctl restart nginx`
  ![2](https://user-images.githubusercontent.com/45087061/102004736-e4776600-3d45-11eb-8b22-ed46d015d95e.png)

- Tes akses website menggunakan server_name yang baru
  ![3](https://user-images.githubusercontent.com/45087061/102004747-fb1dbd00-3d45-11eb-8fa6-600917a54c38.png)
