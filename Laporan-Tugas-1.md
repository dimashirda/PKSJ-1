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

4.  Jalankan Vagrant
  ```bash
  vagrant up
  ```
5. Masuk kedalam vagrant
  ```bash
  vagrant ssh
  ```
  
### 2. Instalasi openssh-server pada Vagrant

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
 
