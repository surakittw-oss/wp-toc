# WP TOC Generator

สร้าง Table of Contents (TOC) + H2 พร้อม `id=` และ style ตามหมวดข่าว สำหรับ WordPress Classic Editor

**ไม่ใช้ Claude API · ไม่กิน token · รันใน browser 100%**

---

## ฟีเจอร์

- เลือกหมวดข่าว 6 หมวด (TSD, TSD POP, TSD Wealth, LIFE, TSD SPORT, The Secret Sauce)
- วางบทความเต็มหรือพิมพ์ H2 มาเองก็ได้
- Detect หัวข้อ H2 อัตโนมัติ (Markdown `##` และ HTML `<h2>`)
- สร้าง HTML code 2 ส่วน พร้อม Copy ได้ทันที
  - **ส่วนที่ 1**: `<h2 id="sectionX" style="...">` ครบทุกหัวข้อ
  - **ส่วนที่ 2**: TOC Block พร้อม anchor links

---

## การติดตั้งและ Deploy

### ขั้นตอนที่ 1 — สร้าง GitHub Repository

1. ไปที่ [github.com](https://github.com) → กด **New repository**
2. ตั้งชื่อ เช่น `wp-toc-generator`
3. เลือก **Public**
4. **ไม่ต้อง** tick Add README
5. กด **Create repository**

---

### ขั้นตอนที่ 2 — ติดตั้ง GitHub Desktop

1. ดาวน์โหลด [GitHub Desktop](https://desktop.github.com)
2. ติดตั้งและ Sign in ด้วย GitHub account

---

### ขั้นตอนที่ 3 — Clone และ Push ไฟล์

1. เปิด GitHub Desktop → **File → Clone repository**
2. เลือก repo `wp-toc-generator` ที่เพิ่งสร้าง
3. เลือก Local Path ที่ต้องการเก็บ → กด **Clone**
4. คัดลอกไฟล์ `index.html` และ `README.md` ลงใน folder นั้น
5. ใน GitHub Desktop จะเห็นไฟล์ใหม่ปรากฏใน **Changes**
6. ใส่ Commit message เช่น `init: add WP TOC Generator`
7. กด **Commit to main**
8. กด **Push origin**

---

### ขั้นตอนที่ 4 — Deploy บน Vercel

1. ไปที่ [vercel.com](https://vercel.com) → Sign in ด้วย GitHub
2. กด **Add New → Project**
3. เลือก repository `wp-toc-generator`
4. ไม่ต้องปรับ settings ใดๆ → กด **Deploy**
5. รอ ~30 วินาที → ได้ URL เช่น `wp-toc-generator.vercel.app`

**เสร็จแล้ว!** ทุกครั้งที่ `git push` เว็บจะ update อัตโนมัติ

---

## โครงสร้างไฟล์

```
wp-toc-generator/
├── index.html    ← ไฟล์เดียว ทุกอย่างอยู่ในนี้
└── README.md
```

---

## Tech Stack

- **HTML + CSS + Vanilla JavaScript** — ไม่มี framework
- **Google Fonts** — IBM Plex Sans Thai + IBM Plex Mono
- **Vercel** — Static hosting ฟรี
- **GitHub Desktop** — สำหรับ push code

---

## License

MIT
