# Jobsheet 4
Aqila Herfian/03/TI-1H

## Percobaan 1: Directory
1. Melihat direktori HOME
   ```
   $ pwd
   $ echo $HOME
   ```
<img src="https://github.com/reyherfian/SO/blob/9871bb61f603ad6efb2c255f9df2b607d59af02b/Minggu%204/JS%204%20percobaan%201.png" alt="latihan 1">

2. Melihat direktori aktual dan parent direktori
```
   $ pwd
   & cd .
   $ pwd
   $ cd ..
   $ pwd
   $ cd
```
<img src="https://github.com/reyherfian/SO/blob/9871bb61f603ad6efb2c255f9df2b607d59af02b/Minggu%204/JS%204%20percobaan%201.2.png" alt="langkah 2">

3. Membuat satu direktori, lebih dari satu direktori atau sub direktori
   ```
   $ pwd
   $ mkdir A B C A/DA/E B/F A/D/A
   $ ls -l
   $ ls -l A
   $ ls -l A/D
   ```
<img src="https://github.com/reyherfian/SO/blob/9871bb61f603ad6efb2c255f9df2b607d59af02b/Minggu%204/JS%204%20percobaan%201.3.png" alt="langkah 3">

4. Menghapus satu atau lebih direktori hanya dapat dilakukan pada direktori kosong dan hanya dapat dihapus oleh pemiliknya kecuali bila diberikan ijin aksesnya
   ```
   $ rmdir B
   $ ls -l B
   $ rmdir B/F B
   $ ls -l B
   ```
<img src="https://github.com/reyherfian/SO/blob/9871bb61f603ad6efb2c255f9df2b607d59af02b/Minggu%204/JS%204%20percobaan%201.4.png" alt="langkah 4">
- $ rmdir B terdapat eror karena direktori B tidak kosong. Jika ada file atau subdirektori, rmdir pasti gagal.
- kalau B tidak ada di folder sekarang, $ ls -l B perintah itu pasti error.

5. Navigasi direktori dengan instruksi cd untuk pindah dari satu direktori ke direktori lain.
   ```
   $ pwd
   $ ls -l
   $ cd A
   $ pwd
   $ cd ..
   $ pwd
   $ cd /home/<user>/C
   $ pwd
   $ cd /<user/C
   $ pwd
   ```
<img src="https://github.com/reyherfian/SO/blob/9871bb61f603ad6efb2c255f9df2b607d59af02b/Minggu%204/JS%204%20percobaan%201.5.png" alt="latihan 5">
- cd /user/C error karena path yang ditulis tidak ada.

## Percobaan 2: Manipulasi file
1. Perintah cp untuk mengkopi file atau seluruh direktori
   ```
   $ cat > contoh
   membuat sebuah file
   [Ctrl-d]
   $ cp contoh contohl
   $ ls -l
   $ cp contoh A
   $ ls -l A
   $ cp contoh contohl A/D
   $ ls -l A/D
   ```
<img src="https://github.com/reyherfian/SO/blob/0056f8ace890e179892940e84ea3622e9e658f89/Minggu%204/JS%204%20percobaan%202.png" alt="langkah 1">

2. Perintah mv untuk memindah file
   ```
   $ mv contoh contoh2
   $ ls -l
   $ mv contohl contoh2 A/D
   $ ls -l A/D
   $ mv contoh contohl C
   $ ls -l C
   ```
<img src="https://github.com/reyherfian/SO/blob/0056f8ace890e179892940e84ea3622e9e658f89/Minggu%204/JS%204%20percobaan%202.2.png" alt="langkah 2">

3. perintah rm untuk menghapus file
   ```
   $ rm contoh2
   $ ls -l
   $ rm -i contoh
   $ rm -rf A C
   $ ls -l
   ```
<img src="https://github.com/reyherfian/SO/blob/0056f8ace890e179892940e84ea3622e9e658f89/Minggu%204/JS%204%20percobaan%202.3.png" alt="langkah 3">

## Percobaan 3: Symbolic link
   ```
$ echo "Hallo apa khabar" > halo.txt
$ ls -l
$ ln halo.txt z
$ ls -l
$ cat z
$ mkdir mydir
$ ln z mydir/halo.juga
$ cat mydir/halo.juga
ln -s z bye.txt
$ ls -l bye.txt
$ cat bye.txt
```
<img src = "https://github.com/reyherfian/SO/blob/ba97e5757f5fa1ddb5d7bc064a36670df909d423/Minggu%204/JS%204%20percobaan%203.png" alt = "percobaan 3">

## percobaan 4
```
$ ls -l
$ file halo.txt
$ fil bye.txt
```
<img src = "https://github.com/reyherfian/SO/blob/494cf9a9b6a3d956a755a57d112c0ed234ba3a82/Minggu%204/JS%204%20percobaan%204.png" alt = "percobaan 4">

