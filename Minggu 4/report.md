# Jobsheet 3
Aqila Herfian/03/TI-1H

## Percobaan 1: Directory
1. Melihat direktori HOME
   *$ pwd*
   *$ echo $HOME*
<img src="https://github.com/reyherfian/SO/blob/9871bb61f603ad6efb2c255f9df2b607d59af02b/Minggu%204/JS%204%20percobaan%201.png" alt="latihan 1">

2. Melihat direktori aktual dan parent direktori
   *$ pwd*
   *& cd .*
   *$ pwd*
   *$ cd ..*
   *$ pwd*
   *$ cd*
<img src="https://github.com/reyherfian/SO/blob/9871bb61f603ad6efb2c255f9df2b607d59af02b/Minggu%204/JS%204%20percobaan%201.2.png" alt="langkah 2">

3. Membuat satu direktori, lebih dari satu direktori atau sub direktori
   *$ pwd*
   *$ mkdir A B C A/DA/E B/F A/D/A*
   *$ ls -l*
   *$ ls -l A*
   *$ ls -l A/D*
<img src="https://github.com/reyherfian/SO/blob/9871bb61f603ad6efb2c255f9df2b607d59af02b/Minggu%204/JS%204%20percobaan%201.3.png" alt="langkah 3">

4. Menghapus satu atau lebih direktori hanya dapat dilakukan pada direktori kosong dan hanya dapat dihapus oleh pemiliknya kecuali bila diberikan ijin aksesnya
   *$ rmdir B*
   *$ ls -l B*
   *$ rmdir B/F B*
   *$ ls -l B*
<img src="https://github.com/reyherfian/SO/blob/9871bb61f603ad6efb2c255f9df2b607d59af02b/Minggu%204/JS%204%20percobaan%201.4.png" alt="langkah 4">
*$ rmdir B* terdapat eror karena direktori B tidak kosong. Jika ada file atau subdirektori, rmdir pasti gagal.
*kalau B tidak ada di folder sekarang, *$ ls -l B* perintah itu pasti error.

5. Navigasi direktori dengan instruksi cd untuk pindah dari satu direktori ke direktori lain.
   *$ pwd*
   *$ ls -l*
   *$ cd A*
   *$ pwd*
   *$ cd ..*
   *$ pwd*
   *$ cd /home/<user>/C*
   *$ pwd*
   *$ cd /<user/C*
   *$ pwd*
<img src="https://github.com/reyherfian/SO/blob/9871bb61f603ad6efb2c255f9df2b607d59af02b/Minggu%204/JS%204%20percobaan%201.5.png" alt="latihan 5">
* cd /<user>/C* error karena path yang ditulis tidak ada.
