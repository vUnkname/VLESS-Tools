# VLESS Tools

ابزار تک‌صفحه‌ای وب برای کار با کانفیگ‌های **VLESS**: ساخت کانفیگ چند IP، استخراج آدرس از لیست کانفیگ‌ها، و Morph دسته‌ای. بدون نصب و بدون سرور — فقط فایل HTML را در مرورگر باز کنید.

**زبان‌ها:** English · فارسی · Русский (سوئیچ در هدر؛ انتخاب در `localStorage` ذخیره می‌شود).

---

## قابلیت‌ها

### ۱. سازنده کانفیگ (Generator)

- یک لینک پایه `vless://` بچسبانید؛ `@host:` با IPها یا رنج CIDR جایگزین می‌شود.
- تب **لیست IP**: ورود دستی، Drag & Drop، یا import فایل (`.txt`, `.csv`, `.log`, `.json`).
- تب **رنج IP**: پیش‌تنظیم CDN (Cloudflare, Fastly, Gcore) از [cdn-ip-ranges](https://github.com/vUnkname/cdn-ip-ranges)؛ shuffle و محدود کردن تعداد رنج.
- رنج‌های بزرگ CDN به‌صورت خودکار به `/24` نمونه‌گیری می‌شوند.
- خروجی **پارت‌بندی** با اندازه قابل تنظیم؛ کپی یا دانلود هر پارت یا کل خروجی.
- متریک زنده: تعداد IP، کانفیگ خروجی، تعداد پارت.

### ۲. استخراج IP (IP Extractor)

- پارس لینک‌های VLESS (یا خطوط IP/CIDR) از textarea.
- فیلتر اختیاری **WS + TLS** (`type=ws` و `security=tls`).
- استخراج **@address**، **sni=**، **host=**.
- گسترش اختیاری CIDR به IP تکی.
- گزارش IP تکراری با دکمه کپی.

### ۳. Morph کانفیگ

- تبدیل دسته‌ای چند کانفیگ VLESS:
  - **حالت Quick spoof:** تغییر `@IP:Port` به آدرس محلی (پیش‌فرض 127.0.0.1:40443).
  - **حالت پیشرفته:** سوییچ Address، SNI، HOST؛ چرخش روی لیست دامنه.

### رابط کاربری

- دو تم: **CyberDeck** (HUD سایبرپانک) و **Simple** (مینیمال تیره).
- Toast برای کپی، ساخت خروجی، و خطاها.
- چیدمان واکنش‌گرا؛ پشتیبانی RTL برای فارسی.

---

## فایل‌ها

| فایل | توضیح |
|------|--------|
| `index.html` | صفحه ورود GitHub Pages — انتخاب Cyber یا Simple. |
| `vless-tools-all-in-one.html` | **مستقل** — CSS، JS، هر دو تم + داده CDN داخلی (~۲۷۰ KB). کاملاً آفلاین. |
| `vless-tools-cyber.html` | تم CyberDeck؛ لینک به نسخه Simple. نیاز به `cyber-theme.css`. |
| `vless-tools-simple.html` | تم ساده؛ لینک به Cyber. نیاز به `simple-theme.css`. |
| `cyber-theme.css` | استایل HUD سایبرپانک. |
| `simple-theme.css` | استایل مینیمال. |

---

## شروع سریع

1. **GitHub Pages:** `index.html` را باز کنید و **Cyber** یا **Simple** را انتخاب کنید.
2. **آفلاین:** `vless-tools-all-in-one.html` را دانلود و در مرورگر باز کنید.
3. **جفت تم‌دار:** `vless-tools-cyber.html` + `cyber-theme.css` (یا simple + css) در یک پوشه.

> **all-in-one** رنج‌های Cloudflare، Fastly و Gcore را داخل خودش دارد — بدون اینترنت. نسخه‌های cyber/simple برای CDN از GitHub درخواست می‌زنند.

---

## تعویض تم

| نسخه | روش |
|------|-----|
| **All-in-one** | دکمه‌های **Simple / Cyber** در هدر؛ ذخیره در `vless-ui-theme`. |
| **Cyber ↔ Simple** | هر HTML به فایل دیگر لینک دارد. |

زبان در `vless-lang` جدا ذخیره می‌شود.

---

## حریم خصوصی

همه پردازش **محلی در مرورگر** است. جز fetch اختیاری لیست CDN از GitHub، چیزی آپلود نمی‌شود.

---

## زبان‌های دیگر

- [English (README.md)](README.md)
- [Русский (README.ru.md)](README.ru.md)
