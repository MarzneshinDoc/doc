---
title: اعلانات  
weight: 5  
---


{{< tabs items="تلگرام,وبهوک" >}}

{{< tab >}}  

برای دریافت اعلانات از طریق ربات تلگرامی، می‌توانید مراحل زیر را دنبال کنید:

{{% steps %}}

### ویرایش فایل `.env`  

ابتدا فایل پیکربندی `.env` را با استفاده از ویرایشگر `nano` باز کنید:

```bash
nano /etc/opt/marzneshin/.env
```

### تنظیم چت آیدی و توکن ربات

مقادیر زیر را در فایل `.env` تنظیم کنید. برای دریافت این مقادیر، از منابع زیر استفاده کنید:

- **توکن ربات تلگرام**: برای دریافت توکن ربات تلگرام، از طریق [@BotFather](https://t.me/botfather) یک ربات جدید بسازید.

```bash
TELEGRAM_API_TOKEN = 123456789:XXXXXXXXXXXXXXXX
```

- **چت آیدی ادمین**: از [@chatidbot](https://t.me/userinfobot) برای دریافت چت آیدی خود استفاده کنید.

```bash
TELEGRAM_ADMIN_ID = 123456789
```

- **کانال تلگرام** (اختیاری): از [@chatidbot](https://t.me/userinfobot) برای دریافت چت آیدی کانال تلگرام خود استفاده کنید.

```bash
TELEGRAM_LOGGER_CHANNEL_ID = -1234567890123
```

- **آدرس پروکسی تلگرام** (اختیاری): اگر از پروکسی استفاده می‌کنید، آدرس پروکسی خود را وارد کنید.

```bash
TELEGRAM_PROXY_URL = "http://localhost:8080"
```

### ریستارت کردن سرویس مرزنشین  

پس از تنظیم مقادیر، برای اعمال تغییرات، باید سرویس مرزنشین را ریستارت کنید:

```bash
marzneshin restart
```

از این بعد اعلانات مرتبط با کاربران رو دریافت خواهید کرد.

{{% /steps %}}


{{< /tab >}}  

{{< tab >}}  

وبهوک روشی برای دریافت اعلان‌های (نوتیفیکیشن‌های) تلگرام بات است که به جای ارسال به خود بات تلگرامی، مستقیماً به API شما ارسال می‌شود. این قابلیت به شما امکان می‌دهد تا در سایت‌ها یا نرم‌افزارهای خود از این اعلان‌ها استفاده کنید. با این حال، استفاده از وبهوک به دانش تخصصی برنامه‌نویسی نیاز دارد و معمولاً برای کاربران عادی مناسب نیست.

{{< /tab >}}  

{{< /tabs >}}


