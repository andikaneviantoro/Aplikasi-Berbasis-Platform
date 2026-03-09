# <h1 align="center">LAPORAN PRAKTIKUM</h1>
### <p align="center">Algoritma Pemrograman</p>

### <p align="center">Modul 2</p>
### <p align="center">Git</p>

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

## Pengenalan Git
Git adalah salah satu sistem pengontrol versi (Version Control System) pada proyek perangkat lunak yang diciptakan oleh Linus Torvalds. Pengontrol versi bertugas mencatat setiap perubahan pada file proyek yang dikerjakan oleh banyak orang maupun sendiri. Git dikenal juga dengan distributed revision control (VCS terdistribusi), artinya penyimpanan database Git tidak hanya berada dalam satu tempat saja.

## Instalasi Git
Disini saya sudah pernah install git 2.33.0.windows.2 dan saya melakukan pengecekan git pada CMD agar pasti sudah terinstall.
<p align="center"><img width="639" height="317" alt="image" src="https://github.com/user-attachments/assets/9ebedc04-119b-46e7-913b-1495b51156b3" /></p>
<p align="center">git sudah terinstall</p>

## Penggunaan Git
### Membuat repository
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




