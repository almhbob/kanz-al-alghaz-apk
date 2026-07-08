# كنز الألغاز — تطبيق أندرويد

غلاف Capacitor يحزم لعبة `kanz-al-alghaz/index.html` كتطبيق أندرويد أصلي.

## البناء التلقائي (GitHub Actions)

كل دفعة (push) تلمس هذا المجلد تُشغّل `.github/workflows/android-apk.yml` تلقائيًا،
والذي يبني ملف APK للتجربة (`app-debug.apk`) ويرفعه كـ Artifact في تبويب Actions.

## البناء يدويًا (على جهاز يملك Android SDK)

```bash
cd mobile
npm install
npx cap sync android
cd android
./gradlew assembleDebug
# الناتج: android/app/build/outputs/apk/debug/app-debug.apk
```

## تحديث محتوى اللعبة داخل التطبيق

عند تعديل `kanz-al-alghaz/index.html`، انسخه إلى `mobile/www/index.html`
(وكذلك `manifest.webmanifest` و`icons/` إن تغيّرت) قبل التشغيل أعلاه.
