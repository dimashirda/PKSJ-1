# Tugas Final Project

### Anggota Kelompok

|Nama      |NRP    |
|---|---|
Rian Danis  | 5114100084
Naufan Arifie | 5114100136
Dimas Hirda P | 5114100147

### Cuckoo - Konfigurasi

- Buka Terminal
- Navigasi ke direktori file konfigurasi
    - /home/Username/Downloads/cuckoo/conf

#### cuckoo.conf
- <i>nano cuckoo.conf</i>
    - [cuckoo]
        - memory_dump = on
        - machinery = virtualbox atau vmware
    - [resultserver]
        - ip = (ip dari host system, bukan virtual machine)

#### auxiliary.conf
- <i> nano auxiliary.conf</i>
    - [mitm]
        - enable = yes
    - [sniffer]
        - interface = (network interface dari virtual machine)
        
#### vmware.conf
- <i> nano vmware.conf</i>
    - [vmware]
        - machines = (nama virtual machine)
        - interface = (nama network interface dari virtual machine)
    - [Nama_virtual_machine]
        - vmx_path = ./nama_virtual_machine/nama_virtual_machine.vmx
        - ip = ip address dari virtual machine

#### processing.conf
- <i> nano processing.conf</i>
    - [memory]
        - enable = yes

#### memory.conf
- <i>nano memory.conf</i>
    -[basic]
        -guest_profile = nama profil volatility dari guest operating system

#### reporting.conf
- <i> nano reporting.conf</i>
    - [reporthtml]
        - enable = yes
    - [mongodb]
        - enable = yes
