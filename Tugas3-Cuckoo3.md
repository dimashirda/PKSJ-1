# Tugas Final Project

### Anggota Kelompok

|Nama      |NRP    |
|---|---|
Rian Danis  | 5114100084
Naufan Arifie | 5114100136
Dimas Hirda P | 5114100147


### Cuckoo - Setting Koneksi Host Only

 - Jalankan perintah update Linux. (setting ip yang digunakan 192.168.56.1)
      ```bash
     vboxmanage hostonlyif create
     vboxmanage hostonlyif ipconfig vboxnet0 --ip 192.168.56.1<
     ```
 - Jika dilihat ip pada ifconfig maka akan keluar interface baru  seperti:
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Cuckoo/Cuckooip.png)
    

  - Lalu, setting NIC pada Virtualbox dengan command 
       ```bash
     vboxmanage modifyvm CuckooBox --hostonlyadapter1 vboxnet0
     vboxmanage modifyvm CuckooBox --nic1 hostonly
     ```
  
  - Nyalakan Virtualbox. Setelah masuk, setting IP pada Connection Properties dan isi dengan static ip yang sesubnet dengan ip host. Gateway diisi dengan IP host.
   
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Cuckoo/vb.png)

  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Cuckoo/vb2.png)
     
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Cuckoo/vb3.png)
     
     
   - Kemudian, untuk mengirim dan mentransfer paket dari host ke virtual machine, maka atur iptable dengan
      ```bash
     iptables -A FORWARD -o eth0 -i vboxnet0 -s 192.168.56.0/24 -m conntrack --ctstate NEW -j ACCEPT
     iptables -A FORWARD -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT
     iptables -A POSTROUTING -t nat -j MASQUERADE
     ```
   - Terakhir, kita harus meng-enable port forwarding pada terminal host
     ```bash
       echo 1 > /proc/sys/net/ipv4/ip_forward
      ``` 
      
  
### Cuckoo - Ambil Snapshot

- Pada Virtualbox. Di setting menu General, atur shared folder. Lalu pada mesin Ubuntu anda, isi folder itu dengan agent.py yang didapat di folder cuckoo.

  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Cuckoo/menushared.png)
   
-  Restart machine virtualbox. Lalu jalankan agent.py
-  Pada menu diatas virtualbox, pilih Menu Machine, lalu pilih take snapshot. Lalu save.

  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Cuckoo/takesnapshot.png)
  
  

### Cuckoo - Jalankan Cuckoo
 
 -  Buka terminal baru. Lalu jalankan command:
  ```bash
     cuckoo run webserver
   ```
   
   Maka, cuckoo akan mendeploy halaman web pada port 8000, sehingga cuckoo dapat dibuka pada alamat http://localhost:8000/
 
 -  Lalu pada terminal lain, jalankan command:
  ```bash
     cuckoo
   ```
 
   Maka proses cuckoo telah berjalan. Buka halaman websitenya.
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Cuckoo/web.png)
  
  Submit file malware
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Cuckoo/web2.png)
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Cuckoo/web3.png)
  
  
  Maka hasil analisis dapat didapatkan pada website.
  
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Cuckoo/web4.png)
  
  ![alt text](https://github.com/dimashirda/PKSJ-1/blob/master/PKSJ/Cuckoo/web5.png)
  
  
   

   
