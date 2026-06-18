<h4>Nama        : Aqila Herfian F.S<h4>
<h4>NIM         : 254107020041<h4>
<h4>Kelas       : TI-1H<h4>
<h4>Mata Kuliah : System Operasi<h4>

## Praktikum 10.1
```
systemctl list - units -- type = service -- state = running
```
<img width="810" height="781" alt="image" src="https://github.com/user-attachments/assets/48e54e8c-13fe-4e66-87bc-06e3be23955c" />

```
systemctl list - unit - files -- type = service | head -30
```
<img width="793" height="781" alt="image" src="https://github.com/user-attachments/assets/7f5ae5c4-ff96-4252-8d35-56e3c3d30c21" />

```
systemd - analyze
systemd - analyze blame | head -15

```
<img width="561" height="316" alt="image" src="https://github.com/user-attachments/assets/2fa0b0df-fbc6-4981-96a1-b47572f2d247" />

## Praktikum 10.2
```
systemctl status ssh
systemctl is - active ssh
systemctl is - enabled ssh
```
<img width="680" height="188" alt="image" src="https://github.com/user-attachments/assets/e13829d4-c7ef-4dc9-a090-60e4c1fc778a" />

```
sudo systemctl restart ssh
systemctl status ssh
```
<img width="810" height="339" alt="image" src="https://github.com/user-attachments/assets/7c9a2b45-1fac-434d-8c17-cef231979bdf" />

```
systemctl list - dependencies ssh
```
<img width="464" height="811" alt="image" src="https://github.com/user-attachments/assets/d784a6b7-bace-43e8-8dd0-38d7b28e3403" />

## Praktikum 10.3
<img width="906" height="539" alt="image" src="https://github.com/user-attachments/assets/bfd39a89-9be9-4c6b-9440-66de466d672a" />

## Praktikum 10.4
<img width="942" height="816" alt="image" src="https://github.com/user-attachments/assets/ac2339b6-e2c2-4175-94c0-d395c1cfb634" />

## Praktikum 10.5
<img width="775" height="803" alt="image" src="https://github.com/user-attachments/assets/fb9db470-6773-43f9-8154-7051ebea7a0e" />

## 1.7 Latihan
### Latihan 10.1
```
systemctl list-units --type=service --state=running
```
<img width="862" height="814" alt="image" src="https://github.com/user-attachments/assets/7ef3233a-3fa9-4f78-9891-9388c5e150ea" />
```
systemd-analyze blame | head -5
```
<img width="579" height="118" alt="image" src="https://github.com/user-attachments/assets/a79d1b9c-8a5c-4baa-874e-0fa3fd991193" />
```
systemctl --failed
journalctl -u demo-web.service -n 30 --no-pager
```
<img width="932" height="594" alt="image" src="https://github.com/user-attachments/assets/3fc97a9c-c85e-4448-bdf6-138603059d4b" />

### Latihan 10.2
```
# Membuat folder praktikum
mkdir -p ~/lab-os/chapter10-services
cd ~/lab-os/chapter10-services

# Membuat dan membuka skrip dengan nano
nano monitor-disk.sh
```
```
#!/bin/bash

while true
do
    echo "=== Penggunaan Disk pada $(date) ==="
    df -h /
    echo "-----------------------------------"
    sleep 30
done
```
```
chmod +x monitor-disk.sh
```
<img width="469" height="420" alt="image" src="https://github.com/user-attachments/assets/4297d9cc-79b5-44af-9c25-1e32af41e260" />
<img width="805" height="115" alt="image" src="https://github.com/user-attachments/assets/6cd26e25-957f-450a-add3-a35c750f6bdf" />

### Latihan 10.3
<img width="937" height="821" alt="image" src="https://github.com/user-attachments/assets/c7bda9f4-390b-4dde-853d-781e2b2605b9" />
