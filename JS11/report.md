<h4>Nama        : Aqila Herfian F.S<h4>
<h4>NIM         : 254107020041<h4>
<h4>Kelas       : TI-1H<h4>
<h4>Mata Kuliah : System Operasi<h4>

## Praktikum 9.1
<img width="680" height="507" alt="image" src="https://github.com/user-attachments/assets/597bc57b-7d13-417e-b0f8-332ea62f9070" />

Analisis
1. Mengapa secret.txt tidak dapat dibaca oleh group dan others setelah chmod 600?
   - Karena digit kedua dan ketiga bernilai nol, maka sistem secara otomatis menutup semua akses bagi anggota grup maupun pengguna lain di luar pemilik file.
2. Apa perbedaan arti 600 dan 755 terhadap file yang diuji?
   - 600: Bersifat sangat privat. Hanya pemilik yang bisa membaca dan memodifikasi file. Mode ini biasanya digunakan untuk file sensitif seperti kunci SSH atau catatan pribadi.
   - 755: Bersifat publik/terbuka. Pemilik punya akses penuh (termasuk eksekusi), sedangkan group dan others diizinkan untuk membaca serta menjalankan file tersebut (eksekusi), namun tidak diizinkan untuk mengubah isinya.
3. Setelah umask 027, permission apa yang dihasilkan untuk file baru, dan mengapa bukan 777?
   - karena file secara default memang tidak seharusnya bisa dieksekusi saat pertama kali dibuat, dan umask 027 bertugas "menyaring" akses tulis bagi grup serta menutup seluruh akses bagi others.

## Praktikum 9.2
<img width="737" height="394" alt="image" src="https://github.com/user-attachments/assets/cb23dfb5-0e44-4385-9822-3bbfbc57dc84" />
<img width="635" height="437" alt="image" src="https://github.com/user-attachments/assets/62a668bb-d1e0-4edb-835a-e0c691d9236b" />

Analisis
1. Mengapa getfacl confidential.txt awalnya tidak menampilkan user tertentu?
   - Pada kondisi awal setelah perintah chmod 640, file confidential.txt hanya memiliki Standard Unix Permissions.
2. Setelah setfacl -m u:userA:r confidential.txt, apa perbedaan output ls -l dan getfacl?
   - Indikator Visual: Pada perintah ls -l, ditandai dengan munculnya simbol tambah (+) di akhir string izin.
   - Detail Akses: Perintah getfacl menjadi satu-satunya cara untuk melihat rincian pengguna spesifik (named user) dan mask yang telah ditambahkan.
3. Mengapa file inherited.txt mewarisi ACL dari direktori shared?
   - Pewarisan izin pada file inherited.txt terjadi karena implementasi Default ACL (flag -d) pada direktori induknya. Dengan mekanisme ini, setiap file baru yang dibuat di dalam direktori tersebut akan otomatis mengadopsi aturan akses yang telah ditentukan tanpa perlu diatur ulang secara manual.

## Praktikum 9.3A
<img width="675" height="419" alt="image" src="https://github.com/user-attachments/assets/fff0477b-355f-4d1e-8710-4ebb17eb3c00" />

Pertanyaan:
1. Apa perbedaan output id userA sebelum dan sesudah menambah group?
   - sebelum: Output hanya akan menampilkan grup primer (primary group) yang biasanya memiliki nama yang sama dengan username (misalnya: uid=1001(userA) gid=1001(userA) groups=1001(userA)).
   - sesudah: daftar pada bagian groups= akan bertambah. Ini menunjukkan bahwa userA kini memiliki hak akses atau izin yang dimiliki oleh grup baru tersebut tanpa kehilangan identitas grup primernya.
2. Bagaimana status passwd -S userB berubah saat akun di-lock?
   - Output passwd -S biasanya menunjukkan status P (Password set/usable) atau PS. Ini menandakan akun aktif dan bisa digunakan untuk otentikasi.
   - Setelah perintah -L dijalankan, status akan berubah menjadi L (Locked) atau muncul tanda seru (!) di depan hash password pada file /etc/shadow.

## Praktikum 9.3B
<img width="712" height="246" alt="image" src="https://github.com/user-attachments/assets/206359df-65bd-4152-938d-9a4b5c586252" />
Pertanyaan:
1. Apa yang ditampilkan id userA vs groups userA?
   - groups userA: Hanya menampilkan daftar nama grup yang diikuti oleh pengguna tersebut secara ringkas.
   - id userA: Menampilkan informasi yang jauh lebih lengkap dan teknis. Perintah ini merinci UID (User ID), GID (Group ID primer), serta daftar seluruh groups (grup tambahan) lengkap dengan nomor ID masing-masing grup.
2. Mengapa -a pada usermod -aG penting?
   - Flag -a adalah pengaman agar kita tidak sengaja menghapus hak akses (keanggotaan grup) yang sudah dimiliki pengguna sebelumnya saat ingin menambahkan grup baru.
  
