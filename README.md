# VP STORE – panduan pasang (gratis)

File: index.html (toko), admin.html (dashboard penjual), firebase-config.js, firestore.rules.

1. Buka console.firebase.google.com, buat proyek baru.
2. Build > Authentication > Get started. Aktifkan provider **Google** dan **Email/Password**.
3. Build > Firestore Database > Create database (production mode). Tab Rules: tempel isi firestore.rules, lalu Publish.
4. Project settings > Your apps > ikon Web (</>) > daftarkan app. Salin isi firebaseConfig ke firebase-config.js.
5. Authentication > Users > Add user. Email: developerdasbord@vpstore.app (ID Developerdasbord di halaman login otomatis jadi email ini). Isi password yang KUAT, jangan Admin123. Salin User UID akun itu.
6. Firestore > Start collection `admins` > Document ID = UID tadi > isi satu field bebas (mis. role = admin). Hanya UID di sini yang boleh mengubah produk.
7. Pasang ke hosting gratis: Firebase Hosting (`firebase deploy`), Netlify (drag-drop folder), atau Cloudflare Pages.
8. Authentication > Settings > Authorized domains: tambahkan domain hosting kamu (syarat login Google).
9. Buka /admin.html, masuk dengan ID dan password, isi nomor WhatsApp lalu tambahkan produk.

Catatan: foto disimpan terkompres di Firestore (gratis, tanpa Firebase Storage). Pembeli wajib login Google sebelum tombol pesan muncul; setiap klik pesan tercatat di dashboard.
