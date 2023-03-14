# DOCKER

## 1. INSTALL DOCKER

1. update sistem dengan perintah berikut:

```sudo apt update```
```sudo apt upgrade```

![installdocker1](https://user-images.githubusercontent.com/82355684/225030924-af818535-bbbf-4c4b-b37e-f66165a5bd21.png)

![installdocker2](https://user-images.githubusercontent.com/82355684/225030934-9ec36b30-fb9d-41fe-9987-39e3716c4569.png)

2. install paket dependensi yag diperlukan

```sudo apt install apt-transport-https ca-certificates curl gnupg lsb-release```

![installdocker3](https://user-images.githubusercontent.com/82355684/225030944-b914cb56-1e68-4547-a3a1-3740aa588925.png)

3. tambahkan kunci GPG resmi Docker ke sistem

```curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg```

4. Tambahkan repository Docker ke sumber software Ubuntu

```echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null```

5. kemudian jalankan perintah berikut unutk memperbaharui paket

```sudo apt update```

![installdocker4](https://user-images.githubusercontent.com/82355684/225030954-8af3aa99-6f44-4bc6-8267-ddba9f97ce4a.png)

6. Install Docker

```sudo apt install docker-ce docker-ce-cli containerd.io```

![installdocker5](https://user-images.githubusercontent.com/82355684/225030963-e596c8ed-89e2-4870-b3bd-7c9d544aecea.png)

7. setelah instalasi selesai, periksa apakah docker berhasil diinstall

```sudo docker run hello-world```

![installdocker6](https://user-images.githubusercontent.com/82355684/225030971-a86b25d0-e90d-4157-8c74-2333acedb371.png)

**Command untuk melihat versi Docker**
* ```docker version```
* ```sudo docker --version```
* ```docker compose version```

