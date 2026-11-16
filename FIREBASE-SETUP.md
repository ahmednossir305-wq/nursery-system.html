# ربط قاعدة البيانات (Firebase - مجاني)
1. console.firebase.google.com → Add project → أي اسم → أوقف Analytics.
2. Build → Firestore Database → Create → Production → أقرب منطقة.
3. تبويب Rules والصق ثم Publish:
```
rules_version = '2';
service cloud.firestore { match /databases/{database}/documents { match /{document=**} { allow read, write: if request.auth != null && request.auth.token.email == 'staff@nursery-app.com'; } } }
```
4. Build → Authentication → Get started → Email/Password → Enable → Users → Add user: `staff@nursery-app.com` + كلمة سر.
5. Project settings → Your apps → Web (</>) → Register → انسخ firebaseConfig وأرسله.
