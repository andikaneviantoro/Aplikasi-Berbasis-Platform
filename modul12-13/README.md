# 📱 Tugas Praktik Modul 12 & 13 — Flutter Provider & Notifikasi

> **Implementasi State Management Provider dan Local Notification pada Flutter**

---

## 📁 Struktur Proyek

```
counter_provider_app/
├── lib/
│   ├── main.dart                  # Entry point & setup Provider
│   ├── counter_provider.dart      # Model Provider untuk counter
│   └── home_screen.dart           # Tampilan utama
├── pubspec.yaml                   # Dependencies
└── README.md
```

---

## 🛠️ Source Code

### `pubspec.yaml`
```yaml
name: counter_provider_app
description: Aplikasi Counter dengan Provider dan Local Notification

environment:
  sdk: ">=3.0.0 <4.0.0"

dependencies:
  flutter:
    sdk: flutter
  provider: ^6.1.2
  flutter_local_notifications: ^17.2.2

flutter:
  uses-material-design: true
```

---

### `lib/counter_provider.dart`
```dart
import 'package:flutter/foundation.dart';

class CounterProvider extends ChangeNotifier {
  int _counter = 0;

  int get counter => _counter;

  void increment() {
    _counter++;
    notifyListeners();
  }
}
```

---

### `lib/main.dart`
```dart
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';
import 'package:flutter_local_notifications/flutter_local_notifications.dart';
import 'counter_provider.dart';
import 'home_screen.dart';

final FlutterLocalNotificationsPlugin flutterLocalNotificationsPlugin =
    FlutterLocalNotificationsPlugin();

Future<void> main() async {
  WidgetsFlutterBinding.ensureInitialized();

  const AndroidInitializationSettings androidInit =
      AndroidInitializationSettings('@mipmap/ic_launcher');

  const InitializationSettings initSettings =
      InitializationSettings(android: androidInit);

  await flutterLocalNotificationsPlugin.initialize(initSettings);

  runApp(
    ChangeNotifierProvider(
      create: (_) => CounterProvider(),
      child: const MyApp(),
    ),
  );
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Counter Provider App',
      debugShowCheckedModeBanner: false,
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: const Color(0xFF1565C0)),
        useMaterial3: true,
      ),
      home: const HomeScreen(),
    );
  }
}
```

---

### `lib/home_screen.dart`
```dart
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';
import 'package:flutter_local_notifications/flutter_local_notifications.dart';
import 'main.dart';
import 'counter_provider.dart';

class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key});

  Future<void> _showNotification(int counterValue) async {
    const AndroidNotificationDetails androidDetails = AndroidNotificationDetails(
      'counter_channel',
      'Counter Notifications',
      channelDescription: 'Notifikasi untuk update nilai counter',
      importance: Importance.max,
      priority: Priority.high,
      color: Color(0xFF1565C0),
    );

    const NotificationDetails notifDetails =
        NotificationDetails(android: androidDetails);

    await flutterLocalNotificationsPlugin.show(
      0,
      'Counter Update',
      'Nilai counter saat ini: $counterValue',
      notifDetails,
    );
  }

  @override
  Widget build(BuildContext context) {
    final counter = context.watch<CounterProvider>();

    return Scaffold(
      backgroundColor: const Color(0xFFE3F2FD),
      appBar: AppBar(
        backgroundColor: const Color(0xFF1565C0),
        title: const Text(
          'Counter Provider App',
          style: TextStyle(color: Colors.white, fontWeight: FontWeight.bold),
        ),
        centerTitle: true,
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            const Icon(Icons.countertops_rounded,
                size: 80, color: Color(0xFF1565C0)),
            const SizedBox(height: 20),
            const Text(
              'Nilai Counter',
              style: TextStyle(
                fontSize: 22,
                color: Color(0xFF1565C0),
                fontWeight: FontWeight.w600,
              ),
            ),
            const SizedBox(height: 12),
            Container(
              padding: const EdgeInsets.symmetric(horizontal: 40, vertical: 20),
              decoration: BoxDecoration(
                color: const Color(0xFF1565C0),
                borderRadius: BorderRadius.circular(20),
                boxShadow: const [
                  BoxShadow(
                    color: Color(0x441565C0),
                    blurRadius: 12,
                    offset: Offset(0, 6),
                  ),
                ],
              ),
              child: Text(
                '${counter.counter}',
                style: const TextStyle(
                  fontSize: 64,
                  fontWeight: FontWeight.bold,
                  color: Colors.white,
                ),
              ),
            ),
            const SizedBox(height: 40),
            ElevatedButton.icon(
              onPressed: () {
                context.read<CounterProvider>().increment();
                _showNotification(counter.counter + 1);
              },
              icon: const Icon(Icons.add, size: 28),
              label: const Text(
                'Tambah  (+)',
                style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
              ),
              style: ElevatedButton.styleFrom(
                backgroundColor: const Color(0xFF1565C0),
                foregroundColor: Colors.white,
                padding:
                    const EdgeInsets.symmetric(horizontal: 40, vertical: 16),
                shape: RoundedRectangleBorder(
                  borderRadius: BorderRadius.circular(14),
                ),
                elevation: 6,
              ),
            ),
          ],
        ),
      ),
    );
  }
}
```

