# INSTALL DOCKER

- Menambahkan beberapa paket setelah melakukan update dan upgrade
  ### pada server Frontend dan Backend ###
```
sudo apt-get install curl apt-transport-https ca-certificates software-properties-common
```

Berikut keterangnya:

	- apt-transport-https = tansfer file dan data melalui https.
	- ca-certificates = untuk cek sertifikat keamanan
	- curl = transfer data
	- software-properties-common = script untuk mengelola software.

![Screen Shot 2020-12-24 at 09 59 37](https://user-images.githubusercontent.com/45087061/105944599-3aa22d80-6096-11eb-8358-a8c8b99b8648.png)
![Screen Shot 2020-12-24 at 10 01 18](https://user-images.githubusercontent.com/45087061/105944649-56a5cf00-6096-11eb-863b-3fe8242d6cfb.png)

- Menambahkan repository docker dan update paket
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt update
apt-cache policy docker-ce
```

![Screen Shot 2020-12-24 at 10 02 34](https://user-images.githubusercontent.com/45087061/105944717-763cf780-6096-11eb-9df1-92be00fdadca.png)
![Screen Shot 2020-12-24 at 10 02 38](https://user-images.githubusercontent.com/45087061/105944736-805ef600-6096-11eb-85e2-47c71dde09f2.png)


- Install docker pada server Frontend dan Backend
``` 
sudo apt install docker-ce
```

![Screen Shot 2020-12-24 at 10 10 48](https://user-images.githubusercontent.com/45087061/105944817-a5ebff80-6096-11eb-94bf-9def9688de40.png)

- Cek status docker
```
sudo systemctl status docker
```

![Screen Shot 2020-12-24 at 10 12 42](https://user-images.githubusercontent.com/45087061/105944868-bf8d4700-6096-11eb-83b8-c56cff117ed3.png)

- Test menjalankan hello-world docker
```
docker run hello-world
docker images
```

![Screen Shot 2020-12-24 at 10 13 37](https://user-images.githubusercontent.com/45087061/105944928-d6339e00-6096-11eb-8e86-c0f7e85c2f70.png)
![Screen Shot 2020-12-24 at 10 17 42](https://user-images.githubusercontent.com/45087061/105944992-f6fbf380-6096-11eb-91a6-ca08fb1ae192.png)

- Login ke docker
```
docker login
``` 
![Screen Shot 2020-12-24 at 10 15 19](https://user-images.githubusercontent.com/45087061/105945031-0c711d80-6097-11eb-92e7-e61fb803825b.png)
![Screen Shot 2020-12-24 at 10 18 06](https://user-images.githubusercontent.com/45087061/105945047-16931c00-6097-11eb-8da6-11a6e98a251b.png)