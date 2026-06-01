<div align="center">
  <br />

  <h1>LAPORAN PRAKTIKUM <br>
  APLIKASI BERBASIS PLATFORM
  </h1>

  <br />

  <h3>MODUL - 8&9 Mobile<br>
  Notifikasi & API Perangkat Keras
  </h3>

  <br />

  <img width="512" height="512" alt="telyu" src="https://github.com/user-attachments/assets/22ae9b17-5e73-48a6-b5dd-281e6c70613e" />



  <br />
  <br />
  <br />

  <h3>Disusun Oleh :</h3>

  <p>
    <strong>Andika Neviantoro</strong><br>
    <strong>2311102167</strong><br>
    <strong>S1 IF-11-REG01</strong>
  </p>

  <br />

  <h3>Dosen Pengampu :</h3>

  <p>
    <strong>Dimas Fanny Hebrasianto Permadi, S.ST., M.Kom</strong>
  </p>
  
  <br />
  <br />
    <h4>Asisten Praktikum :</h4>
    <strong>Apri Pandu Wicaksono </strong> <br>
    <strong>Rangga Pradarrell Fathi</strong>
  <br />

  <h3>LABORATORIUM HIGH PERFORMANCE
 <br>FAKULTAS INFORMATIKA <br>UNIVERSITAS TELKOM PURWOKERTO <br>2026</h3>
</div>

<hr>


## 📌 Deskripsi Proyek

Aplikasi Flutter sederhana yang mengimplementasikan penggunaan **API Perangkat Keras** pada platform mobile. Aplikasi ini mendemonstrasikan:

- Mengakses **kamera perangkat** secara langsung untuk mengambil foto
- Mengakses **galeri foto** untuk memilih foto yang sudah ada
- Menampilkan **notifikasi lokal** sebagai feedback setelah foto berhasil diambil/dipilih

---

## 📚 Dasar Teori

### 1. Camera API pada Flutter

Camera API adalah antarmuka pemrograman yang memungkinkan aplikasi mobile mengakses perangkat keras kamera secara langsung. Pada Flutter, akses kamera dapat dilakukan melalui beberapa pendekatan:

- **Package `camera`** — memberikan kontrol penuh atas kamera (preview, zoom, flash, dll)
- **Package `image_picker`** — cara yang lebih sederhana untuk mengambil foto dari kamera maupun galeri tanpa perlu mengelola lifecycle kamera secara manual

Package `image_picker` menggunakan `ImageSource.camera` untuk membuka kamera native perangkat dan `ImageSource.gallery` untuk membuka galeri. Hasil foto dikembalikan sebagai objek `XFile` yang berisi path file sementara.

**Cara kerja:**
1. Aplikasi memanggil `ImagePicker().pickImage(source: ImageSource.camera)`
2. Sistem operasi membuka aplikasi kamera native
3. Pengguna mengambil foto dan mengkonfirmasi
4. Path file foto dikembalikan ke aplikasi Flutter
5. File ditampilkan menggunakan widget `Image.file(File(path))`

### 2. image_picker

`image_picker` adalah package Flutter resmi yang menyediakan abstraksi untuk mengakses kamera dan galeri di Android maupun iOS. Package ini menangani semua detail platform-specific secara otomatis, termasuk:

- Permintaan izin kamera dan penyimpanan
- Membuka intent kamera (Android) / UIImagePickerController (iOS)
- Kompresi gambar via parameter `imageQuality`
- Pemilihan kamera depan/belakang via `preferredCameraDevice`

### 3. Notifikasi Lokal (flutter_local_notifications)

Notifikasi lokal adalah notifikasi yang dibuat dan ditampilkan oleh aplikasi itu sendiri tanpa memerlukan koneksi internet atau server. Berbeda dengan push notification (FCM/APNs) yang dikirim dari server eksternal, notifikasi lokal sepenuhnya dikelola di dalam perangkat.

**Package `flutter_local_notifications`** menyediakan API terpadu untuk:
- Menampilkan notifikasi instan
- Menjadwalkan notifikasi di waktu tertentu
- Mengelola channel notifikasi (Android 8.0+)
- Kustomisasi ikon, suara, dan vibasi

**Alur kerja notifikasi lokal:**
1. Inisialisasi plugin dengan `InitializationSettings` untuk Android & iOS
2. Buat `AndroidNotificationDetails` dengan Channel ID yang unik
3. Panggil `flutterLocalNotificationsPlugin.show()` untuk menampilkan notifikasi

### 4. Permission Handling