## Praktikum 9.3C
<img width="681" height="317" alt="image" src="https://github.com/user-attachments/assets/74830e85-a95c-4514-a744-600878f14f60" />

Pertanyaan:
1. Apa arti nilai yang ditampilkan chage -l userA?
   - Perintah chage -l menampilkan rincian kebijakan masa berlaku kata sandi untuk pengguna tertentu.
2. Bagaimana cara membuktikan userB terkunci dari output passwd -S?
   - Status Terkunci: Akan muncul kode L (artinya Locked) atau simbol tanda seru (!) di depan nama pengguna.
   - Status Aktif: Akan muncul kode P (artinya Password usable) atau PS, yang menunjukkan akun dalam kondisi normal dan bisa digunakan untuk otentikasi.
3. Kapan sebaiknya menggunakan chage -d 0 vs passwd -e?
   - chage -d 0: Mengubah tanggal terakhir pengganti kata sandi menjadi 0 (Epoch), yang secara teknis membuat kata sandi dianggap sudah sangat lama dan kedaluwarsa. Ini adalah cara yang lebih "tradisional" dan sering digunakan dalam skrip otomatisasi atau saat baru membuat akun baru untuk mahasiswa.
   - passwd -e (expire): Perintah ini lebih modern dan lebih mudah diingat secara sintaksis karena langsung menargetkan status expired.

Tantangan
Buat user bernama intern yang:
• memiliki shell /bin/bash;
• menjadi anggota labgroup;
• dipaksa ganti password pada login pertama;
• password expired setelah 45 hari dengan warning 7 hari sebelumnya.
'''
sudo useradd -m -s /bin/bash -G labgroup intern
sudo passwd intern
sudo chage -M 45 -W 7 intern
sudo chage -d 0 intern
id intern
sudo chage -l intern
'''

## Praktikum 9.4
<img width="944" height="362" alt="image" src="https://github.com/user-attachments/assets/9b0a8791-55f9-4f58-8678-3bf155b8f91f" />

Analisis
1. Mengapa aturan disimpan di /etc/sudoers.d//, bukan langsung di /etc/sudoers?
   - Memudahkan pengelolaan hak akses secara terpisah untuk setiap user atau proyek tanpa mengganggu konfigurasi utama.
   - Mengurangi risiko kesalahan fatal yang dapat menyebabkan seluruh sistem terkunci jika file /etc/sudoers utama rusak.
   - Saat sistem operasi melakukan pembaruan, file konfigurasi utama /etc/sudoers sering kali ditimpa, sedangkan file di dalam .d/ akan tetap aman dan terjaga.
2. Mana perintah yang bisa dijalankan tanpa password, dan mana yang masih perlu autentikasi?
   - /usr/bin/apt update: Adanya direktif NOPASSWD: sebelum perintah tersebut.
   - /usr/bin/apt upgrade: Termasuk dalam daftar setelah direktif NOPASSWD:.
   - /bin/systemctl status *: (Perlu Autentikasi)	Tidak menggunakan direktif NOPASSWD, sehingga mengikuti kebijakan default sistem.
3. Informasi apa saja yang dicatat di log sudo?
   - Timestamp: Waktu dan tanggal saat perintah dijalankan.
   - Hostname: Nama mesin tempat perintah dieksekusi.
   - User Pengakses: Nama pengguna yang memicu perintah sudo (dalam hal ini userA).
   - Terminal (TTY): Lokasi terminal yang digunakan.
   - Direktori Kerja (PWD): Lokasi folder tempat pengguna berada saat menjalankan perintah.
   - User Target: Identitas pengguna yang hak aksesnya dipinjam (biasanya root).
   - Perintah: Perintah lengkap yang dijalankan oleh pengguna tersebut.

## Praktikum 9.5
<img width="585" height="225" alt="image" src="https://github.com/user-attachments/assets/f31ae6eb-c2f9-4929-9251-e745d472d18a" />

Analisis
1. Apa perbedaan soft limit dan hard limit saat quota mulai terlampaui?
   - Soft Limit: Merupakan ambang batas peringatan. Jika pengguna melewati batas ini, mereka masih bisa menulis data ke disk, namun sistem akan memberikan peringatan dan memulai perhitungan masa tenggang (grace period). Jika grace period habis dan pengguna belum menghapus file, maka soft limit akan berubah fungsinya menjadi hard limit.
   - Hard Limit: Merupakan batas mutlak yang tidak bisa ditawar. Begitu pengguna mencapai kapasitas ini (misalnya 10 MB atau 10240 KB), sistem akan secara paksa menghentikan semua proses penulisan data dan memunculkan pesan error "Disk quota exceeded".
2. Mengapa praktikum ini memakai loopback filesystem, bukan langsung /home/?
   - Mengonfigurasi kuota langsung pada /home/ atau partisi utama sangat berisiko.
   - Dengan loopback, kita membuat lingkungan "laboratorium" kecil di dalam file.
