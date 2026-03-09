# <h1 align="center">LAPORAN PRAKTIKUM</h1>
### <p align="center">Aplikasi Berbasis Platform</p>

### <p align="center">Modul 3</p>
### <p align="center">HTML</p>

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

## 3.1. Pengennalan HTML
HTML atau HyperText Markup Language merupakan bahasa dasar yang digunakan untuk membangun
sebuah web dimana HTML menangani elemen-elemen dasar pada pembangunan sebuah website. Struktur
HTML paling dasar adalah sebagai berikut:
<p align="center"><img width="365" height="183" alt="image" src="https://github.com/user-attachments/assets/c5ef1ef4-0807-4321-ba16-d75b3e0f7cdf" /></p>

### 3.1.1. Tag HTML
Tag dalam HTML secara normal memiliki sepasang tag di mana tag pertama merupakan tag pembuka dan
yang kedua merupakan tag penutup. Konten yang ingin ditampilkan pada laman web diletakkan di antara kedua tag tersebut.

<p align="center"><nama_tag> letakkan konten di sini ... </nama_tag></p>

Tag dalam HTML tidak semuanya berbentuk pasangan, ada beberapa tag yang hanya berdiri sendiri seperti tag “<br/>” yang berguna untuk berpindah baris.

### 3.1.2. Elemen HTML
Elemen HTML merupakan tag HTML yang telah memiliki konten atau isi di antara kedua tag pembuka danpenutupnya. Elemen HTML dapat berupa teks atau juga dapat menyisipkan tag HTML lain pada elemen tersebut.
```
<!DOCTYPE html>
<html>

<head>
  <!-- Contoh elemen berisi tag lain -->
  <title>Page Title</title>
</head> asdff

<body>
  <h1>My First Heading</h1>
  <!-- Contoh Elemen berisi Teks -->
  <p>My first paragraph.</p>
</body>
</html>
```
### 3.1.3. Atribut HTML
Atribut HTML merupakan tambahan informasi dari sebuah tag HTML. Bentuk atribut untuk setiap tag HTML berbeda-beda sehingga kegunaan atribut juga berbeda seperti menambahkan informasi warna elemen, ukuran lebar, ukuran panjang dan lain-lain. Namun, mayoritas atribut yang sering muncul untuk setiap tag HTML adalah atribut “id” dan “class” karena kedua atribut ini berperan besar dalam pengembangan laman web dengan CSS dan JavaScript. Atribut HTML dideklarasikan di dalam tag pembuka pada setiap elemen HTML dengan format nama_atribut=”value”, setiap nilai atribut diapit oleh petik dua.
```
<a href=”www.google.co.id” > Google.co.id </a>
<input type=”button” id=”btnSubmit” class=”btnSubmit1” value=”Kirim”/>
```

## 3.2. Dasar Sintaks HTML
```
<!DOCTYPE html>
<html>

<head>
  <title>Page Title</title>
</head>

<body>
  <h1>My First Heading</h1>
  <p>My first paragraph.</p>
</body>

</html>
```
Seperti yang sudah dijelaskan sebelumnya struktur dasar HTML antara lain berupa:
• Deklarasi <! DOCTYPE html> mendefinisikan dokumen menjadi HTML5
• Elemen <html> adalah elemen dasar dari halaman HTML
• Elemen <head> berisi informasi meta tentang dokumen
• Elemen <title> menentukan judul untuk dokumen
• Elemen <body> berisi konten halaman yang terlihat

## 3.3. Heading
Heading pada HTML merupakan tag yang berguna untuk menampilkan judul dari konten laman web yang
dibangun. Heading dalam sebuah laman web berperan penting untuk aplikasi mesin pencarian karena
sistem mesin pencarian bekerja dengan menggunakan Heading laman web kita sebagai index pencarian. Dalam HTML terdapat enam tingkatan Heading di mana semakin kecil nilai heading nya maka semakin penting dan semakin besar ukurannya pada laman web.
```
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
```
<p align="center"><img width="310" height="329" alt="image" src="https://github.com/user-attachments/assets/79cede82-46e1-487d-a142-f9112c9d84b2" /></p>

