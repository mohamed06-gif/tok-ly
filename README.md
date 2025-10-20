[README.md](https://github.com/user-attachments/files/23007925/README.md)
# tik ly — Fullstack Social App (React + Vite, Express + MongoDB, Socket.io)

## Overview
نسخة تجريبية كاملة من تطبيق تواصل اجتماعي اسمه **tik ly**. الواجهة مبنية بـ React + Vite، والخادم بـ Express مع MongoDB (Atlas) لتخزين المستخدمين والمشاركات. يدعم JWT للتحقق، رفع صور/فيديوهات (Multer)، لایكات وتعليقات، ودردشة مباشرة عبر Socket.io.

**ملاحظة مهمة:** هذه النسخة مخصصة للتجربة/demo. للاستخدام الإنتاجي استعمل S3 لتخزين الملفات واحتفظ بالـ DB في خدمة موثوقة.

## محتويات الحزمة
- `frontend/` — React + Vite app
- `backend/` — Express API + Socket.io
- `netlify.toml` — إعداد Netlify للواجهة

## المتطلبات
- Node.js v18+
- npm
- حساب MongoDB Atlas (URI)
- (اختياري) AWS S3 إذا تبي تخزّن الوسائط خارجيًا

## متغيرات البيئة المطلوبة (backend `.env`)
```
PORT=4000
MONGO_URI=<your MongoDB connection string>
JWT_SECRET=<random secret>
USE_S3=false
S3_BUCKET=
S3_KEY=
S3_SECRET=
```
## متغيرات الواجهة (frontend) في Netlify أو محليًا
```
VITE_API_BASE=http://localhost:4000/api
```
## تشغيل محلي سريع
1. backend:
```bash
cd backend
npm install
# أنشئ ملف .env بحسب الأعلى
node server.js
```
2. frontend:
```bash
cd frontend
npm install
npm run dev
# افتح http://localhost:5173
```

## نشر
- **Frontend**: Netlify — ربط المستودع، بناء الأمر: `cd frontend && npm install && npm run build`، مجلد النشر `frontend/dist`. اضبط متغير `VITE_API_BASE` لعنوان backend العام.
- **Backend**: Render / Railway / Heroku — اربط الريبو واضبط متغيرات البيئة أعلاه. أعد توجيه البنية `node server.js`.

---
لو تحتاج أجهز ملف ZIP للتنزيل أعمله و أقدمه لك. هذه الحزمة تحتوي مثال جاهز ويحتاج تهيئة متغيرات البيئة فقط.
