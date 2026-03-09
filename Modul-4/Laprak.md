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

## 4.1. Pengenalan CSS
Cascading Style Sheets (CSS) merupakan bahasa yang membantu memperindah tampilan dari laman web
yang telah dibangun dengan HTML. CSS mendeskripsikan bagaimana bentuk tampilan elemen HTML
seharusnya saat ditampilkan pada laman browser. Format penulisan CSS secara umum ditunjukkan pada gambar berikut.
<p align="center"><img width="535" height="128" alt="image" src="https://github.com/user-attachments/assets/df433055-5c6b-4d6c-bf36-f5926f428a57" /></p>
Selector merupakan elemen HTML yang akan ditambahkan CSS kemudian diikuti dengan declaration block yang terdiri dari property elemen yang akan dirubah beserta value dari property-nya. Setiap deklarasi selector dapat merubah banyak nilai property sekaligus dengan dipisahkan dengan titik koma dan untuk semua declaration block dari satu selector berada di antara kurung kurawal.

### 4.1.1. CaRa Menyisipkan CSS
Terdapat tiga cara untuk menyisipkan atau mendefinisikan CSS ke dalam HTML, antara lain:
a. External Style Sheet
Eksternal Style Sheet merupakan cara menyisipkan atau mendefinisikan CSS ke dalam HTML dengan
memanggil file dengan ekstensi .css ke dalam file HTML. Pemanggilannya diletakkan di antara elemen <head></head> dengan menggunakan tag <link/>.
```
<head>
<link rel="stylesheet" type="text/css" href="myStyleSheet.css">
</head>
```
b. Internal Style Sheet
Internal Style Sheet merupakan cara menyisipkan atau mendefinisikan CSS ke dalam HTML dengan
menggunakan tag <style> </style> pada elemen <head></head>. Biasanya digunakan ketika satu
laman membutuhkan style CSS yang berbeda dari yang telah dipanggil pada Eksternal Style Sheet.
```
<head>
  <style>
    body {
      background-color: blue;
    }
    h1 {
      color: maroon;
      margin-left: 40px;
    }
  </style>
</head>
```
c. Inline Style
Inline Style menyisipkan atau mendefinisikan CSS ke dalam HTML dengan menambahkan atribut style
pada elemen yang ingin ditambahkan CSS. Biasanya digunakan hanya untuk satu elemen yang
membutuhkan style CSS yang berbeda dari yang telah didefinisikan pada Internal Style atau Eksternal Style.
```
<h1 style="color:lightblue; font-size:30px;">Praktikum Web Programming</h1>
```


### 4.1.2. Selector
Selector pada CSS digunakan untuk menemukan elemen HTML untuk diberi CSS berdasarkan selector yang didefinisikan. Bentuk selector ada beberapa antara lain nama elemen HTML, atribut ID dan atribut Class.
```
/*Selector dengan Elemen
HTML*/
p {
  text-align: center;
  color: red;
}

/*Selector dengan Id Elemen
HTML*/
#para1 {
  text-align: center;
  color: red;
}

/*Selector dengan Class Elemen
HTML*/
p.center {
  text-align: center;
  color:
}
```

## 4.2. Font Properties
Sebuah laman web tentunya tidak lepas oleh penggunaan teks, oleh karena itu memiliki tampilan teks yang tepat sangat diperlukan agar sebuah web memiliki tampilan yang baik dan menarik. CSS dapat menangani kebutuhan tampilan teks dengan font properties.

| Font Properties | Keterangan |
|-----------------|------------|
| `font-family` | Menentukan jenis font yang digunakan |
| `font-size` | Mengatur ukuran font |
| `font-style` | Mengatur style font (normal, italic, oblique) |
| `font-weight` | Mengatur ketebalan font (normal atau bold) |

Contoh penerapannya sebagai berikut:
```
p.example {
  font-family: Arial;
  font-size: 20px;
  color: ligh;
  dddddfont-style: italic;
  font-weight: bold;
}
```
<p align="center"><img width="279" height="79" alt="image" src="https://github.com/user-attachments/assets/4fe8f8e0-c77c-4ddf-9b01-5f3fad2c6e54" /></p>

