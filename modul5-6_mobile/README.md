<div align="center">
  <br />

  <h1>LAPORAN PRAKTIKUM <br>
  APLIKASI BERBASIS PLATFORM
  </h1>

  <br />

  <h3>MODUL - 5&6 Mobile<br>
  Antar Muka Pengguna Lanjutan & Interaksi Pengguna
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

# Dasar Teori
# Antar Muka Pengguna Lanjutan
## 1.1 Row
Row merupakan suatu widget yang digunakan untuk membuat widget-widget tersusun berjajar 
secara horizontal. Parameter children berisi kumpulan atau list dari widget karena kita dapat menyusun beberapa widget sekaligus di dalamnya. Jika mengacu pada contoh tombol-tombol di atas kodenya seperti berikut:

```
ow(
 children: <Widget>[
 const FlutterLogo(),
 const Expanded(
 child: Text("Flutter's hot reload helps you quickly and easily experiment, build UIs, add 
features, and fix bug faster. Experience sub-second reload times, without losing state, on 
emulators, simulators, and hardware for iOS and Android."),
 ),
 const Icon(Icons.sentiment_very_satisfied),
 ],
)
```

## 1.2 Column
Column merupakan suatu widget yang digunakan untuk membuat widget-widget tersusun berjajar 
secara vertikal. berikut adalah contoh penerapan Column:

```
Column(
 children: const <Widget>[
 Text('Deliver features faster'),
 Text('Craft beautiful UIs'),
 Expanded(
 child: FittedBox(
 fit: BoxFit.contain, // otherwise the logo will be tiny
 child: FlutterLogo(),
 ),
 ),
 ],
)
```

## 1.3 Nested Rows & Columns
Salah satu hal yang paling mendasar ketika membuat layout adalah mengaturnya secara horizontal 
dan vertikal. Untuk mengatasi hal tersebut bisa menggunakan widget Row dan Column secara 
bersamaan.
Untuk membuat Row atau Column, bisa ditambahkan pada children di setiap widget Row ataupun 
Column. Contoh berikut ini akan menunjukkan bahwa memungkinkan untuk membuat Row atau 
Column di dalam widget Row atau Column

## 1.4 CustomScrollView
Widget ini memungkinkan membuat efek pada list, grid, maupun header yang lebar. Misalnya, ketika 
ingin membuat scroll view yang berisi app bar yang lebar yang meliputi list dan grid secara bersamaan, maka bisa menggunakan 3 widget sliver, yaitu SliverAppBar, SliverList, dan SliverGrid.

# Interaksi Pengguna
## 2.1 Packages
Secara singkat, dart package terdapat pada direktori yang didalamnya terdapat file pubspec. Contoh 
penggunaan packages adalah membuat request ke server menggunakan protokol http, custom 
navigation/route handling menggunakan fluro, dsb.

## 2.2 Stateful & Stateless
Widget stateless tidak pernah berubah. Ikon, IconButton, dan Teks adalah contoh widget stateless. 
Sub kelas widget stateless StatelessWidget.Widget stateful bersifat dinamis misalnya, ia dapat 
mengubah tampilannya sebagai respons terhadap peristiwa yang dipicu oleh interaksi pengguna atau 
saat menerima data. Kotak centang, Radio, Slider, InkWell, Form, dan TextField adalah contoh widget 
stateful. Subkelas widget stateful StatefulWidget

## 2.3 Form
```
import 'package:flutter/material.dart';
void main() => runApp(const MyApp());
class MyApp extends StatelessWidget {
 const MyApp({Key? key}) : super(key: key);
 @override
 Widget build(BuildContext context) {
 const appTitle = 'Form Styling Demo';
 return MaterialApp(
 title: appTitle,
 home: Scaffold(
 appBar: AppBar(
 title: const Text(appTitle),
 ),
 body: const MyCustomForm(),
 ),
 );
 }
}
class MyCustomForm extends StatelessWidget {
 const MyCustomForm({Key? key}) : super(key: key);
 @override
 Widget build(BuildContext context) {
 return Column(
 crossAxisAlignment: CrossAxisAlignment.start,
 children: <Widget>[
 const Padding(
 padding: EdgeInsets.symmetric(horizontal: 8, vertical: 16),
 child: TextField(
 decoration: InputDecoration(
 border: OutlineInputBorder(),
 hintText: 'Enter a search term',
 ),
 ),
 ),
 Padding(
 padding: const EdgeInsets.symmetric(horizontal: 8, 
vertical: 16),
 child: TextFormField(
 decoration: const InputDecoration(
 border: UnderlineInputBorder(),
 labelText: 'Enter your username',
 ),
 ),
 ),
 ],
 );
 }
}
```

## 2.4 Menu
Salah satu hal penting dari pembuatan aplikasi adalah menu. Menu ini berfungsi untuk separasi antar 
fitur atau page. Sulit rasanya apabila semua fitur ditampilkan dalam satu halaman, selain sulit 
pengguna akan kesulitan dalam mengoperasikannya. Maka disini menu page sangat bermanfaat.
Secara umum terdapat 2 jenis widget menu yang sering digunakan, yaitu `bottom navigation bar` dan 
`tab bar`. Karena Flutter mendukung penuh guideline yang dibuat oleh Google, yaitu Material Design

