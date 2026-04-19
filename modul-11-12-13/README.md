<div align="center">
  <br />

  <h1>LAPORAN PRAKTIKUM <br>
  APLIKASI BERBASIS PLATFORM
  </h1>

  <br />

  <h3>MODUL - 11-12-13<br>
  LARAVEL
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


# Dasar Praktikum
Buat project bisa menggunakan Laravel dimana kalian diminta membuat web inventari toko punya pak cik sama mas aimar (yang ga paham suki) dimana terdapat sebuah crud untuk mengelola produk, dengan tampilan seperti datatable, form create, form edit, dan konfirmasi modal untuk delete. Dan untuk data disimpan dalam database, gunakan database factory dan seeder (biar datanya ga kosong banget). dan buat nilai plus tambahkan dokumentasi project nya (bawaan ai juga udah ada pasti), please wok bantuin biar mas jakobi bisa belanja di toko nya mas aimar, jangan lupa terapin sistem login yaa (pake sistem session), #KingNasirPembantaiNgawiTimur

# Dasar Teori
## 1.1 Framework & MVC
Framework atau dalam Bahasa Indonesia dapat diartikan sebagai “kerangka kerja” merupakan kumpulan
dari fungsi-fungsi/prosedur-prosedur dan class-class untuk tujuan tertentu yang sudah siap digunakan 
sehingga bisa lebih mempermudah dan mempercepat pekerjaan seorang programmer, tanpa harus 
membuat fungsi atau class dari awal.

### 1.1.1 Pengenalan Laravel
Laravel adalah sebuah web application framework yang bersifat open-source yang digunakan untuk 
membangun aplikasi php dinamis. Laravel menjadi sebuah framework PHP dengan model MVC (Model, View, Controller) yang dapat mempercepat pengembang untuk membuat sebuah aplikasi web. Selain ringan dan cepat, Laravel juga memiliki dokumentasi yang lengkap disertai dengan contoh implementasi kodenya.

### 1.1.2 Cara Kerja Laravel

<p align="center"><img width="546" height="151" alt="image" src="https://github.com/user-attachments/assets/ff64b66a-ea12-4c57-9f13-13d2ec06455a" /></p>

Ketika suatu URL dibuka, maka file index.php akan dibaca. Di dalam file ini, Laravel memeriksa apakah URL tersebut terdaftar pada Routing yang sudah dibuat. Jika ada pemetaannya dan memenuhi Security (jika diharuskan, autentikasi misalnya) maka Laravel akan memanggil Controller sesuai yang dipetakan oleh Routing. Di dalam Controller semua logika back-end dieksekusi, lalu dapat mengembalikan View (tampilan) ke browser. Tampilan ini disimpan dalam Caching agar pemrosesan setelahnya lebih cepat

### 1.1.3 Routing
Pengaturan Routing berada pada file routes/web.php. Disini kita dapat mengatur pemetaan URL dengan aksi yang ingin kita lakukan. Method nya pun dapat diatur jika hanya untuk menerima method tertentu saja (post, get, atau yang lainnya). 

