# การติดตั้งและใช้ Git สำหรับ macOS

## ติดตั้ง Git
ตรวจสอบว่า Git ได้ถูกติดตั้งใน macOS สามารถใช้ Homebrew เพื่อทำการติดตั้ง:

```
brew install git
```

## สร้างคีย์ SSH
สร้างคีย์ SSH เพื่อสามารถ clone private repository ได้:

```
ssh-keygen -t ed25519 -C "your_email@example.com"
cd ~
copy ssh key มาใส่ใน
https://github.com/settings/keys
```

## การตั้งค่า Git
กำหนดค่าข้อมูลผู้ใช้ Git:

```
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

## เริ่มต้น Git Repository
สร้าง Git repository ใหม่หรือ clone จาก repository ที่มีอยู่:

```
git init
# หรือ
git clone <repository_url>
```

## ทำการ Commit การเปลี่ยนแปลง
เพิ่มและทำการ Commit การเปลี่ยนแปลงไปยัง repository:

```
get status
git add .
git commit -m "Your commit message"
เพิ่ม -m "Your commit message" เพื่อ commit หลายบรรทัด
```

## การ Stash การเปลี่ยนแปลง
ทำการ Stash เพื่อนำ code ไปยัง branch อิ่นๆ:

```
git stash save "Your stash message"
```

## Stash หลายรอบ

```
git stash save "First stash message"
# ทำการเปลี่ยนแปลงเพิ่มเติม
git stash save "Second stash message"
```

## ดูรายการ Stash

```
git stash list
```

## ทำการ Apply Stash
ทำการ Apply Stash ไปยัง working directory:

```
git stash apply stash@{0}
```

## ทำการ Apply และ Drop Stash
ทำการ Apply Stash และลบ Stash ออกจากรายการ:

```
git stash pop stash@{0}
```

## Apply Stash ที่กำหนดเอง
ทำการ Apply Stash ที่กำหนดเอง:

```
git stash apply stash@{1}
```