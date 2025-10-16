# TOEIC Online Practice Test @AiAm — Firebase + Thai Explanations

เวอร์ชันนี้:
- แสดงเฉลยและคำอธิบายภาษาไทย **ทันที** เมื่อเลือกคำตอบ
- เก็บชื่อผู้ทำ + คะแนน ลง **Firebase Firestore** (ผ่าน Anonymous Auth)
- ใช้ได้กับ Vercel แบบ Static

## วิธีตั้งค่า Firebase (ครั้งแรก 5–10 นาที)
1) ไปที่ https://console.firebase.google.com → Add project (เช่น `toeic-online`)
2) สร้าง **Web App** (ไอคอน `</>`) แล้วคัดลอกค่า **firebaseConfig**
3) เปิดเมนู **Build → Authentication** → Sign-in method → เปิด **Anonymous**
4) เปิด **Build → Firestore Database** → Create database → Start in test mode (สำหรับทดลอง)
5) แก้ไฟล์ `index.html`:
   - ใส่ค่า `firebaseConfig` ของคุณแทน `YOUR_...`
6) Deploy ขึ้น Vercel ตามปกติ

## ตัวอย่าง Firestore Rules (สำหรับทดลอง)
> ใช้เพื่อการเรียนรู้เท่านั้น ควรล็อกให้ปลอดภัยก่อนใช้งานจริง
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}
```

## โครงสร้างข้อมูลที่บันทึก
คอลเลกชัน: `results`
```
{
  name: string,
  score: number,
  total: number,
  percent: number,
  createdAt: serverTimestamp(),
  uid: string
}
```

## Deploy บน Vercel
- ใช้ `vercel.json` นี้เพื่อชี้ทุกเส้นทางไปที่ `index.html`

© 2025 AiAm
