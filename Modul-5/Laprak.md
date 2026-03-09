<div align="center">
  <br />

  <h1>LAPORAN PRAKTIKUM <br>
  APLIKASI BERBASIS PLATFORM
  </h1>

  <br />

  <h3>MODUL I <br>
  GIT
  </h3>

  <br />

  <img width="300" height="369" alt="logo" src="https://github.com/user-attachments/assets/b65bc963-853b-4946-b998-8845eeaa2d39" />


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

## 5.1. Pengenalan Bootstrap
Bootstrap merupakan sebuah front-end framework gratis untuk pengembangan antar muka web yang lebih cepat dan lebih mudah. Dikembangkan oleh Mark Otto dan Jacom Thornton di Twitter dan dirilis sebagai produk open source pada Agustus 2011 di GitHub. Bootstrap mencakup template desain berbasis HTML dan CSS untuk tipografi, form, button, navigasi, modal, image carousells dan masih banyak lagi, serta terdapat opsional plugin JavaScript. Selain itu, Bootstrap memiliki kemampuan untuk membuat desain responsif yang secara otomatis menyesuaikan diri agar terlihat baik di segala perangkat, mulai dari perangkat ponsel hingga desktop pc.

### 5.1.1. Pemasangan Bootstrap
Bootstrap merupakan produk yang mengusung konsep open source sehingga untuk pemasangannya dapat
dilakukan dengan beberapa cara sebagai berikut:
a. Unduh di http://getbootstrap.com, selanjutnya pasang pada project web kalian seperti memanggil
External Style Sheet pada CSS.
b. Memanggil Bootstrap CDN (Content Delivery Network), sehingga kita tidak perlu mengunduh dan
memasangnya pada laman website, hanya memanggil source dari Bootstrap. Cara ini membutuhkan
koneksi internet untuk menghasilkan perubahan tampilan CSS.
```
<!-- Pemanggilan Bootstrap dengan CDN -->

<!-- CSS -->

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css"
rel="stylesheet" integrity="sha384-
9ndCyUaIbzAi2FUVXJi0CjmCapSmO7SnpJef0486qhLnuZ2cdeRhO02iuK6FUUVM"
crossorigin="anonymous">

<!-- jQuery library -->

<script src="https://code.jquery.com/jquery-3.7.0.min.js" integrity="sha256-
2Pmvv0kuTBOenSvLm6bvfBSSHrUJ+3A7x6P5Ebd07/g=" crossorigin="anonymous"></script>

<!-- JavaScript -->

<script
src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"
integrity="sha384-geWF76RCwLtnZ8qwWowPQNguL3RmwHVBC9FhGdlKrxdiJJigb/j/68SIy3Te4Bkz"
crossorigin="anonymous"></script>
```


## 5.2. Bootstrap Container
Bootstrap container adalah elemen paling dasar yang dibutuhkan dalam layouting menggunakan Bootstrap Grid. Container berbentuk class CSS yang sisipkan pada elemen HTML <div>. Pada gambar 5-1 terdapat dua class container pada Bootstrap yang dapat dipilih yaitu:
a. Class .container menyediakan container yang responsive dengan lebar yang tetap.
b. Class .container-fluid menyediakan container dengan lebar yang penuh mencakup seluruh area pandang.
<p align="center"><img width="711" height="103" alt="image" src="https://github.com/user-attachments/assets/28089516-fc25-4789-ae37-f47ff08b0af3" /></p>

## 5.3. Bootstrap Grid
Sistem grid pada Bootstrap menggunakan rangkaian container, rows dan column untuk tata letak dan
keselarasan elemen atau konten. Dibangun dengan flexbox dan sangat responsif terhadap perangkat yang digunakan untuk menampilkan laman web. Struktur dasar grid pada Bootstrap sebagai berikut.
```
<div class="row">
  <div class="col-*-#"></div>
  <div class="col-*-#"></div>
</div>
<div class="row">
  <div class="col-*-#"></div>
  <div class="col-*-#"></div>
  <div class="col-*-#"></div>
</div>
```
Pertama diawali dengan <div class=”container”>. Kemudian buat sebuah baris sebelum mendeklarasikan sebuah kolom dengan menggunakan <div class=”row”>. Terakhir buat elemen div dengan mendefinisikan class “col-*-#”. Tanda * dan # mewakili jenis dan ukuran column yang akan digunakan, value yang dapat didefinisikan dapat dilihat pada tabel 1 :

