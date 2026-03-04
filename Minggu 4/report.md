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





