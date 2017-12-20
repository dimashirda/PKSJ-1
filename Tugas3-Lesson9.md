# Tugas Final Project

### Anggota Kelompok

|Nama      |NRP    |
|---|---|
Rian Danis  | 5114100084
Naufan Arifie | 5114100136
Dimas Hirda P | 5114100147


### DVWA
  ### Lesson 9
  #### 1. Edit Index.php di metasploitable
  
  ```bash
  cd /var/www/dvwa/vulnerabilities/xss_s
  sudo nano index.php
  ```
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%209/250.PNG)
  
  Mengganti limit menjadi 250 command sekaligus
  
  #### 2. login dan pastikan setting sekuritas low
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%209/low.PNG)
  
  #### 3. Uji coba
  
  Test 1
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%209/test1.PNG)
  
  Menguji coba xss exploit test
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%209/test1_result.PNG)
  
  Reset database setiap akan melakukan uji coba berikutnya
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%209/reset.PNG)
  
  Test 2 dan hasilnya
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%209/test2.PNG)
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%209/test2_result.PNG)
  
  Test 3 dan hasilnya
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%209/test3.PNG)
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%209/test3_result.PNG)
  
  
