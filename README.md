# WP TOC Generator

Static web app สำหรับทีมเว็บ **The Standard** ใช้สร้าง Table of Contents + H2 style สำหรับ WordPress Classic Editor

> 0 token · no API · ไฟล์เดียว deploy บน Vercel

---

## Features

- **TOC Generator** — สร้าง TOC Block + H2 พร้อม `id=` และ style สีตามหมวดข่าว
- **H2 Preview** — แสดง H2 style จริงๆ ทันทีก่อนกด Generate
- **Button Generator** — สร้างปุ่ม HTML พร้อม preview real-time
- **Google OAuth** — จำกัดการใช้งานเฉพาะอีเมล `@thestandard.co`

---

## Input Modes

รองรับการวางเนื้อหา 5 รูปแบบ

| รูปแบบ | ตัวอย่าง |
|--------|---------|
| HTML จาก WordPress | `<h2><b>หัวข้อ</b></h2>` |
| Markdown | `## หัวข้อ` |
| Numbered list | `1. หัวข้อ` |
| Bold | `**หัวข้อ**` |
| Plain text | เว้นบรรทัดว่างทั้งสองด้าน |

---

## หมวดข่าว + Style

| หมวด | สี Border-left |
|------|---------------|
| NEWS | `#e62227` แดง |
| POP | `#0000ff` น้ำเงิน |
| WEALTH | `#c19380` โรสโกลด์ |
| LIFE | `#000000` ดำ |
| SPORT | `#ffa5f7` ชมพู |
| The Secret Sauce | `#ffcd00` เหลือง + glassmorphism |

---

## Output Tabs

| Tab | รายละเอียด |
|-----|-----------|
| **H2 + id= + style** | H2 พร้อม anchor id และ style ตามหมวด |
| **TOC Block** | HTML block สำหรับวางบนสุดบทความ |
| **บทความรวม** | TOC + เนื้อหา + H2 replace ครบในครั้งเดียว |
| **วิธีใช้** | คู่มือการใช้งาน |

---

## Google OAuth Setup

1. ไปที่ [Google Cloud Console](https://console.cloud.google.com) → สร้าง project
2. **APIs & Services → Credentials** → สร้าง OAuth 2.0 Client ID
3. เลือก type: **Web application**
4. เพิ่ม Authorized JavaScript origins: `https://your-app.vercel.app`
5. ใส่ Client ID ใน `index.html`

```html
<div id="g_id_onload"
  data-client_id="YOUR_CLIENT_ID.apps.googleusercontent.com"
  ...>
</div>
```

6. เปลี่ยน domain ใน script

```js
const ALLOWED_DOMAIN = 'thestandard.co'
```

---

## Deploy

```bash
# 1. Clone หรือ fork repo
git clone https://github.com/your-org/wp-toc-generator

# 2. แก้ Client ID และ domain ใน index.html

# 3. Push ขึ้น GitHub → Vercel auto-deploy
git add .
git commit -m "update"
git push
```

Vercel จะ deploy `index.html` เป็น static site โดยอัตโนมัติ

---

## File Structure

```
/
└── index.html      ← ทั้ง app อยู่ในไฟล์เดียว
└── README.md
```

---

## Tech Stack

- Vanilla HTML / CSS / JavaScript — ไม่มี framework
- Font: **Prompt** + JetBrains Mono (Google Fonts)
- Auth: Google Identity Services (GSI)
- Deploy: Vercel (static)

---

## Changelog

| Version | รายละเอียด |
|---------|-----------|
| v1.0 | TOC Generator + Button Generator |
| v1.1 | เพิ่ม H2 Preview panel + status bar |
| v1.2 | เพิ่ม Google OAuth + user bar |
| v1.3 | เพิ่มปุ่ม Clear (input + output) |

---

*WP TOC Generator — The Standard Web Team*
