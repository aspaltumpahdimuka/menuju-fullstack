# Intro CSS

## Syntax dasar
```css
selector {
    property: value;
}

```
### universal selector
```css
* {
    color: red;
}
```

### type selector
```css
div {
    font-family: sans-serif;
}
```

### class selector
Class selector akan memilih semua elemen dengan kelas yang diberikan, yang merupakan atribut yang Anda tempatkan pada elemen HTML. Berikut ini cara menambahkan kelas ke tag HTML dan memilihnya di CSS:
```html
<div class="test"><p>ini tes</p></div>
```
```css
.test {
    color: red;
}
```

### id selector
ID selector mirip dengan penyeleksi kelas. Selektor ini memilih elemen dengan ID yang diberikan, yang merupakan atribut lain yang Anda tempatkan pada elemen HTML. Perbedaan utama antara kelas dan ID adalah sebuah elemen hanya dapat memiliki satu ID. ID tidak dapat diulang pada satu halaman dan tidak boleh mengandung spasi:
```html
<div class="judul"><p>ini tes</p></div>
```
```css
#judul {
    color: red;
}
```

## Bagaimana jika kita memiliki dua kelompok elemen yang memiliki beberapa pernyataan gaya yang sama?
```css
.read {
  color: white;
  background-color: black;
  /* several unique declarations */
}

.unread {
  color: white;
  background-color: black;
  /* several unique declarations */
}
```
Kedua penyeleksi .read dan .unread memiliki deklarasi color: white; dan background-color: black; yang sama, namun memiliki beberapa deklarasi uniknya masing-masing. Untuk mengurangi pengulangan, kita dapat mengelompokkan kedua penyeleksi ini sebagai daftar yang dipisahkan dengan koma:

```css
.read,
.unread {
  color: white;
  background-color: black;
}

.read {
  /* several unique declarations */
}

.unread {
  /* several unique declarations */
}
```
## selector berantai
Cara lain untuk menggunakan selektor adalah dengan merantainya sebagai daftar tanpa pemisahan. Katakanlah kita memiliki HTML berikut ini:
```html
<div>
  <div class="subsection header">Latest Posts</div>
  <p class="subsection preview">This is where a preview for a post might go.</p>
</div>
```
Kita memiliki dua elemen dengan kelas 'subsection' yang memiliki gaya unik, tetapi bagaimana jika kita hanya ingin menerapkan aturan terpisah pada elemen yang juga memiliki header sebagai kelas kedua? Nah, kita dapat merantai kedua penyeleksi kelas bersama-sama di CSS kita seperti itu:
```css
.subsection.header {
  color: red;
}
```
```html
<div>
  <div class="subsection header">Latest Posts</div>
  <p class="subsection" id="preview">
    This is where a preview for a post might go.
  </p>
</div>
```
```css
.subsection.header {
  color: red;
}

.subsection#preview {
  color: blue;
}
```

### selector turunan
```html
<!-- index.html -->

<div class="ancestor">
  <!-- A -->
  <div class="contents">
    <!-- B -->
    <div class="contents"><!-- C --></div>
  </div>
</div>

<div class="contents"></div>
<!-- D -->
```
```css
/* styles.css */

.ancestor .contents {
  /* some declarations */
}
```
pada contoh di atas maka B dan C yang akan dipilih


## Override
```css
/* styles.css */
.first_declared, .last_declared {
  background-color: rgb(200, 50, 150);
  font-weight: 800;
}
.first_declared {
  color: rgb(50, 50, 200); /* Tambahkan titik koma di sini */
  font-size: 32px;
}
.last_declared {
  font-size: 14px;
  font-weight: 800;
}
```
```html
<!-- index.html -->
<div class="first_declared last_declared">Ini adalah contoh teks</div>
```

Pada contoh di atas, elemen `<div>` memiliki kedua kelas "first_declared" dan "last_declared". Sekarang mari kita lihat aturan CSS-nya.

1. `.first_declared, .last_declared`: Aturan ini mengatur warna latar belakang menjadi `rgb(200, 50, 150)` dan ketebalan font menjadi `800` untuk elemen yang memiliki salah satu dari kelas "first_declared" atau "last_declared".

2. `.first_declared`: Aturan ini mengatur warna teks menjadi `rgb(50, 50, 200)` dan ukuran font menjadi `32px` untuk elemen yang memiliki kelas "first_declared".

3. `.last_declared`: Aturan ini mengatur ukuran font menjadi `14px` dan ketebalan font menjadi `800` untuk elemen yang memiliki kelas "last_declared".

Karena elemen `<div>` memiliki kedua kelas "first_declared" dan "last_declared", maka:

- Warna latar belakang dan ketebalan font akan ditentukan oleh aturan `.first_declared, .last_declared`.
- Warna teks akan ditimpa oleh aturan `.first_declared`.
- Ukuran font akan ditimpa oleh aturan `.last_declared`.

Sehingga, pada contoh ini, elemen akan memiliki warna latar belakang `rgb(200, 50, 150)`, warna teks `rgb(50, 50, 200)`, ukuran font `14px`, dan ketebalan font `800`.

## Properti yang perlu diketahui
### color dan background-color
color untuk warna teks.
background-color untuk warna belakang elemen
```css
p {
  /* hex example: */
  color: #1100ff;
}

p {
  /* rgb example: */
  color: rgb(100, 0, 127);
}

p {
  /* hsl example: */
  color: hsl(15, 82%, 56%);
}
```

### Dasar typografi dan text-align
- font-family mengatur font yang digunakan
- font-size ukuran font
- font-weight ketebalan font
- text-align mengatur letak font

## lebar dan tinggi gambar
```css
img {
  height: auto;
  width: 500px;
}
```
- height mengatur tinggi
- width mengatur lebar

## Menambahkan CSS ke HTML
### external css
sumbernya dari file css yang terpisah dengan html
```html
<!-- index.html -->

<head>
  <link rel="stylesheet" href="styles.css" />
</head>
```
```css
/* styles.css */

div {
  color: white;
  background-color: black;
}

p {
  color: red;
}
```
### Internal css
aturan css ada di elemen style yang diletakan di head
```html
<head>
  <style>
    div {
      color: white;
      background-color: black;
    }

    p {
      color: red;
    }
  </style>
</head>
<body>
  ...
</body>
```

### inline css
diletakan di elemen yang diatur
```html
<body>
  <div style="color: white; background-color: black;">...</div>
</body>
```

## Misi
Kerjakan misi di [Intro CSS](./misi/css/)




