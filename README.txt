# AiAm practice exam online — Phase 2.5 (Multi-category + Premium-ready)

ไฟล์:
- index.html — เลือกหมวดข้อสอบ
- tests.html — เลือกชุดข้อสอบ (ฟรี / Premium)
- exam.html — หน้าทำข้อสอบ (พิมพ์ชื่อได้ ไม่ต้องล็อกอิน) + เฉลยไทย + บันทึกคะแนนลง Firestore
- premium.html — หน้า Premium (เดโม่การสมัคร)
- admin.html — Dashboard แสดงรายชื่อผู้ทำข้อสอบแบบเรียลไทม์
- auth.html — หน้า Login/Signup (เตรียมไว้สำหรับ Phase 3)

## วิธีใช้งาน
1) อัปโหลดไฟล์ทั้งหมดขึ้น GitHub โปรเจกต์ของคุณ
2) (สำคัญ) ถ้าเคยใช้ `vercel.json` แบบ rewrite ทั้งหมดไป `index.html` ให้ลบไฟล์นั้นออก เพื่อให้หลายหน้า .html ใช้งานได้
3) Vercel → Redeploy
4) เปิด `exam.html` และ `admin.html` แล้วใส่ค่า `firebaseConfig` ของคุณ
5) ทดลองเริ่มที่ `/` (index.html)

## เส้นทางตัวอย่าง
- / → index.html
- /tests.html?category=toeic
- /exam.html?test=toeic-set1
- /premium.html
- /admin.html

© 2025 AiAm practice exam online
