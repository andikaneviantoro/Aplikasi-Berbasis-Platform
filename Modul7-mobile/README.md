<div align="center">
  <br />

  <h1>LAPORAN PRAKTIKUM <br>
  APLIKASI BERBASIS PLATFORM
  </h1>

  <br />

  <h3>MODUL - 7 Mobile<br>
  NAVIGASI & NOTIFIKASI
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

## 📚 Dasar Teori

Tugas Praktik Modul 7 – Flutter
Buat aplikasi sederhana bertema “Data Mahasiswa” dengan ketentuan:

* Memiliki 3 halaman:
   1. Home
   2. Form Mahasiswa
   3. Profil Developer
* Form berisi:
   * Nama
   * NIM
   * Kelas
* Tambahkan tombol Simpan untuk menampilkan data yang diinput.
* Saat tombol ditekan, tampilkan SnackBar sebagai notifikasi berhasil.
* Gunakan:
   * StatefulWidget
   * StatelessWidget
   * Navigator.push & Navigator.pop
   * Google Fonts package
* Tambahkan minimal:
   * AppBar
   * Container
   * Column
   * ElevatedButton
Bonus

* Icon
* Tema warna menarik
Output
Aplikasi dapat berpindah halaman, menampilkan data mahasiswa, dan menampilkan notifikasi SnackBar.

### 1. Flutter

Flutter adalah framework open-source buatan Google untuk membangun aplikasi mobile, web, dan desktop dari satu basis kode (*codebase*) menggunakan bahasa pemrograman **Dart**. Flutter menggunakan konsep *widget* sebagai unit terkecil pembangun antarmuka (UI), di mana setiap elemen tampilan — mulai dari teks, tombol, hingga layout — adalah sebuah widget.

**Keunggulan Flutter:**
- Hot Reload: perubahan kode langsung terlihat tanpa restart aplikasi
- Widget yang kaya dan dapat dikustomisasi
- Performa tinggi karena dirender langsung ke canvas (tidak bergantung pada komponen native)
- Satu kode untuk Android, iOS, Web, dan Desktop

---

### 2. Widget di Flutter

Widget di Flutter dibagi menjadi dua jenis utama:

#### a. StatelessWidget

`StatelessWidget` adalah widget yang **tidak memiliki state** (keadaan) yang berubah selama waktu hidupnya. Widget ini cocok untuk tampilan yang sifatnya statis — data yang ditampilkan tidak berubah akibat interaksi pengguna.

```dart
class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text('Home')),
      body: const Text('Ini adalah halaman statis'),
    );
  }
}
```

**Kapan digunakan:**
- Halaman yang hanya menampilkan informasi tetap
- Widget tampilan yang tidak berinteraksi dengan data dinamis
- Contoh dalam proyek ini: `HomeScreen`, `ProfilDeveloperScreen`

#### b. StatefulWidget

`StatefulWidget` adalah widget yang **memiliki state** yang dapat berubah. Widget ini terdiri dari dua class: class widget itu sendiri dan class `State`-nya. Ketika state berubah (melalui `setState()`), Flutter akan me-*rebuild* tampilan secara otomatis.

```dart
class FormMahasiswaScreen extends StatefulWidget {
  const FormMahasiswaScreen({super.key});

  @override
  State<FormMahasiswaScreen> createState() => _FormMahasiswaScreenState();
}

class _FormMahasiswaScreenState extends State<FormMahasiswaScreen> {
  String _nama = '';

  void _updateNama(String value) {
    setState(() {
      _nama = value; // UI otomatis diperbarui
    });
  }

  @override
  Widget build(BuildContext context) {
    return Text(_nama);
  }
}
```

**Kapan digunakan:**
- Form input yang data-nya bisa berubah
- Halaman yang menampilkan hasil interaksi pengguna
- Contoh dalam proyek ini: `FormMahasiswaScreen`

---

### 3. Navigator (Navigasi Antar Halaman)

Flutter menggunakan konsep **stack** untuk manajemen navigasi. Halaman-halaman disusun seperti tumpukan — halaman baru ditaruh di atas (*push*), dan untuk kembali halaman tersebut diambil dari tumpukan (*pop*).

#### Navigator.push
Digunakan untuk **berpindah ke halaman baru** (menambahkan halaman ke stack).

```dart
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (context) => const FormMahasiswaScreen(),
  ),
);
```

#### Navigator.pop
Digunakan untuk **kembali ke halaman sebelumnya** (menghapus halaman teratas dari stack).

```dart
Navigator.pop(context);
```

**Ilustrasi Stack Navigasi:**
```
[HomeScreen]  →push→  [HomeScreen | FormMahasiswaScreen]
                                         ↓ pop
              ←pop←   [HomeScreen]
```

---

### 4. Google Fonts Package

`google_fonts` adalah package Flutter yang memungkinkan penggunaan font dari Google Fonts secara langsung tanpa perlu mengunduh dan mendaftarkan file font secara manual.

**Cara menggunakan:**

1. Tambahkan dependency di `pubspec.yaml`:
```yaml
dependencies:
  google_fonts: ^6.1.0
```

