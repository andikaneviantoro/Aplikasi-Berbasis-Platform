# <h1 align="center">LAPORAN PRAKTIKUM</h1>
### <p align="center">Aplikasi Berbasis Platform</p>

### <p align="center">Modul 6</p>
### <p align="center">JAVASCRIPT & JQUERY</p>

<p align="center"> <img width="367" height="369" alt="image" src="https://github.com/user-attachments/assets/80ef8bff-aca4-4e1a-b7eb-6d894fdb53ad" /> </p> 

### <p align="center">Disusun Oleh:</p>
### <p align="center">ANDIKA NEVIANTORO</p>
### <p align="center">2311102167</p>
### <p align="center">S1 IF-11-01</p>

### <p align="center">Dosen Pengampu:</p>
### <p align="center">Dimas Fanny Hebrasianto Permadi, S.ST., M.Kom</p>


### <p align="center">PROGRAM STUDI S1 INOFRMATIKA</p>
### <p align="center">FAKULTAS INFORMATIKA</p>
### <p align="center">TELKOM UNIVERSITY PURWOKERTO</p>
### <p align="center">2025/2026</p>


# Dasar Teori

## 6.1. Pengenalan Bootstrap
### 6.1.1. Sejarah Singkat Javascript
Javascript, seperti namanya, merupakan bahasa pemrograman scripting. Dan seperti bahasa scripting lainnya, Javascript umumnya digunakan hanya untuk program yang tidak terlalu besar, biasanya hanya beberapa ratus baris. Javascript pada umumnya mengontrol program yang berbasis Java. Jadi memang pada dasarnya Javascript tidak dirancang untuk digunakan dalam aplikasi skala besar. Meskipun dibuat dengan tujuan awal untuk mengendalikan program Java, komunitas Javascript
menggunakan bahasa ini untuk tujuan lain, memanipulasi gambar dan isi dari dokumen HTML. Singkatnya, pada akhirnya Javascript digunakan untuk satu tujuan utama, “menghidupkan” dokumen HTML dengan mengubah konten statis menjadi dinamis dan interaktif. Bersamaan dengan perkembangan Internet dan dunia web yang pesat, Javascript akhirnya menjadi bahasa utama dan satu-satunya untuk membuat HTML menjadi interaktif di dalam browser.

### 6.1.2. Prinsip Dasar Javascript
Prinsip dasar yang terdapat pada bahasa pemrograman javascript adalah sebagai berikut.
1. Javascript mendukung paradigma pemrograman imparatif (Javascript dapat menjalankan perintah
program baris demi baris, dengan masing-masing baris berisi satu atau lebih perintah), fungsional (struktur dan elemen-elemen dalam program sebagai fungsi matematis yang tidak memiliki keadaan (state) dan data yang dapat berubah (mutable data)), dan orientasi objek (segala sesuatu yang terlibat dalam program dapat disebut sebagai “objek”).
2. Javascript memiliki model pemrograman fungsional yang sangat ekspresif.
3. Pemrograman berorientasi objek (PBO) pada Javascript memiliki perbedaan dari PBO pada umumnya.
4. Program kompleks pada Javascript umumnya dipandang sebagai program-program kecil yang saling
berinteraksi.

## 6.2. Sintaks Umum pada Javascript
### 6.2.1. Tipe data dasar
Seperti kebanyakan bahasa pemrograman lainnya, Javascript memiliki beberapa tipe data untuk
dimanipulasi. Seluruh nilai yang ada dalam Javascript selalu memiliki tipe data. Tipe data yang dimiliki oleh Javascript adalah sebagai berikut:
• Number (bilangan)
• String (serangkaian karakter)
• Boolean (benar / salah)
• Object
• Function (fungsi)
• Array
• Date
• RegExp (regular expression)
• Null (tidak berlaku / kosong)
• Undefined (tidak didefinisikan)
Kebanyakan dari tipe data yang disebutkan di atas sama seperti tipe data sejenis pada bahasa
pemrograman lainnya. Misalnya, sebuah boolean terdiri dari dua nilai saja, yaitu true dan false.

### 6.2.2. Variabel
Seperti pada bahasa pemrograman lainnya, variabel dalam Javascript merupakan sebuah tempat untuk
menyimpan data sementara. Variabel dibuat dengan kata kunci var pada Javascript.
```
var a; // a berisi undefined
var nama = "Budi"; // nama berisi "Budi"
```
Nilai yang ada di dalam variabel dapat diganti dengan mengisikan nilai baru, dan bahkan dapat diganti tipe datanya juga.
```
nama = "Anton"; // nama sekarang berisi string "Anton"
nama = 1; // nama sekarang berisi integer 1
```
Walaupun kemampuan untuk menggantikan tipe data ini sangat memudahkan kita dalam mengembangkan
aplikasi, fitur ini harus digunakan dengan sangat hati-hati. Perubahan tipe data yang tidak diperkirkan dengan baik dapat menyebabkan berbagai kesalahan (error) pada program, misalnya jika kita mencoba mengakses method charAt() (fungsi yang mengembalikan nilai char pada indeks sebuah string) setelah mengubah tipe pada contoh di atas.

### 6.2.3. Array
Array merupakan sebuah tipe data yang digunakan untuk menampung banyak tipe data lainnya. Berbeda dengan tipe data object, array pada Javascript merupakan sebuah tipe khusus. Walaupun memiliki method dan properti, array bukanlah objek, melainkan sebuah tipe yang “mirip objek”. Pembuatan array dalam Javascript dilakukan dengan menggunakan kurung siku ([]):
```
var data = ["satu", 2, true];
```
Elemen array pada Javascript tidak harus memiliki tipe data yang sama seperti contoh diatas. Selain itu Javascript juga mendukung untuk membuat array di dalam array yang biasa dikenal dengan array dua dimensi seperti contoh dibawah ini.
```
var arr2 = [["satu", "dua"], ["tiga", "empat"]];
```
Pengaksesan elemen dalam array dilakukan dengan menggunakan kurung siku. Nilai yang kita berikan
dalam kurung siku adalah urutan elemen penulisan array (indeks), yang dimulai dari nilai 0. Jika indeks yang diakses tidak ada, maka kita akan mendapatkan nilai undefined.
```
data[2]; // mengembalikan true
arr2[0][1]; // mengembalikan "dua"
data[10]; // mengembalikan undefined
```
Sebagai sebuah objek khusus, array juga memiliki method dan properti. Beberapa method dan properti yang populer misalnya length, pop(), dan push().
```
var data = ["a", "b", "c"];
// data.length mengembalikan 3
data.push("d"); // mengembalikan 4 data menjadi ["a", "b", "c", "d"]
data.pop(); // mengembalikan "d", data menjadi ["a", "b", "c"]
```

### 6.2.4. Pengendalian Struktur
Javascript memiliki perintah-perintah pengendalian struktur (control stucture) yang sama dengan bahasa dalam keluarga C. Perintah if dan else digunakan untuk percabangan, sementara perintah for, for-in, while, dan do-while digunakan untuk perulangan. Percabangan pada Javascript bisa dikatakan sama persis dengan C atau Java:
```
var gelar;
var pendidikan = "S2";
if (pendidikan === "S1") {
gelar = "Sarjana";
} else if (pendidikan === "S2") {
gelar = "Master";
} else if (pendidikan === "S3") {
gelar = "Doktor";
} else {
gelar = "Tidak Diketahui";
}
gelar; // gelar berisi "Master"
```
Satu hal yang perlu diperhatikan, tiga buah sama dengan (===) digunakan pada operasi perbandingan di Javascript. Javascript mendukung dua operator perbandingan sama dengan, yaitu == dan ===. Perbedaan utamanya adalah == mengubah tipe data yang dicek menjadi nilai terdekat, sementara === memastikan tipe data dari dua nilai yang dibandingkan sama. Untuk mendapatkan nilai perbandingan paling akurat, selalu gunakan === ketika mengecek nilai. Sama seperti if, perulangan do, do-while, dan for memiliki cara pemakaian yang dapat dikatakan sama persis dengan C atau Java:
```
while (true) {
    // tak pernah berhenti
} var input; do {
input = get_input();
} while (inputIsNotValid(input)) for
(var i = 0; i < 5; i++) {
    // berulang sebanyak 5 kali }
```