3. Dari output repquota, informasi apa yang menunjukkan quota sudah aktif?
   - aftar Statistik Penggunaan: Munculnya baris informasi yang mencakup kolom used, soft, dan hard untuk setiap user atau group.
   - Status Grace Period: Adanya kolom waktu (biasanya kosong jika belum melewati soft limit) yang menunjukkan sisa waktu yang diberikan kepada pengguna sebelum akses tulis diblokir.
   - Identitas User/Group: Munculnya nama pengguna (seperti userA) di dalam laporan tersebut membuktikan bahwa database kuota (aquota.user atau aquota.group) sudah berhasil dipetakan ke sistem berkas yang sedang diuji.

Tantangan
Coba atur quota baru untuk userA dengan batas inode yang sangat kecil, kemudian jelaskan kapan pembatasan
inode lebih penting daripada pembatasan block.
<img width="944" height="572" alt="image" src="https://github.com/user-attachments/assets/423f6662-40b0-43f1-ac37-1664a874900c" />

'''
sudo umount /mnt/quota-test 2>/dev/null
sudo rm /tmp/quota-test.img
sudo dd if=/dev/zero of=/tmp/quota-test.img bs=1M count=100
sudo mkfs.ext4 /tmp/quota-test.img

sudo mkdir -p /mnt/quota-test
sudo mount -o loop,usrquota,grpquota /tmp/quota-test.img /mnt/quota-test
mount | grep quota-test

sudo quotacheck -cugm /mnt/quota-test
sudo quotaon -v /mnt/quota-test
sudo repquota /mnt/quota-test
'''

## Latihan 9.A
<img width="745" height="635" alt="image" src="https://github.com/user-attachments/assets/6852e5ca-7664-4553-924c-954e8acb574a" />

1. - /usr/bin/passwd: Membutuhkan bit SUID karena user biasa perlu mengubah password mereka sendiri, yang artinya sistem harus menulis ke file sensitif /etc/shadow yang hanya bisa diakses oleh root.
   - /usr/bin/sudo: Digunakan untuk menjalankan perintah sebagai user lain. File ini harus memiliki SUID agar dapat melakukan verifikasi autentikasi terhadap database keamanan sistem.
   - /usr/bin/chage: Sesuai praktikum kita sebelumnya, file ini perlu SUID agar user bisa melihat atau mengubah informasi masa berlaku password mereka yang tersimpan di file sistem terproteksi.
2. Setiap direktori di luar sistem temporer (seperti direktori konfigurasi atau direktori aplikasi di /var/www/) yang memiliki permission 777. Risiko utamanya adalah Privilege Escalation, di mana penyerang bisa menyisipkan skrip berbahaya yang kemudian dijalankan oleh sistem atau user lain.
3. Konfigurasi
'''   
sudo mkdir -p /srv/webapp
sudo chgrp webapp-team /srv/webapp

sudo chmod 2775 /srv/webapp
sudo setfacl -m u:deploy:rx /srv/webapp

sudo setfacl -d -m g:webapp-team:rwx /srv/webapp
sudo setfacl -d -m u:deploy:rx /srv/webapp
'''

## Latihan 9.B
Buat user intern: Gunakan useradd dengan shell Bash agar user memiliki antarmuka terminal yang standar.
Tambahkan ke labgroup: Pastikan grup ini sudah ada sebelum menambahkan user ke dalamnya.
'''
sudo groupadd labgroup
sudo useradd -m -s /bin/bash -G labgroup intern
sudo passwd intern
'''
Maksimum umur password (-M): Diatur ke 45 hari.
Peringatan kedaluwarsa (-W): Diatur mulai 7 hari sebelum jatuh tempo.
Paksa ganti saat login pertama (-d 0): Memastikan user segera mengganti password bawaan saat pertama kali masuk ke sistem.
'''
sudo chage -M 45 -W 7 -d 0 intern
'''
Untuk memberikan izin systemctl status saja, kita harus membuat file konfigurasi khusus di direktori sudoers.d.
Modularitas: Menyimpan aturan di /etc/sudoers.d/ lebih aman daripada mengedit file utama.
Sintaks Perintah: Tentukan jalur lengkap binari perintah agar tidak bisa disalahgunakan.
'''
sudo visudo -f /etc/sudoers.d/sudo-intern
intern ALL=(root) /bin/systemctl status *
'''
Soft Limit vs Hard Limit: Soft limit memberikan peringatan, sedangkan hard limit memblokir penulisan data secara mutlak.
Blok vs Inode: Pembatasan block menjaga kapasitas (misal: 10MB), sedangkan inode menjaga jumlah file (misal: 100 file).
'''
sudo edquota -u intern
'''
Hasil Verifikasi yang Diharapkan
Untuk memastikan semua langkah berhasil, Kakak bisa menjalankan perintah audit berikut:
sudo chage -l intern: Pastikan password expires menunjukkan 45 hari ke depan.
sudo -l -U intern: Verifikasi bahwa user hanya boleh menjalankan systemctl status.
sudo repquota /home: Pastikan statistik kuota untuk user intern sudah muncul dengan batasan yang baru diatur.
