# Repository PKSJ 2015/2016


Anggota Kelompok
- Ardi Nusawan      5113100096
- Gian Sebastian A. 5113100132
- Ronauli Sidabukke 5113100142 

## Pendahuluan
**SNORT**
Snort adalah sebuah software yang berguna untuk mengamati aktivitas dalam suatu jaringan komputer. Snort dapat digunakan sebagai suatu Network Intrusion Detection System (NIDS) yang berskala ringan (lightweight).

Cara Kerja Snort




Komponen – komponen Snort IDS (Intrusion Detection System) meliputi :

-Rule Snort : database yang berisi pola – pola serangan berupa signature jenis -jenis serangan. Rule snort harus selalu terupdate secara rutin agar ketika ada suatu teknik serangan yang baru, serangan tersebut dapat terdeteksi.
-Snort Engine : program yang berjalan sebagai daemon proses yang selalu bekerja untuk membaca paket data dan kemudian membadingkan dengan Rule Snort.
-Alert : catatan serangan pada deteksi penyusupan. Jika Snort engine mendeteksi paket data yang lewat sebagai sebuah serangan, maka snort engine akam mengirimkan alert berupa log file. Kemudian alert tersebut akan tersimpan di dalam database.
