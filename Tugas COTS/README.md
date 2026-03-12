<div align="center">
  <br />

  <h1>LAPORAN PRAKTIKUM <br>
  APLIKASI BERBASIS PLATFORM
  </h1>

  <br />

  <h3>TUGAS COTS<br>
  WEB MANAJEMEN PRODUK "SPORTZONE"
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
Buatlah sebuah halaman web sederhana untuk menampilkan data produk. Pada halaman tersebut terdapat form input dan tabel data produk.
Ketentuan:
1. Gunakan Bootstrap untuk tampilan halaman.
2. Buat form input dengan data:
   * Nama Produk
   * Kategori
   * Harga
4. Data yang diinput dari form harus ditampilkan pada tabel.
5. Gunakan JQuery Datatable pada tabel.
6. Tambahkan tombol hapus pada setiap data di tabel.
7. Pastikan tabel memiliki fitur search dan pagination.
8. Bikin crud sederhana dengan sistem penyimpanan dengan mapping object
  
Output:
* Halaman memiliki form input produk
* Data yang dimasukkan muncul di tabel
* Tabel menggunakan Datatable
* Tampilan menggunakan Bootstrap


# PENGERJAAN
## 1.1 Penggunaan Bootstrap untuk Halaman
Website ini dibangun menggunakan Bootstrap 5.3.2 sebagai framework CSS utama. Bootstrap --digunakan untuk beberapa komponen, seperti:
- Sistem grid layout (`.main-grid` dengan dua kolom)
- Komponen form (`form-control`, `form-select`, `input-group`)
- Utility classes (`mb-3`, `mb-4`, `d-flex`, `gap-2`, `flex-grow-1`, `mt-3`)
- Responsive design (breakpoint 900px untuk mobile)

Bukti kodenya:
```
<link href="https://cdnjs.cloudflare.com/ajax/libs/bootstrap/5.3.2/css/bootstrap.min.css" rel="stylesheet"/>
<script src="https://cdnjs.cloudflare.com/ajax/libs/bootstrap/5.3.2/js/bootstrap.bundle.min.js"></script>
```

## 1.2 Form Input dengan Data
Form input terdapat di panel kiri halaman dengan 3 field wajib:
| Field        | Tipe Input          | Keterangan                                                                 |
|--------------|---------------------|----------------------------------------------------------------------------|
| Nama Produk  | text                | Input bebas untuk memasukkan nama produk                                  |
| Kategori     | select (dropdown)   | Pilihan: Sepatu, Pakaian, Perlengkapan, Aksesoris, Lainnya                |
| Harga        | number              | Input angka untuk harga produk, dilengkapi prefix **"Rp"** menggunakan input-group |

Bukti inputan manual pada program:
```
<input type="text" id="inputNama" class="form-control" placeholder="cth. Nike Air Zoom Pegasus"/>

<select id="inputKategori" class="form-select">
  <option value="Sepatu">Sepatu</option>
  ...
</select>

<div class="input-group">
  <span class="input-group-text">Rp</span>
  <input type="number" id="inputHarga" class="form-control" placeholder="0" min="0"/>
</div>
```
Tampilan Form (Sebelum diisi & setelah diisi)
<p align="center"><img width="452" height="457" alt="image" src="https://github.com/user-attachments/assets/bdbad418-e328-46c6-9458-84cca20374bf" /></p>
<p align="center"><img width="409" height="462" alt="image" src="https://github.com/user-attachments/assets/114c274b-4a96-4d1e-b560-73ee7f111fd6" /></p>

## 1.3 Inputan Data pada Tabel
Setiap data yang disubmit melalui form langsung ditambahkan ke tabel secara dinamis menggunakan JavaScript. Tabel menampilkan kolom: ID, Nama Produk, Kategori, Harga, Tanggal Ditambahkan, dan Aksi.
Bukti kode:
```
function addProduct(nama, kategori, harga, toast=true) {
    const id = nextId++;
    const now = new Date().toLocaleDateString('id-ID', ...);
    const product = { id, nama, kategori, harga, createdAt: now };
    productStore[id] = product;
    dt.row.add(buildRow(product)).draw(false); // ← data langsung masuk tabel
    updateStats();
}
```
- Pengisian data baru
  <p align="center"><img width="397" height="463" alt="image" src="https://github.com/user-attachments/assets/6d396531-dd80-44bd-b420-44e159b12565" />
</p>