## 6.3. Object orientation pada Javascript
Javascript memiliki dua jenis tipe data utama, yaitu tipe data dasar dan objek. Tipe data dasar pada Javascript adalah angka (numbers), rentetan karakter (strings), boolean (true dan false), null, dan undefined. Nilai-nilai selain tipe data dasar secara otomatis dianggap sebagai objek. Objek dalam Javascript didefinisikan sebagai mutable properties collection, yang artinya adalah sekumpulan properti (ciri khas) yang dapat berubah nilainya. Karena nilai-nilai selain tipe data dasar merupakan objek, maka pada Javascript sebuah Array adalah objek. Fungsi adalah objek dan Regular expression juga merupakan objek.

### 6.3.1. Pembuatan Object pada Javascript
Notasi pembuatan objek pada Javascript sangat sederhana, yaitu sepasang kurung kurawal yang
membungkus properti. Notasi pembuatan objek ini dikenal dengan nama object literal. Object literal dapat digunakan kapanpun pada ekspresi Javascript yang valid:
```
var objek_kosong = {};
var mobil = {
    "warna-badan": "merah",
    "nomor-polisi": "BK1234AB"
};
```
Nama properti dari sebuah objek harus berupa string, dan boleh berisi string kosong (""). Jika merupakan nama Javascript yang legal, kita tidak memerlukan petik ganda pada nama properti. Petik ganda seperti pada contoh ("warna-badan") hanya diperlukan untuk nama Javascript ilegal atau kata kunci seperti “if” atau “var”. Misalnya, "nomor-polisi" memerlukan tanda petik, sementara nomor_polisi tidak. Contoh lain, variasi tidak memerlukan tanda petik, sementara "var" perlu.

Sebuah objek dapat menyimpan banyak properti, dan setiap properti dipisahkan dengan tanda koma (,). Jika ada banyak properti, nilai dari properti pada setiap objek boleh berbeda-beda:
```
var jadwal = {
  platform: 34,
  telah_berangkat: false,
  tujuan: "Medan",
  asal: "Jakarta"
};
```
Karena dapat diisikan dengan nilai apapun (termasuk objek), maka kita dapat membuat objek yang
mengandung objek lain (nested object; objek bersarang) seperti berikut:
```
var jadwal = { platform: 34,
telah_berangkat: false, asal:
{       kode_kota: "MDN",
nama_kota: "Medan",
waktu: "2013-12-29 14:00"
    }, tujuan: {
kode_kota: "JKT",
nama_kota: "Jakarta",
waktu: "2013-12-29 17.30"
    }
};
```

### 6.3.2. Akses Nilai Property
Akses nilai properti dapat dilakukan dengan dua cara, yaitu.
1. Penggunaan kurung siku ([]) setelah nama objek. Kurung siku kemudian diisikan dengan nama
properti, yang harus berupa string. Cara ini biasanya digunakan untuk nama properti yang adalah
nama ilegal atau kata kunci Javascript.
2. Penggunaan tanda titik (.) setelah nama objek diikuti dengan nama properti. Notasi ini merupakan
notasi yang umum digunakan pada bahasa pemrograman lainnya. Notasi ini tidak dapat digunakan
untuk nama ilegal atau kata kunci Javascript.

Contoh penggunaan kedua cara pemanggilan di atas adalah sebagai berikut:
```
mobil["warna-badan"] // Hasil: "merah"
jadwal.platform // Hasil: 34
```
Sebagai bahasa dinamis, Javascript tidak akan melemparkan pesan kesalahan jika kita mengakses properti yang tidak ada dalam objek. Kita akan menerima nilai undefined jika mengakses properti yang tidak ada:
```
jadwal.nomor_kursi // Hasil: undefined mobil
["jumlah-roda"] // Hasil: undefined
```
Pengaksesan properti pada Javascript juga dapat digunakan secara dinamis untuk mengubah nilai dari properti tersebut. Perubahan nilai properti juga dapat dilakukan untuk properti yang bahkan tidak ada pada objek tersebut:
```
mobil["jumlah-roda"] = 4;
mobil.bahan_bakar = "Bensin";
```

### 6.3.3. Prototype pada Javascript
Pada Javascript yang mengimplementasikan PBO kita tidak lagi perlu menuliskan kelas, dan langsung melakukan penurunan terhadap objek. Misalkan kita memiliki objek mobil yang sederhana seperti berikut:
```
var mobil = { nama: "Mobil",
jumlahBan: 4 };
```
Kita dapat langsung menurunkan objek tersebut dengan menggunakan fungsi Object.create seperti
berikut:
```
var truk = Object.create(mobil);
// truk.nama === "Mobil"
// truk.jumlahBan === 4
```

## 6.4. Function pada Javascript
Sebuah fungsi membungkus satu atau banyak perintah. Setiap kali fungsi dipanggil, maka perintahperintah yang ada di dalam fungsi tersebut dijalankan. Secara umum fungsi digunakan untuk penggunaan kembali kode (code reuse) dan penyimpanan informasi (information hiding). Implementasi fungsi kelas pertama juga memungkinkan penggunaan fungsi sebagai unit-unit yang dapat dikombinasikan, seperti layaknya sebuah lego. Dukungan terhadap pemrograman berorientasi objek juga berarti fungsi dapat digunakan untuk
memberikan perilaku tertentu dari sebuah objek.

### 6.4.1/ Pembuatan Fungsi pada Javascript
Sebuah fungsi pada Javascript dibuat dengan cara seperti berikut:
```
function tambah(a, b) {
hasil = a + b;
return hasil;
}
```
Cara penulisan fungsi seperti diatas dikenal dengan nama function declaration, atau deklarasi fungsi.
Terdapat empat komponen yang membangun fungsi di atas, yaitu:
1. Kata kunci function, yang memberitahu Javascript bahwa akan dibuat sebuah fungsi.
2. Nama fungsi, dalam contoh di atas adalah tambah. Dengan memberikan sebuah fungsi nama maka
pemanggilan fungsi dapat dirujuk dengan nama tersebut. Harus diingat bawa nama fungsi bersifat
opsional, yang berarti fungsi pada Javascript tidak harus diberi nama.
3. Daftar parameter fungsi, yaitu a, b pada contoh di atas. Daftar parameter ini selalu dikelilingi oleh tanda kurung (()). Parameter boleh kosong, tetapi tanda kurung wajib tetap dituliskan. Parameter fungsi akan secara otomatis didefinisikan menjadi variabel yang hanya bisa dipakai di dalam fungsi. Variabel pada parameter ini diisi dengan nilai yang dikirimkan kepada fungsi secara otomatis.
4. Sekumpulan perintah yang ada di dalam kurung kurawal ({}). Perintah-perintah ini dikenal dengan nama badan fungsi. Badan fungsi dieksekusi secara berurut ketika fungsi dijalankan.
Penulisan deklarasi fungsi (function declaration) seperti di atas merupakan cara penulisan fungsi yang umumnya kita gunakan pada bahasa pemrograman imperatif dan berorientasi objek. Tetapi selain deklarasi fungsi Javascript juga mendukung cara penulisan fungsi lain, yaitu dengan memanfaatkan ekspresi fungsi (function expression). Ekspresi fungsi merupakan cara pembuatan fungsi yang memperbolehkan menuliskan fungsi tanpa nama. Fungsi yang dibuat tanpa nama dikenal dengan sebutan fungsi anonim atau fungsi lambda. Berikut adalah cara membuat fungsi dengan ekspresi fungsi:
```
var tambah = function (a, b) {
hasil = a + b;
return hasil;
};
```

Terdapat hanya sedikit perbedaan antara ekspresi fungsi dan deklarasi fungsi:
1. Penamaan fungsi. Pada deklarasi fungsi, nama fungsi langsung diberikan sesuai dengan sintaks yang disediakan Javascript. Penggunaan ekspresi fungsi pada dasarnya menyimpan sebuah fungsi anonim ke dalam variabel dan nama fungsi adalah nama variabel yang dibuat. Perlu diingat juga bahwa pada dasarnya ekspresi fungsi adalah fungsi anonim. Penyimpanan ke dalam variabel hanya diperlukan karena kita akan memanggil fungsi nantinya.
2. Ekspresi fungsi dapat dipandang sebagai sebuah ekspresi atau perintah standar bagi Javascript, sama seperti penuliskan kode var i = 0. Deklarasi fungsi merupakan konstruksi khusus untuk membuat fungsi. Hal ini berarti pada akhir dari ekspresi fungsi kita harus menambahkan, sementara pada
deklarasi fungsi hal tersebut tidak penting.