## percobaan 5
< img src = "https://github.com/reyherfian/SO/blob/5b5297f50b6198de6973ce91cf63fd4287ec85fa/Minggu%204/JS%204%20percobaan%205.png" alt = "percobaan 5">

## percobaan 6
<img src = "https://github.com/reyherfian/SO/blob/d5385a5f791d71112dd80ff2f5c7c1e798aee73a/Minggu%204/JS%204%20percobaan%206.png" alt = "percobaan 6">

## Latihan 1
<img src = "https://github.com/reyherfian/SO/blob/8161158e8a2a7818c2a02f65a1fb1563a8d61f80/Minggu%204/JS%204%20latihan%201.1.png">

<img src = "https://github.com/reyherfian/SO/blob/8161158e8a2a7818c2a02f65a1fb1563a8d61f80/Minggu%204/JS%204%20latihan%201.2.png">

<img src = "https://github.com/reyherfian/SO/blob/8161158e8a2a7818c2a02f65a1fb1563a8d61f80/Minggu%204/JS%204%20latihan%201.3.png">

<img src = "https://github.com/reyherfian/SO/blob/8161158e8a2a7818c2a02f65a1fb1563a8d61f80/Minggu%204/JS%204%20latihan%202.png">

<img src = "https://github.com/reyherfian/SO/blob/8161158e8a2a7818c2a02f65a1fb1563a8d61f80/Minggu%204/JS%204%20latihan%203.png">

<img src = "https://github.com/reyherfian/SO/blob/8161158e8a2a7818c2a02f65a1fb1563a8d61f80/Minggu%204/JS%204%20latihan%2045.png">

<img src = "https://github.com/reyherfian/SO/blob/8161158e8a2a7818c2a02f65a1fb1563a8d61f80/Minggu%204/JS%204%20latihan%20678.png">

## Laporan Resmi
a. - Perintah pwd (Print Working Directory) digunakan untuk memastikan posisi folder kamu saat ini agar tidak salah saat memanipulasi file. 
   - Perintah cd .. berfungsi untuk naik satu tingkat ke folder "induk"       (parent), sementara cd ~ atau cd saja akan selalu membawa kamu pulang ke    folder Home user.
   - Penggunaan ls -l memberikan informasi detail seperti tipe file (karakter pertama), izin akses, pemilik, dan waktu modifikasi.
   - cp (copy) menduplikasi file ke lokasi baru tanpa menghapus aslinya.
   - mv (move) memindahkan file atau bisa juga digunakan untuk mengubah nama file (rename).
   - rm (remove) menghapus file secara permanen. Penggunaan flag -i (interactive) sangat disarankan untuk pemula agar sistem meminta konfirmasi sebelum menghapus
   - Hard Link: Membuat nama lain untuk data yang sama. Jika file asli dihapus, data tetap ada selama masih ada link lain yang menunjuk ke sana
   - Soft Link (Symbolic): Berfungsi seperti shortcut di Windows. Jika file asli dihapus, link ini akan rusak (broken link) karena ia hanya menunjuk ke alamat file aslinya.
     
b. <img src = "https://github.com/reyherfian/SO/blob/bc6313a5017dae57eda1ab9b72bdc9bd3727163f/Minggu%204/JS%204%20laoran%20resmi.png">

c. - "rmdir: failed to remove 'B': Directory not empty": Penyebab: Perintah rmdir hanya dapat digunakan untuk menghapus direktori yang benar-benar kosong. Kesalahan ini muncul karena direktori B masih memiliki sub-direktori atau file di dalamnya, seperti folder F
- "No such file or directory": Sistem tidak dapat menemukan file atau direktori yang dimaksud karena kesalahan penulisan nama atau jalur (path). Perlu diperhatikan bahwa Linux bersifat case sensitive, sehingga penggunaan huruf besar dan kecil sangat berpengaruh (contoh: A dan a dianggap berbeda)
- "Permission denied": Pengguna mencoba mengakses atau memodifikasi file/direktori yang memiliki hak akses terbatas, seperti direktori /etc atau /root yang hanya boleh dikelola oleh superuser.

## kesimpulan
Sistem file pada Linux diatur secara hirarkhikal menyerupai pohon (tree) yang dimulai dari direktori root dengan simbol /.
Linux memiliki standar direktori dengan fungsi yang spesifik, seperti /etc untuk file konfigurasi administrasi , /dev untuk representasi perangkat keras , /proc sebagai pseudo-filesystem yang berisi informasi kernel dan proses , serta /home sebagai tempat penyimpanan data bagi pengguna umum.
Melalui instruksi baris perintah (command line), pengguna dapat melakukan manipulasi file dan direktori secara cepat, mulai dari pencarian file menggunakan find atau locate , hingga pencarian teks spesifik di dalam file menggunakan perintah grep.


