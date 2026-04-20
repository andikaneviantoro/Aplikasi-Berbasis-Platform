<div align="center">
  <br />

  <h1>LAPORAN PRAKTIKUM <br>
  APLIKASI BERBASIS PLATFORM
  </h1>

  <br />

  <h3>UTS<br>
  WEB PROFILE & DASBOARD PENGELOLA
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


# Soal UTS
membuat web portofolio dimana layaknya web portofolio pasti ada:
- landing page buat nampilin skill dan data diri kalian
- tambahin fitur login dan terdapat dashboard khusus admin buat ngerubah konten dari portofolio yang kalian tampilin: misal deskripsi, foto, skill, dan data lain nya bisa dirubah dari dashboard admin (mungkin create, edit).
- untuk ketentuan pertama jelas harus pake laravel
- untuk styling dibebasin, boleh tailwind boleh yang lain
- lalu system nya wajib pake ajax. Otomatis data ga bisa ditampilin langsung ya, harus fetch data ke backend dulu buat ngambil informasi kalian skill dan data diri.

# Dasar Teori
Website portfolio ini dibuat menggunakan Laravel sebagai framework utama, dengan konsep landing page yang menampilkan data diri dan skill secara dinamis. Sistemnya menggunakan metode AJAX sehingga seluruh informasi seperti deskripsi, foto profil, skill, dan data pendukung lainnya tidak itampilkan secara statis, melainkan di-fetch terlebih dahulu dari backend sebelum ditampilkan ke halaman. elain itu, website ini juga dilengkapi fitur login dan dashboard admin yang memungkinkan admin untuk engelola konten portfolio, seperti menambahkan (create) dan mengubah (edit) informasi sesuai ebutuhan. Untuk tampilan antarmuka, styling dibebaskan menggunakan framework seperti Tailwind CSS, Bootstrap, atau metode lainnya sesuai kreativitas pengembang.

# PENGERJAAN
## Tampilan & Fitur
## 1.1 Landing Page
<p align="center"><img width="1901" height="909" alt="image" src="https://github.com/user-attachments/assets/963c894f-5960-42f3-901d-37d7e3cc7114" /></p>

Pada Menu navbar, berisikan About, Education, Skills, Portfolio, Github, Contact, dan Login Admin.
Dimana saat di klik, tampilan akan mengarah ke bagian yang dituju.

## 1.2 Profile
<p align="center"><img width="928" height="655" alt="image" src="https://github.com/user-attachments/assets/52110632-9df9-42cc-818f-716812917666" /></p>

Terdapat Identitas diri dan deskripsi singkat, status label, dan foto profile

## 1.3 About Me
<p align="center"><img width="937" height="574" alt="image" src="https://github.com/user-attachments/assets/3e2beff1-5644-4531-88ea-d4acb3ca93d7" /></p>

Deskripsi diri serta terdapat tambahan penggunaan API quote dan cuaca

## 1.4 Education
<p align="center"><img width="940" height="426" alt="image" src="https://github.com/user-attachments/assets/159cf789-4c20-49fe-aa43-d2097e131ddd" /></p>

Riwayat pendidikan dari jenjang sekolah menengah hingga saat ini sarjana

## 1.5 Skills
<p align="center"><img width="942" height="622" alt="image" src="https://github.com/user-attachments/assets/469de8b9-0b03-455a-a6b8-bbda6345e868" /></p>

Berisi skills yang dikuasai atau pernah dipelajari

## 1.6 Portfolio
<p align="center"><img width="933" height="461" alt="image" src="https://github.com/user-attachments/assets/7aa9635c-82c3-45ec-a4ee-0a2246fd405e" /></p>

Portfolio yang pernah dikerjakan

## 1.7 Github
<p align="center"><img width="934" height="738" alt="image" src="https://github.com/user-attachments/assets/3aaf4415-2bcf-4840-a4aa-b023dbcbe8bc" /></p>

Menggunakan pemanggilan API Github untuk menampilkan profile github dan repository

## Contact
<p align="center"><img width="941" height="383" alt="image" src="https://github.com/user-attachments/assets/717f6871-abc9-43f0-8443-995f1c4bef62" /></p>

Kontak person saya

## Login Admin
<p align="center"><img width="1918" height="912" alt="image" src="https://github.com/user-attachments/assets/7595e184-d1f7-4dba-8455-58706ea3fc36" /></p>

Login dengan input email yang sudah dibuat pada database.

*Email: admin@portfolio.com*

*Password: password123*

## Dasboard Admin (pengelolaan data)
<p align="center"><img width="1919" height="909" alt="image" src="https://github.com/user-attachments/assets/c772f913-8240-4e09-a802-5a18ef6bbfba" /></p>

Terdapat detail jumlah data yang ditampilkan pada web profile. Menu aksi cepat atau shourtcut untuk memudahkan pengguna tertuju ke menu lain.

## Edit Profile
<p align="center"><img width="1918" height="911" alt="image" src="https://github.com/user-attachments/assets/b8b2820f-1e00-42fc-9269-5b4524fb8ab3" /></p>

Ubah foto profil, dan ubah informasi data diri.

## Kelola data skill
<p align="center"><img width="1919" height="907" alt="image" src="https://github.com/user-attachments/assets/45b40c44-7714-4b61-afdc-bf3fab8d15b2" /></p>
<p align="center"><img width="1919" height="913" alt="image" src="https://github.com/user-attachments/assets/eb898ada-5ec7-4ccd-b5a2-95e1a9a2255c" /></p>
<p align="center"><img width="1919" height="905" alt="image" src="https://github.com/user-attachments/assets/4dae15f5-3fe3-4b14-841d-5cff8fb84545" /></p>

Dapat menambah, mengubah, dan menghapus data skill

## Kelola data Pendidikan
<p align="center"><img width="1919" height="909" alt="image" src="https://github.com/user-attachments/assets/a17b740c-8719-4578-8a00-36c67026ae7b" /></p>

Sama juga seperti menu data skill, fitur ini dapat mengelola data pendidikan

## Kelola data Project
<p align="center"><img width="1919" height="910" alt="image" src="https://github.com/user-attachments/assets/81414b42-aaff-4a1b-acf0-1d6b26ea376d" /></p>

Mengelola semua data project

## Mengelola Kontak
<p align="center"><img width="1919" height="913" alt="image" src="https://github.com/user-attachments/assets/871b8a13-17df-459b-a423-fce2b81245dc" /></p>
<p align="center"><img width="1919" height="909" alt="image" src="https://github.com/user-attachments/assets/cc3735f7-5847-495f-9852-0d0fc3e6b094" /></p>

Dapat mengelola kontak, melampirkan url link, serta dapat memilih warna baghround dan icon.


# *THANKS FOR UTS KEBUT SEMALEMNYA...:)*
