# Jobsheet 6
Aqila Herfian/03/TI-1H

# Latihan 6.A
1. Jalankan ps aux –forest dan temukan proses dengan PID 1. Apa
nama dan fungsi proses tersebut dalam sistem Linux modern?
- nama proses ini adalah systemd atau init
- Proses pertama yang dijalankan oleh kernel saat booting dan bertanggung jawab untuk memulai layanan sistem lain.
- <img src="https://github.com/reyherfian/SO/blob/18772fdd7eb278f9fe4f05bf04a5b80da78e0d13/Minggu%206/JS%206%20A1.png" alt="A1">

2. Hitung berapa proses yang dimiliki oleh user root dan berapa yang
dimiliki oleh user Anda. Mengapa root memiliki lebih banyak proses?
- terdapat 87 root. Karena ia menjalankan layanan sistem inti, drivr, dan manajemen hardware yang diperlukan agar sistem operasi tetap berjalan stabil di background.
- <img src="https://github.com/reyherfian/SO/blob/18772fdd7eb278f9fe4f05bf04a5b80da78e0d13/Minggu%206/JS%206%20A2.png" alt="A2">

3. Temukan semua proses yang berada dalam kondisi S. Mengapa sebagian
besar proses di sistem berada dalam kondisi ini?
- kebanyakan berstatus sleeping karena sedang menunggu perintah dan tidak butuh tenaga CPU saat itu.
- <img src="https://github.com/reyherfian/SO/blob/18772fdd7eb278f9fe4f05bf04a5b80da78e0d13/Minggu%206/JS%206%20A3.png" alt="A3">

# Latihan 6B
1.  Jalankan tiga perintah sleep dengan durasi 100, 200, dan 300 detik di
background. Verifikasi ketiganya dengan jobs.
- <img src="https://github.com/reyherfian/SO/blob/18772fdd7eb278f9fe4f05bf04a5b80da78e0d13/Minggu%206/JS%206%20B1.png" alt="B1">
2.  Bawa job kedua ke foreground, jeda dengan Ctrl+Z , lalu kembalikan
ke background dengan bg.
- <img src="https://github.com/reyherfian/SO/blob/18772fdd7eb278f9fe4f05bf04a5b80da78e0d13/Minggu%206/JS%206%20B2.png" alt="B2">
3.  Bawa job kedua ke foreground, jeda dengan Ctrl+Z , lalu kembalikan
ke background dengan bg.
- <img src="https://github.com/reyherfian/SO/blob/18772fdd7eb278f9fe4f05bf04a5b80da78e0d13/Minggu%206/JS%206%20B3.png" alt="B3">

# Latihan 6C
1. Jalankan dua proses sleep: satu dengan nice +5 dan satu dengan nice
+15. Verifikasi nilai NI keduanya dengan ps.
- <img src="https://github.com/reyherfian/SO/blob/18772fdd7eb278f9fe4f05bf04a5b80da78e0d13/Minggu%206/JS%206%20C1.png" alt="C1"> 
2. Gunakan renice untuk mengubah nice proses pertama menjadi +10.
Proses mana yang kini lebih diprioritaskan scheduler?
- proses dengan nilai +1= lebih diprioritaskan oleh scheduler dibandingkan proses dengan +15.
- <img src="https://github.com/reyherfian/SO/blob/18772fdd7eb278f9fe4f05bf04a5b80da78e0d13/Minggu%206/JS%206%20C2.png" alt="C2">
3. Kirim SIGSTOP ke salah satu proses, verifikasi kondisi T-nya, lalu kirim
SIGCONT. Akhiri semua proses percobaan dengan pkill sleep
- <img src="https://github.com/reyherfian/SO/blob/18772fdd7eb278f9fe4f05bf04a5b80da78e0d13/Minggu%206/JS%206%20C3.png" alt="C3">
