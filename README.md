
# 📚 Student Registration System (ระบบลงทะเบียนนักศึกษา)

ระบบจัดการข้อมูลนักศึกษาแบบครบวงจรด้วย Django พร้อมรองรับการ deploy บน Render.com

---

## 🧾 รายละเอียดโปรเจกต์

ระบบนี้ถูกพัฒนาด้วย Django Framework มีฟีเจอร์หลัก ๆ ดังนี้:

- เพิ่ม/ลบ/แก้ไข/ค้นหา/แสดงรายชื่อนักศึกษา
- อัปโหลดรูปภาพนักศึกษา
- ระบบเทมเพลต HTML พร้อม Bootstrap (ผ่าน templates)
- พร้อมใช้งานทันทีทั้งแบบ local และบน Render

---

## ⚙️ เทคโนโลยีที่ใช้

- Python 3.10+
- Django 4.x
- SQLite (ฐานข้อมูล local)
- Gunicorn (สำหรับ production server)
- Render (สำหรับ deploy ออนไลน์)

---

## 📦 วิธีติดตั้งและใช้งาน (Local)

### 1. โหลดโปรเจกต์
ดาวน์โหลด ZIP จาก GitHub หรือ clone:
```bash
git clone https://github.com/yourusername/student_register.git
cd student_register
```

### 2. สร้าง virtual environment และ activate
```bash
python -m venv venv
venv\Scripts\activate        # สำหรับ Windows
source venv/bin/activate      # สำหรับ macOS/Linux
```

### 3. ติดตั้ง dependencies
```bash
pip install -r requirements.txt
```

### 4. สร้างฐานข้อมูลและรันเซิร์ฟเวอร์
```bash
python manage.py makemigrations
python manage.py migrate
python manage.py runserver
```

แล้วเข้าเว็บที่: [http://127.0.0.1:8000](http://127.0.0.1:8000)

---

## 🌐 Deploy ขึ้น Render

### ✅ โครงสร้างที่ Render รองรับ:
- `manage.py` อยู่ root
- `requirements.txt` อยู่ root
- Django project folder คือ `student_register/`
- Start command ใช้ `gunicorn student_register.wsgi`

### 1. ไปที่ https://dashboard.render.com → New → Web Service
ตั้งค่าดังนี้:

| Field | ค่า |
|-------|-----|
| Root Directory | *(ว่างเปล่า)* |
| Build Command | `pip install -r requirements.txt` |
| Start Command | `gunicorn student_register.wsgi` |
| Instance Type | Free |
| Environment | Python 3 |

### 2. รอ Deploy ให้เสร็จ → ระบบออนไลน์!

---

## 📁 โครงสร้างโฟลเดอร์หลัก

```plaintext
student_register-main/
├── manage.py
├── requirements.txt
├── Procfile
├── student_register/        # Django project
│   ├── settings.py
│   └── wsgi.py
├── students/                # Django app
│   ├── models.py
│   ├── views.py
│   └── urls.py
├── templates/
│   └── students/
│       ├── student_form.html
│       ├── student_list.html
│       └── student_confirm_delete.html
```

---

## ✨ ฟีเจอร์

- สร้างนักศึกษาใหม่
- อัปโหลดรูป
- ค้นหาชื่อนักศึกษา
- ลบ/แก้ไข/ดูรายชื่อ
- Responsive UI พร้อม Bootstrap

---

## 🧑‍💻 ผู้จัดทำ

**วงศกร หวลมานพ (Wonsagorn)**  
GitHub: [https://github.com/wonsagorn](https://github.com/wonsagorn)

---

## 📄 License
เผยแพร่ภายใต้ MIT License – ใช้เพื่อการศึกษาและพัฒนาต่อได้อย่างอิสระ
