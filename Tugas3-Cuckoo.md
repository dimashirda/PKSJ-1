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
- <i>sudo adduser cuckoo</i>

#### 5. Instal Django-based web interface
- <i>sudo apt-get install mongodb</i>
 
#### 6. Instal TCPdump
- <i>sudo apt-get install tcpdump</i>
- <i>sudo apt-get install libcap2-bin</i>
- <i>sudo setcap cap_net_raw,cap_net_admin=eip /ust/sbin/tcpdump</i>
- <i>getcap /ust/sbin/tcpdump</i>

#### 7. Instal Volatility
-<i> sudo apt install git</i>
-<i> git clone https://github.com/colatilityfoundation/volatility.git</i>
-Navigasike folder volatility
     -cd /home/Username/volatility
-<i> sudo python setup.py install</i>

#### 8. install plug-in untuk Volatility
- Distorm3
     - Download Distorm3
     - Navigasi ke folder download
          -<i> tar -xvzf distorm-3.4.0.tar.gz</i>
     - Navigasi ke folder distorm-3.4.0
          - <i> cd /home/Username/Downloads/distorm-3.4.0</i>
     - <i> sudo python setup.py install</i>
- Yara
    - Instal autoreconf
         - <i> sudo apt-get install autoconf</i>
    - Instal libtool-bin
         -<i> sudo apt-get isntall libtool-bin</i>
    - Download Yara
    - Navigasi ke download folder
         - <i> tar -xvzf yara-3.5.0.tar.gz</i>
    - Navigasi ke folder yara-3.5.0
         - <i> cd /home/Username/Downloads/yara-3.5.0 </i>
    - <i> ./bootstrap.sh</i>
    - <i> /configure --withcrypto --enable-magic --enable-cuckoo </i>
    - <i> make </i>
    - <i> sudo make install </i>
    - <i> sudo -H pip install yara-python </i>
- PyCrypto
    - Download PyCrypto
    - Navigasi ke folder downloads
        -<i> tar -xvzf pycrypto-2.6.1.tar.gz</i>
    - Navigasi ke folder pycrypto-2.6.1
        - <i> cd /home/Username/Downloads/pycrypto-2.6.1</i>
    - <i> python setup.py build</i>
    - <i> sudo python setup.py install</i>
- Openpyxl
    - <i>sudo -H pip install openpyxl</i>
- UJSON
    - <i> sudo -H pip install ujson</i>
-IPython
    - <i> sudo -H pip install jupyter</i>
    
#### 9 Instal Mitmproxy
- <i> sudo apt-get install python3-pip python3-dev libssl-dev libtiff5-dev libjpeg8-dev zlib1g-dev libwebp-dev </i>
- <i> sudo pip3 install mitmproxy</i>
- <i> mitmproxy</i>
- <i> cd ~/.mitmproxy</i>
- <i> cp mitmproxy-ca-cert.p12 /home/Username/Downloads/cuckoo/analyzer/windows/bin/cert.p12</i>
- <i> mitmdump - /usr/local/bin/mitmdump </i>
