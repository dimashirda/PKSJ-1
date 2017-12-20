# Tugas Final Project

### Anggota Kelompok

|Nama      |NRP    |
|---|---|
Rian Danis  | 5114100084
Naufan Arifie | 5114100136
Dimas Hirda P | 5114100147


### Cuckoo - Instalasi

#### 1. Linux
 - Instal Linux sebagai Sistem Operasi Utama
 - Jalankan perintah update Linux 
   -- <i> sudo apt-get update</i>
#### 2. Library Python
- Instal file dependensi python 
    - <i>sudo apt-get install python python-pip python-dev libffi-dev libssl-dev</i>
- instal libxml2-dev dan libxslt-dev 
    - <i> sudo apt-get install libxml2-dev libxslt-dev</i>
- instal kebutuhan text file menggunakan PyPl
    - Download Cuckoo Sandbox
         - extract file tar gz dengan 
              - <i> tar -xvzf</i>
    - Navigasi kedalam folder Cuckoo -- cd/home/Username/Downloads/cuckoo
    - jalankan
         - <i>sudo -H pip install -r requirements.txt</i>
         - <i>sudo -H pip install --upgrade pip</i>
#### 3. Software Virtualisasi
- instal VMware player
     - Downoad VMware Workstation Player
     - Navigasikan ke cd/home/Username/Downloads
     - <i> sudo chmod u+x VMWare-Player-12.5.1-4542065.x86_64.bundle</i>
     - <i> sudo ./VMWare-Player-12.5.1-4542065.x86_64.bundle</i>
#### 4. Buat subfolder untuk Cuckoo
- <i> sudo adduser cuckoo</i>