## 4.3. List Properties
Dalam HTML terdapat elemen yang berguna membuat sebuah list menggunakan simbol dan karakter. Tag
yang digunakan adalah tag <ul></ul> atau <ol></ol>. Tag <ul> digunakan ketika akan menggunakan list dengan penanda berupa simbol atau bisa dikatakan unordered list, sedangkan tag <ol> digunakan ketika akan menggunakan list dengan penanda karakter yang memiliki urutan atau bisa dikatakan ordered list. Namun di dalam tag tersebut juga harus didefinisikan tag pendukung yaitu <li></li> untuk mendefinisikan elemen-elemen list yang akan ditampilkan. Untuk setiap tag ordered list atau unordered list memiliki satu atribut untuk mendefinisikan tipe simbol atau karakter yang akan digunakan yaitu atribut type. Contoh penerapan dan tipe masing-masing tag sebagai berikut:
```
<h3>List of Property</h3>
<ol type="1">
    <li>Indoor
        <ul type="circle">
            <li>Sofa</li>
        </ul>
        <ul type="disc">
            <li>Tanaman Hias</li>
        </ul>
        <ul type="square">
            <li>Lampu Baca</li>
        </ul>
        <ul type="none">
            <li>Rak Buku</li>
        </ul>
    </li>
    <li>Outdoor
        <ol type="A">
            <li>Payung Pantai</li>
        </ol>
        <ol type="a">
            <li>Ayunan</li>
        </ol>
        <ol type="I">
            <li>Kursi Taman</li>
        </ol>
        <ol type="i">
            <li>Lampu Taman</li>
        </ol>
    </li>
</ol>
```
<p align="center"><img width="198" height="222" alt="image" src="https://github.com/user-attachments/assets/bb248e59-45d0-4385-bcda-4e4b3bbbffb7" />
</p>
Dengan ditambahkan CSS pada elemen list, maka list yang ditampilkan dapat lebih menarik, berikut CSS properties untuk elemen list.

| Lists Specified Properties | Keterangan |
|----------------------------|------------|
| `list-style-image` | Membuat sebuah gambar menjadi penanda list |
| `list-style-position` | Mengatur posisi penanda list di dalam konten atau di luar konten |
| `list-style-type` | Mengatur jenis penanda list |

| Lists General Properties | Keterangan |
|--------------------------|------------|
| `background-color` | Mengatur warna latar belakang elemen list |
| `padding` | Mengatur ruang jarak elemen konten dengan pembatas pada bagian dalam |
| `margin` | Mengatur ruang jarak elemen konten dengan pembatas pada bagian luar |

Contoh penerapannya sebagai berikut:
<p align="center"><img width="275" height="249" alt="image" src="https://github.com/user-attachments/assets/730f0222-0eb1-4e90-9558-821d1b3d52ff" /></p>

```
Ul.listsatu {
background-color: tomato;
margin: 10px 5px 10px 5px;
list-style-type: lower-alpha;
list-style-position: inside;
}
ol.listdua {
background-color: lightblue;
list-style-type: lower-roman;
padding: 5px 5px 15px 15px;
list-style-position: inside;
}
```

## 4.4. Alignment of Text
Pengaturan alignment pada sebuah teks juga dapat ditangani oleh CSS dengan properties pada tabel
| Properties | Value | Keterangan |
|-----------|-------|------------|
| `text-align` | `center` | Membuat teks menjadi rata tengah |
| `text-align` | `left` | Membuat teks menjadi rata kiri |
| `text-align` | `right` | Membuat teks menjadi rata kanan |
| `text-align` | `justify` | Membuat paragraf menjadi rata kanan dan kiri |

Contoh penerapannya pada gambar
<p align="center"><img width="436" height="87" alt="image" src="https://github.com/user-attachments/assets/4ebde531-6bf8-44d1-9fe9-536719d6197a" /></p>

