# 🚀 วิธี Deploy ขึ้นเว็บ (เลือกอันที่ชอบ)

## 🥇 ทางลัด: Netlify Drop (30 วินาที — ไม่ต้องสมัคร)

1. เปิด https://app.netlify.com/drop
2. ลากไฟล์ `index.html` ไปวาง
3. รอ 10 วินาที → ได้ URL เช่น `https://radiant-mochi-a1b2c3.netlify.app`
4. ✅ เปิดบนมือถือ/แท็บเล็ต/คอมพ์ ที่ไหนก็ได้

**ถ้าอยากเปลี่ยนชื่อ URL:**
- หลัง deploy คลิกชื่อ site → Site settings → Change site name
- เปลี่ยนเป็น `myname-exam-sim` → URL ใหม่: `https://myname-exam-sim.netlify.app`

---

## 🥈 GitHub Pages (เก็บ source code ด้วย)

### ครั้งแรก: สมัคร GitHub (ข้ามถ้ามีแล้ว)
1. https://github.com/signup → ยืนยัน email

### Deploy:
1. https://github.com/new
2. Repository name: `exam-simulator` (หรือชื่ออะไรก็ได้)
3. เลือก **Public** → ติ๊ก "Add a README file" → กด **Create repository**
4. ในหน้า repo → กด **Add file** (ด้านขวา) → **Upload files**
5. ลากทั้ง `index.html` และ `README.md` ไปวาง → กด **Commit changes**
6. กดเมนู **Settings** (บน) → ซ้ายมือเลือก **Pages**
7. ใต้ "Build and deployment":
   - Source: **Deploy from a branch**
   - Branch: **main** / folder: **/ (root)** → กด **Save**
8. รอ 1-2 นาที → refresh หน้า → จะเห็น:
   ```
   ✅ Your site is live at https://USERNAME.github.io/exam-simulator/
   ```

### อัปเดตในอนาคต:
- แก้ไฟล์ → upload ใหม่ทับ → auto deploy ภายใน 1 นาที

---

## 🥉 Cloudflare Pages (เร็วที่สุด — CDN ทั่วโลก)

1. https://dash.cloudflare.com/sign-up → สมัคร
2. ซ้ายมือ → **Workers & Pages** → **Create application** → **Pages** → **Upload assets**
3. ตั้งชื่อ project: `exam-simulator`
4. ลาก folder ที่มี `index.html` ไปวาง → **Deploy site**
5. ได้ URL: `https://exam-simulator.pages.dev`

---

## 💡 Tips

- **Custom domain ของตัวเอง:** ทุก service รองรับฟรี (เช่น exam.yourname.com) — Settings → Custom domains
- **HTTPS:** ได้อัตโนมัติทุก service
- **อัปเดตไฟล์:** Netlify/Cloudflare ลากไฟล์ใหม่ทับ, GitHub ก็ upload ทับ
- **ปิดไม่ให้คนอื่นเห็น:** Netlify มี password protection (paid), GitHub ใช้ private repo (แต่ต้อง paid plan สำหรับ Pages)

---

## ⚠️ ข้อควรรู้

1. **ครั้งแรกที่เปิดต้องมีเน็ต** — โหลด React/Babel/Sora font จาก CDN (~700KB)
2. **AI Verify ใช้ API Key ของตัวเอง** — Key ไม่ได้ถูก hard-code อยู่ในไฟล์ ปลอดภัย deploy ขึ้นเว็บ public ได้
3. **ไม่มี database** — ทุกครั้งที่เปิดต้อง upload ไฟล์ .md ใหม่ (ไม่จำของเก่า)