### 6.4.2. Pemanggilan Fungsi
Sebuah fungsi dapat dipanggil untuk menjalankan seluruh kode yang ada di dalam fungsi tersebut, sesuai dengan parameter yang kita berikan. Pemanggilan fungsi dilakukan dengan cara menuliskan nama fungsi tersebut, kemudian mengisikan argumen yang ada di dalam tanda kurung.

Misalkan fungsi tambah yang kita buat pada bagian sebelumnya:
```
var tambah = function (a, b) {
hasil = a + b;
return hasil;
};
```
dapat dipanggil seperti berikut:
```
tambah(3, 5);
```
Yang terjadi pada kode di atas adalah nilai a dan b masing-masing digantikan dengan 3 dan 5. Seperti yang dapat dilihat, hal ini berarti pengisian argumen pada saat pemanggilan fungsi harus berurut sesuai dengan deklarasi fungsi.

Sama seperti sebuah variabel, fungsi juga mengembalikan nilai ketika dipanggil. Dalam kasus di atas, tambah(3, 5) akan mengembalikan nilai 8. Nilai ini tentunya dapat disimpan ke dalam variabel baru, atau bahkan dikirimkan sebagai sebuah argumen ke fungsi lain lagi:
```
var simpan = tambah(3, 5); // simpan === 8
tambah(simpan, 2); // mengembalikan 10
tambah(tambah(3, 5), 2) // juga mengembalikan 10
tambah(tambah(2, 3), 4) // mengembalikan 9
```
Fungsi akan mengembalikan nilai ketika kata kunci return ditemukan. Pengembalian nilai fungsi dapat dilakukan kapanpun, dan fungsi akan segera berhenti ketika kata kunci return ditemukan. Berikut adalah contoh kode yang memberikan gambaran tentang pengembalian nilai fungsi:
```
var naikkan = function (n) {
var hasil = n + 10; return
hasil;
// kode di bawah tidak dijalankan lagi hasil
= hasil * 100;
} naikkan(10); // mengembalikan
20 naikkan(25); // mengembalikan
35
```
Sebuah ekspresi dapat juga diberikan langsung kepada keyword return, dan ekspresi tersebut akan
dijalankan sebelum nilai dikembalikan. Hal ini berarti fungsi tambah maupun naikkan yang sebelumnya bisa disederhanakan dengan tidak lagi menyimpan nilai di variabel hasil terlebih dahulu:
```
var naikkan = function (n) {
return n + 10;
} var tambah = function (a,
b) { return a + b;
} tambah(4, 4); // mengembalikan 8
naikkan(10); // mengembalikan 20
tambah(naikkan(5), 7); // mengembalikan 22
```

## 6.5. Pengenalan jQuery
jQuery adalah sebuah library Javascript yang dibuat oleh John Resig pada tahun 2006. jQuery
memungkinkan manipulasi dokumen HTML dilakukan hanya dalam beberapa baris code. Beberapa fitur
utama yang terdapat pada jQuery adalah:

- DOM manipulation – jQuery memungkinkan untuk memodifikasi DOM (Document Object Model)
menggunakan source selector yang disebut dengan Sizzle.
- Event Handling – jQuery dapat menangani sebuah aksi pada dokumen HTML seperti saat pengguna
melakukan click pada sebuah objek.
- Ajax Support – jQuery dapat memfasilitasi pembuatan website menggunakan teknologi AJAX.
- Animations – pada jQuery terdapat build-in animasi yang dapat digunakan pada halaman web.
- Lightweight – ukuran file jQuery sangat ringan yaitu sekitar 19KB.

jQuery dapat dengan mudah digunakan pada sebuah situs web dengan berbagai cara.
1. Instalasi Lokal
- Kunjungi link https://jquery.com/download/ untuk mengunduh library jQuery.
- Letakkan library yang sudah diunduh pada satu folder yang sama dengan file HTML dengan kode berikut.
```
<html>

<head>
  <title>The jQuery Example</title>
  <script type="text/javascript" src="jquery-3.7.0.min.js">
  </script>
  <script type="text/javascript">
    $(document).ready(function() {
    document.write("Hello, World!");
    });
  </script>

</head>

<body>
  <h1>Hello</h1>
</body>

</html>
```
Note: pastikan atribut src memiliki nilai yang sama dengan nama file library jQuery.
- Buka file HTML tersebut menggunakan web browser seperti Mozilla atau Chrome. Dan hasil yang
didapatkan adalah sebuah teks “Hello World” seperti yang ditulis pada bagian document.write().

2. Menggunakan CDN (Content Delivery Network)
- Buka file HTML tersebut menggunakan web browser seperti Mozilla atau Chrome. Dan hasil yang
didapatkan adalah sebuah teks “Hello World” seperti yang ditulis pada bagian document.write().
https://code.jquery.com/jquery-3.7.1.min.js
- Buka file HTML menggunakan web browser dan hasil yang ditampilkan akan sama dengan cara
instalasi lokal.

## 6.6. Kegunaan Lanjutan jQuery
### 6.6.1. Efek hide/show
contoh code:
```
<!DOCTYPE html>
<html>
<head>
  <script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>
  <script>
    $(document).ready(function() {
      $("#hide").click(function() {
        $("p").hide();
      });
      $("#show").click(function() {
        $("p").show();
      });
    });
  </script>
</head>

<body>

  <p>If you click on the "Hide" button, I will disappear.</p>
  <button id="hide">Hide</button>
  <button id="show">Show</button>

</body>

</html>
```
Penjelasan code:
- Pada baris 4-5, dilakukan pemanggilan library jQuery menggunakan CDN.
- Pada baris 6-15, fungsi jQuery hide/show diaplikasikan pada tag html <p>. Apabila button dengan id ‘hide’ diklik, maka semua konten pada tag <p> akan disembunyikan. Selain itu, apabila button dengan id ‘show’ diklik, maka semua konten pada tag <p> akan dimunculkan.

### 6.6.2. Efek animasi
Contoh code:
```
<!DOCTYPE html>
<html>

<head>
    <script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>
    <script>
        $(document).ready(function () {
            $("button").click(function () {
                $("div").animate({
                    height: 'toggle'
                });
            });
        });
    </script>
</head>

<body>
    <p>Click the button multiple times to toggle the animation.</p>
    <button>Start Animation</button>
    <p>By default, all HTML elements have a static position, and cannot be moved.
        To manipulate the position, remember to first set the CSS position property of
        the element to relative, fixed, or absolute!</p>
    <div style="background:#98bf21; height:100px; width:100px; position:absolute;">
    </div>
</body>

</html>
```
Penjelasan code:
- Pada baris 6-15, fungsi jQuery menganimasikan “toggle” pada tag <div> yang terdapat pada body HTML berdasarkan tinggi elemen.

