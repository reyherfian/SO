# Jobsheet 7
Aqila Herfian/03/TI-1H

## Tugas 1: Toolkit Bash Administrator
tujuan: membuat konsumisasi shell agar pekerjaan lebih efisien.
<img src="https://github.com/reyherfian/SO/blob/ca6c5550a032ec5ed03ddc25b0110b5d5126ac93/Minggu7/Tugas%201.png" alt="Tugas 1">
```
cat <<'EOF' >> ~/.bashrc
export PATH="$HOME/praktikum-os/week07-bash/bin:$PATH"
alias ll='ls -lah --color=auto'
alias hist10='history | tail -n 10'

backup_conf_absen03() {
    if [ $# -ne 1 ]; then echo "Usage: backup_conf_absen03 <file>"; return 1; fi
    cp -- "$1" "$HOME/praktikum-os/week07-bash/backup/$(basename "$1").bak"
    echo "Backup selesai di folder backup"
}
EOF
```
## Tugas 2 & 3
<img src="https://github.com/reyherfian/SO/blob/ca6c5550a032ec5ed03ddc25b0110b5d5126ac93/Minggu7/Tugas%202%263.png" alt="Tugas 2&3">
```
find /etc -name "*.conf" > audit-konfigurasi-absen03.txt 2> audit-error-absen03.log
echo "Jumlah file ditemukan: $(wc -l < audit-konfigurasi-absen03.txt)" | tee -a audit-konfigurasi-absen03.txt
```

```
cat <<'EOF' > ~/praktikum-os/week07-bash/bin/daily-healthcheck
#!/usr/bin/env bash
echo "--- Health Check Absen03 ---"
date
hostname
uptime -p
df -h /
free -h
EOF

chmod +x ~/praktikum-os/week07-bash/bin/daily-healthcheck
daily-healthcheck | tee healthcheck-absen03.log 
```

## Tugas 4
<img src="https://github.com/reyherfian/SO/blob/ca6c5550a032ec5ed03ddc25b0110b5d5126ac93/Minggu7/Tugas%204.png" alt="Tugas 4">

```
cd ~/praktikum-os/week07-bash/ruang-nama
touch "laporan server april.txt"
touch "backup [mingguan] server.conf"
echo "File yang akan diproses: " *.txt
cp -- "backup [mingguan] server.conf" "$HOME/praktikum-os/week07-bash/backup/"
cd ~/praktikum-os/week07-bash
tar -czf arsip-absen03.tar.gz backup/
```