## 3.4. Hyperlink
Hyperlink dalam HTML memungkinkan halaman web berpindah laman atau bernavigasi menuju laman web
yang lain. Tag yang digunakan adalah tag <a>...</a>
```
<a href="www.google.co.id"> Visit Google </a>
```
output:
<img width="394" height="104" alt="image" src="https://github.com/user-attachments/assets/a1f2aaf7-f0e1-40cf-9d1f-b4221cefceb7" />
Dalam tag Hyperlink pada HTML ada satu atribut yang harus digunakan agar konten yang ada di antara tag hyperlink berjalan dan dapat melakukan navigasi menuju laman web lain yaitu atribut href. Atribut ini bernilai url atau alamat dari laman web tujuan.

## 3.5. Tabel
Tabel pada HTML merupakan salah satu elemen penting khususnya digunakan untuk menampilkan data
yang membutuhkan bentuk tabel. Tabel pada HTML didefinisikan dengan tag <table></table> dengan setiap pendefinisian baris menggunakan tag <tr></tr>, pendefinisian heading tabel menggunakan tag <th></th> dan pendefinisian kolom menggunakan tag <td></td>.
```
<table width=”80%” height=”50%” border="1">
  <tr>
    <th>Nama Lengkap</th>
    <th>Kota Kelahiran</th>
    <th>Age</th>
  </tr>
  <tr>
    <td>Budi</td>
    <td>Jakarta</td>
    <td>35</td>
  </tr>
  <tr>
    <td>Andi</td>
    <td>Semarang</td>
    <td>52</td>
  </tr>

  <tr>
    <td>Rasyid</td>
    <td>Surabaya</td>
    <td>22</td>
  </tr>
</table>
```
<p align="center"><img width="664" height="279" alt="image" src="https://github.com/user-attachments/assets/28eda226-fc3c-4375-8a80-ab0e9aaafc51" /></p>
Dalam tabel HTML kita dapat melakukan operasi Merge Cell yang biasanya dapat dilakukan pada aplikasi perkantoran seperti Microsoft Word atau Excel dengan cara menambahkan atribut colspan dan rowspan pada tag pembuka kolom yaitu <td> nilai dari atribut tersebut berupa jumlah kolom atau baris yang akan digabungkan.
  
```
<table width=”80%” height=”50%” border="1">
    <tr>
        <th rowspan="2">Nama Lengkap</th>
        <th colspan="2">Gelar Pendidikan</th>
        <th rowspan="2">Age</th>
    </tr>
    <tr>
        <th> Sarjana </th>
        <th> Magister </th>
    </tr>
    <tr>
        <td>Budi</td>
        <td>S.Kom</td>
        <td>M.Sc</td>
        <td>35</td>
    </tr>
    <tr>
        <td>Andi</td>
        <td>S.SiKom</td>
        <td>M.T</td>
        <td>52</td>
    </tr>
</table>
```
<p align="center"><img width="777" height="303" alt="image" src="https://github.com/user-attachments/assets/96d3774f-5657-4de4-97c6-af8cca0f7e95" /></p>

## 3.6. Image
Menampilkan gambar pada halaman web merupakan sebuah improvisasi dalam pembuatan desain sebuah
web yang dapat memperindah tampilan website. Tag HTML yang digunakan adalah <img/> tag ini tidak
memiliki pasangan penutup maka dari itu diakhir tag pembuka ditambahkan garis miring seperti di atas. Terdapat satu atribut wajib yang harus ditambahkan seperti atribut href pada tag Hyperlink yaitu atribut src yang bernilai alamat direktori gambar disimpan.
```
<img src="wp (35).jpg" width="50%" height="50%"/>
<p>Ini Gambar Kincir Angin</p>
```
<p align="center"><img width="506" height="489" alt="image" src="https://github.com/user-attachments/assets/3f500a45-7ddf-400c-9ee2-ba03f84623b5" /></p>

## 3.7. Audio/ Video Elemen
Sebelum berkembangnya teknologi HTML5, untuk menyisipkan audio atau video, diperlukan sebuah plugin seperti Flash Player namun sekarang dengan HTML5 memiliki tag yang dapat menyisipkan audio atau video ke dalam laman web. Untuk audio menggunakan tag <audio> untuk tag pembuka dan <source> untuk memanggil url atau alamat direktori file. Sedangkan untuk video menggunakan tag <video>.
```
<audio controls>
    <source src="lagu.ogg" type="audio/ogg">
    <source src="lagu.mp3" type="audio/mpeg"> Your browser does not support the audio
    element.
</audio>
<video width="400" controls>
    <source src="task.mp4" type="video/mp4">
    <source src="task.ogg" type="video/ogg"> Your browser does not support HTML5
    video.
</video>
<p>
    Video courtesy of
    <a href="https://www.bigbuckbunny.org/" target="_blank">Big Buck Bunny</a>.
</p>
```
<p align="center"><img width="608" height="232" alt="image" src="https://github.com/user-attachments/assets/88bb8cec-ca4b-41e8-8c7a-7123ff1f3f59" /></p>