| Feature / Size        | Extra Small | Small | Medium | Large | Extra Large |
|-----------------------|-------------|-------|--------|-------|-------------|
| Max container width   | None (auto) | 540px | 720px  | 960px | 1140px      |
| Class prefix          | .col-       | .col-sm- | .col-md- | .col-lg- | .col-xl- |
| # of columns          | 12          | 12    | 12     | 12    | 12          |
| Nestable              | Yes         | Yes   | Yes    | Yes   | Yes         |
| Column Ordering       | Yes         | Yes   | Yes    | Yes   | Yes         |

Contoh penerapannya sebagai berikut:
```
<div class=”container”>
  <div class="row">
    <div class="col-12 col-md-8">.col-12 .col-md-8</div>
    <div class="col-6 col-md-4">.col-6 .col-md-4</div>
  </div>
  <div class="row">
    <div class="col-6 col-md-4">.col-6 .col-md-4</div>
    <div class="col-6 col-md-4">.col-6 .col-md-4</div>
    <div class="col-6 col-md-4">.col-6 .col-md-4</div>
  </div>
    <div class="row">
    <div class="col-6">.col-6</div>
    <div class="col-6">.col-6</div>
  </div>
</div>
```
<img width="139" height="132" alt="image" src="https://github.com/user-attachments/assets/2eb704d1-ec02-4a27-a126-2835afb6c0bf" />

## 5.4. Text Style
Bootstrap menyediakan banyak class untuk mengatur style sebuah teks elemen HTML. Beberapa contohnya antara lain:
| Class | Keterangan |
|------|------------|
| `.text-left` | Mengatur teks menjadi rata kiri dalam sebuah elemen. |
| `.text-center` | Mengatur teks menjadi rata tengah dalam sebuah elemen. |
| `.text-right` | Mengatur teks menjadi rata kanan dalam sebuah elemen. |
| `.text-lowercase` | Mengatur seluruh teks pada elemen menjadi huruf kecil. |
| `.text-uppercase` | Mengatur seluruh teks pada elemen menjadi huruf besar. |
| `.text-capitalize` | Menjadikan huruf pertama besar untuk setiap kata pada sebuah elemen. |
| `.fw-bold` | Mengatur ketebalan huruf menjadi **bold**. |
| `.fw-light` | Mengatur ketebalan huruf menjadi **light**. |
| `.fw-normal` | Mengatur ketebalan huruf menjadi **normal**. |
| `.fst-italic` | Mengatur gaya teks menjadi miring (*italic*). |
| `.h1 s.d .h6` | Mengatur teks pada sebuah elemen agar tampil seperti tag **H1 sampai H6** pada HTML. |

## 5.5. Bootstrap Table, Image & Button
Bootstrap menyediakan class untuk pengaturan style elemen tabel, gambar dan tombol menjadi lebih
menarik.
a. Bootstrap Table
Tabel pada Bootstrap dipanggil dengan class .table secara default, namun ada beberapa class tambahan yang dapat didefinisikan pada elemen tabel yang lain berikut dapat dilihat pada Tabel:

| Class | Keterangan |
|------|------------|
| `.table-dark` | Membuat tampilan tabel memiliki latar belakang gelap. |
| `.thead-light` | Membuat elemen `<thead>` pada tabel memiliki latar belakang cerah. |
| `.thead-dark` | Membuat elemen `<thead>` pada tabel memiliki latar belakang gelap. |
| `.table-striped` | Membuat tampilan tabel memiliki latar belakang setiap row yang berbeda. |
| `.table-bordered` | Membuat tampilan tabel sederhana dengan border tipis. |
| `.table-hover` | Membuat tampilan tabel yang akan berubah warna latar belakang row saat didekati kursor. |
| `.table-sm` | Membuat tampilan tabel sederhana dengan ukuran padding yang minim. |

