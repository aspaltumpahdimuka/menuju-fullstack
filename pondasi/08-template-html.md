# Template HTML

## Misi
1. Bagaimana menulis template atau struktur dari HTML
2. Bagaimana membuka dokumen HTML di browser

### Membuat file HTML
1. buat folder TOP-struktur-html
2. di dalam folder, buat nama file index.hmtl
3. di baris pertama:
```html
<!DOCTYPE html>
```
4. elemen HTML
```html
<html></html>
```
5. beri atribut lang sebagai bahasa yang digunakan pada html.
```html
<!DOCTYPE html>
<html lang="en">


</html>
```
6. tambah elemen head
```html
<!DOCTYPE html>
<html lang="en">
<head>
    
</head>

</html>

```
Elemen <head> adalah tempat kita meletakkan meta-informasi penting tentang halaman web kita, dan hal-hal yang diperlukan agar halaman web kita dapat dirender dengan benar di browser. Di dalam <head>, kita tidak boleh menggunakan elemen apa pun yang menampilkan konten pada halaman web.

7. tambahkan elemen meta
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
</head>

</html>
```

Kita harus selalu memiliki tag meta untuk pengkodean charset halaman web di elemen head: <meta charset="utf-8">.

Mengatur pengkodean sangat penting karena memastikan bahwa halaman web akan menampilkan simbol dan karakter khusus dari berbagai bahasa dengan benar di browser.

8. elemen title
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <title>Struktur HTML</title>
</head>

</html>
```
Mengatur judul halaman pada tab browser

9. body elemen
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <title>Struktur HTML</title>
</head>

<body>
    
</body>

</html>
```
tempat konten halaman berada.

10. Untuk membuka file html, klik kanan, buka menggunkan aplikasi browser
