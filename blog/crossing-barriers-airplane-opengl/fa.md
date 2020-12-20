---
title: 'گیم کلاسیک: عبور هواپیما از موانع'
date: '2014-02-23'
tags:
  - opengl
  - c++
  - game
seo:
  title: 'گیم کلاسیک: عبور هواپیما از موانع'
  description: یه گیم ساده با زبان سی پلاس پلاس و OpenGL منتشر شده روی مخزن گیت‌هاب
  openGraph:
    images:
      - url: 'https://hallaji.com/blog/crossing-barriers-airplane-opengl/screenshot.jpg'
        width: 596
        height: 596
        alt: تصویر عبور هواپیما از موانع
---

[repo]: https://github.com/hallaji/crossing-barriers
[wiki]: https://en.wikipedia.org/wiki/Silicon_Graphics
[download]: https://github.com/hallaji/crossing-barriers/archive/master.zip
[screenshot]: /blog/crossing-barriers-airplane-opengl/screenshot.svg

OpenGL یک API هست که از GPU یا واحد پردازش گرافیک برای رندر کردن گرافیک برداری دو بعدی و سه بعدی
استفاده می کنه و توسط شرکت [سیلیکون گرافیکس][wiki] توسعه داده شده. مدت ها پیش با زبان ++C و
OpenGL یه گیم ساده ای رو برنامه‌نویسی کردم و سورس اش رو روی مخزن [گیت‌هاب][repo] منتشر کردم که اگر
دوست داشتید دانلود و تست کنید.

---

![Screenshot][screenshot]

## گام اول

برای اینکه بتونید سورس رو کامپایل و اجرا کنید بایستی کتابخانه OpenGL Utility Toolkit رو داشته باشید. ابتدا
سورس رو [دانلود][download] کنید. داخل دایرکتوری ‍`glut-3.7.6-bin` سه فایل موجود هست.
به پوشه Microsoft Visual Studio در محل نصب  روی هارد دیسک مراجعه کنید و  هر کدوم از فایل ها رو
در دایرکتوری مشخص شده کپی کنید:

```bash
Copy  glut.h      ->    \vc\include\
Copy  glut32.dll  ->    \vc\lib\
```

همچنین به پوشه ویندوز مراجعه کنید و فایل با پسوند ‍`lib` رو به هر دو دایرکتوری سیستمی کپی کنید:

```bash
Copy  glut32.lib  ->   \Windows\System
                       \Windows\System32
```

## گام دوم

فایل `Bricks.raw` موجود در دایرکتوری در واقع pattern آجری هست که توسط نرم افزار فوتوشاپ آماده کردم.
اگه خواستید pattern رو تغییر بدید بایستی تصویر مورد نظر خودتون رو با فوتوشاپ باز کنید و با فرمت `raw`
ذخیره کنید.  قبل از اینکه پروژه رو با Visual Studio استارت و اجرا کنید، قدم نهایی این هست که این فایل رو
در کنار فایل اجرایی پروژه که با پسوند `exe` در پوشه Debug تولید میشه کپی کنید.
