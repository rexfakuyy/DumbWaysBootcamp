# PROSES INSTALASI SERVER NGINX DAN DEPLOY APLIKASI NODEJS
## Instalasi NGINX

```markdown
1. Hal pertama yang harus dilakukan setelah instalasi server ubuntu ialah mengupdate dan upgrade paket yang sudah ada dengan perintah sudo apt update kemudian dilanjutkan dengan sudo apt upgrade.
```
![step 1](https://user-images.githubusercontent.com/45087061/101566419-8b37cb80-3a01-11eb-98bc-c1fb577f8afa.png)
![step 2](https://user-images.githubusercontent.com/45087061/101566813-39437580-3a02-11eb-8eeb-ec7464fa534d.png)

```markdown
2. Setelah proses upgrade selesai barulah install nginx dan jalankan servicenya.
```
![step 3](https://user-images.githubusercontent.com/45087061/101566832-48c2be80-3a02-11eb-96a5-bd0aef448975.png)
![step 4](https://user-images.githubusercontent.com/45087061/101566913-6f80f500-3a02-11eb-9eeb-71cd682ebe06.png)

```markdown
3. Uji coba mengakses server nginx pada komputer lokal dengan cara memasukkan ip servernya
```
![step 5](https://user-images.githubusercontent.com/45087061/101566991-9808ef00-3a02-11eb-9576-55b45ba87a27.png)

---
## Instalasi NodeJS dan Deploy Aplikasinya (Housy)

```markdown
1. Untuk melakukan instalasi nodejs cukup menjalankan perintah sudo apt -y install nodejs atau *curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash* untuk versi 10.x
```
![step 6](https://user-images.githubusercontent.com/45087061/101567286-21202600-3a03-11eb-8efb-fb13cd90064f.png)

```markdown
2. Kemudian reboot VMnya lalu ketik *nvm install 10* dan cek versinya dengan *node -v* dan *npm -v* untuk npmnya
```
![step 7](https://user-images.githubusercontent.com/45087061/101567481-765c3780-3a03-11eb-8a22-839fd6641f47.png)
![step 8](https://user-images.githubusercontent.com/45087061/101567621-bf13f080-3a03-11eb-8c48-7430e65c3f25.png)
![step 9](https://user-images.githubusercontent.com/45087061/101567696-dd79ec00-3a03-11eb-9fbb-6f897cc94c2b.png)

```markdown
3. Clone repository yang ada pada https://github.com/DumbwaysDotId/DW15WDTPH_housy ke server local untuk nantinya di deploy
```
![step 10](https://user-images.githubusercontent.com/45087061/101567848-2b8eef80-3a04-11eb-828d-f7e8acbb0601.png)

```markdown
4. Setelah itu cd ke DW15WDTPH_housy untuk menginstall semua paket yang ada dengan menjalankan perinyah *npm install*
```
![step 11](https://user-images.githubusercontent.com/45087061/101567909-482b2780-3a04-11eb-9307-d9972eff10e0.png)
![step 12](https://user-images.githubusercontent.com/45087061/101568011-6d1f9a80-3a04-11eb-8af4-8c5b5ca65eba.png)

```markdown
5. Selanjutnya jika semua paket terinstall, jalankan perintah *npm start* agar aplikasi bisa diakses pada komputer local
```
![step 13](https://user-images.githubusercontent.com/45087061/101568101-9dffcf80-3a04-11eb-8a6f-4c702cc7f42a.png)
![step 14](https://user-images.githubusercontent.com/45087061/101568129-a8ba6480-3a04-11eb-96b9-ce95faa12cc7.png)

```markdown
6. Hasilnya bisa diakses dengan 192.168.100.12:3000

**Noted:** port 3000 adalah port default dari NodeJS nya.
```
![step 15](https://user-images.githubusercontent.com/45087061/101568339-ff27a300-3a04-11eb-8b4d-7aa4788e5aed.png)