Contoh penerapannya sebagai berikut:
```
<!--Tabel Hover Style -->
<table class="table table-hover">
    <thead>
        <tr>
            <th scope="col">#</th>
            <th scope="col">Nama Lengkap</th>
            <th scope="col">Asal Kota</th>
            <th scope="col">Umur</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th scope="row">1</th>
            <td>Budi Rojadi</td>
            <td>Semarang</td>
            <td>35 th</td>
        </tr>
        <tr>
            <th scope="row">2</th>
            <td>Yulia Santi</td>
            <td>Bekasi</td>
            <td>32</td>
        </tr>
        <tr>
            <th scope="row">3</th>
            <td>Fahri Abdilah</td>
            <td>Medan</td>
            <td>38 th</td>
        </tr>
    </tbody>
</table>
```
<img width="549" height="133" alt="image" src="https://github.com/user-attachments/assets/2aa398e8-1c54-47c0-a061-6d9fad83dca7" />
<img width="550" height="125" alt="image" src="https://github.com/user-attachments/assets/7bb38873-f1d2-4649-b85e-a2bcac20a2cd" />

b. Bootstrap Image
Bootstrap dapat menangani desain gambar agar responsif pada setiap perangkat yang menampilkan
laman web. Dengan menambahkan class .img-fluid pada elemen tag <img> pada HTML maka gambar
yang didefinisikan pada laman web akan memiliki ukuran yang responsif menyesuaikan ukuran layar
perangkat. Class tersebut mengatur ukuran gambar dengan menyesuaikan ukuran dari parent element
sebagai wadah atau container elemen gambar. Terdapat class .thumbnail yang berguna menjadikan
gambar menjadi berukuran kecil dan sedikit memiliki border disekitarnya dapat dilihat pada gambar:

<img width="536" height="203" alt="image" src="https://github.com/user-attachments/assets/6b3bc2cc-44ac-41fb-88ae-23943141cdc6" />

```
<div class="container">
  <h2>Thumbnail & Fluid</h2>
  <img src="cinqueterre.jpg" class="img-thumbnail" alt="Cinque Terre" >
  <img src="cinqueterre.jpg" class="img-fluid" alt="Responsive image">
</div>
```
c. Bootstrap Button
Tampilan button pada elemen HTML dapat dirubah dengan menambahkan beberapa class untuk
button oleh Bootstrap. Bootstrap membuat tampilan button menjadi lebih menarik dan memberikan
user experience yang baik. Class yang digunakan secara default adalah .btn namun dengan disertai
class lain seperti berikut untuk memberikan perubahan warna dan ukuran button:

| Class | Keterangan |
|------|------------|
| `.btn-primary` | Membuat tampilan button dengan desain utama (primary). |
| `.btn-secondary` | Membuat tampilan button dengan desain secondary. |
| `.btn-danger` | Membuat tampilan button dengan desain berwarna merah. |
| `.btn-success` | Membuat tampilan button dengan desain berwarna hijau. |
| `.btn-warning` | Membuat tampilan button dengan desain berwarna kuning. |
| `.btn-info` | Membuat tampilan button dengan desain sebuah informasi. |
| `.btn-link` | Membuat tampilan button dengan desain seperti hyperlink. |
| `.btn-sm` | Membuat tampilan button berukuran small (kecil). |
| `.btn-lg` | Membuat tampilan button berukuran besar (large). |

Contoh penerapan class button:
```
<div class="container">
  <h4>Button Styles</h4>
  <button type="button" class="btn btn-secondary">Secondary</button>
  <button type="button" class="btn btn-primary btn-lg">Primary</button>
  <button type="button" class="btn btn-success w-100">Success</button>
  <button type="button" class="btn btn-info btn-sm">Info</button>
  <button type="button" class="btn btn-warning">Warning</button>
  <button type="button" class="btn btn-danger">Danger</button>
  <button type="button" class="btn btn-link">Link</button>
</div>
```
<img width="543" height="144" alt="image" src="https://github.com/user-attachments/assets/df8f1425-ddf2-438d-b313-e92356c57d49" />


