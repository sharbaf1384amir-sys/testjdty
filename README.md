# SMS Forwarder - اپ اندروید کنترل والدین

## چه کاری می‌کنه؟
- هر پیامکی که به گوشی فرزند میاد، فوراً به ربات تلگرام شما ارسال میشه
- بعد از deploy، سرور آدرس ثابت می‌گیره
- اگه URL تنظیم کنید، موقع باز شدن اپ، مرورگر با اون URL باز میشه
- سرویس بعد از خاموش/روشن شدن گوشی هم خودکار شروع میشه

---

## مرحله ۱: تنظیم آدرس سرور

فایل زیر رو باز کنید:
```
app/src/main/java/com/parentcontrol/smsforwarder/Config.kt
```

خط زیر رو ویرایش کنید:
```kotlin
var SERVER_URL = "https://YOUR_SERVER_URL/api/sms"
```

بعد از deploy کردن سرور در Replit، آدرس اینجور میشه:
```
https://[نام-پروژه].replit.app/api/sms
```

---

## مرحله ۲ (اختیاری): تنظیم سایت

اگه می‌خواید موقع باز شدن اپ یه سایت نشون داده بشه:
```kotlin
var WEBSITE_URL = "https://google.com"  // آدرس سایت دلخواه
```
اگه خالی بمونه، اپ خودش نمایش داده میشه.

---

## مرحله ۳: ساخت APK

### روش ۱: Android Studio (توصیه‌شده)
1. [Android Studio](https://developer.android.com/studio) رو نصب کنید
2. پوشه `android-app` رو به عنوان پروژه باز کنید
3. منوی `Build` ← `Build Bundle(s) / APK(s)` ← `Build APK(s)` رو بزنید
4. APK در مسیر `app/build/outputs/apk/debug/app-debug.apk` ساخته میشه

### روش ۲: Command Line (اگه Java و Android SDK دارید)
```bash
cd android-app
./gradlew assembleDebug
```

---

## مرحله ۴: نصب روی گوشی
1. APK رو به گوشی منتقل کنید
2. در تنظیمات گوشی، **نصب از منابع ناشناس** رو فعال کنید
3. APK رو نصب کنید
4. اپ رو باز کنید و دسترسی پیامک رو بدید

---

## ساختار پیامک در تلگرام
```
📩 پیامک جدید
👤 از: 09123456789
🕐 زمان: ۱۴۰۵/۳/۲۱ ۱۴:۳۰
📱 دستگاه: Samsung Galaxy A54

💬 متن:
متن پیامک اینجاست
```

---

## نیازمندی‌ها
- Android 5.0 (API 21) یا بالاتر
- اتصال اینترنت برای ارسال به سرور
