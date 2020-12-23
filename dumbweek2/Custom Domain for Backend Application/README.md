# CUSTOM DOMAIN

- Membuat domain baru di cloudflare dengan nama `api.reckypramana` dan saya matikan semua proxy, ganti menjadi `DNS Only` untuk server backend saya agar SSL lets encrypt tidak bentrok dengan SSL Cloudflare
  ![Screen Shot 2020-12-19 at 11 06 50](https://user-images.githubusercontent.com/45087061/102742240-047ed900-4387-11eb-9356-5f3046950338.png)

- Ubah konfigurasi `server_name` backend dari IP menjadi `api.reckypramana.instructype.com` pada file `housy-backend.conf` yang ada di /etc/nginx/sites-available/
