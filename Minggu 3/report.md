# Jobsheet 3
Aqila Herfian/03/TI-1H

### Latihan 3.1
```sudo ls -lhS /var/log | head -10 | tee large-logs.txt```
<img src="https://github.com/reyherfian/SO/blob/b66c273755b7caf3de8d097985b3699ea6e5dda1/Minggu%203/JS%203%20(1).png" alt="latihan 3.1">

### Latihan 3.2
```cut -d: -f1 /etc/passwd | sort | tee sorted-users.txt```
<img src="https://github.com/reyherfian/SO/blob/b66c273755b7caf3de8d097985b3699ea6e5dda1/Minggu%203/JS%203%20(2).png" alt="latihan 3.2">

### Latihan 3.3
```
#!/bin/bash

LOGFILE="/home/amoebadut/monitor.log"

for i in $(seq 1 12); do
  echo "=== $(date '+%Y-%m-%d %H:%M:%S') ===" | tee -a "$LOGFILE"
  top -bn1 | grep "Cpu(s)" | tee -a "$LOGFILE"
  free -h | grep "Mem:" | tee -a "$LOGFILE"
  sleep 5
done
```
<img src="https://github.com/reyherfian/SO/blob/b66c273755b7caf3de8d097985b3699ea6e5dda1/Minggu%203/JS%203%20(4).png" alt="latihan 3.3">

### Latihan 3.4
```find / -name "*.conf" 2>/dev/null | tee conf-files.txt | wc -l```
<img src="https://github.com/reyherfian/SO/blob/b66c273755b7caf3de8d097985b3699ea6e5dda1/Minggu%203/JS%203%20(3).png" alt="latihan 3.4">
<img src="https://github.com/reyherfian/SO/blob/b66c273755b7caf3de8d097985b3699ea6e5dda1/Minggu%203/JS%203%20(5).png">

### Latihan 3.5
```
#!/bin/bash

TIMESTAMP="$(date '+%Y-%m-%d %H:%M:%S')"

echo "[$TIMESTAMP] Backup dimulai" | tee -a backup-success.log

tar -czvf backup.tar.gz $HOME 2>> backup-error.log | tee -a backup-success.log

echo "[$TIMESTAMP] Backup selesai" | tee -a backup-success.log
```
<img src="https://github.com/reyherfian/SO/blob/b66c273755b7caf3de8d097985b3699ea6e5dda1/Minggu%203/JS%203%20(6).png" alt="latihan 3.5">