- Data akan muncul di baris pertama pada tabel
<p align="ceneter"><img width="937" height="584" alt="image" src="https://github.com/user-attachments/assets/df68d72e-bb07-4904-b63d-7706f1feb862" />
</p>

## 1.4 Penggunaan Jquery Datatable pada tabel
Tabel produk diinisialisasi menggunakan jQuery DataTable 1.10.21 yang terintegrasi dengan Bootstrap 5. Berikut konfigurasi yang digunakan:
| Opsi        | Nilai               | Fungsi                                   |
|-------------|--------------------|-------------------------------------------|
| pageLength  | 5                  | Default menampilkan 5 baris data          |
| lengthMenu  | [5, 10, 25, 50]    | Pilihan jumlah baris yang ditampilkan     |
| order       | [[0, 'desc']]      | Urut by ID descending                     |
| language    | id-ID              | Menggunakan bahasa Indonesia              |

Bukti kode:
.Js
```
dt = $('#productTable').DataTable({
    pageLength: 5,
    lengthMenu: [5, 10, 25, 50],
    order: [[0, 'desc']],
    language: {
        search: "Cari:",
        lengthMenu: "Tampilkan _MENU_ produk",
        ...
    }
});
```
.html
```
<link href=".../dataTables.bootstrap5.min.css" rel="stylesheet"/>
<script src=".../jquery.dataTables.min.js"></script>
<script src=".../dataTables.bootstrap5.min.js"></script>
```
Tampilan:
<p align="center"><img width="357" height="510" alt="image" src="https://github.com/user-attachments/assets/0f25d852-5170-406b-8bcd-698bf0ca507e" /></p>

## 1.5 Tambah Button Hapus pada Setiap Data
Setiap baris tabel memiliki dua tombol aksi di kolom "Aksi": tombol Edit (kuning) dan tombol Hapus (oranye/merah). Klik tombol Hapus akan memunculkan konfirmasi, lalu menghapus data dari `productStore` dan menghapus baris dari DataTable secara real-time.

Bukti kode:
```
function actionBtns(id) {
    return `<div class="action-btns">
      <button class="btn-edit-row" data-id="${id}"><i class="fa fa-pen"></i></button>
      <button class="btn-del-row"  data-id="${id}"><i class="fa fa-trash"></i></button>
    </div>`;
}

function deleteProduct(id) {
    if (!confirm(`Hapus produk "${p.nama}"?`)) return;
    delete productStore[id];             // hapus dari mapping object
    dt.rows(...).remove().draw();        // hapus dari tabel
    updateStats();
}
```

- Tombol Edit dan Hapus
  <p align="center"><img width="873" height="121" alt="image" src="https://github.com/user-attachments/assets/06cc399a-683f-4e22-a58e-d055156210db" /></p>
  
- Konfirmasi hapus data
  <p align="center"><img width="1904" height="926" alt="image" src="https://github.com/user-attachments/assets/cd228755-6bb0-41da-9a43-bef0568bb26f" /></p>

## 1.6 Fitur Search dan Pagination
Fitur search pada web ini, dapat memfilter data secara real-time berdasarkan semua kolom — nama produk, kategori, harga, maupun tanggal. Sedangkan Pagination dibawah tabel terdapat navigasi halaman dengan tombol `<` (Previous) dan `>` (Next). Dropdown di kiri atas tabel memungkinkan user memilih jumlah data per halaman (5 / 10 / 25 / 50).

Bukti kode:
```
language: {
    search: "Cari:",
    lengthMenu: "Tampilkan _MENU_ produk",
    info: "Menampilkan _START_–_END_ dari _TOTAL_ produk",
    paginate: { previous: "‹", next: "›" }
}
```

- Fitur search
  Dapat mencari berdasarkan semua kolom
  <p align="center"><img width="882" height="148" alt="image" src="https://github.com/user-attachments/assets/518ecbfd-5a2b-49bf-9692-044d3daee853" /></p>
  <p align="center"><img width="885" height="217" alt="image" src="https://github.com/user-attachments/assets/5d32ca1d-11fc-4cfe-9444-627e3d853e6a" /></p>
  <p align="center"><img width="885" height="148" alt="image" src="https://github.com/user-attachments/assets/5e756318-be12-4b73-8b7b-8fc3690e7a02" /></p>
  <p align="center"><img width="883" height="403" alt="image" src="https://github.com/user-attachments/assets/8ce90821-1024-4960-aeda-0e26e9564fd4" /></p>
  
