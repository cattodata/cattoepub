# 🐱 CattoEPUB 📘 & CattoTranslate 🌐

**Convert complex Thai PDFs into clean, readable EPUBs using AI-powered OCR**  
แปลง PDF เป็น EPUB ด้วย GenAI + Typhoon OCR รองรับภาษาไทยโดยเฉพาะ ทำงานบนเบราว์เซอร์ ไม่ต้องติดตั้ง ไม่ส่งข้อมูลขึ้นเซิร์ฟเวอร์

🔗 **CattoEPUB:** [cattodata.com/cattoepub](https://cattodata.com/cattoepub)  
🔗 **CattoTranslate:** [cattodata.com/cattoepub/translate.html](https://cattodata.com/cattoepub/translate.html)  
📦 **GitHub:** [github.com/cattodata/cattoepub](https://github.com/cattodata/cattoepub)

![Client-Side](https://img.shields.io/badge/Client--Side-JavaScript-yellow)
![Thai OCR](https://img.shields.io/badge/Thai%20OCR-Typhoon-blue)
![PWA](https://img.shields.io/badge/PWA-Offline-purple)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📱 2 Tools

| Tool | File | Description |
|------|------|-------------|
| **🐱 CattoEPUB** | `index.html` | Convert PDF → EPUB with Typhoon OCR, optimized for Thai |
| **🐱 CattoTranslate** | `translate.html` | Translate entire PDF/EPUB books with AI (EN↔TH) |

---

## 💡 Origin

### Original: Bepub by Ken Takahashi
Based on a Python notebook by **Ken Takahashi** shared in [ชุมชนนักอ่าน eBook](https://www.facebook.com/groups/ebookreader/posts/25556985560668239) — a Google Colab script using Typhoon OCR to convert Thai PDFs to EPUB.

- 🔗 [Original Colab](https://colab.research.google.com/drive/1lgmYkuEeSUlVDLpplXCnFIQdJP9YMWjw?usp=sharing)

### Web Version: by cattoData
**cattoData** rebuilt it as a **browser-based web app** — no installation needed, with many added features including AI book translation (**CattoTranslate**).

---

## ✨ Features

### 🌐 Architecture — Client-Side Web App
- Runs 100% in browser (PDF.js + JSZip + AI API)
- **PWA** — installable on mobile/desktop, works offline
- **Mobile Ready** — fully responsive
- 🔒 Privacy-first — data sent only to AI API, nothing stored on servers

### 📘 CattoEPUB — PDF to EPUB Converter

- **Typhoon OCR** — optimized for Thai language
- **💎 Token Saver Mode** — save ~85% tokens: extract text first, skip blanks, compress images
- **⚡ Parallel Processing** — 3-5 pages simultaneously
- **🖼️ Smart Image Embed** — embeds real illustrations, skips scanned pages
- **✏️ Edit OCR Results** — edit text page by page before building EPUB
- **▶️ Resume & Recovery** — stop/resume anytime, auto-save to localStorage
- **📕 Upload existing EPUB** — resume from partial conversion
- **📊 Stats & Cost Estimate** — track pages, tokens, and estimated cost
- **📑 Auto Table of Contents** — auto-detect chapters, edit/add/delete entries
- **🛡️ Smart Retry** — exponential backoff for rate limits, auto-stop on fatal errors

### 🌐 CattoTranslate — AI Book Translator

- **Translate entire books** while preserving layout and formatting
- Supports **PDF + EPUB** input → EPUB output
- **EN↔TH** + more language pairs
- 4 translation styles: Natural / Formal / Creative / Literal
- **📖 Glossary** — custom term pairs injected into every prompt
- **📖 EPUB Reader** — read translations in-browser
- **✏️ Edit Translations** — click to edit any translated text
- **💾 Resume & Recovery** — auto-save, export/import JSON backup
- Context overlap for continuous translation across pages

### 🎨 Shared Features
- 🌙 **Dark Mode**
- 🌐 **i18n** — Thai / English UI
- 🔑 **Remember API Key** in localStorage
- 📄 **PDF Preview** thumbnail
- 🔔 **Browser + Sound Notifications** on completion
- ⌨️ **Keyboard Shortcuts** — `Ctrl+Enter` start, `Escape` stop

---

## 🚀 Getting Started

### Online
Visit [cattodata.com/cattoepub](https://cattodata.com/cattoepub) — ready to use!

### CattoEPUB
1. **Get API Key** — Sign up at [opentyphoon.ai](https://opentyphoon.ai) → Profile → API Keys
2. **Upload PDF** → enable Token Saver (recommended)
3. **Click "เริ่มแปลงไฟล์"** → download EPUB + TXT

### CattoTranslate
1. **Upload PDF/EPUB** → select language direction (EN↔TH)
2. **Choose style** + add Glossary terms if needed
3. **Click "เริ่มแปล"** → read/edit/download EPUB

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| PDF Reader | [PDF.js](https://mozilla.github.io/pdf.js/) 3.11.174 |
| EPUB Builder | [JSZip](https://stuk.github.io/jszip/) 3.10.1 |
| OCR | [Typhoon OCR](https://opentyphoon.ai) |
| Translation | [Typhoon V2](https://opentyphoon.ai) |
| UI | Vanilla HTML/CSS/JS |
| Fonts | Sarabun, Plus Jakarta Sans, JetBrains Mono |
| PWA | Service Worker + manifest.json |

---

## 📁 Project Structure

```
cattoepub/
├── index.html        ← 🐱 CattoEPUB — PDF to EPUB Converter
├── translate.html    ← 🐱 CattoTranslate — AI Book Translator
├── cattodata.png     ← Logo
├── manifest.json     ← PWA manifest
├── sw.js             ← Service Worker (offline caching)
└── README.md         ← This file
```

---

## ⚖️ Colab vs Web

| | Colab (Original) | Web (CattoEPUB) |
|---|---|---|
| Environment | Google Colab (Python) | Browser |
| Install | pip install required | No install (PWA) |
| Token Saver | ❌ | ✅ Save ~85% |
| Parallel | ❌ One page at a time | ✅ 3-5 pages |
| Resume | ❌ | ✅ Close & come back |
| Error Handling | Basic | ✅ Retry + Auto-stop |
| Table of Contents | ❌ | ✅ Auto-detect + editable |
| Cover | ❌ | ✅ |
| Book Translation | ❌ | ✅ CattoTranslate EN↔TH |
| Glossary | ❌ | ✅ Custom term pairs |
| EPUB Reader | ❌ | ✅ Read in browser |
| Edit Text | ❌ | ✅ Edit before building |
| Dark Mode | ❌ | ✅ |
| Mobile | ❌ | ✅ Responsive + PWA |

---

## ⚠️ Disclaimer

This tool is intended for converting/translating files that you have the legal right to use, for personal reading only. It must not be used with copyrighted content without permission, or to distribute, publish, or sell converted/translated files. Users are solely responsible for their use of this tool. The developer is not liable for any unlawful use.

---

## 🙏 Credits

- **Ken Takahashi** — Original idea & Colab notebook ([Facebook](https://www.facebook.com/groups/ebookreader/posts/25556985560668239) · [Colab](https://colab.research.google.com/drive/1lgmYkuEeSUlVDLpplXCnFIQdJP9YMWjw?usp=sharing))
- **cattoData** — Web version + all additional features
- **Typhoon** by [SCB 10X](https://opentyphoon.ai) — Thai OCR & Translation API
- Shared in [ชุมชนนักอ่าน eBook](https://www.facebook.com/groups/778412228952249/) · Trusted by Thai ebook community 🇹🇭

---

## ☕ Support

If these tools help you read better — [buy me a coffee](mailto:cattodata@gmail.com?subject=CattoEPUB%20—%20อยากสนับสนุน%20☕&body=สวัสดีครับ%20อยากสนับสนุน%20CattoEPUB%20ครับ%20ขอบัญชีสำหรับโอนด้วยครับ)! All tools are free and will remain free.

---

## 📄 License

MIT License — Free to use and modify, just give credit.
