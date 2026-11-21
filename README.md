# LENANON-CAR — مركز تحديثات تطبيق لوحات لبنان

هذا المستودع مخصّص لاستضافة **تحديثات التطبيق وقاعدة البيانات** عبر GitHub Releases وملف `manifest.json` بدءاً من الإصدار **v1.9.0**.
(الكود المصدري للتطبيق محفوظ بشكل مستقل في مستودع `LebanonPlates`.)

## طريقة نشر تحديث جديد

### 1. تحديث التطبيق (APK)
1. أنشئ **GitHub Release** جديداً بوسم `v1.9.0` (أو رقم الإصدار الجديد).
2. ارفع ملف الـ APK الموقّع بمفتاح الزبائن (`LebanonPlates_v1.9.0.apk`).
3. احسب بصمة `SHA-256` للملف (في PowerShell: `Get-FileHash LebanonPlates_v1.9.0.apk -Algorithm SHA256`).
4. حدّث قسم `"app"` في [manifest.json](manifest.json) وادفع التعديل إلى الفرع `main`.

### 2. تحديث قاعدة البيانات (`plates.db.zip`)
1. اضغط ملف `plates.db` في أرشيف `plates.db.zip` (التطبيق يفك الضغط ويتحقق من `SHA-256` وبنية SQLite تلقائياً).
2. ارفعه في GitHub Release بوسم `db-v1.0.0` (أو رقم إصدار القاعدة).
3. حدّث قسم `"database"` في [manifest.json](manifest.json) وادفع التعديل إلى الفرع `main`.
