# شبیه‌سازهای تعاملی تجهیزات | Interactive Equipment Simulators

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![SVG](https://img.shields.io/badge/SVG-FFB13B?style=flat-square&logo=svg&logoColor=black)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

> ساخت ابزارهای آنلاین تعاملی برای شناخت، آموزش و تنظیم تجهیزات امنیتی و الکترونیکی.

این مخزن شامل نمونه‌ای از **شبیه‌ساز تعاملی برد سنسور هایک‌ویژن DS-PDP18-EG2** است؛ ابزاری تحت وب که کاربر می‌تواند روی هر بخش از برد کلیک یا موس را روی آن ببرد و توضیحات، مشخصات و تنظیمات همان بخش را ببیند.

ساخته‌شده توسط **[IntelliSoft](http://intellsoft.ir)** — سازنده ابزارهای آنلاین تعاملی برای تجهیزات.

---

## 🌐 دموی زنده

**[https://intellsoft.github.io/hikvision-pdp18-detector/](https://intellsoft.github.io/hikvision-pdp18-detector/)**

وب‌سایت سازنده:  
**[http://intellsoft.ir](http://intellsoft.ir)**

---

## ✨ این پروژه چه کاری انجام می‌دهد؟

- نمایش تصویری و تعاملی برد الکترونیکی به کمک **SVG**
- هایلایت هر قطعه با هاور، کلیک یا لمس
- نمایش توضیح کوتاه در Tooltip
- نمایش توضیحات کامل، مشخصات فنی و تنظیمات در پنل کناری
- امکان تغییر وضعیت جامپرها و مشاهده حالت فعلی
- طراحی واکنش‌گرا (Responsive) برای موبایل و دسکتاپ
- دسترس‌پذیری با پشتیبانی از کیبورد (`Enter` / `Space`)
- سئوی کامل شامل متاتگ‌ها، Open Graph، Twitter Card و داده ساختاریافته `JSON-LD`

---

## 🧠 ایده اصلی: چطور یک شبیه‌ساز تعاملی بسازیم؟

برای ساخت شبیه‌ساز تعاملی هر تجهیز، می‌توان از همین الگو استفاده کرد:

### ۱. تصویر یا SVG تجهیز را آماده کنید
بهتر است به‌جای تصویر bitmap از **SVG** استفاده شود تا:
- کیفیت در همه اندازه‌ها حفظ شود
- هر قطعه به‌صورت جداگانه قابل هایلایت باشد
- امکان اضافه کردن رویداد کلیک و هاور وجود داشته باشد

### ۲. هر قطعه را به یک Hotspot تبدیل کنید
هر بخش مهم برد داخل یک گروه SVG با کلاس `hv-hotspot` و ویژگی `data-part` قرار می‌گیرد:

```html
<g class="hv-hotspot" data-part="eolTamper" tabindex="0" role="button">
  <!-- شکل قطعه -->
  <rect class="hv-hl" x="..." y="..." width="..." height="..." />
</g>
