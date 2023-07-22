# Pengenalan

Pada pelajaran sebelumnya, kita telah membahas sintaks dasar CSS dan selektor-selektor. Sekarang, saatnya menggabungkan pengetahuan tentang selektor dengan konsep C dari CSS - yaitu "cascade" (aliran).

# Ikhtisar Pelajaran

Bagian ini berisi gambaran umum tentang topik-topik yang akan Anda pelajari dalam pelajaran ini.

1. Apa yang dilakukan "cascade".
2. Spesifitas dan penggabungan selektor CSS.
3. Bagaimana "inheritance" mempengaruhi beberapa properti.
Aliran (Cascade) pada CSS

Kadang-kadang kita dapat memiliki aturan-aturan yang saling bertentangan, dan akhirnya menghasilkan beberapa hasil yang tidak terduga. "Tapi saya ingin paragraf-paragraf ini berwarna biru, mengapa mereka merah seperti paragraf-paragraf lain ini?!" Sejenak seperti ini bisa sangat menjengkelkan, namun penting untuk dipahami bahwa CSS tidak beroperasi melawan keinginan kita. CSS hanya melakukan apa yang kita perintahkan. Satu pengecualian dari hal ini adalah gaya bawaan yang disediakan oleh browser. Gaya bawaan ini berbeda dari satu browser ke browser lainnya, dan itulah mengapa beberapa elemen menciptakan "gap" besar di antara mereka dan elemen lain, atau mengapa tombol-tombol memiliki tampilan tertentu, meskipun kita tidak menulis aturan CSS untuk menggayainya seperti itu.

Jadi, jika Anda mendapatkan hasil yang tidak terduga seperti ini, maka entah karena gaya bawaan tersebut, karena belum memahami cara kerja suatu properti, atau karena belum memahami hal kecil yang disebut "cascade" (aliran).

"Aliran" (cascade) adalah yang menentukan aturan mana yang sebenarnya akan diterapkan pada HTML kita. Ada beberapa faktor yang digunakan aliran untuk menentukannya. Kami akan meneliti tiga dari faktor-faktor tersebut, yang akan membantu Anda menghindari momen frustrasi "Saya benci CSS".

# Spesifitas

Sebuah deklarasi CSS yang lebih spesifik akan lebih diutamakan daripada yang kurang spesifik. Inline styles, yang telah kita bahas dalam pelajaran sebelumnya, memiliki spesifitas tertinggi dibandingkan dengan selektor-selektor lainnya, sementara setiap jenis selektor memiliki tingkat spesifitas masing-masing yang berkontribusi pada seberapa spesifik suatu deklarasi. Selektor-selektor lain juga berkontribusi pada spesifitas, namun kami hanya akan fokus pada selektor-selektor yang telah kita bahas sejauh ini:

1. Selektor ID (selektor paling spesifik)
2. Selektor Class
3. Selektor Tipe

Spesifitas hanya akan diperhitungkan ketika sebuah elemen memiliki beberapa deklarasi yang saling bertentangan yang menargetkannya, mirip dengan adu pinalti. Selektor ID akan selalu mengalahkan jumlah selektor class apapun, selektor class akan selalu mengalahkan jumlah selektor tipe apapun, dan selektor tipe akan selalu mengalahkan jumlah selektor apapun yang kurang spesifik darinya. Ketika tidak ada deklarasi dengan selektor yang lebih spesifik, maka jumlah yang lebih besar dari satu jenis selektor akan mengalahkan jumlah yang lebih kecil dari jenis selektor yang sama.

Mari kita lihat beberapa contoh sederhana untuk menggambarkan bagaimana spesifitas berfungsi. Pertimbangkan kode HTML dan CSS berikut:

```html
<!-- index.html -->

<div class="main">
  <div class="list subsection"></div>
</div>
/* aturan 1 */
.subsection {
  color: blue;
}

/* aturan 2 */
.main .list {
  color: red;
}
```

Pada contoh di atas, kedua aturan menggunakan selektor class saja, tetapi aturan 2 lebih spesifik karena menggunakan lebih banyak selektor class. Oleh karena itu, deklarasi `color: red;` akan diutamakan.

Sekarang, mari kita ubah sedikit:

```html
<!-- index.html -->

<div class="main">
  <div class="list" id="subsection"></div>
</div>
/* aturan 1 */
#subsection {
  color: blue;
}

/* aturan 2 */
.main .list {
  color: red;
}
```

Pada contoh di atas, meskipun aturan 2 memiliki lebih banyak selektor class daripada selektor ID, aturan 1 lebih spesifik karena ID lebih diutamakan daripada class. Dalam kasus ini, deklarasi `color: blue;` akan diutamakan.

