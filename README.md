# ระบบลงทะเบียนนักศึกษา (Student Registration System)

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![Django](https://img.shields.io/badge/Django-4.x-green)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

---

## 📦 ภาพรวมระบบ

เว็บแอปพลิเคชันจัดการข้อมูลนักศึกษาด้วย Django Framework ประกอบด้วยความสามารถในการ:
- เพิ่ม/แก้ไข/ลบ/แสดงรายชื่อนักศึกษา
- รองรับการอัปโหลดรูปภาพนักศึกษา
- UI ใช้งานง่ายด้วย Bootstrap 5
- รองรับการ Deploy จริงผ่าน Render

---

## 🛠 เทคโนโลยีที่ใช้

- Python 3.10+
- Django 4.x
- SQLite3 (ฐานข้อมูล)
- Bootstrap 5
- HTML5/CSS3/JavaScript
- Gunicorn (production)

---

## 🚀 ขั้นตอนการติดตั้ง (Local)

### 1. Clone โปรเจกต์

```bash
git clone <REPO_URL>
cd student_register
```

### 2. สร้าง Virtual Environment

```bash
python -m venv venv
venv\Scripts\activate      # Windows
source venv/bin/activate     # macOS/Linux
```

### 3. ติดตั้ง Dependencies

```bash
pip install -r requirements.txt
```

### 4. Migrate ฐานข้อมูล และสร้าง superuser

```bash
python manage.py migrate
python manage.py createsuperuser
```

### 5. รันเซิร์ฟเวอร์

```bash
python manage.py runserver
```

---

## 🔍 โครงสร้างโปรเจกต์

```
student_register/
├── manage.py
├── requirements.txt
├── Procfile
├── .env
├── student_register/        # Django Project
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── students/                # App หลัก
│   ├── models.py
│   ├── views.py
│   ├── urls.py
│   ├── forms.py
│   └── migrations/
├── templates/
│   └── students/
│       ├── student_form.html
│       ├── student_list.html
│       └── student_confirm_delete.html
```

---

## 🧠 อธิบายโค้ดสำคัญ

### 📁 `models.py`

```python
class Student(models.Model):
    student_id = models.CharField(max_length=20)
    name = models.CharField(max_length=100)
    email = models.EmailField()
    phone = models.CharField(max_length=15)
    image = models.ImageField(upload_to='student_images/', blank=True)
```

📌 สร้างตาราง `Student` เก็บข้อมูลนักศึกษา พร้อมรองรับรูปภาพ

---

### 📁 `forms.py`

```python
class StudentForm(forms.ModelForm):
    class Meta:
        model = Student
        fields = '__all__'
```

📌 ฟอร์ม Django อิงจาก Model สำหรับเพิ่ม/แก้ไขข้อมูล

---

### 📁 `views.py`

ฟังก์ชันหลัก:
- `student_list`: แสดงรายการนักศึกษา
- `student_create`: เพิ่มข้อมูล
- `student_update`: แก้ไข
- `student_delete`: ลบ

---

### 📁 `urls.py`

```python
urlpatterns = [
    path('', student_list, name='student_list'),
    path('create/', student_create, name='student_create'),
    path('update/<int:pk>/', student_update, name='student_update'),
    path('delete/<int:pk>/', student_delete, name='student_delete'),
]
```

📌 กำหนดเส้นทางเข้าถึงแต่ละฟังก์ชันของ views

---

## 🖼️ Templates (HTML)

### ✅ `student_list.html`
- แสดงตารางรายชื่อนักศึกษา
- มีปุ่ม "แก้ไข" และ "ลบ"
- ใช้ Bootstrap table และปุ่มสีสัน

### ✅ `student_form.html`
- ฟอร์มกรอกข้อมูลนักศึกษา
- รองรับการอัปโหลดรูป

### ✅ `student_confirm_delete.html`
- ยืนยันการลบ

---

## 🌐 การ Deploy บน Render

1. เชื่อม GitHub repo เข้ากับ [https://render.com](https://render.com)
2. ตั้งค่า:
   - Build Command: `pip install -r requirements.txt`
   - Start Command: `gunicorn student_register.wsgi`
   - Root Directory: *(เว้นว่าง)*

3. Render จะออนไลน์เว็บให้อัตโนมัติ!

---

## 📄 License

เผยแพร่ภายใต้ MIT License – ใช้เพื่อการศึกษา/พัฒนาต่อได้อย่างอิสระ

---

## 🙋‍♂️ ผู้พัฒนา

**วงศกร หวลมานพ**  
GitHub: [https://github.com/wonsagorn](https://github.com/wonsagorn)