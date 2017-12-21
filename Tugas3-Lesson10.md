# Tugas Final Project

### Anggota Kelompok

|Nama      |NRP    |
|---|---|
Rian Danis  | 5114100084
Naufan Arifie | 5114100136
Dimas Hirda P | 5114100147


### DVWA
  ### Lesson 10
  
  #### 1. Pastikan sudah login, dan setting sekuritas low. Buka halaman CSRF
  Basic operation mengubah password melalui CSRF, password akan diganti menjadi "abc123"
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%2010/CSRF.PNG)
  
  #### 2. Ganti url
  Merubah url password menjadi password yang lain, misal "test123"
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%2010/Change_to_test.PNG)
  
  Logout, dan login lagi dengan password baru
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%2010/login_again.PNG)
  
  #### 3. Mengganti password melalui Curl
  Ambil cookie dengan memasukkan script di menu xss reflected
  
  <script>alert(document.cookie)</script>
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%2010/xss_reflected.PNG)
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%2010/Cookie.PNG)
  
  Copykan ke leafpad, dan buat sintax untuk curl
  ```bash
  curl --cookie"xxxxxxx" --location"xxxxxxx"
  ```
  Bagian cookie diganti dengan cookie yang telah didapatkan, dan location adalah url mengganti password tadi
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%2010/crul.PNG)
  
  Copy-paste ke terminal di folder root
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%2010/curl_terminal.PNG)
  
  Jika berhasil akan muncul seperti ini
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%2010/pass_change.PNG)
  
  Silahkan login dengan password yang terakhir diganti
  
  
  
  
  
  
  
  