```css
/* aturan 1 */
#subsection .list {
  background-color: yellow;
  color: blue;
}

/* aturan 2 */
#subsection .main .list {
  color: red;
}
```

Pada contoh terakhir ini, kedua aturan menggunakan selektor ID dan class, sehingga

 tidak ada aturan yang lebih spesifik daripada yang lain. Maka aliran akan memeriksa jumlah dari setiap jenis selektor. Kedua aturan hanya memiliki satu selektor ID, tetapi aturan 2 memiliki lebih banyak selektor class, sehingga aturan 2 memiliki spesifitas yang lebih tinggi!

Meskipun deklarasi `color: red;` akan diutamakan, deklarasi `background-color: yellow;` masih akan diterapkan karena tidak ada deklarasi yang saling bertentangan untuk properti tersebut.

# Tidak Semua Meningkatkan Spesifitas

Ketika membandingkan selektor-selektor, Anda mungkin menemukan simbol-simbol khusus untuk selektor universal (*) serta kombinator (+, ~, >, dan spasi kosong). Simbol-simbol ini tidak menambahkan spesifitas apa pun pada diri mereka sendiri.

```css
/* aturan 1 */
.class.second-class {
  font-size: 12px;
}

/* aturan 2 */
.class .second-class {
  font-size: 24px;
}
```

Kedua aturan di atas memiliki spesifitas yang sama. Aturan 1 menggunakan "chaining selector" (tanpa spasi) dan aturan 2 menggunakan kombinator keturunan (spasi kosong). Namun, kedua aturan memiliki dua class dan simbol kombinator itu sendiri tidak menambahkan spesifitas.

```css
/* aturan 1 */
.class.second-class {
  font-size: 12px;
}

/* aturan 2 */
.class > .second-class {
  font-size: 24px;
}
```

Contoh ini menunjukkan hal yang sama. Meskipun aturan 2 menggunakan kombinator child (>) ini tidak mengubah nilai spesifitas. Kedua aturan masih memiliki dua class sehingga memiliki nilai spesifitas yang sama.

```css
/* aturan 1 */
* {
  color: black;
}

/* aturan 2 */
h1 {
  color: orange;
}
```

Dalam contoh ini, aturan 2 akan memiliki spesifitas yang lebih tinggi dan nilai oranye akan diutamakan untuk elemen ini. Aturan 2 menggunakan selektor tipe, yang memiliki nilai spesifitas paling rendah. Namun, aturan 1 menggunakan selektor universal (*) yang tidak memiliki nilai spesifitas sama sekali.

# Warisan (Inheritance)

Warisan (inheritance) mengacu pada properti CSS tertentu yang, ketika diterapkan pada suatu elemen, akan diwarisi oleh elemen turunannya, bahkan jika kita tidak menulis aturan secara eksplisit untuk turunannya tersebut. Properti-properti berbasis tipografi (seperti warna, ukuran font, font-family, dll.) biasanya diwariskan, sementara sebagian besar properti lainnya tidak diwariskan.

Pengecualian dari ini adalah ketika secara langsung menargetkan suatu elemen, karena ini selalu mengalahkan warisan:

```html
<!-- index.html -->

<div id="parent">
  <div class="child"></div>
</div>
/* styles.css */

#parent {
  color: red;
}

.child {
  color: blue;
}
```

Meskipun elemen induk memiliki spesifitas lebih tinggi dengan ID, elemen anak akan memiliki gaya `color: blue` diterapkan karena deklarasi itu secara langsung menargetkannya, sedangkan `color: red` dari induk hanya diwarisi.

# Urutan Aturan

Faktor terakhir, yang menjadi penentu akhir, penyeimbang dari penyeimbang. Misalkan setelah semua faktor lainnya sudah diperhitungkan, masih ada beberapa aturan yang saling bertentangan yang menargetkan suatu elemen. Bagaimana aliran menentukan aturan mana yang akan diterapkan?

Sangat sederhana, sebenarnya. Aturan mana yang terakhir didefinisikan akan menjadi yang menang.

```css
/* styles.css */

.alert {
  color: red;
}

.warning {
  color: yellow;
}
```

Untuk elemen yang memiliki kelas alert dan warning, aliran akan memeriksa setiap faktor lainnya, termasuk warisan (tidak ada di sini) dan spesifitas (tidak ada aturan yang lebih spesifik daripada aturan lainnya). Karena aturan .warning yang terakhir didefinisikan, dan tidak ada faktor lain yang dapat menentukan aturan mana yang akan diterapkan, maka aturan .warning akan diterapkan pada elemen tersebut.

## Misi
1. Kerjakan misi css nomor 6
2. perbaiki halaman web resep masakan dengan menambahkan css