Pada Android 6.0+ (API 23), akses ke kamera, penyimpanan, dan notifikasi harus diminta secara eksplisit saat runtime. Pada Android 13+ (API 33), izin notifikasi (`POST_NOTIFICATIONS`) juga harus diminta secara runtime. Flutter menangani ini melalui deklarasi di `AndroidManifest.xml` dan runtime request oleh masing-masing package.


## 📷 Fitur 1 — Ambil Foto (Camera API)

### Deskripsi
Fitur ini memungkinkan pengguna membuka kamera perangkat secara langsung dengan menekan tombol **"Buka Kamera"**. Setelah foto diambil, gambar langsung ditampilkan di halaman yang sama.

### Source Code

**`lib/home_page.dart` — Fungsi ambil foto dari kamera:**

```dart
Future<void> _ambilFotoKamera() async {
  setState(() => _isLoading = true);

  try {
    // Membuka kamera perangkat menggunakan ImagePicker
    final XFile? foto = await _picker.pickImage(
      source: ImageSource.camera,           // Sumber: kamera langsung
      imageQuality: 85,                     // Kualitas kompresi gambar (0-100)
      preferredCameraDevice: CameraDevice.rear, // Gunakan kamera belakang
    );

    if (foto != null) {
      // Untuk web: baca sebagai bytes (Image.file tidak support web)
      if (kIsWeb) {
        final bytes = await foto.readAsBytes();
        setState(() {
          _selectedImageBytes = bytes;
          _imageSource = 'Kamera 📸';
        });
      } else {
        // Untuk Android/iOS: simpan sebagai File
        setState(() {
          _selectedImageFile = File(foto.path);
          _imageSource = 'Kamera 📸';
        });
      }

      // Jalankan animasi fade-in
      _fadeController.reset();
      _fadeController.forward();

      // Tampilkan notifikasi lokal
      await NotificationService.showCameraNotification();

      // Tampilkan SnackBar konfirmasi
      if (mounted) {
        _showSnackBar('✅ Foto berhasil diambil dari kamera!', Colors.green);
      }
    }
  } catch (e) {
    if (mounted) {
      _showSnackBar('❌ Gagal membuka kamera: $e', Colors.red);
    }
  } finally {
    setState(() => _isLoading = false);
  }
}
```

**Tombol Kamera (Widget `_CameraButton`):**

```dart
Expanded(
  child: _CameraButton(
    icon: Icons.camera_alt,
    label: 'Buka Kamera',
    subtitle: 'Ambil foto langsung',
    color: const Color(0xFF1A73E8),  // Warna biru
    isLoading: _isLoading,
    onPressed: _ambilFotoKamera,     // Fungsi yang dipanggil saat ditekan
  ),
),
```

**Widget custom `_CameraButton`:**

```dart
class _CameraButton extends StatelessWidget {
  final IconData icon;
  final String label;
  final String subtitle;
  final Color color;
  final bool isLoading;
  final VoidCallback onPressed;

  @override
  Widget build(BuildContext context) {
    return Material(
      color: color,
      borderRadius: BorderRadius.circular(16),
      elevation: 4,
      child: InkWell(
        onTap: isLoading ? null : onPressed,  // Nonaktif saat loading
        borderRadius: BorderRadius.circular(16),
        splashColor: Colors.white24,           // Efek ripple putih
        child: Padding(
          padding: const EdgeInsets.symmetric(vertical: 18, horizontal: 12),
          child: Column(
            children: [
              // Tampilkan loading spinner atau ikon
              isLoading
                  ? const CircularProgressIndicator(strokeWidth: 3)
                  : Icon(icon, color: Colors.white, size: 32),
              const SizedBox(height: 10),
              Text(label, style: const TextStyle(color: Colors.white,
                  fontSize: 14, fontWeight: FontWeight.bold)),
              Text(subtitle, style: const TextStyle(
                  color: Colors.white70, fontSize: 11)),
            ],
          ),
        ),
      ),
    );
  }
}
```

### Penjelasan Widget

| Widget | Fungsi |
|--------|--------|
| `ImagePicker` | Instance plugin untuk mengakses kamera dan galeri |
| `ImageSource.camera` | Konstanta yang memberi tahu `image_picker` untuk membuka kamera |
| `XFile` | Objek hasil dari `pickImage()` yang berisi path file foto |
| `Image.file()` | Menampilkan gambar dari file lokal di Android/iOS |
| `Image.memory()` | Menampilkan gambar dari bytes, digunakan untuk Flutter Web |
| `kIsWeb` | Konstanta dari `package:flutter/foundation.dart` untuk deteksi platform web |
| `FadeTransition` | Animasi fade-in saat foto baru dimuat (durasi 600ms) |
| `AnimatedContainer` | Container yang berubah tinggi secara animasi (200px → 320px) |

---

## Fitur 2 — Pilih Foto dari Galeri