## Buttons
ElevatedButton adalah tombol yang biasa kita gunakan saat kita mendaftar,submit,login dst. berikut 
merupakan sourcecode dari ElevatedButton : 
```
ElevatedButton(
 onPressed: () {
 print('ini done');
 },
 child: new Text('submit'),
)
```
TextButton
```
TextButton ( 
child : text(‘menu’),
onprossed : () {
print (‘sukses’);
}
)
```
DropdownButton
untuk membuat DropdownButton kita harus memiliki value di dalamnya agar dapat bekerja contoh 
sourcecode sebagai berikut :
```
DropdownButton(
 value: selectedValue,
 onChanged: (String? newValue){
 setState(() {
 selectedValue = newValue!;
 });
 },
 items: dropdownItems
 )
```

# Pengerjaan
## Source Code Lengkap

```
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Talkyu',
      theme: ThemeData(
        colorScheme: .fromSeed(seedColor: Colors.deepPurple),
      ),
      home: const MyHomePage(title: 'Talkyu'),
      debugShowCheckedModeBanner: false,
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key, required this.title});

  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Column(
        crossAxisAlignment: CrossAxisAlignment.end,
        children: <Widget> [
          const Padding(
            padding: EdgeInsetsGeometry.symmetric(horizontal: 4, vertical: 4),
            child: TextField(
              decoration: InputDecoration(
                  hintText: "Masukin aku plis",
                  border: OutlineInputBorder()
              ),
            ),
          ),
          Padding(
            padding: EdgeInsetsGeometry.symmetric(horizontal: 6, vertical: 6),
            child: TextField(
              decoration: InputDecoration(
                  labelText: "Apa Jenis Nyawitmu",
                  border: OutlineInputBorder()
              ),
            ),
          )
        ],
      ),
    );
  }
}
```

## Penjelasan Source Code
### main()
```
void main() {
  runApp(const MyApp());
}
```
Fungsi main() adalah titik masuk dari setiap aplikasi Dart/Flutter. runApp() dipanggil untuk menjalankan widget root bernama MyApp.

### MyApp
```
class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Talkyu',
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
      ),
      home: const MyHomePage(title: 'Talkyu'),
      debugShowCheckedModeBanner: false,
    );
  }
}
```
MyApp adalah widget StatelessWidget yang berfungsi sebagai konfigurasi utama aplikasi. Di sini didefinisikan nama aplikasi, tema warna menggunakan ColorScheme.fromSeed dengan warna dasar deepPurple, serta halaman pertama yang ditampilkan yaitu MyHomePage. debugShowCheckedModeBanner: false digunakan untuk menyembunyikan banner "DEBUG" di pojok layar.

### MyHomePage
```
class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key, required this.title});

  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}
```
MyHomePage adalah widget StatefulWidget, artinya widget ini dapat menyimpan dan mengubah state selama aplikasi berjalan. Widget ini menerima parameter title yang wajib diisi. Method createState() menghubungkan widget ini dengan class state-nya yaitu _MyHomePageState.

### _MyHomePageState
```
class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) { ... }
}
```
Class ini menyimpan state dari MyHomePage. Terdapat variabel _counter dan method _incrementCounter() yang merupakan sisa kode template bawaan Flutter dan belum digunakan pada UI saat ini.

### Struktur UI
```
Scaffold(
  body: Column(
    crossAxisAlignment: CrossAxisAlignment.end,
    children: [
      Padding(..., child: TextField(...)),
      Padding(..., child: TextField(...)),
    ],
  ),
)
```
UI dibangun dengan Scaffold sebagai kerangka halaman, lalu Column untuk menyusun widget secara vertikal. crossAxisAlignment: CrossAxisAlignment.end membuat setiap child disejajarkan ke sisi kanan. Masing-masing TextField dibungkus Padding untuk memberi jarak di sekitarnya.

### TextField Pertama
```
Padding(
  padding: EdgeInsets.symmetric(horizontal: 4, vertical: 4),
  child: TextField(
    decoration: InputDecoration(
      hintText: "Masukin aku plis",
      border: OutlineInputBorder(),
    ),
  ),
)
```
TextField pertama menggunakan hintText yaitu teks placeholder yang tampil saat kolom masih kosong dan akan hilang begitu pengguna mulai mengetik. OutlineInputBorder memberi tampilan border kotak di sekeliling field.

### TextField Kedua
```
Padding(
  padding: EdgeInsets.symmetric(horizontal: 6, vertical: 6),
  child: TextField(
    decoration: InputDecoration(
      labelText: "Apa Jenis Nyawitmu",
      border: OutlineInputBorder(),
    ),
  ),
)
```
TextField kedua menggunakan labelText yang berbeda dengan hintText. Label ini tetap terlihat meski pengguna sudah mengetik — saat field aktif, label akan berpindah (float) ke atas border secara otomatis.

## Output Program
<p align="center"><img width="502" height="773" alt="image" src="https://github.com/user-attachments/assets/d1259499-b053-45af-9773-54320e353e4e" /></p>
Aplikasi menampilkan dua buah TextField yang tersusun vertikal. TextField pertama berisi teks jokowow tanpa label, hanya menggunakan border kotak biasa. TextField kedua menampilkan label Apa Jenis Nyawitmu yang mengambang di atas border karena field sedang terisi teks prawowo. Latar belakang layar berwarna ungu muda, mengikuti tema deepPurple yang sudah dikonfigurasi di ThemeData.