## 5.6. Bootstrap Form
Bootstrap menyediakan perubahan elemen form pada HTML baik pada segi tata letak tampilan atau
tampilan antarmuka elemen-elemen dalam form. Class .form-control digunakan untuk sebagian besar
elemen input dalam tag <form> untuk memberikan styling yang konsisten. Ada beberapa cara untuk
mengatur tata letak tampilan form di Bootstrap:
1. Vertical Form (Default): Ini merupakan tampilan default saat tag form tidak didefinisikan class khusus. Setiap elemen form akan ditampilkan secara vertikal.
2. Inline Form: Untuk membuat form inline di Bootstrap, Anda dapat menggunakan utility classes
tertentu pada container form. Ini akan membuat elemen-elemen form berada dalam satu baris.
3. Horizontal Form: Untuk membuat form horizontal di Bootstrap, Anda dapat menggunakan sistem
grid Bootstrap. Gunakan class .row pada container dan .col-* untuk mengatur lebar kolom label
dan input.
```
<div class="container">
    <h3>Horizontal form</h3>
    <form action="/action_page.php">
        <div class="row mb-3">
            <label for="uname" class="col-sm-2 col-form-label">Username:</label>
            <div class="col-sm-10">
                <input type="text" class="form-control" id="uname" placeholder="Enter username" name="uname">
            </div>
        </div>
        <div class="row mb-3">
            <label for="pwd" class="col-sm-2 col-form-label">Password:</label>
            <div class="col-sm-10">
                <input type="password" class="form-control" id="pwd" placeholder="Enter
password" name="pwd">
            </div>
        </div>
        <div class="row">
            <div class="col-sm-10 offset-sm-2">
                <button type="submit" class="btn btn-success">Submit</button>
            </div>
        </div>
    </form>
</div>
```
<img width="362" height="150" alt="image" src="https://github.com/user-attachments/assets/850e4669-8bc0-4ab3-b312-9218b0edf153" />


# UNGUIDED (Buat halaman ramadan dan gunakan bootstrap (sebisa mungkin tanpa meggunakan native css full bootstap))
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
  </style>
</head>
<body style="font-family:'Lora',Georgia,serif;" style="background-color:#08101f;">

<!-- NAVBAR -->
<nav class="navbar navbar-expand-lg navbar-dark sticky-top border-bottom border-warning border-opacity-25"
     style="background-color:rgba(8,16,31,.95);backdrop-filter:blur(12px);">
  <div class="container">
    <a class="navbar-brand d-flex align-items-center gap-2 text-warning fw-semibold" href="#">
      <i class="bi bi-moon-stars-fill"></i>
      <span class="fs-5">رمضان مبارك</span>
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
         style="background: radial-gradient(ellipse 80% 60% at 50% 0%, rgba(13,110,94,.4) 0%, transparent 65%), #08101f;">
  <div class="container py-5 position-relative" style="z-index:1;">
    <div class="row align-items-center justify-content-between gy-5">

      <div class="col-lg-6 text-center text-lg-start">
        <span class="badge bg-warning bg-opacity-10 text-warning border border-warning border-opacity-25 rounded-pill px-3 py-2 mb-4 d-inline-block"
              style="letter-spacing:.2em;font-size:.7rem;">
          <i class="bi bi-stars me-1"></i>1447 HIJRIAH · 2025 MASEHI
        </span>

        <h1 class="text-warning mb-2 lh-1" style="animation:glow 4s ease-in-out infinite;"
            style="font-size:clamp(3rem,11vw,8.5rem);font-weight:700;">
          رَمَضَانُ مُبَارَك
        </h1>

        <p class="text-warning text-opacity-50 mb-4 fst-italic"
           style="letter-spacing:.3em;font-size:.8rem;">
          Ramadhānu Mubārak — Ramadan Berkah
        </p>

        <hr class="border-warning border-opacity-25 my-4">

        <p class="" style="color:#f0d9a8;" mb-4 lh-lg fs-6">
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