### Deskripsi
Fitur ini memungkinkan pengguna membuka galeri foto perangkat dan memilih foto yang sudah ada dengan menekan tombol **"Pilih Galeri"**. Foto yang dipilih langsung ditampilkan di halaman yang sama.

### Source Code

**`lib/home_page.dart` — Fungsi pilih foto dari galeri:**

```dart
Future<void> _pilihFotoGaleri() async {
  setState(() => _isLoading = true);

  try {
    // Membuka galeri foto menggunakan ImagePicker
    final XFile? foto = await _picker.pickImage(
      source: ImageSource.gallery,  // Sumber: galeri perangkat
      imageQuality: 85,             // Kualitas kompresi gambar
    );

    if (foto != null) {
      if (kIsWeb) {
        // Web: baca sebagai bytes
        final bytes = await foto.readAsBytes();
        setState(() {
          _selectedImageBytes = bytes;
          _imageSource = 'Galeri 🖼️';
        });
      } else {
        // Mobile: simpan sebagai File
        setState(() {
          _selectedImageFile = File(foto.path);
          _imageSource = 'Galeri 🖼️';
        });
      }

      _fadeController.reset();
      _fadeController.forward();

      // Tampilkan notifikasi lokal galeri
      await NotificationService.showGalleryNotification();

      if (mounted) {
        _showSnackBar('✅ Foto berhasil dipilih dari galeri!', Colors.blue);
      }
    }
  } catch (e) {
    if (mounted) {
      _showSnackBar('❌ Gagal membuka galeri: $e', Colors.red);
    }
  } finally {
    setState(() => _isLoading = false);
  }
}
```

**Tombol Galeri:**

```dart
Expanded(
  child: _CameraButton(
    icon: Icons.photo_library,
    label: 'Pilih Galeri',
    subtitle: 'Foto yang ada',
    color: const Color(0xFF34A853),  // Warna hijau
    isLoading: _isLoading,
    onPressed: _pilihFotoGaleri,     // Fungsi yang dipanggil saat ditekan
  ),
),
```

**Menampilkan foto hasil (platform-aware):**

```dart
Widget _buildImage() {
  if (_selectedImageBytes != null) {
    // Web: gunakan Image.memory dari bytes
    return Image.memory(
      _selectedImageBytes!,
      fit: BoxFit.cover,
      width: double.infinity,
    );
  } else if (_selectedImageFile != null) {
    // Mobile: gunakan Image.file
    return Image.file(
      _selectedImageFile!,
      fit: BoxFit.cover,
      width: double.infinity,
    );
  }
  return const SizedBox();
}
```

### Penjelasan Widget

| Widget | Fungsi |
|--------|--------|
| `ImageSource.gallery` | Konstanta untuk membuka galeri foto perangkat |
| `BoxFit.cover` | Gambar mengisi seluruh container tanpa distorsi |
| `setState()` | Memberitahu Flutter untuk rebuild widget setelah state berubah |
| `SnackBar` | Pesan popup floating di bawah layar sebagai feedback pengguna |
| `ScaffoldMessenger` | Widget untuk menampilkan SnackBar secara global dalam Scaffold |

---

## Fitur 3 — Notifikasi Lokal

### Deskripsi
Setelah foto berhasil diambil atau dipilih, aplikasi menampilkan **notifikasi lokal** di notification bar perangkat menggunakan package `flutter_local_notifications`. Terdapat dua jenis notifikasi: satu untuk foto dari kamera dan satu untuk foto dari galeri.

### Source Code

**`lib/main.dart` — Inisialisasi plugin notifikasi:**

```dart
// Instance global plugin, bisa diakses dari seluruh file
final FlutterLocalNotificationsPlugin flutterLocalNotificationsPlugin =
    FlutterLocalNotificationsPlugin();

void main() async {
  // Wajib dipanggil sebelum menggunakan plugin apapun
  WidgetsFlutterBinding.ensureInitialized();

  // Setting inisialisasi untuk Android
  // '@mipmap/ic_launcher' adalah ikon notifikasi (dari res/mipmap)
  const AndroidInitializationSettings androidSettings =
      AndroidInitializationSettings('@mipmap/ic_launcher');

  // Setting inisialisasi untuk iOS
  const DarwinInitializationSettings iosSettings =
      DarwinInitializationSettings(
    requestAlertPermission: true,  // Minta izin tampilkan alert
    requestBadgePermission: true,  // Minta izin badge di ikon app
    requestSoundPermission: true,  // Minta izin suara notifikasi
  );

  // Gabungkan setting Android dan iOS
  const InitializationSettings initSettings = InitializationSettings(
    android: androidSettings,
    iOS: iosSettings,
  );

  // Inisialisasi plugin dengan setting di atas
  await flutterLocalNotificationsPlugin.initialize(initSettings);

  runApp(const MyApp());
}
```