## 3.8. Form
Form pada HTML digunakan sebagai wadah untuk menampung dan mengumpulkan data-data dari
pengguna jika diperlukan untuk disimpan dalam sebuah database. Tag dasar untuk pemanggilan
form adalah <form> ... </form> dan diantara tag form tersebut merupakan tempat mendefinisikan
elemenelemen yang dibutuhkan form yang akan dibuat nantinya. Atribut utama dari tag form yaitu
action, atribut ini bernilai tujuan data akan diolah dengan bahasa pemrograman web saat tombol
“Submit” ditekan, selain itu atribut method yang hanya bernilai POST atau GET ini juga sangat dibutuhkan untuk pengolahan data dengan bahasa pemrograman web. Pembahasan lebih lanjut ada pada modul PHP.

### 3.8.1. Elemen Form
Elemen-elemen form pada html adalah sebagai berikut:
| Tag | Type | Fungsionalitas |
|-----|------|----------------|
| `<input/>` | `type="text"` | Menampilkan elemen untuk input data teks |
| `<input/>` | `type="password"` | Menampilkan elemen untuk input data password |
| `<input/>` | `type="email"` | Menampilkan elemen untuk input data email |
| `<input/>` | `type="radio"` | Menampilkan elemen untuk pemilihan data berbentuk radio |
| `<input/>` | `type="checkbox"` | Menampilkan elemen untuk pemilihan data berbentuk checkbox |
| `<input/>` | `type="submit"` | Menampilkan elemen tombol untuk pengolahan data form |
| `<select> <option> ... </option> </select>` | - | Menampilkan elemen untuk pemilihan data berbentuk dropdown list |
| `<textarea> ... </textarea>` | - | Menampilkan elemen untuk input data dalam bentuk paragraf panjang |
| `<button> ... </button>` | `type="button"` | Menampilkan elemen tombol |

### 3.8.2. Atribut Elemen Form
Atribut-atribut elemen form yang sering digunakan antara lain sebagai berikut:
| Atribut | Value | Fungsionalitas |
|--------|-------|----------------|
| `id` | Bebas | Menambahkan informasi ID dari elemen untuk kebutuhan CSS, JavaScript atau bahasa pemrograman web lainnya |
| `name` | Bebas | Menambahkan informasi Name dari elemen untuk kebutuhan JavaScript atau bahasa pemrograman web lainnya |
| `class` | Bebas | Menambahkan informasi Class dari elemen untuk kebutuhan CSS, JavaScript atau bahasa pemrograman web lainnya |
| `placeholder` | Bebas | Menampilkan informasi sementara tentang elemen sebelum pengguna memberikan input |
| `value` | Bebas | Memberikan nilai default pada elemen, khususnya pada elemen `input` dan `option` |
| `disabled` | - | Membuat elemen menjadi tidak dapat dioperasikan |
| `readonly` | - | Membuat elemen `input` tidak dapat diubah atau diberi input |
| `checked` | - | Membuat elemen `checkbox` atau `radio button` terpilih secara default |
| `selected` | - | Membuat elemen `option` pada tag `select` terpilih secara default |