<!-- MARQUEE STRIP -->
<div class="overflow-hidden border-top border-bottom border-warning border-opacity-25 py-3 bg-warning bg-opacity-10">
  <span class="text-warning text-opacity-75" style="font-family:'Amiri',serif;animation:marquee 26s linear infinite;display:inline-block;white-space:nowrap;" style="font-size:1.1rem;letter-spacing:.4em;">
    سُبْحَانَ اللّٰهِ &nbsp;·&nbsp; الْحَمْدُ لِلّٰهِ &nbsp;·&nbsp; اَللّٰهُ أَكْبَرُ &nbsp;·&nbsp; لَا إِلٰهَ إِلَّا اللّٰهُ &nbsp;·&nbsp; اَسْتَغْفِرُ اللّٰهَ &nbsp;·&nbsp;
    سُبْحَانَ اللّٰهِ &nbsp;·&nbsp; الْحَمْدُ لِلّٰهِ &nbsp;·&nbsp; اَللّٰهُ أَكْبَرُ &nbsp;·&nbsp; لَا إِلٰهَ إِلَّا اللّٰهُ &nbsp;·&nbsp; اَسْتَغْفِرُ اللّٰهَ &nbsp;·&nbsp;
  </span>
</div>

<!-- JADWAL SHOLAT — Cilacap -->
<section id="sholat" class="py-5">
  <div class="container">
    <div class="text-center mb-5">
      <p class="text-warning text-opacity-50 text-uppercase mb-1" style="letter-spacing:.4em;font-size:.72rem;">
        <i class="bi bi-geo-alt me-1"></i>Cilacap, Jawa Tengah
      </p>
      <h2 class="fw-bold text-warning">Jadwal Sholat Hari Ini</h2>
      <p class="" style="color:#5ecfb8;" fst-italic small">Ahad, 8 Maret 2026 · 8 Ramadan 1447 H</p>
    </div>
    <div class="row g-3 justify-content-center">

      <!-- Imsak -->
      <div class="col-6 col-md-4 col-xl-2">
        <div class="h-100 bg-warning bg-opacity-10 border border-warning rounded-4 p-3 text-center d-flex flex-column align-items-center justify-content-center gap-2">
          <div class="bg-warning bg-opacity-25 rounded-circle d-flex align-items-center justify-content-center" style="width:46px;height:46px;">
            <i class="bi bi-moon-fill text-warning fs-5"></i>
          </div>
          <div class="text-warning fw-bold fs-5">04:10</div>
          <div class="" style="color:#5ecfb8;" text-uppercase" style="font-size:.7rem;letter-spacing:.15em;">Imsak</div>
          <span class="badge bg-warning text-dark rounded-pill" style="font-size:.6rem;">Sahur selesai</span>
        </div>
      </div>

      <!-- Subuh -->
      <div class="col-6 col-md-4 col-xl-2">
        <div class="h-100 border" style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important; rounded-4 p-3 text-center d-flex flex-column align-items-center justify-content-center gap-2">
          <div class="bg-success bg-opacity-25 rounded-circle d-flex align-items-center justify-content-center" style="width:46px;height:46px;">
            <i class="bi bi-sunrise text-success fs-5"></i>
          </div>
          <div class="text-warning fw-bold fs-5">04:20</div>
          <div class="" style="color:#5ecfb8;" text-uppercase" style="font-size:.7rem;letter-spacing:.15em;">Subuh</div>
        </div>
      </div>

      <!-- Dzuhur -->
      <div class="col-6 col-md-4 col-xl-2">
        <div class="h-100 border" style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important; rounded-4 p-3 text-center d-flex flex-column align-items-center justify-content-center gap-2">
          <div class="bg-success bg-opacity-25 rounded-circle d-flex align-items-center justify-content-center" style="width:46px;height:46px;">
            <i class="bi bi-sun text-success fs-5"></i>
          </div>
          <div class="text-warning fw-bold fs-5">11:52</div>
          <div class="" style="color:#5ecfb8;" text-uppercase" style="font-size:.7rem;letter-spacing:.15em;">Dzuhur</div>
        </div>
      </div>

      <!-- Ashar -->
      <div class="col-6 col-md-4 col-xl-2">
        <div class="h-100 border" style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important; rounded-4 p-3 text-center d-flex flex-column align-items-center justify-content-center gap-2">
          <div class="bg-success bg-opacity-25 rounded-circle d-flex align-items-center justify-content-center" style="width:46px;height:46px;">
            <i class="bi bi-sun-fill text-success fs-5"></i>
          </div>
          <div class="text-warning fw-bold fs-5">15:12</div>
          <div class="" style="color:#5ecfb8;" text-uppercase" style="font-size:.7rem;letter-spacing:.15em;">Ashar</div>
        </div>
      </div>

      <!-- Maghrib -->
      <div class="col-6 col-md-4 col-xl-2">
        <div class="h-100 bg-warning bg-opacity-10 border border-warning rounded-4 p-3 text-center d-flex flex-column align-items-center justify-content-center gap-2">
          <div class="bg-warning bg-opacity-25 rounded-circle d-flex align-items-center justify-content-center" style="width:46px;height:46px;">
            <i class="bi bi-sunset-fill text-warning fs-5"></i>
          </div>
          <div class="text-warning fw-bold fs-5">17:55</div>
          <div class="" style="color:#5ecfb8;" text-uppercase" style="font-size:.7rem;letter-spacing:.15em;">Maghrib</div>
          <span class="badge bg-warning text-dark rounded-pill" style="font-size:.6rem;">Buka puasa</span>
        </div>
      </div>

      <!-- Isya -->
      <div class="col-6 col-md-4 col-xl-2">
        <div class="h-100 border" style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important; rounded-4 p-3 text-center d-flex flex-column align-items-center justify-content-center gap-2">
          <div class="bg-success bg-opacity-25 rounded-circle d-flex align-items-center justify-content-center" style="width:46px;height:46px;">
            <i class="bi bi-moon-stars-fill text-success fs-5"></i>
          </div>
          <div class="text-warning fw-bold fs-5">19:05</div>
          <div class="" style="color:#5ecfb8;" text-uppercase" style="font-size:.7rem;letter-spacing:.15em;">Isya</div>
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
        <div class="h-100 border" style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important; rounded-4 p-4 d-flex flex-column gap-3">
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
        <div class="h-100 border" style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important; rounded-4 p-4 d-flex flex-column gap-3">
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
        <div class="h-100 border" style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important; rounded-4 p-4 d-flex flex-column gap-3">
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
        <div class="h-100 border" style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important; rounded-4 p-4 d-flex flex-column gap-3">
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
          <div class="border" style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important; rounded-4 overflow-hidden">
            <h2 class="accordion-header">
              <button class="accordion-button collapsed bg-transparent text-warning shadow-none gap-3 fw-semibold"
                      type="button" data-bs-toggle="collapse" data-bs-target="#d1">
                <i class="bi bi-moon text-warning fs-5"></i>Niat Puasa Ramadan
              </button>
            </h2>
            <div id="d1" class="accordion-collapse collapse" data-bs-parent="#doaAcc">
              <div class="accordion-body">
                <p class="text-warning text-end lh-lg mb-3" style="font-size:1.65rem;direction:rtl;">
                  نَوَيْتُ صَوْمَ غَدٍ عَنْ أَدَاءِ فَرْضِ شَهْرِ رَمَضَانَ هٰذِهِ السَّنَةِ لِلّٰهِ تَعَالَى
                </p>
                <hr class="border-warning border-opacity-25">
                <p class="fst-italic small mb-1" style="color:#5ecfb8;">"Nawaitu shauma ghadin 'an adā'i fardhi syahri Ramadhāna hādzihis sanati lillāhi ta'ālā."</p>
                <p class="" style="color:#f0d9a8;" small mb-0">Artinya: Saya niat berpuasa esok hari untuk menunaikan kewajiban Ramadan tahun ini karena Allah Ta'ala.</p>
              </div>
            </div>
          </div>
          <div class="border" style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important; rounded-4 overflow-hidden">
            <h2 class="accordion-header">
              <button class="accordion-button collapsed bg-transparent text-warning shadow-none gap-3 fw-semibold"
                      type="button" data-bs-toggle="collapse" data-bs-target="#d2">
                <i class="bi bi-sunset text-warning fs-5"></i>Doa Buka Puasa
              </button>
            </h2>
            <div id="d2" class="accordion-collapse collapse" data-bs-parent="#doaAcc">
              <div class="accordion-body">
                <p class="text-warning text-end lh-lg mb-3" style="font-size:1.65rem;direction:rtl;">
                  اَللّٰهُمَّ لَكَ صُمْتُ وَبِكَ آمَنْتُ وَعَلَى رِزْقِكَ أَفْطَرْتُ
                </p>
                <hr class="border-warning border-opacity-25">
                <p class="fst-italic small mb-1" style="color:#5ecfb8;">"Allāhumma laka shumtu wa bika āmantu wa 'alā rizqika afthartu."</p>
                <p class="" style="color:#f0d9a8;" small mb-0">Artinya: Ya Allah, untuk-Mu aku berpuasa, kepada-Mu aku beriman, dan dengan rezeki-Mu aku berbuka.</p>
              </div>
            </div>
          </div>
          <div class="border" style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important; rounded-4 overflow-hidden">
            <h2 class="accordion-header">
              <button class="accordion-button collapsed bg-transparent text-warning shadow-none gap-3 fw-semibold"
                      type="button" data-bs-toggle="collapse" data-bs-target="#d3">
                <i class="bi bi-stars text-warning fs-5"></i>Doa Lailatul Qadr
              </button>
            </h2>
            <div id="d3" class="accordion-collapse collapse" data-bs-parent="#doaAcc">
              <div class="accordion-body">
                <p class="text-warning text-end lh-lg mb-3" style="font-size:1.65rem;direction:rtl;">
                  اَللّٰهُمَّ إِنَّكَ عَفُوٌّ كَرِيمٌ تُحِبُّ الْعَفْوَ فَاعْفُ عَنِّي
                </p>
                <hr class="border-warning border-opacity-25">
                <p class="fst-italic small mb-1" style="color:#5ecfb8;">"Allāhumma innaka 'afuwwun karīmun tuhibbul 'afwa fa'fu 'annī."</p>
                <p class="" style="color:#f0d9a8;" small mb-0">Artinya: Ya Allah, Engkau Maha Pemaaf lagi Maha Mulia, Engkau menyukai maaf, maka maafkanlah aku.</p>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col-lg-5">
        <div class="h-100 border" style="background:rgba(18,136,112,.18);border-color:rgba(18,136,112,.45)!important; rounded-4 p-4 p-lg-5 d-flex flex-column justify-content-center align-items-center text-center gap-4">
          <i class="bi bi-quote text-warning opacity-25" style="font-size:3.5rem;line-height:1;"></i>
          <p class="text-warning lh-lg mb-0" style="font-size:clamp(1.3rem,2.5vw,1.65rem);direction:rtl;line-height:2.1;">
            شَهْرُ رَمَضَانَ الَّذِيْٓ اُنْزِلَ فِيْهِ الْقُرْاٰنُ
          </p>
          <hr class="border-warning border-opacity-25 w-25">
          <p class="" style="color:#f0d9a8;" fst-italic small lh-lg mb-0">"Bulan Ramadan adalah bulan yang di dalamnya diturunkan Al-Qur'an sebagai petunjuk bagi manusia."</p>
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
        <div class="text-warning fs-4">رَمَضَانُ مُبَارَك</div>
        <p class="" style="color:#5ecfb8;" mb-0 mt-1" style="font-size:.72rem;letter-spacing:.15em;">RAMADAN BERKAH · 1447 H</p>
      </div>
      <div class="col-md-4 text-center">
        <span class="text-warning text-opacity-40 fs-5">بِسْمِ اللّٰهِ</span>
        <p class="" style="color:#5ecfb8;" mb-0 mt-1" style="font-size:.7rem;">Dika Berbagi · Ramadhan Berkah</p>
      </div>
      <div class="col-md-4 d-flex justify-content-center justify-content-md-end align-items-center gap-3">
        <a href="#" class="text-warning text-opacity-75 fs-5"><i class="bi bi-instagram"></i></a>
        <a href="#" class="text-warning text-opacity-75 fs-5"><i class="bi bi-twitter-x"></i></a>
        <a href="#" class="text-warning text-opacity-75 fs-5"><i class="bi bi-youtube"></i></a>
      </div>
    </div>
  </div>
</footer>

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>

</body>
</html>
```
Output:
<img width="1893" height="964" alt="image" src="https://github.com/user-attachments/assets/5afae0c8-7925-4fde-a844-9a70a4b5e306" />
<img width="1904" height="961" alt="image" src="https://github.com/user-attachments/assets/f9762354-2ac8-46b4-8b31-497c7ae7daca" />




