# Proyek Terrarium Bagian 1: Pengantar HTML

![Pengantar HTML](/sketchnotes/webdev101-html.png)

> Sketchnote oleh [Tomomi Imura](https://twitter.com/girlie_mac)

## Pre-Lecture Kuis

[Pre-lecture kuis](https://happy-mud-02d95f10f.azurestaticapps.net/quiz/15)

### Pengantar

HTML, atau HyperText Markup Language, adalah 'kerangka' web. Jika CSS 'mendandani' HTML Anda dan Javascript membuatnya hidup, HTML adalah tubuh aplikasi web Anda. Sintaks HTML bahkan mencerminkan ide itu, karena menyertakan tag-tag "head" (kepala), "body" (Tubuh), dan "footer" (Kaki).

Pada pelajaran ini, kita akan menggunakan HTML untuk menata 'kerangka' dari tampilan virtual terrarium kita. Dia akan memiliki judul dan tiga kolom: kolom kanan dan kolom kiri di mana ada tanaman hidup yang dapat diseret, dan area tengah yang akan menjadi terrarium yang tampak seperti kaca. Pada akhir pelajaran ini, Anda akan melihat tanaman di kolom, tetapi tampilan akan terlihat sedikit aneh; jangan khawatir, di bagian selanjutnya kamu akan menambahkan CSS ke tampilan web agar terlihat lebih menarik.

### Tugas

Pada komputer Anda, buat folder dengan nama 'terrarium' dan di dalamnya buat file 'index.html'.
Anda dapat membuat ini pada Visual Studio Code setelah membuat folder terrarium buka jendela VS code yang baru, klik 'buka folder' dan navigasi ke folder baru Anda. Klik tombol file kecil di panel explorer dan buat file baru.

![explorer di VS Code](images/vs-code-index.png)

Or

Gunakan perintah ini pada git bash Anda:

- `mkdir terrarium`
- `cd terrarium`
- `touch index.html`
- `code index.html` or `nano index.html`

> file index.html menunjukkan ke browser bahwa itu adalah file default dalam folder; URL seperti `https://anysite.com/test` mungkin dibuat menggunakan struktur folder termasuk folder bernama `test` dengan `index.html` di dalamnya; `index.html` tidak harus ditampilkan di URL.

## DocType dan tag-tag html

Baris pertama pada file HTML adalah doctype-nya. Agak mengejutkan bahwa Anda perlu memiliki baris ini di bagian paling atas file, tapi ini memberi tahu browser lama bahwa browser perlu merender halaman dalam mode standar, mengikuti spesifikasi html saat ini.

> Tip: di VS Code, Anda bisa mengarahkan kursor ke sebuah tag dan mendapatkan informasi tentang penggunaannya dari panduan Referensi MDN.

Baris kedua harus berupa tag `<html>`, diikuti dengan tag penutup `</html>`. Tag-tag ini adalah elemen root dari antarmuka Anda.

### Tugas

Tambahkan baris-baris ini pada bagian atas file `index.html`:

```HTML
<!DOCTYPE html>
<html></html>
```

Ada beberapa mode berbeda yang dapat ditentukan dengan menyetel DocType dengan string kueri: [Quirks Mode and Standards Mode](https://developer.mozilla.org/docs/Web/HTML/Quirks_Mode_and_Standards_Mode). Mode-mode ini digunakan untuk mendukung browser lama yang biasanya tidak digunakan saat ini (Netscape Navigator 4 dan Internet Explore 5). Anda dapat tetap menggunakan deklarasi doctype standar.

---

## The document's 'head'

Area 'head' dari dokument HTML mengandung informasi yang penting tentang halaman web Anda, juga dikenal sebagai [metadata](https://developer.mozilla.org/docs/Web/HTML/Element/meta). Pada kasus kita, kita memberi tahu server web ke mana halaman ini akan dikirim untuk dirender, empat hal ini:

- Judul halaman
- metadata halaman yaitu:
- 'character set', memberi tahu tentang pengkodean karakter apa yang digunakan di halaman
- informasi browser, termasuk `x-ua-compatible` yang menunjukkan bahwa browser IE=edge didukung
- informasi tentang viewport yang harus berperilaku saat dimuat. Menyetel viewport agar memiliki skala awal 1 mengontrol tingkat zoom saat halaman pertama kali dimuat.

### Tugas

Tambahkan blok 'head' ke document Anda di antara tag `<html>` pembuka dan penutup.

```html
<head>
  <title>Welcome to my Virtual Terrarium</title>
  <meta charset="utf-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
</head>
```

✅ Apa yang terjadi jika Anda menyetel tag meta viewport seperti ini: `<meta name="viewport" content="width=600">`? Baca lebih lanjut tentang [viewport](https://developer.mozilla.org/docs/Web/HTML/Viewport_meta_tag).

---

### Tag HTML

Dalam HTML, Anda bisa menambahkan tag-tag ke dalam file .html untuk membuat elemen-elemen pada sebuah halaman web. Setiap tag biasanya memiliki tag pembuka dan penutup, seperti ini: `<p>hello</p>` untuk menunjukkan paragraf. Buat isi interface Anda dengan menambahkan sekumpulan tag `<body>` di dalam pasangan tag `html`; markup Anda sekarang terlihat seperti ini:

### Tugas

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Welcome to my Virtual Terrarium</title>
    <meta charset="utf-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
  </head>
  <body></body>
</html>
```

Sekarang, Anda bisa mulai membangun halaman Anda. Biasanya, Anda menggunakan tag `<div>` untuk membuat elemen terpisah di halaman. Kita akan membuat serangkaian elemen `<div>` element yang berisi gambar.

### Gambar

Salah satu tag html yang tidak membutuhkan tag penutup adalah `<img>`, karena dia mempunyai elemen `src` yang berisi semua informasi yang dibutuhkan halaman untuk memuat item.

Buat folder di dalam aplikasi mu dengan nama `images` dan di dalamnya, tambahkan semua image pada [source code folder](../solution/images); (ada 14 gambar tanaman).

### Tugas

Tambahkan gambar tanamam tersebut ke dalam dua kolom di antara tag `<body></body>`:

```html
<div id="page">
  <div id="left-container" class="container">
    <div class="plant-holder">
      <img class="plant" alt="plant" id="plant1" src="./images/plant1.png" />
    </div>
    <div class="plant-holder">
      <img class="plant" alt="plant" id="plant2" src="./images/plant2.png" />
    </div>
    <div class="plant-holder">
      <img class="plant" alt="plant" id="plant3" src="./images/plant3.png" />
    </div>
    <div class="plant-holder">
      <img class="plant" alt="plant" id="plant4" src="./images/plant4.png" />
    </div>
    <div class="plant-holder">
      <img class="plant" alt="plant" id="plant5" src="./images/plant5.png" />
    </div>
    <div class="plant-holder">
      <img class="plant" alt="plant" id="plant6" src="./images/plant6.png" />
    </div>
    <div class="plant-holder">
      <img class="plant" alt="plant" id="plant7" src="./images/plant7.png" />
    </div>
  </div>
  <div id="right-container" class="container">
    <div class="plant-holder">
      <img class="plant" alt="plant" id="plant8" src="./images/plant8.png" />
    </div>
    <div class="plant-holder">
      <img class="plant" alt="plant" id="plant9" src="./images/plant9.png" />
    </div>
    <div class="plant-holder">
      <img class="plant" alt="plant" id="plant10" src="./images/plant10.png" />
    </div>
    <div class="plant-holder">
      <img class="plant" alt="plant" id="plant11" src="./images/plant11.png" />
    </div>
    <div class="plant-holder">
      <img class="plant" alt="plant" id="plant12" src="./images/plant12.png" />
    </div>
    <div class="plant-holder">
      <img class="plant" alt="plant" id="plant13" src="./images/plant13.png" />
    </div>
    <div class="plant-holder">
      <img class="plant" alt="plant" id="plant14" src="./images/plant14.png" />
    </div>
  </div>
</div>
```