# UNGUIDED (Buka kembali halaman ramadan dan tambahkan button atau semacam nya ketika di klik akan menampilkan modal "selamat anda mendapatkan THR" buat se interaktif itu dan sebagus mungkin.)
```
//2311102167
//Andika Neviantoro

<!DOCTYPE html>
<html lang="id" data-bs-theme="dark">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>رَمَضَانُ مُبَارَك — Ramadan Berkah</title>

  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet"/>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.css" rel="stylesheet"/>
  <link href="https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&family=Lora:ital,wght@0,400;0,600;1,400&display=swap" rel="stylesheet"/>

  <style>
    /* @keyframes — tidak bisa diganti Bootstrap */
    @keyframes glow {
      0%,100% { text-shadow: 0 0 20px rgba(255,193,7,.4); }
      50%      { text-shadow: 0 0 55px rgba(255,193,7,.9), 0 0 90px rgba(255,193,7,.3); }
    }
    @keyframes floatUp {
      0%,100% { transform: translateY(0); }
      50%      { transform: translateY(-10px); }
    }
    @keyframes marquee {
      from { transform: translateX(0); }
      to   { transform: translateX(-50%); }
    }
    @keyframes pulse {
      0%,100% { opacity: 1; }
      50%      { opacity: .4; }
    }
    @keyframes spin { to { transform: rotate(360deg); } }

    /* THR-specific keyframes */
    @keyframes thrBtnPulse {
      0%,100% { box-shadow: 0 0 0 0 rgba(255,193,7,.7), 0 0 20px rgba(255,193,7,.3); }
      50%      { box-shadow: 0 0 0 14px rgba(255,193,7,0), 0 0 40px rgba(255,193,7,.6); }
    }
    @keyframes thrBtnShine {
      0%   { left: -80%; }
      40%  { left: 130%; }
      100% { left: 130%; }
    }
    @keyframes confettiFall {
      0%   { transform: translateY(-20px) rotate(0deg); opacity:1; }
      100% { transform: translateY(500px) rotate(800deg); opacity:0; }
    }
    @keyframes revealUp {
      from { transform: translateY(30px); opacity:0; }
      to   { transform: translateY(0);    opacity:1; }
    }
    @keyframes coinSpin {
      0%   { transform: rotateY(0deg); }
      100% { transform: rotateY(360deg); }
    }
    @keyframes starBurst {
      0%   { transform: scale(0) rotate(0deg);   opacity:1; }
      80%  { transform: scale(1.2) rotate(360deg); opacity:1; }
      100% { transform: scale(1) rotate(360deg);  opacity:1; }
    }
    @keyframes shimmerText {
      0%   { background-position: -200% center; }
      100% { background-position:  200% center; }
    }
    @keyframes ringPulse {
      0%,100% { transform: scale(1);   opacity:.6; }
      50%      { transform: scale(1.15); opacity:.2; }
    }

    /* THR Button shine sweep — pseudo-element, mustahil Bootstrap */
    .thr-btn::after {
      content:'';
      position:absolute;
      top:-50%; left:-80%;
      width:55%; height:200%;
      background:rgba(255,255,255,.22);
      transform:skewX(-20deg);
      animation:thrBtnShine 2.8s ease-in-out infinite;
    }

    /* Gradient text — mustahil Bootstrap */
    .text-gold-shimmer {
      background: linear-gradient(90deg,#ffc107,#ffe680,#ffc107,#d4a800,#ffc107);
      background-size:200% auto;
      -webkit-background-clip:text;
      background-clip:text;
      color:transparent;
      animation:shimmerText 2s linear infinite;
    }
  </style>
</head>
<body style="font-family:'Lora',Georgia,serif;background-color:#08101f;">

<!-- NAVBAR -->
<nav class="navbar navbar-expand-lg navbar-dark sticky-top border-bottom border-warning border-opacity-25"
     style="background-color:rgba(8,16,31,.95);backdrop-filter:blur(12px);">
  <div class="container">
    <a class="navbar-brand d-flex align-items-center gap-2 text-warning fw-semibold" href="#">
      <i class="bi bi-moon-stars-fill"></i>
      <span class="fs-5" style="font-family:'Amiri',serif;">رمضان مبارك</span>
    </a>
    <button class="navbar-toggler border-warning border-opacity-50" type="button"
            data-bs-toggle="collapse" data-bs-target="#nav">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="nav">
      <ul class="navbar-nav ms-auto align-items-lg-center gap-lg-1">
        <li class="nav-item"><a class="nav-link text-warning text-opacity-75" href="#sholat">Jadwal Sholat</a></li>
        <li class="nav-item"><a class="nav-link text-warning text-opacity-75" href="#amalan">Amalan</a></li>
        <li class="nav-item"><a class="nav-link text-warning text-opacity-75" href="#doa">Doa</a></li>
        <li class="nav-item ms-lg-2">
          <a class="btn btn-warning btn-sm px-3 fw-semibold text-dark" href="#">
            <i class="bi bi-heart-fill me-1"></i>Zakat
          </a>
        </li>
      </ul>
    </div>
  </div>
</nav>

<!-- HERO -->
<section class="min-vh-100 d-flex align-items-center position-relative overflow-hidden"
         style="background:radial-gradient(ellipse 80% 60% at 50% 0%,rgba(13,110,94,.4) 0%,transparent 65%),#08101f;">
  <div class="container py-5 position-relative" style="z-index:1;">
    <div class="row align-items-center justify-content-between gy-5">

      <div class="col-lg-6 text-center text-lg-start">
        <span class="badge bg-warning bg-opacity-10 text-warning border border-warning border-opacity-25 rounded-pill px-3 py-2 mb-4 d-inline-block"
              style="letter-spacing:.2em;font-size:.7rem;">
          <i class="bi bi-stars me-1"></i>1447 HIJRIAH · 2025 MASEHI
        </span>

        <h1 class="text-warning mb-2 lh-1"
            style="font-family:'Amiri',serif;font-size:clamp(3rem,11vw,8.5rem);font-weight:700;animation:glow 4s ease-in-out infinite;">
          رَمَضَانُ مُبَارَك
        </h1>

        <p class="text-warning text-opacity-50 mb-4 fst-italic"
           style="letter-spacing:.3em;font-size:.8rem;">
          Ramadhānu Mubārak — Ramadan Berkah
        </p>

        <hr class="border-warning border-opacity-25 my-4">

        <p class="mb-4 lh-lg fs-6" style="color:#f0d9a8;">
          Bulan penuh keberkahan telah kembali hadir.<br>
          Semoga puasa, doa, dan amal kita diterima Allah SWT.
        </p>

        <div class="d-flex flex-wrap gap-3 justify-content-center justify-content-lg-start">
          <a href="#sholat" class="btn btn-warning btn-lg px-4 fw-semibold text-dark">
            <i class="bi bi-clock me-2"></i>Jadwal Sholat
          </a>
          <a href="#doa" class="btn btn-outline-warning btn-lg px-4">
            <i class="bi bi-book me-2"></i>Doa Harian
          </a>
        </div>
      </div>

      <!-- Masjid SVG -->
      <div class="col-lg-5 d-flex justify-content-center">
        <div style="animation:floatUp 4s ease-in-out infinite;">
          <svg viewBox="0 0 300 320" width="min(300px,75vw)" fill="none" xmlns="http://www.w3.org/2000/svg">
            <circle cx="240" cy="45"  r="2"   fill="#ffc107" opacity=".7"/>
            <circle cx="55"  cy="65"  r="1.5" fill="#ffc107" opacity=".5"/>
            <circle cx="275" cy="95"  r="1.5" fill="#ffc107" opacity=".4"/>
            <circle cx="25"  cy="115" r="2"   fill="#ffc107" opacity=".55"/>
            <circle cx="160" cy="18"  r="1.5" fill="#ffc107" opacity=".5"/>
            <path d="M200 42 A38 38 0 1 1 224 94 A26 26 0 1 0 200 42Z" fill="#ffc107" opacity=".9"/>
            <rect x="55" y="195" width="190" height="115" rx="3" fill="#0d5244"/>
            <ellipse cx="150" cy="195" rx="75" ry="52"  fill="#128870"/>
            <rect x="75" y="195" width="150" height="9"  fill="#0d5244"/>
            <ellipse cx="75"  cy="212" rx="28" ry="20" fill="#128870"/>
            <ellipse cx="225" cy="212" rx="28" ry="20" fill="#128870"/>
            <rect x="32"  y="155" width="16" height="120" rx="2" fill="#0d5244"/>
            <polygon points="40,136 32,157 48,157" fill="#ffc107"/>
            <line x1="40" y1="126" x2="40" y2="138" stroke="#ffc107" stroke-width="1.5"/>
            <rect x="252" y="155" width="16" height="120" rx="2" fill="#0d5244"/>
            <polygon points="260,136 252,157 268,157" fill="#ffc107"/>
            <line x1="260" y1="126" x2="260" y2="138" stroke="#ffc107" stroke-width="1.5"/>
            <path d="M132 310 L132 262 Q150 244 168 262 L168 310Z" fill="#08101f" opacity=".7"/>
            <ellipse cx="103" cy="245" rx="11" ry="14" fill="#08101f" opacity=".5"/>
            <ellipse cx="197" cy="245" rx="11" ry="14" fill="#08101f" opacity=".5"/>
            <line x1="55" y1="195" x2="245" y2="195" stroke="#ffc107" stroke-width="1.5" opacity=".55"/>
            <line x1="20" y1="310" x2="280" y2="310" stroke="#ffc107" stroke-width="1"   opacity=".2"/>
          </svg>
        </div>
      </div>
    </div>

    <!-- ═══════ TOMBOL THR ═══════ -->
    <div class="row mt-5 pt-2">
      <div class="col-12 text-center">
        <p class="text-uppercase mb-3" style="color:#5ecfb8;letter-spacing:.35em;font-size:.7rem;">
          <i class="bi bi-gift-fill me-1"></i>Ada Kejutan Spesial Untukmu
        </p>
        <div class="d-inline-block position-relative">
          <!-- Ring animasi luar -->
          <span class="position-absolute top-50 start-50 translate-middle rounded-pill"
                style="width:110%;height:145%;border:2px solid rgba(255,193,7,.35);animation:ringPulse 2s ease-in-out infinite;pointer-events:none;"></span>
          <button type="button"
                  class="btn btn-warning btn-lg px-5 py-3 fw-bold text-dark rounded-pill position-relative overflow-hidden thr-btn"
                  data-bs-toggle="modal" data-bs-target="#modalTHR"
                  style="font-size:1.05rem;letter-spacing:.04em;animation:thrBtnPulse 2s ease-in-out infinite;">
            <i class="bi bi-envelope-open-heart-fill me-2 fs-5"></i>
            Buka Amplop THR Kamu
            <i class="bi bi-stars ms-2"></i>
          </button>
        </div>
        <p class="mt-3 mb-0" style="color:rgba(255,193,7,.45);font-size:.75rem;">
          <i class="bi bi-arrow-up me-1" style="animation:pulse 1.5s ease-in-out infinite;display:inline-block;"></i>
          Klik tombol di atas untuk membuka amplop
        </p>
      </div>
    </div>

  </div>
</section>

<!-- MARQUEE STRIP -->
<div class="overflow-hidden border-top border-bottom border-warning border-opacity-25 py-3 bg-warning bg-opacity-10">
  <span class="text-warning text-opacity-75"
        style="font-family:'Amiri',serif;animation:marquee 26s linear infinite;display:inline-block;white-space:nowrap;font-size:1.1rem;letter-spacing:.4em;">
    سُبْحَانَ اللّٰهِ &nbsp;·&nbsp; الْحَمْدُ لِلّٰهِ &nbsp;·&nbsp; اَللّٰهُ أَكْبَرُ &nbsp;·&nbsp; لَا إِلٰهَ إِلَّا اللّٰهُ &nbsp;·&nbsp; اَسْتَغْفِرُ اللّٰهَ &nbsp;·&nbsp;
    سُبْحَانَ اللّٰهِ &nbsp;·&nbsp; الْحَمْدُ لِلّٰهِ &nbsp;·&nbsp; اَللّٰهُ أَكْبَرُ &nbsp;·&nbsp; لَا إِلٰهَ إِلَّا اللّٰهُ &nbsp;·&nbsp; اَسْتَغْفِرُ اللّٰهَ &nbsp;·&nbsp;
  </span>
</div>

<!-- JADWAL SHOLAT -->
<section id="sholat" class="py-5">
  <div class="container">
    <div class="text-center mb-5">
      <p class="text-warning text-opacity-50 text-uppercase mb-1" style="letter-spacing:.4em;font-size:.72rem;">
        <i class="bi bi-geo-alt me-1"></i>Cilacap, Jawa Tengah
      </p>
      <h2 class="fw-bold text-warning">Jadwal Sholat Hari Ini</h2>
      <p class="fst-italic small" style="color:#5ecfb8;">Ahad, 8 Maret 2026 · 8 Ramadan 1447 H</p>
    </div>
    <div class="row g-3 justify-content-center">

      <!-- Imsak -->
      <div class="col-6 col-md-4 col-xl-2">
        <div class="h-100 bg-warning bg-opacity-10 border border-warning rounded-4 p-3 text-center d-flex flex-column align-items-center justify-content-center gap-2">
          <div class="bg-warning bg-opacity-25 rounded-circle d-flex align-items-center justify-content-center" style="width:46px;height:46px;">
            <i class="bi bi-moon-fill text-warning fs-5"></i>
          </div>
          <div class="text-warning fw-bold fs-5">04:10</div>
          <div class="text-uppercase" style="color:#5ecfb8;font-size:.7rem;letter-spacing:.15em;">Imsak</div>
          <span class="badge bg-warning text-dark rounded-pill" style="font-size:.6rem;">Sahur selesai</span>
        </div>
      </div>

      <!-- Subuh -->
      <div class="col-6 col-md-4 col-xl-2">
        <div class="h-100 rounded-4 p-3 text-center d-flex flex-column align-items-center justify-content-center gap-2 border"
             style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important;">
          <div class="bg-success bg-opacity-25 rounded-circle d-flex align-items-center justify-content-center" style="width:46px;height:46px;">
            <i class="bi bi-sunrise text-success fs-5"></i>
          </div>
          <div class="text-warning fw-bold fs-5">04:20</div>
          <div class="text-uppercase" style="color:#5ecfb8;font-size:.7rem;letter-spacing:.15em;">Subuh</div>
        </div>
      </div>

      <!-- Dzuhur -->
      <div class="col-6 col-md-4 col-xl-2">
        <div class="h-100 rounded-4 p-3 text-center d-flex flex-column align-items-center justify-content-center gap-2 border"
             style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important;">
          <div class="bg-success bg-opacity-25 rounded-circle d-flex align-items-center justify-content-center" style="width:46px;height:46px;">
            <i class="bi bi-sun text-success fs-5"></i>
          </div>
          <div class="text-warning fw-bold fs-5">11:52</div>
          <div class="text-uppercase" style="color:#5ecfb8;font-size:.7rem;letter-spacing:.15em;">Dzuhur</div>
        </div>
      </div>

      <!-- Ashar -->
      <div class="col-6 col-md-4 col-xl-2">
        <div class="h-100 rounded-4 p-3 text-center d-flex flex-column align-items-center justify-content-center gap-2 border"
             style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important;">
          <div class="bg-success bg-opacity-25 rounded-circle d-flex align-items-center justify-content-center" style="width:46px;height:46px;">
            <i class="bi bi-sun-fill text-success fs-5"></i>
          </div>
          <div class="text-warning fw-bold fs-5">15:12</div>
          <div class="text-uppercase" style="color:#5ecfb8;font-size:.7rem;letter-spacing:.15em;">Ashar</div>
        </div>
      </div>

      <!-- Maghrib -->
      <div class="col-6 col-md-4 col-xl-2">
        <div class="h-100 bg-warning bg-opacity-10 border border-warning rounded-4 p-3 text-center d-flex flex-column align-items-center justify-content-center gap-2">
          <div class="bg-warning bg-opacity-25 rounded-circle d-flex align-items-center justify-content-center" style="width:46px;height:46px;">
            <i class="bi bi-sunset-fill text-warning fs-5"></i>
          </div>
          <div class="text-warning fw-bold fs-5">17:55</div>
          <div class="text-uppercase" style="color:#5ecfb8;font-size:.7rem;letter-spacing:.15em;">Maghrib</div>
          <span class="badge bg-warning text-dark rounded-pill" style="font-size:.6rem;">Buka puasa</span>
        </div>
      </div>

      <!-- Isya -->
      <div class="col-6 col-md-4 col-xl-2">
        <div class="h-100 rounded-4 p-3 text-center d-flex flex-column align-items-center justify-content-center gap-2 border"
             style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important;">
          <div class="bg-success bg-opacity-25 rounded-circle d-flex align-items-center justify-content-center" style="width:46px;height:46px;">
            <i class="bi bi-moon-stars-fill text-success fs-5"></i>
          </div>
          <div class="text-warning fw-bold fs-5">19:05</div>
          <div class="text-uppercase" style="color:#5ecfb8;font-size:.7rem;letter-spacing:.15em;">Isya</div>
        </div>
      </div>

    </div>
  </div>
</section>

<hr class="border-warning border-opacity-10 mx-5">

<!-- AMALAN -->
<section id="amalan" class="py-5">
  <div class="container">
    <div class="text-center mb-5">
      <p class="text-warning text-opacity-50 text-uppercase mb-1" style="letter-spacing:.4em;font-size:.72rem;">Perbanyak di bulan suci</p>
      <h2 class="fw-bold text-warning">Amalan Utama Ramadan</h2>
    </div>
    <div class="row g-4">
      <div class="col-md-6 col-lg-3">
        <div class="h-100 rounded-4 p-4 d-flex flex-column gap-3 border"
             style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important;">
          <i class="bi bi-book-half text-warning fs-1"></i>
          <div class="flex-grow-1">
            <h5 class="fw-semibold mb-2">Tilawah Al-Qur'an</h5>
            <p class="small lh-lg mb-0" style="color:#f0d9a8;">Targetkan 1 juz sehari agar khatam dalam 30 hari penuh berkah.</p>
          </div>
          <div>
            <div class="d-flex justify-content-between mb-1">
              <small style="color:#5ecfb8;">8 / 30 juz</small>
              <small class="text-warning">27%</small>
            </div>
            <div class="progress rounded-pill" style="height:4px;">
              <div class="progress-bar bg-warning rounded-pill" style="width:27%"></div>
            </div>
          </div>
        </div>
      </div>
      <div class="col-md-6 col-lg-3">
        <div class="h-100 rounded-4 p-4 d-flex flex-column gap-3 border"
             style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important;">
          <i class="bi bi-person-arms-up text-warning fs-1"></i>
          <div class="flex-grow-1">
            <h5 class="fw-semibold mb-2">Sholat Tarawih</h5>
            <p class="small lh-lg mb-0" style="color:#f0d9a8;">Hidupkan malam Ramadan bersama jamaah di masjid.</p>
          </div>
          <div class="d-flex gap-2 flex-wrap">
            <span class="badge bg-success bg-opacity-25 text-success rounded-pill px-3 py-2">8 Rakaat</span>
            <span class="badge bg-success bg-opacity-25 text-success rounded-pill px-3 py-2">+ Witir 3</span>
          </div>
        </div>
      </div>
      <div class="col-md-6 col-lg-3">
        <div class="h-100 rounded-4 p-4 d-flex flex-column gap-3 border"
             style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important;">
          <i class="bi bi-heart-fill text-warning fs-1"></i>
          <div class="flex-grow-1">
            <h5 class="fw-semibold mb-2">Sedekah & Zakat</h5>
            <p class="small lh-lg mb-0" style="color:#f0d9a8;">Setiap sedekah dilipatgandakan pahalanya di bulan ini.</p>
          </div>
          <a href="#" class="btn btn-warning btn-sm fw-semibold text-dark w-100">
            <i class="bi bi-send me-1"></i>Salurkan Sekarang
          </a>
        </div>
      </div>
      <div class="col-md-6 col-lg-3">
        <div class="h-100 rounded-4 p-4 d-flex flex-column gap-3 border"
             style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important;">
          <i class="bi bi-stars text-warning fs-1"></i>
          <div class="flex-grow-1">
            <h5 class="fw-semibold mb-2">I'tikaf</h5>
            <p class="small lh-lg mb-0" style="color:#f0d9a8;">Berdiam di masjid pada 10 malam terakhir demi Lailatul Qadr.</p>
          </div>
          <span class="badge bg-warning bg-opacity-25 text-warning rounded-pill px-3 py-2 text-center w-100">
            <i class="bi bi-calendar-event me-1"></i>21–30 Ramadan
          </span>
        </div>
      </div>
    </div>
  </div>
</section>

<hr class="border-warning border-opacity-10 mx-5">

<!-- DOA -->
<section id="doa" class="py-5">
  <div class="container">
    <div class="text-center mb-5">
      <p class="text-warning text-opacity-50 text-uppercase mb-1" style="letter-spacing:.4em;font-size:.72rem;">Hafalan harian</p>
      <h2 class="fw-bold text-warning">Doa-Doa Ramadan</h2>
    </div>
    <div class="row g-4 justify-content-center">
      <div class="col-lg-7">
        <div class="accordion d-flex flex-column gap-3" id="doaAcc">

          <div class="rounded-4 overflow-hidden border"
               style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important;">
            <h2 class="accordion-header">
              <button class="accordion-button collapsed bg-transparent text-warning shadow-none gap-3 fw-semibold"
                      type="button" data-bs-toggle="collapse" data-bs-target="#d1">
                <i class="bi bi-moon text-warning fs-5"></i>Niat Puasa Ramadan
              </button>
            </h2>
            <div id="d1" class="accordion-collapse collapse" data-bs-parent="#doaAcc">
              <div class="accordion-body">
                <p class="text-warning text-end lh-lg mb-3" style="font-family:'Amiri',serif;font-size:1.65rem;direction:rtl;">
                  نَوَيْتُ صَوْمَ غَدٍ عَنْ أَدَاءِ فَرْضِ شَهْرِ رَمَضَانَ هٰذِهِ السَّنَةِ لِلّٰهِ تَعَالَى
                </p>
                <hr class="border-warning border-opacity-25">
                <p class="fst-italic small mb-1" style="color:#5ecfb8;">"Nawaitu shauma ghadin 'an adā'i fardhi syahri Ramadhāna hādzihis sanati lillāhi ta'ālā."</p>
                <p class="small mb-0" style="color:#f0d9a8;">Artinya: Saya niat berpuasa esok hari untuk menunaikan kewajiban Ramadan tahun ini karena Allah Ta'ala.</p>
              </div>
            </div>
          </div>

          <div class="rounded-4 overflow-hidden border"
               style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important;">
            <h2 class="accordion-header">
              <button class="accordion-button collapsed bg-transparent text-warning shadow-none gap-3 fw-semibold"
                      type="button" data-bs-toggle="collapse" data-bs-target="#d2">
                <i class="bi bi-sunset text-warning fs-5"></i>Doa Buka Puasa
              </button>
            </h2>
            <div id="d2" class="accordion-collapse collapse" data-bs-parent="#doaAcc">
              <div class="accordion-body">
                <p class="text-warning text-end lh-lg mb-3" style="font-family:'Amiri',serif;font-size:1.65rem;direction:rtl;">
                  اَللّٰهُمَّ لَكَ صُمْتُ وَبِكَ آمَنْتُ وَعَلَى رِزْقِكَ أَفْطَرْتُ
                </p>
                <hr class="border-warning border-opacity-25">
                <p class="fst-italic small mb-1" style="color:#5ecfb8;">"Allāhumma laka shumtu wa bika āmantu wa 'alā rizqika afthartu."</p>
                <p class="small mb-0" style="color:#f0d9a8;">Artinya: Ya Allah, untuk-Mu aku berpuasa, kepada-Mu aku beriman, dan dengan rezeki-Mu aku berbuka.</p>
              </div>
            </div>
          </div>

          <div class="rounded-4 overflow-hidden border"
               style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important;">
            <h2 class="accordion-header">
              <button class="accordion-button collapsed bg-transparent text-warning shadow-none gap-3 fw-semibold"
                      type="button" data-bs-toggle="collapse" data-bs-target="#d3">
                <i class="bi bi-stars text-warning fs-5"></i>Doa Lailatul Qadr
              </button>
            </h2>
            <div id="d3" class="accordion-collapse collapse" data-bs-parent="#doaAcc">
              <div class="accordion-body">
                <p class="text-warning text-end lh-lg mb-3" style="font-family:'Amiri',serif;font-size:1.65rem;direction:rtl;">
                  اَللّٰهُمَّ إِنَّكَ عَفُوٌّ كَرِيمٌ تُحِبُّ الْعَفْوَ فَاعْفُ عَنِّي
                </p>
                <hr class="border-warning border-opacity-25">
                <p class="fst-italic small mb-1" style="color:#5ecfb8;">"Allāhumma innaka 'afuwwun karīmun tuhibbul 'afwa fa'fu 'annī."</p>
                <p class="small mb-0" style="color:#f0d9a8;">Artinya: Ya Allah, Engkau Maha Pemaaf lagi Maha Mulia, Engkau menyukai maaf, maka maafkanlah aku.</p>
              </div>
            </div>
          </div>

        </div>
      </div>
      <div class="col-lg-5">
        <div class="h-100 rounded-4 p-4 p-lg-5 d-flex flex-column justify-content-center align-items-center text-center gap-4 border"
             style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important;">
          <i class="bi bi-quote text-warning opacity-25" style="font-size:3.5rem;line-height:1;"></i>
          <p class="text-warning lh-lg mb-0" style="font-family:'Amiri',serif;font-size:clamp(1.3rem,2.5vw,1.65rem);direction:rtl;line-height:2.1;">
            شَهْرُ رَمَضَانَ الَّذِيْٓ اُنْزِلَ فِيْهِ الْقُرْاٰنُ
          </p>
          <hr class="border-warning border-opacity-25 w-25">
          <p class="fst-italic small lh-lg mb-0" style="color:#f0d9a8;">"Bulan Ramadan adalah bulan yang di dalamnya diturunkan Al-Qur'an sebagai petunjuk bagi manusia."</p>
          <span class="text-warning fw-semibold" style="font-size:.8rem;letter-spacing:.1em;">QS. Al-Baqarah: 185</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer class="border-top border-warning border-opacity-10 py-4 bg-warning bg-opacity-10">
  <div class="container">
    <div class="row align-items-center gy-3 text-center text-md-start">
      <div class="col-md-4">
        <div class="text-warning fs-4" style="font-family:'Amiri',serif;">رَمَضَانُ مُبَارَك</div>
        <p class="mb-0 mt-1" style="color:#5ecfb8;font-size:.72rem;letter-spacing:.15em;">RAMADAN BERKAH · 1447 H</p>
      </div>
      <div class="col-md-4 text-center">
        <span class="text-warning text-opacity-40 fs-5" style="font-family:'Amiri',serif;">بِسْمِ اللّٰهِ</span>
        <p class="mb-0 mt-1" style="color:#5ecfb8;font-size:.7rem;">Dika Berbagi · Ramadhan Berkah</p>
      </div>
      <div class="col-md-4 d-flex justify-content-center justify-content-md-end align-items-center gap-3">
        <a href="#" class="text-warning text-opacity-75 fs-5"><i class="bi bi-instagram"></i></a>
        <a href="#" class="text-warning text-opacity-75 fs-5"><i class="bi bi-twitter-x"></i></a>
        <a href="#" class="text-warning text-opacity-75 fs-5"><i class="bi bi-youtube"></i></a>
      </div>
    </div>
  </div>
</footer>


<!-- ═══════════════════════════════════════════
     MODAL THR — Interaktif 3 langkah
═══════════════════════════════════════════ -->
<div class="modal fade" id="modalTHR" tabindex="-1" aria-hidden="true">
  <div class="modal-dialog modal-dialog-centered modal-md">
    <div class="modal-content border-0 overflow-hidden position-relative text-center"
         id="thrModalContent"
         style="background:linear-gradient(160deg,#0d1f12 0%,#0a1a10 50%,#0d1a0a 100%);border:1px solid rgba(255,193,7,.25)!important;border-radius:1.25rem;">

      <!-- Confetti layer -->
      <div id="confettiBox" class="position-absolute w-100 overflow-hidden"
           style="top:0;left:0;height:100%;pointer-events:none;z-index:0;"></div>

      <!-- Tutup -->
      <button type="button" class="btn-close btn-close-white position-absolute top-0 end-0 m-3"
              data-bs-dismiss="modal" style="z-index:20;opacity:.6;"></button>

      <div class="modal-body p-0 position-relative" style="z-index:1;">

        <!-- ── STEP 1: Amplop tertutup ── -->
        <div id="step1" class="p-4 p-md-5">
          <p class="text-uppercase mb-4" style="color:#5ecfb8;letter-spacing:.3em;font-size:.68rem;">
            <i class="bi bi-gift-fill me-1"></i>Hadiah Istimewa Ramadan
          </p>

          <!-- Amplop interaktif -->
          <div class="d-flex justify-content-center mb-4">
            <div id="envelopeWrap" class="position-relative d-inline-block" style="cursor:pointer;" onclick="stepReveal()">
              <!-- Cincin dekorasi -->
              <span class="position-absolute top-50 start-50 translate-middle rounded-circle"
                    style="width:175px;height:175px;border:1.5px dashed rgba(255,193,7,.25);animation:spin 12s linear infinite;pointer-events:none;"></span>
              <span class="position-absolute top-50 start-50 translate-middle rounded-circle"
                    style="width:148px;height:148px;border:1.5px solid rgba(255,193,7,.12);animation:spin 8s linear infinite reverse;pointer-events:none;"></span>

              <!-- SVG Amplop -->
              <div id="envelopeSvgBox" style="animation:floatUp 2.5s ease-in-out infinite;">
                <svg viewBox="0 0 180 130" width="140">
                  <!-- Badan -->
                  <rect x="4" y="28" width="172" height="98" rx="8" fill="#8B1A1A" stroke="#f39c12" stroke-width="2.5"/>
                  <!-- Flap atas -->
                  <polygon points="4,28 90,84 176,28" fill="#c0392b" stroke="#f39c12" stroke-width="2"/>
                  <!-- Segitiga bawah kiri-kanan -->
                  <polygon points="4,126 58,76 90,96 122,76 176,126" fill="#7a1515"/>
                  <!-- Ornamen bintang tengah -->
                  <polygon points="90,52 94,64 107,64 97,72 101,84 90,76 79,84 83,72 73,64 86,64"
                           fill="#f39c12" opacity=".95"/>
                  <!-- Tulisan arab -->
                  <text x="90" y="116" text-anchor="middle" font-family="Amiri,serif"
                        font-size="17" fill="#f39c12" opacity=".85">مبارك</text>
                  <!-- Garis hias -->
                  <line x1="30" y1="100" x2="55" y2="100" stroke="#f39c12" stroke-width="1" opacity=".4"/>
                  <line x1="125" y1="100" x2="150" y2="100" stroke="#f39c12" stroke-width="1" opacity=".4"/>
                </svg>
              </div>
            </div>
          </div>

          <h4 class="fw-bold text-warning mb-2">Ada Amplop Untukmu! 🎁</h4>
          <p class="mb-4" style="color:#5ecfb8;font-size:.9rem;">Ketuk amplop atau tekan tombol di bawah</p>

          <button class="btn btn-warning btn-lg rounded-pill px-5 fw-bold text-dark"
                  onclick="stepReveal()" style="font-size:.95rem;">
            <i class="bi bi-envelope-open-fill me-2"></i>Buka Amplop!
          </button>
        </div>

        <!-- ── STEP 2: Kocok nominal ── -->
        <div id="step2" class="p-4 p-md-5 d-none">
          <p class="text-uppercase mb-3" style="color:#5ecfb8;letter-spacing:.3em;font-size:.68rem;">
            <i class="bi bi-shuffle me-1"></i>Mengocok nominal THR...
          </p>

          <div class="d-flex justify-content-center mb-4">
            <div class="position-relative d-flex align-items-center justify-content-center rounded-circle bg-warning bg-opacity-10 border border-warning"
                 style="width:130px;height:130px;border-opacity:.4!important;">
              <i class="bi bi-currency-dollar text-warning" style="font-size:4.5rem;animation:coinSpin 0.4s linear infinite;" id="coinIcon"></i>
            </div>
          </div>

          <div class="mb-4">
            <p class="text-uppercase mb-1" style="color:#5ecfb8;letter-spacing:.2em;font-size:.68rem;">Nominal THR Kamu</p>
            <div id="slotDisplay" class="fw-bold text-warning"
                 style="font-size:clamp(2rem,8vw,3rem);font-family:'Lora',serif;min-height:4rem;letter-spacing:.02em;">
              Rp ???.???
            </div>
          </div>

          <div class="progress rounded-pill mb-3 mx-auto" style="height:6px;max-width:260px;">
            <div id="loadBar" class="progress-bar bg-warning rounded-pill" style="width:0%;transition:width .1s linear;"></div>
          </div>
          <p class="mb-0" style="color:rgba(255,193,7,.5);font-size:.78rem;">Sedang diproses...</p>
        </div>

        <!-- ── STEP 3: Reveal ── -->
        <div id="step3" class="p-4 p-md-5 d-none">

          <div class="mb-3" style="animation:starBurst .6s ease both;">
            <span class="d-inline-flex align-items-center gap-2 badge bg-warning text-dark rounded-pill px-4 py-2 fw-bold"
                  style="font-size:.85rem;letter-spacing:.05em;">
              <i class="bi bi-trophy-fill"></i>SELAMAT!
            </span>
          </div>

          <h2 class="fw-bold mb-1 text-gold-shimmer"
              style="font-size:clamp(1.4rem,5vw,2rem);animation:revealUp .5s ease both .1s;opacity:0;animation-fill-mode:forwards;">
            🎉 Selamat, Kamu Mendapat THR!
          </h2>

          <p class="text-warning text-opacity-60 mb-4"
             style="font-family:'Amiri',serif;font-size:1.1rem;animation:revealUp .5s ease both .2s;opacity:0;animation-fill-mode:forwards;">
            تَقَبَّلَ اللّٰهُ مِنَّا وَمِنْكُم
          </p>

          <!-- Nominal box -->
          <div class="rounded-4 py-4 px-3 mb-4 border border-warning border-opacity-50 bg-warning bg-opacity-10"
               style="animation:revealUp .5s ease both .3s;opacity:0;animation-fill-mode:forwards;">
            <p class="text-uppercase mb-1" style="color:#5ecfb8;font-size:.68rem;letter-spacing:.3em;">Nominal THR Kamu</p>
            <div id="finalNominal" class="fw-bold text-warning"
                 style="font-size:clamp(2rem,8vw,3.2rem);font-family:'Lora',serif;">
              Rp 1.000.000
            </div>
            <p class="text-success small mt-1 mb-0">
              <i class="bi bi-check-circle-fill me-1"></i>Sudah dikirim ke rekening kamu 🎊
            </p>
          </div>

          <!-- Ucapan -->
          <div class="mb-4" style="animation:revealUp .5s ease both .4s;opacity:0;animation-fill-mode:forwards;">
            <p class="lh-lg mb-1" style="color:#f0d9a8;font-size:.92rem;">
              Selamat Hari Raya Idul Fitri 1447 H<br>
              <span class="text-warning fw-semibold">Minal Aidin wal Faizin</span> 🌙✨
            </p>
            <p class="mb-0" style="color:#5ecfb8;font-size:.82rem;">Mohon maaf lahir dan batin</p>
          </div>

          <!-- Reaksi emoji -->
          <div class="d-flex justify-content-center gap-2 mb-4 flex-wrap"
               style="animation:revealUp .5s ease both .5s;opacity:0;animation-fill-mode:forwards;">
            <button class="btn btn-outline-warning rounded-pill px-3 py-2 react-btn" onclick="doReact(this,'🤩')">🤩 Senang</button>
            <button class="btn btn-outline-warning rounded-pill px-3 py-2 react-btn" onclick="doReact(this,'🙏')">🙏 Syukur</button>
            <button class="btn btn-outline-warning rounded-pill px-3 py-2 react-btn" onclick="doReact(this,'💛')">💛 Makasih</button>
          </div>

          <!-- Aksi -->
          <div class="d-flex gap-2 justify-content-center flex-wrap"
               style="animation:revealUp .5s ease both .6s;opacity:0;animation-fill-mode:forwards;">
            <button class="btn btn-warning fw-bold text-dark rounded-pill px-4" onclick="doShare()">
              <i class="bi bi-share-fill me-2"></i>Bagikan
            </button>
            <button class="btn btn-outline-warning rounded-pill px-4" onclick="resetModal()">
              <i class="bi bi-arrow-counterclockwise me-2"></i>Coba Lagi
            </button>
            <button class="btn btn-outline-secondary rounded-pill px-4" data-bs-dismiss="modal">
              Tutup
            </button>
          </div>

        </div>
      </div>
    </div>
  </div>
</div>


<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
<script>
  /* ── Reset saat modal dibuka ── */
  document.getElementById('modalTHR').addEventListener('show.bs.modal', resetModal);

  function resetModal() {
    show('step1'); hide('step2'); hide('step3');
    document.getElementById('confettiBox').innerHTML = '';
    document.getElementById('envelopeSvgBox').style.animation = 'floatUp 2.5s ease-in-out infinite';
    document.getElementById('envelopeSvgBox').style.transform = '';
    document.getElementById('envelopeSvgBox').style.opacity = '1';
    document.getElementById('slotDisplay').textContent = 'Rp ???.???';
    document.getElementById('loadBar').style.width = '0%';
    document.querySelectorAll('.react-btn').forEach(b => {
      b.classList.remove('btn-warning','text-dark');
      b.classList.add('btn-outline-warning');
    });
  }

  function show(id) { document.getElementById(id).classList.remove('d-none'); }
  function hide(id) { document.getElementById(id).classList.add('d-none'); }

  /* ── STEP 1 → 2: Animasi buka amplop ── */
  function stepReveal() {
    const box = document.getElementById('envelopeSvgBox');
    box.style.transition = 'transform .15s ease, opacity .3s ease';
    box.style.transform = 'scale(1.15) rotate(4deg)';
    setTimeout(() => {
      box.style.transform = 'scale(0) rotate(25deg)';
      box.style.opacity = '0';
    }, 120);
    setTimeout(() => {
      hide('step1');
      show('step2');
      runSlotMachine();
    }, 450);
  }

  /* ── STEP 2: Slot machine nominal ── */
  const nominals = [
    'Rp 250.000','Rp 500.000','Rp 750.000',
    'Rp 1.000.000','Rp 1.500.000','Rp 2.000.000','Rp 3.000.000'
  ];

  function runSlotMachine() {
    const picked = nominals[Math.floor(Math.random() * nominals.length)];
    const slot   = document.getElementById('slotDisplay');
    const bar    = document.getElementById('loadBar');
    const coin   = document.getElementById('coinIcon');
    let prog = 0, spinCount = 0;
    const totalSpins = 28;

    const ticker = setInterval(() => {
      slot.textContent = nominals[Math.floor(Math.random() * nominals.length)];
      spinCount++;
      prog = Math.min(100, (spinCount / totalSpins) * 100);
      bar.style.width = prog + '%';

      // perlambat di akhir
      if (spinCount >= totalSpins) {
        clearInterval(ticker);
        coin.style.animation = 'none';
        slot.textContent = picked;
        document.getElementById('finalNominal').textContent = picked;
        setTimeout(() => {
          hide('step2');
          show('step3');
          launchConfetti();
        }, 600);
      }
    }, spinCount < 20 ? 80 : 160);
  }

  /* ── Confetti ── */
  function launchConfetti() {
    const box    = document.getElementById('confettiBox');
    const colors = ['#ffc107','#ff6b35','#ff3d7f','#00d4aa','#a8ff3e','#ff9ef5','#ffffff','#f39c12'];
    const shapes = ['0','2px','50%'];
    box.innerHTML = '';

    const spawn = (count, delay) => setTimeout(() => {
      for (let i = 0; i < count; i++) {
        const el = document.createElement('div');
        const sz = Math.random() * 10 + 5;
        el.style.cssText = `
          position:absolute;
          left:${Math.random()*100}%;
          top:-${Math.random()*10+5}%;
          width:${sz}px; height:${sz}px;
          background:${colors[Math.floor(Math.random()*colors.length)]};
          border-radius:${shapes[Math.floor(Math.random()*shapes.length)]};
          animation:confettiFall ${Math.random()*1.4+.8}s linear ${Math.random()*.6}s forwards;
        `;
        box.appendChild(el);
      }
    }, delay);

    spawn(70, 0);
    spawn(50, 500);
    spawn(40, 1100);
  }

  /* ── Reaksi emoji melayang ── */
  function doReact(btn, emoji) {
    document.querySelectorAll('.react-btn').forEach(b => {
      b.classList.remove('btn-warning','text-dark');
      b.classList.add('btn-outline-warning');
    });
    btn.classList.remove('btn-outline-warning');
    btn.classList.add('btn-warning','text-dark');

    const modal = document.getElementById('thrModalContent');
    for (let i = 0; i < 4; i++) {
      setTimeout(() => {
        const fly = document.createElement('div');
        fly.textContent = emoji;
        fly.style.cssText = `
          position:absolute;
          font-size:${1.8 + Math.random()}rem;
          left:${20 + Math.random()*60}%;
          bottom:15%;
          z-index:99;
          pointer-events:none;
          animation:floatUp ${.9+Math.random()*.5}s ease forwards;
          opacity:1;
        `;
        modal.appendChild(fly);
        setTimeout(() => fly.remove(), 1400);
      }, i * 120);
    }
  }

  /* ── Share / Salin ── */
  function doShare() {
    const nom  = document.getElementById('finalNominal').textContent;
    const text = `🎉 Alhamdulillah! Saya mendapat THR ${nom} di bulan Ramadan!\n🌙 Selamat Hari Raya Idul Fitri 1447 H\n✨ Minal Aidin wal Faizin 🙏`;
    if (navigator.share) {
      navigator.share({ title: 'THR Ramadan', text });
    } else {
      navigator.clipboard.writeText(text).then(() => {
        const btn = event.currentTarget;
        const ori = btn.innerHTML;
        btn.innerHTML = '<i class="bi bi-check-circle-fill me-2"></i>Tersalin!';
        btn.classList.replace('btn-warning','btn-success');
        btn.classList.remove('text-dark');
        btn.classList.add('text-white');
        setTimeout(() => {
          btn.innerHTML = ori;
          btn.classList.replace('btn-success','btn-warning');
          btn.classList.remove('text-white');
          btn.classList.add('text-dark');
        }, 2200);
      });
    }
  }
</script>

</body>
</html>
```
Output:
<img width="1901" height="961" alt="image" src="https://github.com/user-attachments/assets/5b0a2084-99cb-49a2-855a-2b83b69bae86" />
<img width="1896" height="969" alt="image" src="https://github.com/user-attachments/assets/beda6987-1cef-42eb-bee5-c3ae357dceef" />
<img width="1901" height="971" alt="image" src="https://github.com/user-attachments/assets/b4456efc-56a6-4975-9040-e0a3c3930ce2" />
<img width="1914" height="974" alt="image" src="https://github.com/user-attachments/assets/e45fc34e-2079-48d4-b4bf-82535ab13eea" />
<img width="1910" height="972" alt="image" src="https://github.com/user-attachments/assets/bc44ccc4-9979-4d27-a07d-2754533d6dc7" />






