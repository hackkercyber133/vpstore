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
9. Buka /admin.html, masuk dengan ID dan password. Menu Pembayaran: isi DP bawaan, nomor WhatsApp, dan rekening (bank/e-wallet). Menu Produk: tambahkan produk (harga boleh ditulis 150000 atau 150rb, foto boleh banyak).

Catatan: foto disimpan terkompres di Firestore (gratis, tanpa Firebase Storage). Pembeli bisa mengisi keranjang tanpa login, tapi wajib login Google untuk checkout. Pesanan baru tersimpan dan muncul di dashboard admin hanya setelah pembeli mengirim bukti DP/lunas; admin lalu menekan Terima atau Tolak. PENTING: salin ulang firestore.rules ke Firebase lalu Publish.

Video produk: di menu Produk, isi kolom Video dengan link YouTube atau alamat file mp4 yang diupload ke GitHub (mis. videos/cooler.mp4). Maksimal 3 video per produk.
