# INSTALL APPLICATION

- Sebelumnya install docker-compose karena docker dan docker-compose adalah 2 aplikasi yang berbeda.
```
sudo curl -L "https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

docker-compose --version

```

- Membuat file `docker-compose.yml` dengan isi seperti berikut

Untuk backend:

![Screen Shot 2020-12-24 at 11 25 54](https://user-images.githubusercontent.com/45087061/105943923-df237000-6094-11eb-9330-862d052181b7.png)


Untuk frontend:

![Screen Shot 2020-12-24 at 11 33 16](https://user-images.githubusercontent.com/45087061/105943965-f2ced680-6094-11eb-8dc2-90526d2e6113.png)

- Menjalankan docker compose dengan perintah 

```
docker-compose up -d
```

backend:

![Screen Shot 2020-12-24 at 11 43 00](https://user-images.githubusercontent.com/45087061/105944044-1d209400-6095-11eb-8d54-fe6759790885.png)


frontend:

![Screen Shot 2020-12-26 at 09 33 33](https://user-images.githubusercontent.com/45087061/105944317-a768f800-6095-11eb-8eb6-60f4cae51f8d.png)

- Cek apakah docker compose sudah berjalan menggunakan `docker ps`
