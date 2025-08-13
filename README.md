# Ngabsen WebView App (Template)

Aplikasi Flutter sederhana yang membungkus `https://ngabsen.smkmaarif9kebumen.sch.id` ke dalam WebView.
Termasuk splash screen & template ikon aplikasi.

## Cara Pakai (Cepat & Aman)

> Syarat: Flutter terpasang (kamu pakai 3.32.8 OK), Android SDK OK.

1. **Buat project baru** (biar folder Android/iOS lengkap):
   ```bash
   flutter create ngabsen_app
   ```
2. **Salin file dari ZIP ini** ke folder project yang baru dibuat:
   - Ganti `lib/main.dart` dengan yang dari ZIP ini.
   - Salin folder `assets/` ke project.
   - Ganti `pubspec.yaml` project dengan yang dari ZIP ini (atau tambahkan bagian yang beda).
3. **Aktifkan dependency dan generate ikon + splash:**
   ```bash
   cd ngabsen_app
   flutter pub get
   dart run flutter_launcher_icons
   dart run flutter_native_splash:create
   ```
4. **Tambahkan permission Internet di AndroidManifest (jika belum ada):**
   Edit `android/app/src/main/AndroidManifest.xml`, di atas `<application ...>` tambahkan:
   ```xml
   <uses-permission android:name="android.permission.INTERNET"/>
   ```
5. **Build APK rilis:**
   ```bash
   flutter build apk --release
   ```
   Hasil: `build/app/outputs/flutter-apk/app-release.apk`

## Kustomisasi
- Ganti `assets/logo.png` untuk splash screen.
- Ganti `assets/app_icon.png` untuk ikon aplikasi.
- Ubah judul app di `lib/main.dart` (MaterialApp title).
- Ubah URL WebView di `lib/main.dart` jika diperlukan.

## Catatan
- Jika web perlu akses kamera/GPS di dalam WebView, pastikan:
  - HTTPS sudah aktif (sudah).
  - Tambahkan permission yang dibutuhkan di `AndroidManifest.xml` (misal `ACCESS_FINE_LOCATION`, `CAMERA`), lalu handle permission via JS/HTML di web.
- Kalau mau package name khusus (misal `id.sch.smkmaarif9kebumen.ngabsen`), jalankan:
  ```bash
  flutter create --org id.sch.smkmaarif9kebumen ngabsen_app
  ```
  **Sebelum** menyalin file-file dari ZIP ini.

Selamat membangun! 🚀