```
h1 {
  text-align: center;
}
h2 {
  text-align: left;
}
h3 {
  text-align: right;
}
```

## 4.5. Colors
Jika berbicara desain antar muka web, permasalahan tentang warna merupakan salah satu hal yang
penting. Pada dasarnya Tag HTML dapat menangani pengaturan warna latar belakang atau teks
menggunakan atribut dari HTML sendiri, namun CSS dapat menangani lebih baik dengan menawarkan
pengaturan yang lebih lengkap.

| Properties | Keterangan | Value |
|------------|------------|-------|
| `background-color` | Mengatur warna latar belakang elemen HTML | Color Names (Red, Green, Orange, dll.), RGB Value (R, G, B), Hex Value (#FFFF00), HSL Value (Hue, Saturation, Light) |
| `color` | Mengatur warna teks elemen HTML | Color Names, RGB Value, Hex Value, HSL Value, RGBA (dengan Opacity), HSLA (dengan Opacity) |

Contoh penerapannya sebagai berikut :
```
body{
  background-color: HSL(20%, 40%, 70%);
  color: orange;
}
```
```
#teks{
  color: #2F3CDF;
}
```
```
/*dengan opacity sebesar 0.5*/
input.text-field{
  background-color: RGBA(32, 55, 122, 0.5);
}
```

## 4.6. Span & Div
Span merupakan elemen HTML yang dapat menangani perubahan konten elemen pada satu baris. Tag
yang digunakan adalah <span></span>. Sedangkan Div merupakan elemen HTML yang digunakan untuk
membuat section untuk beberapa elemen HTML di dalamnya. Tag yang digunakan yaitu <div></div>.
```
<div class=”section1”>
  <p> Content of <span class=”mark”> Property </span> </p>
</div>
/*CSS Properties*/
.section1 {
  background-color: lightgrey;
  padding: 10px 5px 10px 5px;
}
.mark {
  background-color: tomato;
  font-style: italic;
  font-weight: bold;
  padding: 10px 10px 10px 10px;
}
```
<p align="center"><img width="236" height="59" alt="image" src="https://github.com/user-attachments/assets/0deb0df0-2fb9-4a7a-bd2b-92927efe4d48" /></p>


# UNGUIDED (Buat halaman untuk merayakan imlek ("karena bubub gua cina") hanya menggunakan css tanpa library dan tanpa js)
```
<!DOCTYPE html>
<html>
<head>
<title>Selamat Tahun Baru Imlek</title>

<style>

body{
    margin:0;
    padding:0;
    background-color:#f2efe9;
    font-family:"Times New Roman", serif;
    text-align:center;
}

/* header dekorasi atas */
.header{
    width:420px;
    margin-top:40px;
}

/* container utama */
.container{
    margin-top:60px;
}

/* judul utama */
h1{
    color:#9b0000;
    font-size:58px;
    line-height:1.25;
    letter-spacing:4px;
    margin-bottom:20px;
}

/* paragraf ucapan */
p{
    color:#9b0000;
    font-size:19px;
    max-width:620px;
    margin:0 auto;
    line-height:1.6;
}

/* lampion kiri */
.lampion-kiri{
    position:absolute;
    left:140px;
    top:70px;
    width:90px;
}

/* lampion kanan */
.lampion-kanan{
    position:absolute;
    right:140px;
    top:70px;
    width:90px;
}

</style>
</head>

<body>

<img src="header.png" class="header">

<img src="lampion.png" class="lampion-kiri">
<img src="lampion.png" class="lampion-kanan">

<div class="container">

<h1>
SELAMAT<br>
TAHUN BARU<br>
IMLEK
</h1>

<p>
Semoga Tahun Baru Imlek ini membawa kebahagiaan,
kesehatan, dan kemakmuran bagi Anda dan keluarga.
</p>

</div>

</body>
</html>
```
Output:
<img width="1915" height="907" alt="image" src="https://github.com/user-attachments/assets/06a31a01-31ba-4a1f-8272-ab812d8b48f0" />