- Tombol pagination
  <p align="center"><img width="203" height="51" alt="image" src="https://github.com/user-attachments/assets/636770db-51ff-4532-baad-bf8c538a8bb5" /></p>
  <p align="center"><img width="210" height="55" alt="image" src="https://github.com/user-attachments/assets/eff33d51-1bf2-4cf3-b05b-32b5422362f2" /></p>


## 1.7 CRUD sederhana dengan mapping Object
Sistem penyimpanan data menggunakan JavaScript object sebagai mapping object dengan `id` sebagai key. Semua operasi CRUD (Create, Read, Update, Delete) Diterapkan pada object ini.

.js
```
let productStore = {};  // Mapping Object utama
let nextId = 1;         // Auto-increment ID
```

| Operasi | Fungsi | Cara Kerja |
|--------|--------|-----------|
| Create | `addProduct()` | Menambahkan produk baru ke dalam penyimpanan dengan `productStore[id] = product` |
| Read | `buildRow()` + DataTable | Mengambil data dari `Object.values(productStore)` lalu menampilkannya ke tabel |
| Update | `updateProduct()` | Memperbarui data produk seperti `productStore[id].nama = nama` dan field lainnya |
| Delete | `deleteProduct()` | Menghapus data produk dari penyimpanan dengan `delete productStore[id]` |

Alur CRUD:
```
// CREATE
productStore[id] = { id, nama, kategori, harga, createdAt };

// READ
const all = Object.values(productStore);

// UPDATE
p.nama = nama; p.kategori = kategori; p.harga = harga;

// DELETE
delete productStore[id];
```
Fitur tambahan (Mode Edit):
Saat tombol Edit ditekan, form beralih ke "Mode Edit Aktif" (ditandai indikator oranye), field terisi data lama, dan tombol berubah menjadi "Update Produk". Setelah disimpan, data di tabel langsung diperbarui tanpa reload.

Tampilan:
- Create
  <p align="center"><img width="1904" height="875" alt="image" src="https://github.com/user-attachments/assets/08e6ee93-d6d8-465b-8e95-892815b0df48" /></p>
  Berhasil dibuat:
  <p align="center"><img width="1902" height="866" alt="image" src="https://github.com/user-attachments/assets/410f52fd-1cd9-4f2e-bb4d-b84284a1cb9b" /></p>

- Read
  <p align="center"><img width="400" height="118" alt="image" src="https://github.com/user-attachments/assets/b2a840bd-1f6d-452f-90ad-5b077cdbde38" /></p>

- Update
  <p align="center"><img width="1903" height="865" alt="image" src="https://github.com/user-attachments/assets/ba94ca34-443c-4bb9-9c2d-9cafb2f45011" /></p>
  Berhasil di Edit:
  <p align="center"><img width="1905" height="868" alt="image" src="https://github.com/user-attachments/assets/bacecd50-4c09-4ea9-b2d2-19a6f0cf6eaf" /></p>
  
- Delete
  <p align="center"><img width="1903" height="913" alt="image" src="https://github.com/user-attachments/assets/4adc8d8c-da41-4e5c-a4e1-0d357e6afc66" /></p>
  Berhasil di Hapus:
  <p align="center"><img width="1904" height="871" alt="image" src="https://github.com/user-attachments/assets/56d5cbd4-65e6-4d43-8e39-7a798d0aa0c9" /></p>

# Output (Tampilan Full Web)
Deskripsi Web SportZone:
Pada form tambah produk terdapat 3 kotak pengisian (nama produk, kategori, harga) dan button untuk menyimpan produk. Sedangkan pada form daftar produk berisi semua data produk yang telah ditambahkan. Terdapat beberapa fitur seperti menampilkann jumlah list data yang ditampilkan, pagination, fitur search untuk mencari data produk sesuai kolom yang dicari, Serta fitur edit dan hapus data untuk masing-masing data, dan fitur hapus keseluruhan data juga terdapat di form ini. Yang terakhir ada Dashboard Cards, berisi ringkasan statistik yang menampilkan total produk, jumlah kategori, dan total nilai inventaris secara real-time, nilainya otomatis terupdate setiap kali produk ditambah, diedit, atau dihapus. 
<p align="center"><img width="1901" height="872" alt="image" src="https://github.com/user-attachments/assets/0d40eba3-b448-4ded-bd58-ce28f52ddd95" /></p>

