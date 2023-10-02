## Trillium

Trilium adalah aplikasi catatan hierarkis untuk membangun basis pengetahuan pribadi yang luas. Dengan hierarki, pengguna dapat mengorganisir informasi dengan baik. Fitur yang dimiliki cukup lengkap, yakni crud note, search, jump to note. Terdapat juga template/formatting untuk memudahkan user dalam membuat note seperti schedule, math formula, dan code block.



## Instalasi
[Back to top](#)

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
    


##  Maintenance
[Back to top](#)

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



## Cara Pemakaian
[Back to top](#)

Penggunaan Web App ini cukup mudah, interface di dalam web app sudah sangat membantu, berikut demo pemakaiannya:

1. Masuk ke [Trillium Notes](http://159.223.70.115:8080)

2. Pada halaman awal, ditampilkan navbar, list note, dan new tab

   ![image](https://github.com/mirzahm14/trillium-notes/assets/88041796/b8aaad10-f534-49e4-8b62-277eb1cd984b)

3. Untuk membuat note baru, user bisa klik new note pada navbar. Setelah membuat note baru, note akan masuk ke dalam list note sesuai dengan hari, tanggal, dan bulan dibuatnya note tersebut.

    ![image](https://github.com/mirzahm14/trillium-notes/assets/88041796/0e2b5c68-837f-4ccb-bcb4-e873a8f239ac)

4. Untuk mencari suatu note, user dapat klik search note pada navbar. Pada menu search ini, user dapat mengisi keyword note yang dicari dan terdapat beberapa opsi untuk membantu pencarian seperti ordered by, fast search, dsb.

    ![image](https://github.com/mirzahm14/trillium-notes/assets/88041796/d4537138-0690-4b97-82fa-5a15d04d27d6)
    
    ![image](https://github.com/mirzahm14/trillium-notes/assets/88041796/7d47ad9f-87e3-4df6-b0b3-5d91da8b1381)

5. User juga dapat langsung masuk ke note yang diinginkan dengan fitur "Jump to note". "Jump to note" dapat diklik pada navbar dan user tinggal mencari keyword notenya. Ketika user sudah memasukkan keyword, web otomatis mencari note dan ketika user mengklik note yang diinginkan, maka langsung akan masuk ke dalam note tersebut.

    ![image](https://github.com/mirzahm14/trillium-notes/assets/88041796/4266d4a0-dbee-4c7c-a71a-4ca5a0e0bfdf)

6. Terdapat fitur note map yang mana web akan menampilkan relasi tiap note yang ada. Note map ini dapat ditampilkan dengan 2 bentuk, yakni tree map dan link map

    ![image](https://github.com/mirzahm14/trillium-notes/assets/88041796/068a281a-7a8c-491b-adf4-80ad36cb0a29)
    
    ![image](https://github.com/mirzahm14/trillium-notes/assets/88041796/e8eaa1a5-8937-45e0-ae28-1fba65cf35c1)

7. Terdapat fitur calendar yang berguna untuk user melihat to-do dari tiap tanggal yang diisi. User tinggal hover tanggal yang diinginkan, dan nanti to-do pada hari itu akan muncul. User juga dapat masuk ke dalam overview notes pada hari yang diklik

    ![image](https://github.com/mirzahm14/trillium-notes/assets/88041796/0f11b2ef-dc0d-469b-bf38-a0234152f2ad)
    
    ![image](https://github.com/mirzahm14/trillium-notes/assets/88041796/ae6f6fd7-57ca-4f2a-b627-cda3b61e5dc5)

8. Selain fitur-fitur di atas, Trillium notes juga menyediakan berbagai fitur/template seperti schedule, math formatting, dan code blocking.

   ![image](https://github.com/mirzahm14/trillium-notes/assets/88041796/bdac6290-e811-45a1-9d61-7977b961a998)


    
## Pembahasan
[Back to top](#)

**Trillium** ini merupakan web app yang layak untuk digunakan mulai dari banyak fitur dan template yang bisa user gunakan hingga konsep hierarki yang diimplementasikan sehingga memudahkan user untuk melakukan track terhadap notes yang dibuat. Ada banyak web-app atau aplikasi sejenis Trillium, namun Trillium memiliki beberapa keunggulan, seperti:
1. Memiliki interface yang mudah dipahami
2. Beragam fitur yang bisa digunakan
3. Dapat digunakan di OS yang berbeda
4. Keamanan yang cukup baik dengan fitur enkripsi yang digunakan

Seperti aplikasi-aplikasi yang dibuat sebelumnya, pasti memiliki kekurangan. Begitupun dengan **Trillium** yang memiliki beberapa kekurangan, seperti:
1. Hanya bisa digunakan untuk 1 user karena tidak ada session atau sistem account yang diterapkan sehingga setiap user harus membuat server masing-masing
2. Tidak ada fitur kolaborasi
3. UI yang ditampilkan kurang menarik dan terlalu monoton

Ada banyak sekali web app yang sejenis dengan **Trillium**, salah satunya ialah Notion. Berikut beberapa perbandingan **Trillium** dengan Notion:
1. **Trillium** belum bisa mendukung penggunaan android dan IOS, sedangkan Notion sudah mendukung 2 OS tersebut
2. **Trillium** beriorientasi terhadap penggunaan pribadi, sedangkan notion lebih cocok digunakan untuk pekerjaan yang bersifat kolaboratif
3. UI Notion lebih minimalis, modern, dan fleksibel, sedangkan **Trillium** lebih monoton dan estetika UInya kurang diutamakan



## Referensi
[Back to top](#)

1. [Docker Installation](https://docs.docker.com/engine/install/ubuntu/) - Docker
2. [Trillium Documentation](https://github.com/zadam/trilium) - Github
3. [Trillium Remote Server Documentation](https://github.com/zadam/trilium/wiki/Docker-server-installation) - Github