```
<!DOCTYPE html>
<html lang="id">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulir Pendaftaran Praktikan</title>
</head>

<body>
    <center>
        <h2>Formulir Pendaftaran Praktikan</h2>
        <form action="#" method="POST">
            <table>
                <tr>
                    <td><label for="nama_id"><b>Nama:</b></label></td>
                    <td>:</td>
                    <td><input type="text" name="nama_input" id="nama_id" placeholder="Input Nama" value="Praktikan"
                            readonly></td>
                </tr>
                <tr>
                    <td><label for="uname_id"><b>Username:</b></label></td>
                    <td>:</td>
                    <td><input type="text" name="uname_input" id="uname_id" placeholder="Input Username"
                            value="Praktikum" disabled></td>
                </tr>
                <tr>
                    <td><label for="password_id"><b>Password:</b></label></td>
                    <td>:</td>
                    <td><input type="password" name="password_input" id="password_id" placeholder="Input Password"></td>
                </tr>
                <tr>
                    <td><label for="email_id"><b>Email:</b></label></td>
                    <td>:</td>
                    <td><input type="email" name="email_input" id="email_id" placeholder="Input Email"></td>
                </tr>
                <tr>
                    <td><b>Jenis Kelamin:</b></td>
                    <td>:</td>
                    <td>
                        <input type="radio" name="jk_input" id="pria" value="Pria">

                        <label for="pria">Pria</label>
                        <input type="radio" name="jk_input" id="wanita" value="Wanita">
                        <label for="wanita">Wanita</label>
                    </td>
                </tr>
                <tr>
                    <td><b>Hobi:</b></td>
                    <td>:</td>
                    <td>
                        <input type="checkbox" name="hobi_input" id="renang" value="Renang">
                        <label for="renang">Renang</label><br>

                        <input type="checkbox" name="hobi_input" id="bersepeda" value="Bersepeda">

                        <label for="bersepeda">Bersepeda</label><br>

                        <input type="checkbox" name="hobi_input" id="memancing" value="Memancing">
                        <label for="memancing">Memancing</label>
                    </td>
                </tr>
                <tr>
                    <td><label for="jp_id"><b>Jenjang Pendidikan:</b></label></td>
                    <td>:</td>
                    <td>
                        <select name="jp_input" id="jp_id">
                            <option value="" selected>------Pilih------</option>
                            <option value="D3">Tamat D3</option>
                            <option value="S1">Tamat S1</option>
                            <option value="S2">Tamat S2</option>
                            <option value="S3">Tamat S3</option>

                        </select>
                    </td>
                </tr>
                <tr>
                    <td><label for="kritik_saran"><b>Kritik & Saran:</b></label></td>
                    <td>:</td>
                    <td><textarea id="kritik_saran" name="kritik_saran" rows="5" cols="30"></textarea></td>
                </tr>
                <tr>
                    <td colspan="3" align="right">
                        <input type="button" value="Cancel" class="btn-cancel">
                        <input type="submit" value="Submit" class="btn-submit">

                    </td>
                </tr>
            </table>
        </form>
    </center>
</body>

</html>
```
<p align="center"><img width="605" height="505" alt="image" src="https://github.com/user-attachments/assets/1869a25b-0587-45a2-9d3d-e885ec38d8d6" /></p>


# UNGUIDED (Buat tampilan table dasar namun harus di tengah layar/center dan tidak boleh menggunakan css atau styling atau apapun itu.)
```
<!DOCTYPE html>
<html>
<head>
    <title>Tabel Data Mahasiswa</title>
</head>
<body>

<table width="100%" height="100%">
<tr>
<td align="center" valign="middle">

<h2>Data Mahasiswa</h2>

<table border="1">
    <tr>
        <th>No</th>
        <th>NIM</th>
        <th>Nama Mahasiswa</th>
        <th>Program Studi</th>
        <th>Angkatan</th>
    </tr>
    
    <tr>
        <td>1</td>
        <td>2311102167</td>
        <td>Andika Neviantoro</td>
        <td>Teknik Informatika</td>
        <td>2023</td>
    </tr>

    <tr>
        <td>2</td>
        <td>2311102191</td>
        <td>Fahreza Ilham Wicaksono</td>
        <td>Teknik Informatika</td>
        <td>2023</td>
    </tr>

    <tr>
        <td>3</td>
        <td>2311102198</td>
        <td>Andreas Besar Wibowo</td>
        <td>Teknik Informatika</td>
        <td>2023</td>
    </tr>

    <tr>
        <td>4</td>
        <td>2311102199</td>
        <td>Irshad Benaya Fardeca</td>
        <td>Teknik Informatika</td>
        <td>2023</td>
    </tr>

    <tr>
        <td>5</td>
        <td>2311102316</td>
        <td>Boutefhika Nuha Ziyadatul Khair</td>
        <td>Teknik Informatika</td>
        <td>2023</td>
    </tr>

</table>

</td>
</tr>
</table>

</body>
</html>
```
Output:
<img width="1919" height="978" alt="image" src="https://github.com/user-attachments/assets/43c62779-cf49-46ee-979a-5d7ceb928be0" />

