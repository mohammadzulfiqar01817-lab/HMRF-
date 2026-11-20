# HMR Foundation — ওয়েব অ্যাপ ও Android প্রস্তুতি

এই প্যাকেজে দেওয়া হয়েছে:
- `index.html` — আপনার দেওয়া HMR Foundation প্রোটোটাইপ
- `manifest.webmanifest` ও `service-worker.js` — PWA ইনস্টল/অফলাইন shell-এর প্রাথমিক ব্যবস্থা
- `capacitor.config.json` ও `package.json` — Android Capacitor wrapper তৈরির কনফিগারেশন

## ওয়েব অ্যাপ প্রকাশ
1. GitHub-এ `hmr-foundation` নামে একটি repository তৈরি করুন।
2. এই ফোল্ডারের সব ফাইল repository-র root-এ upload করুন।
3. GitHub repository → Settings → Pages → Deploy from a branch নির্বাচন করুন।
4. Branch `main`, folder `/(root)` দিয়ে Save করুন।
5. প্রকাশিত URL হবে `https://YOUR-USERNAME.github.io/hmr-foundation/` (username GitHub-এর নিজের username দিয়ে বদলাতে হবে)।

## Android APK তৈরির প্রস্তুতি
এটি source project; APK এখনো build করা হয়নি। APK build করতে কম্পিউটারে Node.js ও Android Studio/Android SDK প্রয়োজন:

```bash
npm install
npx cap add android
npx cap sync android
npx cap open android
```

Android Studio-তে Gradle sync শেষ হলে Build → Build Bundle(s) / APK(s) → Build APK(s) নির্বাচন করুন।

## গুরুত্বপূর্ণ নিরাপত্তা সতর্কতা
বর্তমান মূল HTML-এ ডেটা `localStorage`-এ থাকে এবং লগইনটি prototype/demo মাত্র। এটি production authentication বা cloud database নয়। বাস্তব সদস্য/আর্থিক তথ্য যোগ করার আগে Firebase/Supabase/নিজস্ব backend, server-side authorization, secure authentication, database rules, backup এবং privacy review আবশ্যক। PWA cache/local storage-এ সংবেদনশীল তথ্য রাখবেন না।
