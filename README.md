# ICT12367 - ระบบลงทะเบียนสัมมนา (Seminar Registration System)

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## 📋 สารบัญ
- ภาพรวมโครงการ
- คุณสมบัติหลัก
- เทคโนโลยีที่ใช้
- ความต้องการของระบบ
- การติดตั้ง
- โครงสร้างโปรเจกต์
- การใช้งาน
- การกำหนดค่า
- การปรับแต่งและขยาย
- การนำไปใช้งานจริง
- การดูแลรักษาและการสนับสนุน
- การมีส่วนร่วมในโครงการ
- ใบอนุญาต
- ติดต่อ

---

## 📌 ภาพรวมโครงการ
ระบบลงทะเบียนสัมมนา (Seminar Registration System) พัฒนาเพื่อรองรับวิชา ICT12367 โดยใช้ Django Framework  
ออกแบบให้รองรับการจัดการสัมมนาแบบครบวงจร ตั้งแต่สร้างหัวข้อ ลงทะเบียน แสดงรายชื่อ วิเคราะห์ข้อมูล และดูผ่านปฏิทิน

---

## ✨ คุณสมบัติหลัก
- สร้าง/ลบ/แก้ไขหัวข้อสัมมนา
- ลงทะเบียนผู้เข้าร่วมแบบมีระบบตรวจสอบ
- ยืนยันสถานะการเข้าร่วม และแสดงปฏิทิน
- แสดงแดชบอร์ดสรุป
- UI รองรับภาษาไทย-อังกฤษ

---

## 🛠 เทคโนโลยีที่ใช้
### Backend
- Django 4.x
- SQLite3 (ปรับใช้ PostgreSQL ได้)
- Python 3.10+

### Frontend
- Bootstrap 5
- Django Crispy Forms + crispy-bootstrap5
- HTML5 / CSS3 / JavaScript

---

## 📦 ความต้องการของระบบ
- Python 3.10+
- Django 4.x
- pip
- virtualenv
- เบราว์เซอร์: Chrome/Firefox/Safari

---

## 🚀 การติดตั้ง

### 1. ติดตั้ง Python
ดูจาก [https://www.python.org/downloads](https://www.python.org/downloads)

### 2. สร้าง virtual environment
```bash
python -m venv venv
venv\Scripts\activate  # Windows
source venv/bin/activate  # macOS/Linux
```

### 3. ติดตั้งแพ็กเกจ
```bash
pip install -r requirements.txt
```

### 4. Migrate และสร้าง admin
```bash
python manage.py migrate
python manage.py createsuperuser
```

### 5. รันเซิร์ฟเวอร์
```bash
python manage.py runserver
```

---

## 📁 โครงสร้างโปรเจกต์

```
student_register/
├── manage.py
├── requirements.txt
├── student_register/
│   ├── settings.py
│   ├── wsgi.py
│   └── urls.py
├── students/
│   ├── models.py
│   ├── views.py
│   ├── forms.py
│   ├── admin.py
│   └── templates/
│       └── students/
│           ├── student_form.html
│           ├── student_list.html
│           ├── student_confirm_delete.html
```

---

## 🧑‍💻 การใช้งานระบบ
- ไปที่ [http://127.0.0.1:8000/](http://127.0.0.1:8000/)
- คลิกสร้างหัวข้อ หรือกรอกแบบฟอร์มลงทะเบียน
- ตรวจสอบข้อมูล ยืนยัน หรือแก้ไข

---

## ⚙️ การกำหนดค่า
### settings.py
```python
LANGUAGE_CODE = 'th'
TIME_ZONE = 'Asia/Bangkok'
STATIC_URL = '/static/'
MEDIA_URL = '/media/'
```

### urls.py
```python
from django.conf import settings
from django.conf.urls.static import static
urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```

---

## 🧩 การปรับแต่งและขยาย
- เพิ่มหมวดหมู่สัมมนา
- สร้างแดชบอร์ดรวมข้อมูลสถิติ
- ส่งออกข้อมูลผู้เข้าร่วมเป็น CSV
- เพิ่มภาษาอังกฤษ
- เชื่อมกับระบบอีเมล SMTP

---

## 🔐 การนำไปใช้งานจริง
- ปิด DEBUG
- ตั้งค่า ALLOWED_HOSTS
- ใช้ PostgreSQL
- ใช้ Gunicorn + Nginx
- เก็บ static ไว้ที่ `STATIC_ROOT`

---

## 🔧 การดูแลรักษา
- สำรองฐานข้อมูล: `cp db.sqlite3 backup.sqlite3`
- อัปเดต: `git pull`, `pip install -r requirements.txt`, `migrate`, `collectstatic`

---

## 🤝 การมีส่วนร่วม
- Fork → แก้ไข → Commit → PR
- ปฏิบัติตาม PEP8
- เพิ่ม test / update README

---

## 📄 License
MIT License – ใช้เพื่อการศึกษาและพัฒนาต่อได้อย่างอิสระ

---

## 📞 ติดต่อ
**ผู้พัฒนา:** วงศกร หวลมานพ  
GitHub: [https://github.com/wonsagorn](https://github.com/wonsagorn)

© 2025 - ระบบลงทะเบียนสัมมนา (ICT12367)