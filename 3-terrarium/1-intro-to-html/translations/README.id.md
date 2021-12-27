# Proyek Terrarium Bagian 1: Pengantar HTML

![Pengantar HTML](/sketchnotes/webdev101-html.png)

> Sketchnote oleh [Tomomi Imura](https://twitter.com/girlie_mac)

## Kuis sebelum membaca

[Kuis sebelum membaca](https://happy-mud-02d95f10f.azurestaticapps.net/quiz/15)

### Pengantar

HTML atau HyperText Markup Language adalah 'kerangka' web. Jika CSS 'mendandani' HTML Anda dan Javascript membuatnya hidup, HTML adalah tubuh aplikasi web Anda. Sintaks HTML bahkan mencerminkan ide itu, karena menyertakan tag-tag "head" (kepala), "body" (Tubuh), dan "footer" (Kaki).

Pada pelajaran ini, kita akan menggunakan HTML untuk menata 'kerangka' dari tampilan virtual terrarium kita. Dia akan memiliki judul dan tiga kolom: kolom kanan dan kolom kiri di mana ada tanaman hidup yang dapat diseret dan area tengah yang akan menjadi terrarium yang tampak seperti kaca. Pada akhir pelajaran ini, Anda akan melihat tanaman di kolom tetapi tampilan akan terlihat sedikit aneh; jangan khawatir, di bagian selanjutnya kamu akan menambahkan CSS ke tampilan web agar terlihat lebih menarik.

### Tugas

Pada komputer Anda, buat folder dengan nama 'terrarium' dan di dalamnya buat file 'index.html'. Anda dapat membuat ini pada Visual Studio Code setelah membuat folder terrarium buka jendela VS code yang baru, klik 'buka folder' dan navigasi ke folder baru Anda. Klik tombol file kecil di panel explorer dan buat file baru.

![explorer dalam VS Code](images/vs-code-index.png)

Atau

Gunakan perintah ini pada git bash Anda:

- `mkdir terrarium`
- `cd terrarium`
- `touch index.html`
- `code index.html` or `nano index.html`

> file index.html menunjukkan ke browser bahwa itu adalah file default dalam folder; URL seperti `https://anysite.com/test` mungkin dibuat menggunakan struktur folder termasuk folder bernama `test` dengan `index.html` di dalamnya; `index.html` tidak harus ditampilkan di URL.

## DocType dan tag-tag html

Baris pertama pada file HTML adalah doctype-nya. Agak mengejutkan bahwa Anda perlu memiliki baris ini di bagian paling atas file tapi ini memberi tahu browser lama bahwa browser perlu merender halaman dalam mode standar, mengikuti spesifikasi html saat ini.

> Tip: di VS Code, Anda bisa mengarahkan kursor ke sebuah tag dan mendapatkan informasi tentang penggunaannya dari panduan Referensi MDN.

Baris kedua harus berupa tag `<html>` diikuti dengan tag penutup `</html>`. Tag-tag ini adalah elemen root dari antarmuka(interface) Anda.

### Tugas

Tambahkan baris-baris ini pada bagian atas file `index.html`:

```HTML
<!DOCTYPE html>
<html></html>
```

Ada beberapa mode berbeda yang dapat ditentukan dengan menyetel DocType dengan string kueri: [Quirks Mode and Standards Mode](https://developer.mozilla.org/docs/Web/HTML/Quirks_Mode_and_Standards_Mode). Mode-mode ini digunakan untuk mendukung browser lama yang biasanya tidak digunakan saat ini (Netscape Navigator 4 dan Internet Explore 5). Anda dapat tetap menggunakan deklarasi doctype standar.

---

## Bagian 'head' dokumen

Area 'head' dari dokument HTML mengandung informasi yang penting tentang halaman web Anda, juga dikenal sebagai [metadata](https://developer.mozilla.org/docs/Web/HTML/Element/meta). Pada kasus kita, kita memberi tahu server web ke mana halaman ini akan dikirim untuk dirender, empat hal ini:

- judul halaman
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

## Bagian `body` dokumen

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

Buat folder di dalam aplikasi Anda dengan nama `images` dan di dalamnya tambahkan semua image pada [source code folder](../solution/images); (ada 14 gambar tanaman).

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

> Catatan: Span vs Div. Div dianggap sebagai 'blok' elemen dan span adalah 'sebaris'. Apa yang akan terjadi jika Anda mengubah div ini menjadi span?

Dengan markup ini, tanamannya sekarang muncul pada layar. Terlihat sangat jelek karena belum ditata dengan CSS dan kita akan melakukannya pada pelajaran berikutnya.

Setiap gambar mempunya teks alternatif yang akan muncul meskipun Anda tidak dapat melihat atau merender gambar. Ini adalah atribut penting yang harus disertakan untuk aksesibilitas. Pelajari lebih lanjut tentang aksesibilitas di pelajaran mendatang; untuk saat ini, ingatlah atribut alt memberikan informasi alternatif untuk sebuah gambar jika pengguna karena alasan tertentu tidak dapat melihatnya (karena koneksi lambat, kesalahan pada atribut src atau jika user menggunakan pembaca layar).

✅ Apakah Anda memperhatikan bahwa setiap gambar memiliki tag alt yang sama? Apakah ini praktik yang baik? Mengapa atau mengapa tidak? Bisakah Anda meningkatkan kode ini?

---

## Markup Semantik

Pada umumnya, lebih baik menggunakan 'semantik' saat menulis HTML. Apa artinya? Ini berarti Anda menggunakan tag HTML untuk mewakili jenis data atau interaksi yang dirancang untuknya. Sebagai contoh, teks judul utama pada halaman harus menggunakan tag `<h1>`.

Tambahkan baris berikut tepat di bawah tag pembuka `<body>`:

```html
<h1>My Terrarium</h1>
```

Menggunakan markup semantik seperti membuat tajuk menjadi `<h1>` dan daftar yang tidak berurutan dirender sebagai `<ul>` membantu screen reader menavigasi halaman. Secara umum tombol harus ditulis sebagai `<button>` dan daftar harus `<li>`. Meskipun _memungkinkan_ menggunakan elemen span dengan gaya khusus dengan penanganan klik untuk meniru tombol, lebih baik untuk orang disabilitas untuk menggunakan teknologi untuk menentukan di mana pada halaman sebuah tombol berada dan untuk berinteraksi dengannya jika elemen tersebut muncul sebagai sebuah tombol. Untuk alasan ini, cobalah untuk menggunakan markup semantik sebanyak mungkin.

✅ Lihat lah pada screen reader dan [bagaimana ia berinteraksi dengan halaman web](https://www.youtube.com/watch?v=OUDV1gqs9GA). Bisakah Anda melihat mengapa markup non semantik dapat membuat pengguna frustasi.

## Terrarium

Bagian akhir dari interface ini melibatkan pembuatan markup yang akan ditata untuk membuat terrarium.

### Tugas:

Tambahkan markup ini di atas tag `</div>` terakhir:

```html
<div id="terrarium">
  <div class="jar-top"></div>
  <div class="jar-walls">
    <div class="jar-glossy-long"></div>
    <div class="jar-glossy-short"></div>
  </div>
  <div class="dirt"></div>
  <div class="jar-bottom"></div>
</div>
```

✅ Walaupun Anda menambahkan markup ini ke layar, Anda tidak melihat apa pun yang dirender. Mengapa?

## 🚀Tantangan

Ada beberapa tag 'lama' liar dalam HTML yang masih menyenangkan untuk dimainkan meskipun kamu tidak boleh menggunakan tag yang tidak digunakan lagi seperti [tag ini](https://developer.mozilla.org/docs/Web/HTML/Element#Obsolete_and_deprecated_elements) di markup Anda. Namun dapatkah Anda menggunakan tag `<marquee>` untuk membuat judul h1 bergulir secara horizontal? (jika Anda melakukannya jangan lupa untuk menghapusnya sesudahnya)

## Kuis setelah membaca

[Kuis setelah membaca](https://happy-mud-02d95f10f.azurestaticapps.net/quiz/16)

## Review & Self Study

HTML adalah sistem blok pembangun yang telah terbukti membantu membangun web menjadi seperti ini. Pelajari sedikit tentang sejarahnya dengan mempelajari tag lama dan baru. Bisakah Anda mencari tahu mengapa beberapa tag tidak digunakan lagi dan beberapa ditambahkan? Tag apa yang mungkin diperkenalkan di masa mendatang?

## Penugasan

[Mempraktekkan HTML mu: Membangun blog tiruan](assignment.md)
