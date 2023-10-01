# Aplikasi Web "Trillium Notes"


## Sekilas Tentang

Deskripsi singkat tentang aplikasi tsb.


# Instalasi

#### Kebutuhan sistem
- Unix / Linux, Windows, macOS
- NodeJS 18+
- NPM 9+
- Docker

#### Proses Instalasi

1. Install Node dan NPM 
    - Node
        - Windows : Gunakan LTS yang tersedia pada https://nodejs.org/en/download
        - Linux : `sudo apt install nodejs`
    - NPM
        - Linux : `sudo apt install npm` 
2. Cek versi Node dan NPM dengan command : `npm -v` dan `node -v`

## Local Server
3. clone repositori **trilium** ke direktori lokal
    ```
    $ git clone https://github.com/zadam/trilium
    ```
4. pindah ke direktori trilium dan install dependancy npm
    ```
    $ cd trilium/
    $ npm install
    ```
5. Jalankan lokal server dengan
    ```
    $ npm run start-server
    ```
6. Server akan jalan pada port 8080 sehingga navigasi ke page browser dengan alamat ```localhost:8080```

## Remote Server / VPS
7. Cari penyedia layananan hosting (Digital Ocean / Google Cloud / AWS)

8. Projek kami menggunakan VPS Digital Ocean

    - Sign Up dan Sign In menggunakan akun yang tersedia
    - Buat First Project dan navigasi ke halaman **Droplet**
    - Pada halaman Droplet buat Virtual Machine (VM) dengan image **Ubuntu 20.04(LTS) x64**
    - Pilih **Authentication Method** dengan password
    - Ganti Hostname sesuai dengan yang diinginkan
    - Create Droplet / VM
9. Connect menggunakan ```ssh``` IP Address yang disediakan VPS dan masukan password

    ```$ ssh root@IPaddress ```

    <Image />

10. Tambah user sebagai superuser dengan :
    ```
    $ sudo adduser [username]
    $ sudo usermod -aG sudo [username]
    ```
11. Connect ssh dengan superuser dan masukan password user

    ```$ ssh user@IPAddrress```

12. Install Docker sesuai dengan image VM

    ```$ sudo apt install docker-ce ```

13. Buat Firewall Rules pada VPS

    - Klik page **Networking** pada VM
    - Pilih edit Firewall dan create Firewall
    - Masukan nama Firewall
    - Pada section **Inbound Rules** pilih **custom** dan pilih port yang diinginkan (misal:8080)
    - Pastikan VM sudah terpilih untuk rules firewall yang dibuat

14. Pull Image Trilium

    ```$ sudo docker pull zadam/trilium:latest```

15. Jalankan image pada remote server
    
    ``` $ sudo docker run -d -p 0.0.0.0:8080:8080 -v ~/trilium-data:/home/node/trilium-data zadam/trilium:latest```

16. Aplikasi dapat diakses dengan IP Adress VPS dengan Port yang sudah dibuat

    [159.223.70.115:8080](http://159.223.70.115:8080)


## Konfigurasi (opsional)

Setting server tambahan yang diperlukan untuk meningkatkan fungsi dan kinerja aplikasi, misalnya:
- batas upload file
- batas memori
- dll

Plugin untuk fungsi tambahan
- login dengan Google/Facebook
- editor Markdown
- dll


##  Maintenance

1. Cek status port

    ```
    $ sudo apt install net-tools
    $ sudo netstat -tulpn
    ```
2. Cek status Docker image

    ```
    $ sudo docker ps
    ```

3. Terminate dan Hapus Docker image

    ```
    $ sudo docker kill [image_id]
    $ sudo docker rm [image_id] 
    ```


## Otomatisasi (opsional)

Skrip shell untuk otomatisasi instalasi, konfigurasi, dan maintenance.


## Cara Pemakaian

- Tampilan aplikasi web
- Fungsi-fungsi utama
- Isi dengan data real/dummy (jangan kosongan) dan sertakan beberapa screenshot


## Pembahasan

- Pendapat anda tentang aplikasi web ini
    - kelebihan
    - kekurangan
- Bandingkan dengan aplikasi web lain yang sejenis


## Referensi

Cantumkan tiap sumber informasi yang anda pakai.