2. Import di file Dart:
```dart
import 'package:google_fonts/google_fonts.dart';
```

3. Gunakan dalam widget:
```dart
Text(
  'Judul',
  style: GoogleFonts.poppins(
    fontSize: 20,
    fontWeight: FontWeight.w700,
  ),
)
```

Dalam proyek ini digunakan font **Poppins** yang diaplikasikan secara global melalui `ThemeData` di `main.dart`.

---

### 5. Widget-Widget Utama

#### AppBar
Komponen header standar di bagian atas halaman yang biasanya berisi judul, ikon navigasi, dan aksi.

```dart
AppBar(
  title: const Text('Data Mahasiswa'),
  leading: IconButton(
    icon: const Icon(Icons.arrow_back),
    onPressed: () => Navigator.pop(context),
  ),
)
```

#### Container
Widget serbaguna untuk menambahkan *padding*, *margin*, warna latar, dekorasi (*border*, *shadow*, *gradient*), dan mengatur ukuran widget di dalamnya.

```dart
Container(
  width: double.infinity,
  padding: const EdgeInsets.all(16),
  decoration: BoxDecoration(
    color: Colors.blue,
    borderRadius: BorderRadius.circular(12),
  ),
  child: const Text('Isi konten'),
)
```

#### Column
Widget layout yang menyusun children secara **vertikal** (dari atas ke bawah).

```dart
Column(
  crossAxisAlignment: CrossAxisAlignment.start,
  children: [
    const Text('Baris 1'),
    const Text('Baris 2'),
    const Text('Baris 3'),
  ],
)
```

#### ElevatedButton
Tombol dengan tampilan *raised* (terangkat) yang digunakan untuk aksi utama.

```dart
ElevatedButton(
  onPressed: () {
    // aksi saat ditekan
  },
  child: const Text('Simpan'),
)
```

---

### 6. Form dan Validasi

Flutter menyediakan widget `Form` bersama `GlobalKey<FormState>` untuk mengelola validasi input secara terpusat.

```dart
final _formKey = GlobalKey<FormState>();

Form(
  key: _formKey,
  child: TextFormField(
    validator: (value) {
      if (value == null || value.isEmpty) {
        return 'Field tidak boleh kosong';
      }
      return null; // null berarti valid
    },
  ),
)

// Validasi semua field sekaligus
if (_formKey.currentState!.validate()) {
  // semua field valid, lanjutkan proses
}
```

---

### 7. SnackBar

`SnackBar` adalah notifikasi singkat yang muncul di bagian bawah layar untuk memberikan umpan balik kepada pengguna.

```dart
ScaffoldMessenger.of(context).showSnackBar(
  SnackBar(
    content: const Text('Data berhasil disimpan!'),
    backgroundColor: Colors.green,
    duration: const Duration(seconds: 3),
    behavior: SnackBarBehavior.floating,
  ),
);
```

## 💻 Penjelasan Kode

### `main.dart` – Entry Point & Tema Global

File utama yang menjadi titik masuk aplikasi Flutter.

```dart
void main() {
  runApp(const DataMahasiswaApp());
}
```

`runApp()` menerima sebuah widget sebagai root dari seluruh aplikasi. Di sini dimasukkan `DataMahasiswaApp` yang merupakan `StatelessWidget` berisi `MaterialApp`.

**Konfigurasi Tema:**
```dart
theme: ThemeData(
  colorScheme: ColorScheme.fromSeed(
    seedColor: const Color(0xFF1565C0), // Warna utama biru
  ),
  textTheme: GoogleFonts.poppinsTextTheme(), // Font global Poppins
),
```

`ThemeData` mendefinisikan tampilan global aplikasi — warna, font, bentuk tombol, dan lainnya — sehingga tidak perlu mendefinisikannya berulang di setiap widget.

---

### `home_screen.dart` – Halaman Home (StatelessWidget)

Halaman pertama yang tampil saat aplikasi dibuka. Menggunakan `StatelessWidget` karena tidak ada data yang berubah di halaman ini.

**Hero Banner dengan Gradient:**
```dart
Container(
  decoration: const BoxDecoration(
    gradient: LinearGradient(
      colors: [Color(0xFF1565C0), Color(0xFF0288D1)],
      begin: Alignment.topLeft,
      end: Alignment.bottomRight,
    ),
    borderRadius: BorderRadius.only(
      bottomLeft: Radius.circular(32),
      bottomRight: Radius.circular(32),
    ),
  ),
  child: Column(/* isi konten banner */),
)
```
`LinearGradient` digunakan untuk membuat efek warna gradasi dari biru tua ke biru muda. `BorderRadius.only` membuat sudut membulat hanya di bagian bawah container.

**Navigasi ke Form Mahasiswa:**
```dart
ElevatedButton.icon(
  icon: const Icon(Icons.arrow_forward_rounded),
  label: const Text('Mulai Input Data'),
  onPressed: () {
    Navigator.push(
      context,
      MaterialPageRoute(
        builder: (context) => const FormMahasiswaScreen(),
      ),
    );
  },
),
```
`Navigator.push` dengan `MaterialPageRoute` digunakan untuk berpindah ke halaman `FormMahasiswaScreen` dengan animasi slide dari kanan (default Android).

