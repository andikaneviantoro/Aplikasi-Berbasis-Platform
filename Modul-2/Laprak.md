<div align="center">
  <br />

  <h1>LAPORAN PRAKTIKUM <br>
  APLIKASI BERBASIS PLATFORM
  </h1>

  <br />

  <h3>MODUL 1 <br>
  GIT
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

## 2.1 Pengenalan Git
Git adalah salah satu sistem pengontrol versi (Version Control System) pada proyek perangkat lunak yang diciptakan oleh Linus Torvalds. Pengontrol versi bertugas mencatat setiap perubahan pada file proyek yang dikerjakan oleh banyak orang maupun sendiri. Git dikenal juga dengan distributed revision control (VCS terdistribusi), artinya penyimpanan database Git tidak hanya berada dalam satu tempat saja.

## 2.2 Instalasi Git
Disini saya sudah pernah install git 2.33.0.windows.2 dan saya melakukan pengecekan git pada CMD agar pasti sudah terinstall.
<p align="center"><img width="639" height="317" alt="image" src="https://github.com/user-attachments/assets/9ebedc04-119b-46e7-913b-1495b51156b3" /></p>
<p align="center">git sudah terinstall</p>

## 2.3 Penggunaan Git
### 2.3.1 Membuat repository
- Buka Github.com
  <img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/2bd7aa5b-e26a-42bd-8665-6efd29f30929" />
- Isi detail repository yang akan dibuat
  <img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/32a01f7b-6077-4205-b125-8d525b0523dc" />
- Klik "Create Repository"
- Jika sudah, akan muncul langkah-langkah untuk membuat repository dengan CMD
- Ikuti langkah-langkah seperti berikut
  <img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/b8ef50b7-76c9-403b-9a4d-900d3e2a45d9" />
- Berikut kode programnya
```
Microsoft Windows [Version 10.0.26100.7623]
(c) Microsoft Corporation. All rights reserved.

D:\MATKUL SEMS 6\PRAKTIKUM ABP\Buat Repo>git init
Initialized empty Git repository in D:/MATKUL SEMS 6/PRAKTIKUM ABP/Buat Repo/.git/

D:\MATKUL SEMS 6\PRAKTIKUM ABP\Buat Repo>git add .

D:\MATKUL SEMS 6\PRAKTIKUM ABP\Buat Repo>git commit -m "dika commit"
[master (root-commit) 73fc0b5] dika commit
 1 file changed, 1 insertion(+)
 create mode 100644 File dika.txt

D:\MATKUL SEMS 6\PRAKTIKUM ABP\Buat Repo>git branch -M main

D:\MATKUL SEMS 6\PRAKTIKUM ABP\Buat Repo>git remote add origin https://github.com/andikaneviantoro/Aplikasi-Berbasis-Platform.git

D:\MATKUL SEMS 6\PRAKTIKUM ABP\Buat Repo>git push -u origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 232 bytes | 232.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/andikaneviantoro/Aplikasi-Berbasis-Platform.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.

D:\MATKUL SEMS 6\PRAKTIKUM ABP\Buat Repo>
```
- Jika sudah, refresh halaman Github dan repository berhasil di buat
  <img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/116dfaaa-b31a-45db-bb9a-cd946ad2ce81" />

### 2.3.2 Clone Repository milik orang lain
Untuk dapat bekerja sama dengan orang lain, kita dapat melakukan cloning repositori orang lain, berikut ini caranya:
- Buka repositori yang akan di-clone pada Github, lalu klik tombol clone.
  <img width="975" height="527" alt="image" src="https://github.com/user-attachments/assets/ce68815a-a9af-4f4d-9ae1-bae1954bfb73" />
- Copy text yang muncul seperti dibawah ini, ini merupakan url dari repositori tujuan yang akan di clone.
  <img width="789" height="613" alt="image" src="https://github.com/user-attachments/assets/6a8e9d2b-6482-403f-af70-cb33dd92230b" />
- Buka command prompt dan ketikan perintah ini
  <img width="975" height="324" alt="image" src="https://github.com/user-attachments/assets/a3d9f8d5-f140-4939-9eaf-92a0fee54e9f" />

# UNGUIDED (Melakukan setup repository via CLI)
Sudah dilakukan dibagian atas pada dasar teori
