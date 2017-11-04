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
 2. ```bash
    sudo apt-get update && apt-get upgrade
    sudo apt-get install lamp-server^
    ```
 3. Install PHP modules
    ```bash
    sudo apt-get install php7.0 php7.0-mysql libapache2-mod-php7.0 php7.0-cli php7.0-cgi php7.0-gd ```
 4. 
