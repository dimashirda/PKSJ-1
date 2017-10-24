# Tugas 1 Perancangan Sistem Keamanan Jaringan 2017

## Langkah-Langkah Pengerjaan

### 1. Setup Environment untuk Vagrant

1.  Siapkan folder agar memiliki vagrant
  ```bash
  vagrant init
  ```
2.  Buka Vagrantfile di terminal
  ```bash
  nano Vagrantfile
  ```
3.  Isi Vagrantfile seperti berikut

![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%201/Screenshot%20from%202017-10-22%2012-29-52.png)

Hapus comment pada baris 

* config.vm.box = "hashicorp/precise64"
* config.vm.network "private_network", ip:
* save Vagrantfile

Perhatikan dalam kasus kami, IP vagrant : 192.168.33.10

4.  Jalankan Vagrant
  ```bash
  vagrant up
  ```

5. Masuk kedalam vagrant
  ```bash
  vagrant ssh
  ```
  
### 2. Instalasi dan setup openssh-server pada Vagrant

1.  Update repositori
  ```bash
  sudo apt-get update
  ```
2.  Install openssh-server
  ```bash
  sudo apt-get install openssh-server
  ```
3.  Cek apakah openssh-server sudah terinstall
  ```bash
  sudo service ssh status
  ```
4.  Set password pada openssh-server
  ```bash
  sudo su
  passwd
  ```
  Dalam kasus ini password dalam server kami : tes

### 3. Instalasi Tools Hydra,Ncrack, dan Medusa pada terminal desktop

1.  Buka terminal baru di desktop

2.  Update repositori
  ```bash
  sudo apt-get update
  ```
3.  Install Tool yang dibutuhkan terlebih dahulu untuk tools
  ```bash
  sudo apt-get install build-essential checkinstall libssl-dev libssh-dev
  ```
4.  Install Hydra
  ```bashT  sudo apt-get install hydra
  ```
5. Install Ncrack

a. Buka link https://nmap.org/ncrack/ dan install ncrack-0.5.tar.gz

b. Extrack dan compile file
  ```bash
tar -xzf ncrack-0.5.tar.gz
cd ncrack-0.5
./configure
make
su root
make install
  ```      
6. Install Medusa

 ```bash
sudo apt-get install medusa
  ```  
  
  
7.  Cek installasi
 ```bash
 hydra
  ``` 
   ```bash
  ncrack
  ```
   ```bash
  medusa
```  
  
  Jika keluar manual penggunaan tools, maka tools telah terinstall.
 
  
### 4. Penggunaan Hydra
1. Penggunaan hydra harus mempunyai list keyword password terlebih dahulu
   Maka buat txt berisi list possible password
 ```bash
  gedit list.txt
  ```   
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%201/serang4.png)
  
  Perhatikan bahwa password yang benar berada di urutan terakhir untuk mempersulit pencarian

2. Jalankan Hydra
 ```bash
  hydra -l [username] -P [text_password] [ip_target] -t [jumlah_thread] [tipe_protocol]
  ```   
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%201/serang5.png)
  
### 5. Penggunaan Ncrack
1. Jalankan Ncrack

 ```bash
  ncrack -p [port] --user [username] -P [text_password] [ip_target]
  ```   
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%201/serang6.png)
  
### 6. Penggunaan Medusa
1. Jalankan Medusa
 ```bash
 medusa -u root -P list.txt -h 192.168.33.10 -M sshMedusa v2.2_rc3 [http://www.foofus.net] (C) JoMo-Kun / Foofus Networks <jmk@foofus.net>
 ```
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Tugas%201/medusacomplete.png)
  
### 7. Instalasi dan penggunaan fail2ban

1.  Update Repositori
```bash
sudo apt-get update
```
2.  Install fail2ban
```bash
sudo apt-get install fail2ban
```
3.  Cek status fail2ban
```bash
sudo service fail2ban status
```
4.  Selain itu kita juga perlu menginstall iptables-persistent
```bash
sudo apt-get install iptables-persistent
```
