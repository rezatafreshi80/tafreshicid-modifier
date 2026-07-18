# tafreshicid
# Issabel / Asterisk Caller ID Normalizer for Iran

This Asterisk dialplan snippet normalizes incoming Caller IDs from SIP trunks in Iran (such as TCI / مخابرات). It helps fix logging, CRM integration, and callback issues in Issabel, FreePBX, and raw Asterisk PBX systems.

## 🇮🇷 مشکل (The Problem)
در بسیاری از خطوط سیپ ترانک مخابرات ایران، شماره تماس‌گیرنده (Caller ID) با پیش‌شماره‌های `98` یا `+98` ارسال می‌شود. همچنین در برخی استان‌ها مانند تهران، پیش‌شماره `021` یا `21` به ابتدای شماره‌های شهری اضافه می‌شود که باعث ایجاد مشکل در ذخیره شماره‌ها در دیتابیس (CDR)، سیستم‌های CRM و همچنین عدم امکان تماس متقابل (Callback) می‌گردد.

## 🚀 راهکار (The Solution)
این اسکریپت بدون نیاز به تغییر در فایل‌های هسته سیستم (Core) و تنها با اضافه کردن یک Context در فایل `extensions_custom.conf`، شماره‌ها را پیش از ورود به مسیر اصلی ایزابل استانداردسازی می‌کند.

### نحوه عملکرد:
1. تبدیل `98` و `+98` به `0`
2. حذف `021` از ابتدای شماره
3. حذف `21` از ابتدای شماره
4. ارسال شماره اصلاح‌شده به Context اصلی ایزابل (`from-pstn`)

## 🛠 راه‌اندازی (Installation)

1. در محیط ایزابل یا فری‌پی‌بی‌ایکس، فایل `/etc/asterisk/extensions_custom.conf` را باز کنید.
2. کدهای موجود در فایل `extensions_custom.conf` همین مخزن را به انتهای آن اضافه کنید.
3. در تنظیمات ترانک (Trunk) خود در محیط وب ایزابل، مقدار `context` را برابر با عبارت زیر قرار دهید:
```text
   context=tafreshiCID


در صورت  عدم استارت   برنامه حتما استریسک   را ریلود و در نهایت   به مراجعه با سایت   توسعه دهنده www.ertebatcenter.com

ویا   09122399179و 02133530748و02133530739 jlhs phwg tvlhddn
   

