# CREATE DOCKER IMAGES

- Membuat Dockerfile dengan isi sebagai berikut
  ![Screen Shot 2020-12-24 at 12 49 28](https://user-images.githubusercontent.com/45087061/105941420-fc097480-608f-11eb-93d6-9c3d2e95cdf7.png)

- Build dengan perintah sebagai berikut `docker build -t namaimage:tag .`
  ![Screen Shot 2020-12-24 at 10 24 36](https://user-images.githubusercontent.com/45087061/105941606-628e9280-6090-11eb-9135-717c8f2a2fa9.png)

- Cek docker images yang sudah di build `docker images`
  ![Screen Shot 2020-12-24 at 10 25 10](https://user-images.githubusercontent.com/45087061/105941671-86ea6f00-6090-11eb-968b-766871a2952a.png)

- Membuat container dari image yang sudah ada
    - `docker container create --name namacontainer -p portlocal:portaplikasi namaimage:tag`
    - `docker container start namacontainer`
  ![Screen Shot 2020-12-24 at 10 44 38](https://user-images.githubusercontent.com/45087061/105941829-de88da80-6090-11eb-9433-248e36b250c8.png)
  ![Screen Shot 2020-12-24 at 10 45 22](https://user-images.githubusercontent.com/45087061/105941845-e8124280-6090-11eb-9b5c-f48b1528def9.png)

### NB: pastikan port tidak bentrok dengan aplikasi lain. ###

- Cek jika container sudah berjalan dengan `docker ps`

- Untuk push image, buat image dengan format akundocker/namaimage:tag dan pastikan sudah login terlebih dahulu. lalu jalankan perintah \
  `docker push namaimage:tag`
  ![Screen Shot 2020-12-24 at 11 19 48](https://user-images.githubusercontent.com/45087061/105942265-7686c400-6091-11eb-89c2-006e5d6bd3de.png)

### Docker Hub saya: ###

[reckyprmn/housyfrontend](https://hub.docker.com/repository/docker/reckyprmn/housyfrontend) \
[reckyprmn/housybackend](https://hub.docker.com/repository/docker/reckyprmn/housybackend)