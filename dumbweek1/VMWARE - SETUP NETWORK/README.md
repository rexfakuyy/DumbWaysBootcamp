# KONFIGURASI VM AGAR DAPAT TERHUBUNG KE JARINGAN INTERNET

```markdown
1. Pilih *Setting* pada VirtualBox lalu klik *Network*. Ubah adapter 1 ke *Bridged Adapter* kemudian pilih hardware komputer lokal yang terhubung ke internet (dalam kasus saya en0: Wi-Fi (AirPort))
```
![step 8](https://user-images.githubusercontent.com/45087061/101562594-4b211a80-39fa-11eb-8b4f-c92040e040ac.png)

```markdown
2. kemudian saat proses instalasi OS, Network connections ubah ip dari DHCP ke STATIC dan masukkan ip secara manual.

**Noted:** pada bagian *Name servers* isi dengan DNS sesuai provider masing-masing. Disini saya isi dengan 192.168.100.1
```
![step 12](https://user-images.githubusercontent.com/45087061/101562945-f5993d80-39fa-11eb-8fa1-cd6466719d87.png)

```markdown
3. Setelah proses instalasi selesai cek ip menggunakan perintah **ifconfig** dan cek ping ke google untuk memastikan server sudah terhubung ke internet
```
![step 23](https://user-images.githubusercontent.com/45087061/101563337-a99ac880-39fb-11eb-93fb-107fd36532e4.png)
![step 24](https://user-images.githubusercontent.com/45087061/101563506-f088be00-39fb-11eb-9b6d-66574faab8b9.png)