---

### `form_mahasiswa_screen.dart` – Form Input (StatefulWidget)

Halaman inti aplikasi tempat pengguna mengisi data mahasiswa. Menggunakan `StatefulWidget` karena ada data yang berubah (isi form dan hasil simpan).

**Deklarasi State:**
```dart
class _FormMahasiswaScreenState extends State<FormMahasiswaScreen> {
  final _formKey = GlobalKey<FormState>();
  final TextEditingController _namaController = TextEditingController();
  final TextEditingController _nimController = TextEditingController();
  final TextEditingController _kelasController = TextEditingController();

  Map<String, String>? _savedData; // Menyimpan data hasil input
  bool _isSaved = false;           // Mengontrol tampilan kartu hasil
```

- `GlobalKey<FormState>` digunakan untuk mengakses dan memvalidasi seluruh form
- `TextEditingController` digunakan untuk membaca dan mengontrol nilai dari `TextFormField`
- `_savedData` dan `_isSaved` adalah state yang mengontrol tampilan kartu hasil setelah simpan

**Validasi dan Penyimpanan Data:**
```dart
void _simpanData() {
  if (_formKey.currentState!.validate()) { // Cek semua field valid
    setState(() {
      _savedData = {
        'nama': _namaController.text.trim(),
        'nim': _nimController.text.trim(),
        'kelas': _kelasController.text.trim(),
      };
      _isSaved = true; // Tampilkan kartu hasil
    });

    ScaffoldMessenger.of(context).showSnackBar(/* ... */);
  }
}
```

`setState()` memberitahu Flutter bahwa ada perubahan state, sehingga Flutter akan memanggil ulang `build()` dan memperbarui UI secara otomatis.

**TextFormField dengan Validasi:**
```dart
TextFormField(
  controller: _namaController,
  decoration: const InputDecoration(
    hintText: 'Masukkan nama lengkap',
    prefixIcon: Icon(Icons.person_outline_rounded),
  ),
  validator: (value) {
    if (value == null || value.trim().isEmpty) {
      return 'Nama tidak boleh kosong'; // Pesan error
    }
    if (value.trim().length < 3) {
      return 'Nama minimal 3 karakter';
    }
    return null; // null = valid
  },
),
```

**SnackBar Notifikasi:**
```dart
ScaffoldMessenger.of(context).showSnackBar(
  SnackBar(
    content: Row(
      children: [
        const Icon(Icons.check_circle_rounded, color: Colors.white),
        const SizedBox(width: 10),
        const Text('Data mahasiswa berhasil disimpan!'),
      ],
    ),
    backgroundColor: const Color(0xFF1B5E20), // Hijau tua
    duration: const Duration(seconds: 3),
    behavior: SnackBarBehavior.floating,      // Melayang di atas konten
  ),
);
```

**Dispose Controller:**
```dart
@override
void dispose() {
  _namaController.dispose();
  _nimController.dispose();
  _kelasController.dispose();
  super.dispose();
}
```

`dispose()` wajib dipanggil untuk membersihkan `TextEditingController` dari memori saat widget dihancurkan, mencegah *memory leak*.

---

### `profil_developer_screen.dart` – Profil Developer (StatelessWidget)

Halaman yang menampilkan informasi pembuat aplikasi. Menggunakan `StatelessWidget` karena semua data bersifat statis.

**Tombol Kembali dengan Navigator.pop:**
```dart
ElevatedButton.icon(
  icon: const Icon(Icons.arrow_back_rounded),
  label: const Text('Kembali ke Beranda'),
  onPressed: () => Navigator.pop(context), // Kembali ke halaman sebelumnya
),
```

`Navigator.pop(context)` menghapus halaman saat ini dari stack navigasi dan kembali ke halaman sebelumnya (HomeScreen).

---

## 📸 Tampilan Aplikasi

| Halaman | Deskripsi |
|---------|-----------|
| **Home** | Hero banner gradient, info cards, menu navigasi |
| **Form Mahasiswa** | Input Nama/NIM/Kelas, validasi, kartu hasil, SnackBar |
| **Profil Developer** | Info akademik, fitur aplikasi, tombol kembali |

## Output:

### Home
<p align="center"><img width="308" height="548" alt="image" src="https://github.com/user-attachments/assets/3baf5a0f-36e8-4ec6-bc02-e5e1b76e0a2f" /></p>

### From Mahasiswa
<p align="center"><img width="306" height="544" alt="image" src="https://github.com/user-attachments/assets/706b7ed2-7057-45da-af57-3dafb3b785b8" /></p>

### Snackbar
<p align="center"><img width="306" height="545" alt="image" src="https://github.com/user-attachments/assets/2ee9cff6-d158-4b8a-892e-7e0aa66adec0" /></p>

### Profil Developer
<p align="center"><img width="306" height="543" alt="image" src="https://github.com/user-attachments/assets/d15b8961-e92b-48b4-9a4f-10b39a429c69" /></p>

