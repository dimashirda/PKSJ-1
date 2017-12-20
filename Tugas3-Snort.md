# Repository PKSJ 2015/2016


Anggota Kelompok
- Naufan Arifie S   5114100136
- Rian Danis P.     5114100132
- Dimas Hirda P.    5114100147 

## Pendahuluan
**SNORT**

Snort adalah sebuah software yang berguna untuk mengamati aktivitas dalam suatu jaringan komputer. Snort dapat digunakan sebagai suatu Network Intrusion Detection System (NIDS) yang berskala ringan (lightweight).

Cara Kerja Snort




Komponen – komponen Snort IDS (Intrusion Detection System) meliputi :

-Rule Snort : database yang berisi pola – pola serangan berupa signature jenis -jenis serangan. Rule snort harus selalu terupdate secara rutin agar ketika ada suatu teknik serangan yang baru, serangan tersebut dapat terdeteksi.
-Snort Engine : program yang berjalan sebagai daemon proses yang selalu bekerja untuk membaca paket data dan kemudian membadingkan dengan Rule Snort.
-Alert : catatan serangan pada deteksi penyusupan. Jika Snort engine mendeteksi paket data yang lewat sebagai sebuah serangan, maka snort engine akam mengirimkan alert berupa log file. Kemudian alert tersebut akan tersimpan di dalam database.


## Langkah Langkah

**Install dependencies**

Sebelum menginstall Snort, terlebih dahulu menginstall file yang dibutuhkan oleh Snort.
 ```bash
  apt-get install openssh-server ethtool build-essential libpcap-dev libpcre3-dev libdumbnet-dev bison flex zlib1g-dev liblzma-dev openssl libssl-dev
  ```
  
  Lalu, install DAQ
  ```bash
  wget https://www.snort.org/downloads/snort/daq-2.0.6.tar.gz
  ```
   
  Setelah DAQ selesai didownload, extract file dan install file DAQ
  
  ```bash
  tar -zxvf daq-2.0.6.tar.gz
  cd daq-2.0.6
  ./configure && make && make install 
  ```
  **Install Snort**
  Install Snort dengan command:
  ```bash
  sudo apt-get install snort
  ```
   **Download file PCAP**
  Donwload file Pcap yang telah disediakan oleh SecRepo pada http://www.secrepo.com/
  
   **Running Snort**
   Setelah mendapatkan file pcap, jalankan Snort pada folder yang sama pada Pcap dengan command:
    ```bash
    sudo snort -v -c /etc/snort/snort.conf -r "namafile"
    ```
   
   **Gambar Percobaan kami**
   
   
   ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Snort/snortrun.png)
   ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Snort/snortresult1.png)
   ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Snort/snortresult2.png)
   ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Snort/snortresult3.png)
   