### 1.1.4 View
Secara default file tampilan pada Laravel menggunakan template engine, yaitu Blade. Sehingga, setiap file tampilan yang kita buat harus mengikuti penamaan namaview.blade.php dan diletakkan pada folder resources/views agar dapat di-load oleh fungsi view(). Penggunaan Blade juga menyediakan banyak directive yang sangat berguna terutama untuk looping data dan templating halaman agar kita tidak menulis kode yang sama berulang kali (biasanya header, menu samping, dan footer memiliki tampilan yang sama untuk tiap halaman). Secara isi, tampilan pada Laravel tetap menggunakan HTML, CSS, dan Javascript. Hal yang harus diperhatikan yaitu jika ingin menggunakan file eksternal CSS / Javascript, maka harus menggunakan fungsi {{ asset('path file di folder public’) }}, dan khusus untuk halaman yang berisi form dengan method selain GET maka harus menambahkan directive @csrf untuk keamanan pengiriman form. 

### 1.1.5 Controller
File Controller diletakkan pada folder app/Http/Controllers. Cara membuatnya bisa dengan cara 
pembuatan file manual dengan memperhatikan hal-hal berikut: meng-extend base Controller dari 
Laravel atau turunannya dan dituliskan namespace “App\Http\Controllers” agar dapat digunakan oleh 
file lain dan dipetakan dari Routing. Atau cara lain dengan perintah di command prompt / console / 
terminal.

## 1.2 CRUD
Pada modul ini kita akan membuat aplikasi yang dapat melakukan create, read, update, dan delete 
terhadap suatu data/tabel. Aplikasi yang akan kita bangun yaitu aplikasi e-commerce dimana kita akan fokus melakukan CRUD terhadap tabel produknya saja.

### 1.2.1 Konfigurasi dan Skema
Hal pertama yang harus dilakukan agar aplikasi dapat terhubung dengan database adalah mengatur 
konfigurasi koneksi. Secara detil, konfigurasi database berada pada file config/database.php. Tetapi untuk konfigurasi standar, kita dapat mengubahnya di file .env pada baris yang berisi 
DB_CONNECTION hingga DB_PASSWORD. Ubah nilainya dengan pengaturan yang kita inginkan.

Buat database bernama ecommerce di DBMS. Untuk membuat tabelnya, dapat dilakukan secara 
otomatis (di-generate) oleh Laravel dari command prompt / console / terminal dengan perintah.

File migrasi xxx_create_products_table.php akan terbuat pada folder database/migrations. Edit file 
ini pada fungsi Schema::create() untuk mendefinisikan kolom yang kita inginkan.

Untuk membuat tabel ke database dari skema ini, maka ketikkan perintah berikut pada command 
prompt / console / terminal:
```
php artisan migrate
```

### 1.2.2 Model
Laravel memberikan tiga cara untuk mengakses ataupun manipulasi data ke database: query langsung, query builder, dan ORM. Query langsung dan query builder menggunakan library Illuminate luminate\Support\Facades\DB) sedangkan ORM menggunakan Eloquent, yang merupakan kelas extend dari Illuminate. File Model diletakkan pada folder app/Models. Untuk membuat Model dalam Laravel, dapat dilakukan dengan manual dengan menambahkan namespace “App\Models” dan meng-extend kelas base Model dari Eloquent (Illuminate\Database\Eloquent\Model) ataupun di-generate oleh Laravel dari command prompt / console / terminal dengan perintah:
```
php artisan make:model Product
```

### 1.2.3 Controller
Setelah Model siap, kita tinggal memanggilnya pada Controller. Berikut kode lengkapnya dalam 
ProductController:
```
<?php

namespace App\Http\Controllers;

use App\Models\Product;
use Illuminate\Http\Request;

class ProductController extends Controller
{
    public function index()
    {
        $products = Product::all();

        return view('products.index', ['products' => $products]);
    }

    public function create()
    {
        return view('products.form', [
            'title'   => 'Tambah',
            'product' => new Product(),
            'route'   => route('products.store'),
            'method'  => 'POST',
        ]);
    }

    public function store(Request $request)
    {
        $validated = $request->validate([
            'name'  => 'required|min:4',
            'price' => 'required|integer|min:1000000',
        ]);

        Product::create($validated);

        return redirect()
            ->route('products.index')
            ->with('success', 'Produk berhasil ditambahkan');
    }

    public function show(Product $product)
    {
        return view('products.show', compact('product'));
    }

    public function edit(Product $product)
    {
        return view('products.form', [
            'title'   => 'Edit',
            'product' => $product,
            'route'   => route('products.update', $product),
            'method'  => 'PUT',
        ]);
    }

    public function update(Request $request, Product $product)
    {
        $validated = $request->validate([
            'name'  => 'required|min:4',
            'price' => 'required|integer|min:1000000',
        ]);

        $product->update($validated);

        return redirect()
            ->route('products.index')
            ->with('success', 'Produk berhasil diperbarui');
    }

    public function destroy(Product $product)
    {
        $product->delete();

        return redirect()
            ->route('products.index')
            ->with('success', 'Produk berhasil dihapus');
    }
}
```

### 1.2.4
Untuk tampilannya, buat file dengan nama index.blade.php yang diletakkan di folder
resources/views/product (folder product dibuat dahulu agar rapi).
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Daftar Produk</title>

    <link 
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" 
        rel="stylesheet"
    >
</head>
<body class="container">

    <div class="row justify-content-center mt-5">
        <div class="col-md-8">

            @if(session('success'))
                <div class="alert alert-success">
                    {{ session('success') }}
                </div>
            @endif

            <div class="d-flex justify-content-between align-items-center mb-3">
                <span>{{ session('msg') }}</span>
                <a href="{{ route('products.create') }}" class="btn btn-primary">
                    Tambah
                </a>
            </div>

            <table class="table table-bordered table-striped">
                <thead>
                    <tr>
                        <th>Nama</th>
                        <th>Harga</th>
                        <th>Aksi</th>
                    </tr>
                </thead>
                <tbody>
                    @foreach($products as $product)
                        <tr>
                            <td>{{ $product->name }}</td>
                            <td>{{ $product->price }}</td>
                            <td>
                                <a 
                                    href="{{ route('products.edit', $product->id) }}" 
                                    class="btn btn-sm btn-primary"
                                >
                                    Edit
                                </a>

                                <form 
                                    method="POST" 
                                    action="{{ route('products.destroy', $product->id) }}" 
                                    style="display:inline"
                                    onsubmit="return confirm('Yakin hapus?')"
                                >
                                    @csrf
                                    @method('DELETE')

                                    <button type="submit" class="btn btn-sm btn-danger">
                                        Hapus
                                    </button>
                                </form>
                            </td>
                        </tr>
                    @endforeach
                </tbody>
            </table>

        </div>
    </div>

    <script 
        src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js">
    </script>

</body>
</html>
```

Dan untuk tampilan form tambah dan edit, dapat dibuat satu halaman saja karena hampir sama. 
Hanya perlu tambahan pengkondisian di beberapa tempat.
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form {{ $title }} Produk</title>

    <link 
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" 
        rel="stylesheet"
    >
</head>
<body class="container">

    <div class="row justify-content-center mt-5">
        <div class="col-md-6">
            <h4>Form {{ $title }} Produk</h4>

            <form class="border p-4" method="POST" action="{{ $route }}">
                @csrf

                @if($method === 'PUT')
                    @method('PUT')
                @endif

                <div class="mb-3">
                    <label for="name" class="form-label">Nama</label>
                    <input 
                        type="text" 
                        name="name" 
                        id="name" 
                        class="form-control @error('name') is-invalid @enderror" 
                        value="{{ old('name', $product->name) }}"
                    >

                    @error('name')
                        <div class="invalid-feedback">
                            {{ $message }}
                        </div>
                    @enderror
                </div>

                <div class="mb-3">
                    <label for="price" class="form-label">Harga</label>
                    <input 
                        type="number" 
                        name="price" 
                        id="price" 
                        class="form-control @error('price') is-invalid @enderror" 
                        value="{{ old('price', $product->price) }}"
                    >

                    @error('price')
                        <div class="invalid-feedback">
                            {{ $message }}
                        </div>
                    @enderror
                </div>

                <div class="text-center">
                    <button type="submit" class="btn btn-success">
                        Simpan
                    </button>
                </div>
            </form>

        </div>
    </div>

    <script 
        src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js">
    </script>

</body>
</html>
```

## 1.3 Templating Halaman
Langkah pertama dalam templating adalah membuat file template-nya, yang dimiliki oleh tiap 
halaman. Untuk contoh kasus pada modul ini, kita membuat file template dengan nama template.blade.php dengan isi:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>@yield('title')</title>

    <link 
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" 
        rel="stylesheet"
    >

    <script src="{{ asset('js/jquery.min.js') }}"></script>

    <script 
        src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js">
    </script>
</head>
<body style="width: 95%;">
    @yield('content')
</body>
</html>
```

Directive @yield digunakan untuk menandakan bahwa di bagian itulah yang akan berbeda untuk tiap 
halamannya. Langkah selanjutnya adalah mengubah tampilan di tiap halaman seperti contoh 
index.blade.php di bawah ini:
```
@extends('template')

@section('title', 'Daftar Produk')

@section('content')
<div class="container">
    <div class="row justify-content-center mt-5">
        <div class="col-md-8">

            @if(session('success'))
                <div class="alert alert-success">
                    {{ session('success') }}
                </div>
            @endif

            <div class="d-flex justify-content-between align-items-center mb-3">
                <span>{{ session('msg') }}</span>

                <a href="{{ route('products.create') }}" class="btn btn-primary">
                    Tambah
                </a>
            </div>

            <table class="table table-bordered table-striped">
                <thead>
                    <tr>
                        <th>Nama</th>
                        <th>Harga</th>
                        <th>Aksi</th>
                    </tr>
                </thead>
                <tbody>
                    @foreach($products as $product)
                        <tr>
                            <td>{{ $product->name }}</td>
                            <td>{{ $product->price }}</td>
                            <td>
                                <a 
                                    href="{{ route('products.edit', $product->id) }}" 
                                    class="btn btn-sm btn-primary"
                                >
                                    Edit
                                </a>

                                <form 
                                    method="POST" 
                                    action="{{ route('products.destroy', $product->id) }}" 
                                    style="display:inline"
                                    onsubmit="return confirm('Yakin hapus?')"
                                >
                                    @csrf
                                    @method('DELETE')

                                    <button type="submit" class="btn btn-sm btn-danger">
                                        Hapus
                                    </button>
                                </form>
                            </td>
                        </tr>
                    @endforeach
                </tbody>
            </table>

        </div>
    </div>
</div>
@endsection
```
Directive @extend digunakan untuk menentukan file template mana yang digunakan oleh halaman
ini. Sedangkan directive @section digunakan untuk mengisi halaman sesuai dengan nama yield yang 
di-define dalam file template. Directive @section dapat diisi dengan string ataupun tag HTML.

## 1.4 Form Validation
Laravel dapat ditambahkan form validation dari sisi server. Di controller, sebelum kita memanggil 
fungsi untuk menambahkan (fungsi store) / mengubah (fungsi update).

## 1.5 Sessiom
Session memiliki fungsi menyimpan suatu variabel pada server dan variabel ini dapat diakses dan 
diubah dimanapun: Routing, Controller, ataupun halaman manapun. Session default pada Laravel 
dikelola sendiri oleh Laravel dan disimpan dalam bentuk file. Selain file, Session pada Laravel juga dapat diubah menjadi disimpan ke database atau menggunakan mekanisme lain. Laravel memiliki dua jenis Session, yaitu Session biasa dan Session flash. Session biasa akan selalu ada selama belum dihapus, time-out, atau browser ditutup. Sedangkan Session flash adalah session yang mhanya berlaku untuk satu request saja, setelah itu Laravel akan menghapusnya secara otomatis. Contoh Session flash sudah pernah kita gunakan melalui fungsi with(‘x’, y) yang digunakan bersamaandengan fungsi redirect.

## 1.6 Middleware
Middleware pada Laravel adalah suatu mekanisme untuk menyaring request yang masuk ke suatu 
Routing. Sebagai contoh, kita bisa membuat Middleware untuk memverifikasi apakah seorang user 
sudah terautentikasi atau memiliki hak akses untuk mengakses URL. Jika user belum terautentikasi 
atau tidak memiliki akses, maka Middleware dapat me-redirect user tersebut ke URL lain. Sebaliknya 
jika user terautentikasi atau memiliki hak akses, maka Middleware akan meneruskan request ke aksi 
yang dipetakan di Routing.
Middleware dapat melakukan hal lain selain untuk autentikasi, misalnya untuk menulis log atau error 
yang terjadi. Dan Middleware dapat kita atur mekanisme yang dilakukannya, yaitu bisa sebelum request diteruskan atau sesudah request diteruskan. Middleware yang kita buat harus berada di older app/Http/Middleware.

## 1.7 Model Relasi
Model Eloquent menyediakan fasilitas agar dua Model yang berelasi dapat langsung memanggil satu 
sama lain. Kita akan mencoba salah satunya yaitu relasi one to many, dengan menggunakan contoh 
kasus relasi Product dengan Variant. Tiap Product dapat memiliki banyak Variant, tetapi tiap Variant hanya dimiliki oleh satu Product.

# PENGERJAAN
## 1. Implementasi Setiap Fitur
##@ 1.1 Sistem Login (Session-Based)
Sistem login menggunakan mekanisme session bawaan Laravel. Setelah login berhasil, sesi pengguna disimpan dan setiap request berikutnya diverifikasi melalui middleware auth.

| Komponen                    | Keterangan                                                                 |
|----------------------------|----------------------------------------------------------------------------|
| AuthController::login()     | Validasi kredensial, memanggil `Auth::attempt()`, lalu `regenerate()` session |
| AuthController::logout()    | Invalidate session + regenerate CSRF token                                 |
| AuthController::register()  | Registrasi akun baru otomatis sebagai role `customer`                      |
| Middleware `auth`           | Melindungi semua route yang membutuhkan login                              |
| Middleware `role:admin`     | Hanya bisa diakses pengguna dengan role `admin`                            |
| Middleware `role:customer`  | Hanya bisa diakses pengguna dengan role `customer`                         |
| RoleMiddleware              | Custom middleware di `app/Http/Middleware/RoleMiddleware.php`              |

### 1.2 CRUD Produk
CRUD produk diimplementasikan menggunakan Laravel Resource Controller. Operasi delete menggunakan Soft Delete sehingga data tidak benar-benar terhapus dari database.

| Method | Route                       | Controller Method | Fungsi                                           |
|--------|-----------------------------|------------------|--------------------------------------------------|
| GET    | /admin/products             | index()          | Tampilkan DataTable semua produk + statistik     |
| GET    | /admin/products/create      | create()         | Tampilkan form tambah produk                     |
| POST   | /admin/products             | store()          | Validasi & simpan produk baru ke database        |
| GET    | /admin/products/{id}/edit   | edit()           | Tampilkan form edit produk yang dipilih          |
| PUT    | /admin/products/{id}        | update()         | Validasi & update data produk di database        |
| DELETE | /admin/products/{id}        | destroy()        | Soft delete produk (ada konfirmasi modal dulu)   |

Validasi form yang diterapkan pada create & edit:

| Field       | Rule Validasi                         | Keterangan                          |
|------------|----------------------------------------|-------------------------------------|
| name       | required \| string \| max:255          | Nama produk wajib diisi             |
| sku        | required \| string \| unique:products  | SKU harus unik di seluruh tabel produk |
| category   | required \| string \| max:100          | Kategori wajib diisi                |
| price      | required \| numeric \| min:0           | Harga minimal 0                     |
| stock      | required \| integer \| min:0           | Stok minimal 0                      |
| description| nullable \| string                     | Deskripsi boleh kosong              |

### 1.3 Tampilan DataTable
Tabel produk menggunakan plugin DataTables 1.13 dengan integrasi Bootstrap 5. Fitur yang aktif antara lain:

| Fitur DataTable        | Keterangan                                                                 |
|------------------------|----------------------------------------------------------------------------|
| Search / Pencarian     | Cari produk berdasarkan nama, SKU, atau kategori secara real-time          |
| Sorting per Kolom      | Klik header kolom untuk mengurutkan data (ascending/descending)            |
| Paginasi               | Navigasi halaman dengan pilihan jumlah baris per halaman (10/25/50)        |
| Info Data              | Menampilkan keterangan jumlah data yang sedang ditampilkan                 |
| Kolom Aksi             | Tombol Edit dan Hapus di setiap baris, kolom ini dikecualikan dari sorting |
| Bahasa Indonesia       | Label DataTable menggunakan bahasa Indonesia                               |

Kolom-kolom yang ditampilkan di DataTable:

| No | Kolom       | Isi                                                                 |
|----|------------|----------------------------------------------------------------------|
| 1  | Nama Produk | Nama + deskripsi singkat (jika ada)                                 |
| 2  | SKU         | Kode unik produk dalam format `code`                                |
| 3  | Kategori    | Badge berwarna biru muda                                             |
| 4  | Harga       | Format Rupiah (Rp xxx.xxx)                                           |
| 5  | Stok        | Angka berwarna: hijau (>10), kuning (1-10), merah (0)                |
| 6  | Status      | Badge: Tersedia / Menipis / Habis                                    |
| 7  | Aksi        | Tombol Edit (biru) dan Hapus (merah)                                 |

### 1.4 Database Factory & Seeder
Factory dan Seeder digunakan agar database tidak kosong saat pertama kali dijalankan. Cukup satu perintah: php artisan migrate --seed

| File                              | Menghasilkan         | Detail                                                                 |
|-----------------------------------|----------------------|------------------------------------------------------------------------|
| database/factories/UserFactory.php    | 10 user              | 3 akun tetap (Pak Cik, Mas Aimar, Mas Jakobi) + 7 customer acak        |
| database/factories/ProductFactory.php | 50 produk            | Nama & kategori realistis dari 8 kategori: Makanan, Elektronik, Pakaian, dll. |
| database/seeders/DatabaseSeeder.php   | Memanggil factory    | Mengorkestrasi semua factory, membuat akun tetap dengan password spesifik |

Akun yang dibuat oleh Seeder:

| Nama             | Email                 | Password   | Role     |
|------------------|----------------------|------------|----------|
| Pak Cik          | pakcik@tokoaimar.com  | pakcik123  | Admin    |
| Mas Aimar        | aimar@tokoaimar.com   | aimar123   | Admin    |
| Mas Jakobi       | jakobi@gmail.com      | jakobi123  | Customer |
| 7 Customer Acak  | (di-generate Faker)   | password   | Customer |

### 1.5 Fitur Belanja untuk Mas Jakobi
Mas Jakobi (dan customer lain) dapat berbelanja melalui halaman /shop setelah login. Keranjang belanja disimpan dalam session PHP.

| Halaman / Fitur       | URL                      | Keterangan                                     |
|-----------------------|--------------------------|------------------------------------------------|
| Katalog Produk        | /shop                    | Grid produk, filter kategori, pencarian        |
| Tambah ke Keranjang   | POST /cart/add/{product} | Input qty lalu klik Beli                       |
| Lihat Keranjang       | /cart                    | Daftar produk + ringkasan harga total          |
| Update Quantity       | PATCH /cart/{id}         | Ubah jumlah item di keranjang                  |
| Hapus Item            | DELETE /cart/{id}        | Hapus produk dari keranjang                    |
| Checkout              | POST /cart/checkout      | Order tersimpan, stok berkurang otomatis       |

### 1.6 Dokumentasi Project
Dokumentasi project tersedia dalam dua file yang disertakan langsung di dalam folder project:

| File       | Isi Dokumentasi                                                                                                      |
|------------|----------------------------------------------------------------------------------------------------------------------|
| README.md  | Fitur lengkap, struktur direktori project, skema database, tech stack, daftar artisan command, catatan pengembangan |
| INSTALL.md | Panduan instalasi step-by-step, konfigurasi `.env`, cara pakai MySQL, reset data, dan troubleshooting umum          |

## Struktur File Project
File-file utama yang dibuat dalam project ini:

| No | Path File                                     | Fungsi                                              |
|----|----------------------------------------------|-----------------------------------------------------|
| 1  | app/Http/Controllers/AuthController.php      | Login, logout, registrasi akun                      |
| 2  | app/Http/Controllers/ProductController.php   | CRUD produk lengkap untuk admin                     |
| 3  | app/Http/Controllers/ShopController.php      | Katalog produk untuk customer                       |
| 4  | app/Http/Controllers/CartController.php      | Keranjang belanja & checkout                        |
| 5  | app/Http/Middleware/RoleMiddleware.php       | Guard akses berdasarkan role                        |
| 6  | app/Models/User.php                          | Model pengguna + helper `isAdmin()`, `isCustomer()` |
| 7  | app/Models/Product.php                       | Model produk + SoftDeletes + scope `inStock()`      |
| 8  | app/Models/Order.php & OrderItem.php         | Model pesanan dan item pesanan                      |
| 9  | database/migrations/ (3 file)                | Buat tabel users, products, orders, order_items     |
| 10 | database/factories/ProductFactory.php        | Cetak 50 produk acak dari 8 kategori                |
| 11 | database/factories/UserFactory.php           | Cetak user acak dengan role customer                |
| 12 | database/seeders/DatabaseSeeder.php          | Isi database dengan data awal lengkap               |
| 13 | resources/views/layouts/app.blade.php        | Layout utama + sidebar navigasi                     |
| 14 | resources/views/layouts/auth.blade.php       | Layout halaman login & register                     |
| 15 | resources/views/auth/login.blade.php         | Form login + tampilan akun demo                     |
| 16 | resources/views/auth/register.blade.php      | Form registrasi akun customer baru                  |
| 17 | resources/views/products/index.blade.php     | DataTable produk + statistik + modal hapus          |
| 18 | resources/views/products/create.blade.php    | Form tambah produk baru                             |
| 19 | resources/views/products/edit.blade.php      | Form edit produk + tombol hapus                     |
| 20 | resources/views/shop/index.blade.php         | Katalog belanja (grid produk + filter)              |
| 21 | resources/views/shop/cart.blade.php          | Halaman keranjang belanja & checkout                |
| 22 | routes/web.php                               | Semua definisi route aplikasi                        |
| 23 | README.md                                    | Dokumentasi utama project                           |
| 24 | INSTALL.md                                   | Panduan instalasi & troubleshooting                 |

# Tampilan Web Toko
## Halaman Login & Sign Up

<p align="center"><img width="1916" height="969" alt="image" src="https://github.com/user-attachments/assets/505c8c12-2286-44c0-9bb2-e10ef667ecf6" /></p>

<p align="center"><img width="1919" height="966" alt="image" src="https://github.com/user-attachments/assets/9fef055d-4394-4b1b-9586-1fd5e2b117a4" /></p>

## Admin
### Dasboard Admin
<p align="center"><img width="1919" height="966" alt="image" src="https://github.com/user-attachments/assets/ff177190-8c54-4962-9b49-e8ee4d2dac83" /></p>

### Produk
<p align="center"><img width="1919" height="971" alt="image" src="https://github.com/user-attachments/assets/7486c768-5dac-472c-9b4e-257d75dcaece" /></p>

### Tambah Produk
<p align="center"><img width="1919" height="972" alt="image" src="https://github.com/user-attachments/assets/203ad13a-9e16-45c4-92cb-c08630fa743d" /></p>

### Edit Produk
<p align="center"><img width="1918" height="972" alt="image" src="https://github.com/user-attachments/assets/a4b4f571-1077-4b80-bcd4-e529b152516d" /></p>

### Hapus Produk
<p align="center"><img width="1919" height="970" alt="image" src="https://github.com/user-attachments/assets/8ac83930-8dac-44f5-a2de-bbde42112e2a" /></p>

## Customer
### Halaman Produk
<p align="center"><img width="1919" height="968" alt="image" src="https://github.com/user-attachments/assets/56dce6d9-47c9-4283-8e6a-d6bde4d94c06" /></p>

### Filtering Produk
<p align="center"><img width="1639" height="136" alt="image" src="https://github.com/user-attachments/assets/ffc36dc6-39c1-4f7a-9a92-09995471c469" /></p>

### Halaman CheckOut
<p align="center"><img width="1917" height="967" alt="image" src="https://github.com/user-attachments/assets/5ff30a5a-c9e4-4c23-8fe4-df291d663c52" /></p>
