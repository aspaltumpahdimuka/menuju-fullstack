# Pengenalan HTML dan CSS

## Apa kepanjangan dari HTML dan CSS?
Kepanjangan dari HTML adalah "Hypertext Markup Language," sedangkan kepanjangan dari CSS adalah "Cascading Style Sheets."

1. **HTML (Hypertext Markup Language)**:
HTML adalah bahasa markah atau markup language yang digunakan untuk membuat dan mendesain halaman web. Ini menyediakan struktur dasar untuk konten sebuah halaman web, seperti teks, gambar, tautan, tabel, formulir, dan elemen-elemen lainnya. HTML menggunakan "tag" untuk memberi tahu browser bagaimana merender dan menampilkan elemen-elemen tersebut di halaman web.

2. **CSS (Cascading Style Sheets)**:
CSS adalah bahasa gaya atau style sheet language yang digunakan untuk mengatur tampilan dan tata letak elemen-elemen HTML di halaman web. Dengan menggunakan CSS, Anda dapat mengubah tampilan dan warna teks, mengatur ukuran gambar, menata letak elemen, dan memberikan efek visual lainnya pada halaman web. CSS berfungsi sebagai lapisan terpisah dari HTML, yang memungkinkan pemisahan antara struktur dan gaya tampilan dari halaman web.

Kombinasi HTML dan CSS memungkinkan pengembang untuk menciptakan halaman web yang menarik, terstruktur, dan responsif dengan mudah. HTML memberikan struktur dan isi konten, sedangkan CSS memberikan gaya dan tampilan visual pada halaman tersebut. Keduanya bekerja bersama untuk menciptakan pengalaman pengguna yang menarik dan konsisten di berbagai perangkat dan platform.

## Di antara HTML dan CSS, mana yang akan Anda gunakan untuk meletakkan paragraf teks pada halaman web?
Untuk meletakkan paragraf teks pada halaman web, Anda akan menggunakan HTML. HTML bertanggung jawab untuk menentukan struktur dan konten dari halaman web, termasuk teks, gambar, tautan, tabel, dan elemen-elemen lainnya.

Untuk membuat paragraf teks dalam HTML, Anda akan menggunakan elemen "p" (paragraf). Berikut adalah contoh sederhana penggunaan elemen "p" untuk menempatkan paragraf teks:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Contoh Paragraf HTML</title>
</head>
<body>

    <p>Ini adalah contoh paragraf teks dalam halaman web.</p>

</body>
</html>
```

Elemen "p" digunakan untuk membuat paragraf baru dalam halaman web, dan teks yang ingin Anda tampilkan diletakkan di dalam elemen "p". Saat halaman web di-render, paragraf tersebut akan muncul dalam bentuk teks pada halaman web.

CSS digunakan untuk mengatur tampilan dan gaya tata letak elemen-elemen HTML, termasuk paragraf teks. Dengan CSS, Anda dapat mengubah ukuran, warna, jarak, dan banyak aspek visual lainnya pada paragraf. Namun, untuk menempatkan paragraf itu sendiri pada halaman web, Anda akan menggunakan elemen "p" dalam HTML.

## Di antara HTML dan CSS, mana yang akan Anda gunakan untuk mengubah font dan warna latar belakang tombol?
Untuk mengubah font dan warna latar belakang tombol, Anda akan menggunakan CSS. CSS (Cascading Style Sheets) bertanggung jawab untuk mengatur tampilan dan tata letak elemen-elemen HTML di halaman web.

Berikut adalah contoh sederhana penggunaan CSS untuk mengubah font dan warna latar belakang tombol:

HTML:
```html
<!DOCTYPE html>
<html>
<head>
    <title>Contoh Tombol dengan CSS</title>
    <link rel="stylesheet" type="text/css" href="style.css">
</head>
<body>

    <button class="my-button">Tombol Saya</button>

</body>
</html>
```

CSS (style.css):
```css
/* Mengubah font dan warna latar belakang tombol */
.my-button {
    font-family: Arial, sans-serif;
    font-size: 16px;
    background-color: #007bff;
    color: #fff;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
}
```

Dalam contoh di atas, kami membuat tombol dengan elemen "button" dalam HTML. Kemudian, kami menggunakan CSS untuk mengubah tampilan tombol tersebut. Dalam CSS, kami menentukan properti "font-family" untuk mengubah font teks tombol menjadi "Arial" atau font sans-serif jika Arial tidak tersedia. Kami juga menggunakan properti "font-size" untuk mengatur ukuran font teks tombol.

Selain itu, kami menggunakan properti "background-color" untuk mengubah warna latar belakang tombol menjadi "#007bff" (biru muda), dan properti "color" untuk mengubah warna teks menjadi putih.

Properti-properti lain seperti "padding" dan "border-radius" digunakan untuk mengatur tata letak dan bentuk tombol. Semua perubahan gaya tersebut diterapkan pada tombol menggunakan kelas CSS ".my-button", yang sesuai dengan kelas tombol dalam elemen "button" di HTML.

Dengan menggunakan CSS, Anda dapat dengan mudah mengubah tampilan berbagai elemen HTML, termasuk tombol, sesuai dengan kebutuhan desain halaman web Anda.