**`lib/notification_service.dart` — Service notifikasi:**

```dart
import 'package:flutter_local_notifications/flutter_local_notifications.dart';
import '../main.dart';

class NotificationService {
  // ID unik untuk setiap notifikasi (mencegah tumpang tindih)
  static const int _cameraNotifId = 1001;
  static const int _galleryNotifId = 1002;

  /// Meminta izin notifikasi (wajib untuk Android 13+)
  static Future<void> requestPermission() async {
    final AndroidFlutterLocalNotificationsPlugin? androidPlugin =
        flutterLocalNotificationsPlugin
            .resolvePlatformSpecificImplementation<
                AndroidFlutterLocalNotificationsPlugin>();

    if (androidPlugin != null) {
      await androidPlugin.requestNotificationsPermission();
    }
  }

  /// Notifikasi setelah foto diambil dari KAMERA
  static Future<void> showCameraNotification() async {
    const AndroidNotificationDetails androidDetails =
        AndroidNotificationDetails(
      'camera_channel',          // Channel ID — unik per kategori notifikasi
      'Kamera Notifikasi',       // Nama channel (tampil di pengaturan HP)
      channelDescription: 'Notifikasi setelah mengambil foto dari kamera',
      importance: Importance.high,   // Prioritas tinggi = tampil sebagai heads-up
      priority: Priority.high,
      playSound: true,               // Mainkan suara notifikasi
      enableVibration: true,         // Aktifkan getaran
      icon: '@mipmap/ic_launcher',   // Ikon notifikasi
    );

    const NotificationDetails notifDetails = NotificationDetails(
      android: androidDetails,
      iOS: DarwinNotificationDetails(
        presentAlert: true,   // Tampilkan sebagai alert di iOS
        presentBadge: true,   // Tampilkan badge di ikon app
        presentSound: true,   // Mainkan suara
      ),
    );

    // Tampilkan notifikasi
    await flutterLocalNotificationsPlugin.show(
      _cameraNotifId,                          // ID notifikasi
      '📸 Foto Berhasil Diambil!',             // Judul notifikasi
      'Foto dari kamera telah berhasil ditangkap dan siap digunakan.',
      notifDetails,
    );
  }

  /// Notifikasi setelah foto dipilih dari GALERI
  static Future<void> showGalleryNotification() async {
    const AndroidNotificationDetails androidDetails =
        AndroidNotificationDetails(
      'gallery_channel',         // Channel ID berbeda dari kamera
      'Galeri Notifikasi',
      channelDescription: 'Notifikasi setelah memilih foto dari galeri',
      importance: Importance.high,
      priority: Priority.high,
      playSound: true,
      enableVibration: true,
    );

    const NotificationDetails notifDetails = NotificationDetails(
      android: androidDetails,
      iOS: DarwinNotificationDetails(
        presentAlert: true,
        presentBadge: true,
        presentSound: true,
      ),
    );

    await flutterLocalNotificationsPlugin.show(
      _galleryNotifId,
      '🖼️ Foto Berhasil Dipilih!',
      'Foto dari galeri telah berhasil dipilih dan ditampilkan.',
      notifDetails,
    );
  }
}
```

### Penjelasan Widget & Komponen Notifikasi

| Komponen | Fungsi |
|----------|--------|
| `FlutterLocalNotificationsPlugin` | Instance utama plugin notifikasi |
| `AndroidInitializationSettings` | Konfigurasi awal untuk platform Android, berisi nama ikon |
| `DarwinInitializationSettings` | Konfigurasi awal untuk platform iOS/macOS |
| `InitializationSettings` | Menggabungkan setting Android dan iOS menjadi satu objek |
| `AndroidNotificationDetails` | Detail notifikasi khusus Android: channel, importance, suara, vibrasi |
| `DarwinNotificationDetails` | Detail notifikasi khusus iOS: alert, badge, sound |
| `NotificationDetails` | Menggabungkan detail Android dan iOS |
| `Importance.high` | Notifikasi tampil sebagai heads-up (muncul di atas layar) |
| `Channel ID` | String unik yang mengidentifikasi kategori notifikasi di Android 8.0+ |
| `.show()` | Method untuk menampilkan notifikasi secara instan |
| `requestNotificationsPermission()` | Meminta izin notifikasi di runtime (Android 13+) |

---

## Output:

<img src="Images/gambar 1.png" width="250">

<img src="Images/gambar 2.png" width="250">

<img src="Images/gambar 3.png" width="250">

<img src="Images/gambar 4.png" width="250">

<img src="Images/gambar 5.png" width="250">