---

## 📸 Screenshot

### Tampilan Halaman Aplikasi

![Home Screen](screenshots/Image1.jpeg)

---

### Notifikasi yang Muncul

![Notification](screenshots/Image2.jpeg)

---

## 📄 Laporan Singkat

### Cara Kerja Provider pada Aplikasi

Provider adalah solusi **state management** yang digunakan untuk menyimpan dan menyebarkan nilai counter ke seluruh widget yang membutuhkannya. Kelas `CounterProvider` mewarisi `ChangeNotifier` sehingga dapat memanggil `notifyListeners()` setiap kali nilai counter berubah melalui method `increment()`. Di `main.dart`, `ChangeNotifierProvider` membungkus seluruh aplikasi agar `CounterProvider` dapat diakses dari mana saja. Pada `HomeScreen`, `context.watch<CounterProvider>()` digunakan untuk **membaca dan mendengarkan** perubahan nilai counter — ketika `notifyListeners()` dipanggil, widget akan otomatis di-rebuild dan menampilkan nilai terbaru tanpa perlu `setState()`.

### Cara Kerja Notifikasi yang Digunakan

Aplikasi menggunakan **Local Notification** melalui package `flutter_local_notifications`. Inisialisasi dilakukan satu kali di `main()` dengan menyiapkan `AndroidInitializationSettings` dan memanggil `initialize()`. Setiap kali tombol **Tambah (+)** ditekan, fungsi `_showNotification()` dipanggil dengan nilai counter terbaru — fungsi ini membuat `AndroidNotificationDetails` (channel, prioritas, warna biru) lalu memanggil `flutterLocalNotificationsPlugin.show()` yang menampilkan notifikasi secara langsung di status bar perangkat dengan **judul "Counter Update"** dan **pesan "Nilai counter saat ini: X"**.

---

## ⚙️ Cara Menjalankan

```bash
# 1. Clone / salin proyek
cd counter_provider_app

# 2. Install dependencies
flutter pub get

# 3. Jalankan di emulator / perangkat fisik
flutter run
```

> **Catatan:** Pastikan izin notifikasi diaktifkan di perangkat Android (Android 13+ memerlukan permission `POST_NOTIFICATIONS` di `AndroidManifest.xml`).

```xml
<!-- Tambahkan di android/app/src/main/AndroidManifest.xml -->
<uses-permission android:name="android.permission.POST_NOTIFICATIONS"/>
```

---

## 📦 Dependencies

| Package | Versi | Fungsi |
|---|---|---|
| `provider` | ^6.1.2 | State management |
| `flutter_local_notifications` | ^17.2.2 | Local notification |

---

*Tugas Praktik Modul 12 & 13 — Pemrograman Mobile Flutter*

