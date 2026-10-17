
# Jawaban Praktikum Web101 — HTML & CSS

**Nama:** Darmawan  
**NIM:** 10224045  
**Kelas:** IF V A

---

## Part 1 — Warm-up

### 1. Anatomi CSS

Contoh aturan CSS:

```css
p.note {
  color: blue;
}
```

- **Selector:** `p.note`
- **Declaration:** `color: blue;`
- **Property:** `color`
- **Value:** `blue`

Selector menentukan elemen HTML yang akan diberi gaya. Declaration berisi property dan value yang dipisahkan oleh titik dua dan diakhiri titik koma.

### 2. Block dan Inline

| Elemen | Tampilan default |
|---|---|
| `span` | Inline |
| `p` | Block |
| `a` | Inline |
| `li` | List-item |
| `h2` | Block |
| `strong` | Inline |

Elemen block biasanya memulai baris baru, sedangkan elemen inline berada dalam aliran teks yang sama. Elemen `li` memiliki tampilan default `list-item`.

### 3. Selector `.box p`

Contoh HTML:

```html
<div class="box">
  <p>A</p>
  <section><p>B</p></section>
</div>
<p>C</p>
<div class="box">
  <section><p>D</p></section>
</div>
```

Selector `.box p` memilih semua elemen `p` yang merupakan keturunan elemen dengan class `box`, baik langsung maupun melalui elemen lain.

**Jawaban: A, B, dan D.**

Paragraf C tidak dipilih karena berada di luar `.box`.

### 4. Specificity CSS

Urutan specificity dari tertinggi ke terendah:

1. `#title`
2. `.heading`
3. `h1`

ID memiliki specificity lebih tinggi daripada class, sedangkan class memiliki specificity lebih tinggi daripada selector elemen. Jika specificity sama, deklarasi yang muncul belakangan biasanya menang, selama tidak ada aturan cascade lain yang lebih diutamakan.

### 5. HTML Nesting

Kode yang salah:

```html
<p>Hello <strong>world</p></strong>
```

Perbaikan:

```html
<p>Hello <strong>world</strong></p>
```

Elemen harus ditutup dengan urutan yang benar. Elemen `<strong>` yang dibuka di dalam `<p>` harus ditutup sebelum elemen `<p>` ditutup.

---

## Part 2 — Semantic HTML

**File:** `profile.html`

Elemen semantik yang digunakan:

- `<header>` untuk pengenalan halaman.
- `<nav>` untuk navigasi utama.
- `<main>` untuk konten utama.
- `<section>` untuk mengelompokkan konten berdasarkan topik.
- `<article>` untuk setiap agenda kegiatan.
- `<address>` untuk informasi kontak.
- `<footer>` untuk bagian penutup halaman.

Tabel program studi menggunakan `<thead>`, `<tbody>`, dan `<th>` agar struktur datanya lebih jelas. Formulir menggunakan `<label>` yang terhubung ke input melalui atribut `for` dan `id`. Input email menggunakan `type="email"`.

**Hasil validasi W3C:** [Isi setelah memvalidasi `profile.html`]

**Jumlah error:** [Isi berdasarkan hasil validator]

**Screenshot validator:** `checkpoints/validator.png`

---

## Part 3 — Selector Golf

**File:** `selector-golf.html`  
**File CSS:** `selector-golf.css`

### 1. Prediksi hasil CSS sebelum diterapkan

Aturan CSS:

```css
p {
  color: blue;
}

section p {
  color: green;
}

.note {
  color: orange;
}
```

Dengan HTML Selector Golf yang diberikan pada praktikum, hasilnya:

| Teks | Warna akhir | Alasan |
|---|---|---|
| Weekly hack nights. | Orange | Class `.note` memiliki specificity lebih tinggi daripada `section p` |
| Bring your own laptop. | Orange | Class `.note` memiliki specificity lebih tinggi daripada `section p` |
| © 2026 Student Affairs | Blue | Paragraf footer hanya cocok dengan selector `p` |

Selector `.note` memiliki specificity satu class, sedangkan `section p` memiliki specificity dua elemen. Karena class lebih tinggi daripada selector elemen, deklarasi orange menang pada kedua paragraf catatan.

### 2. Urutan specificity

Urutan dari tertinggi ke terendah:

1. `#tech p`
2. `.club p`
3. `main section p`
4. `p`

Selector yang memiliki ID berada di atas selector class. Selector class berada di atas selector yang hanya menggunakan elemen.

### 3. Tantangan selector

| No. | Selector | Fungsi |
|---|---|---|
| 1 | `h2` | Memilih semua elemen h2 |
| 2 | `.note` | Memilih elemen dengan class note |
| 3 | `.club.featured` | Memilih elemen yang memiliki kedua class tersebut |
| 4 | `p.note` | Memilih paragraf dengan class note |
| 5 | `section p` | Memilih paragraf di dalam section |
| 6 | `h1, .tagline` | Menerapkan aturan yang sama ke dua selector |
| 7 | `nav a` | Memilih tautan di dalam navigasi |
| 8 | `nav a:hover` | Memilih tautan navigasi saat pointer berada di atasnya |
| 9 | `a[target="_blank"]` | Memilih tautan yang memiliki target `_blank` |
| 10 | `li:first-child` | Memilih elemen li yang merupakan anak pertama dari induknya |
| 11 | `header#top` | Memilih elemen header dengan ID top |

---

## Part 4 — Styling Profile

**File:** `style.css`  
**Checkpoint HTML:** `checkpoints/part4-profile.html`  
**Checkpoint CSS:** `checkpoints/part4-style.css`

### Jenis selector yang digunakan

- **Type selector:** `body`
- **Class selector:** `.card` atau `section`
- **ID selector:** `#about`
- **Descendant selector:** `nav ul`
- **Grouping selector:** `h1, h2, h3`
- **Pseudo-class selector:** `nav a:hover`

### Box Model

Diketahui:

```css
.card {
  width: 300px;
  padding: 16px;
  border: 1px solid;
  margin: 24px;
}
```

Jika menggunakan `box-sizing: content-box`:

- Lebar konten = 300 px.
- Padding kiri dan kanan = 32 px.
- Border kiri dan kanan = 2 px.
- Lebar kotak termasuk padding dan border = 334 px.
- Margin kiri dan kanan = 48 px.
- Total ruang horizontal termasuk margin = 382 px.

Jika menggunakan `box-sizing: border-box` dengan `width: 300px`:

- Lebar kotak termasuk padding dan border = 300 px.
- Padding kiri dan kanan = 32 px.
- Border kiri dan kanan = 2 px.
- Lebar konten = 266 px.
- Total ruang horizontal termasuk margin = 348 px.

### Pengamatan melalui DevTools

**Elemen yang diperiksa:** [Isi elemen yang kamu periksa]

**Computed width:** [Isi nilai aktual dari DevTools]

**Computed padding dan margin:** [Isi nilai aktual dari DevTools]

---

## Part 5 — Debugging HTML & CSS

**File hasil perbaikan:** `debug.html`  
**Checkpoint:** `checkpoints/part5-debug-fixed.html`

| No. | Kesalahan awal | Perbaikan |
|---|---|---|
| 1 | `colour` bukan nama property CSS yang valid | Mengubahnya menjadi `color` |
| 2 | Deklarasi background header tidak diakhiri titik koma | Menambahkan `;` setelah `lightblue` |
| 3 | Selector `.Card` tidak cocok dengan class `card` | Menyamakan nama class dan selector menjadi `.card` |
| 4 | Nilai `18 px` mengandung spasi yang salah | Mengubahnya menjadi `18px` |
| 5 | Nilai `centre` tidak valid untuk `text-align` | Mengubahnya menjadi `center` |
| 6 | Elemen h1 ditutup menggunakan `</h2>` | Mengubahnya menjadi `</h1>` |
| 7 | Atribut href tidak memiliki tanda kutip penutup | Memperbaikinya menjadi `href="#about"` |
| 8 | Atribut class pada card memiliki sintaks yang rusak | Mengubahnya menjadi `class="card"` |
| 9 | ID HTML `newsList` tidak cocok dengan selector `#news-list` | Menyamakan ID dan selector menjadi `newsList` atau `news-list` |
| 10 | Gambar tidak memiliki teks alternatif yang bermakna | Menambahkan alt yang menjelaskan gambar |

### Pelajaran dari debugging

HTML yang valid dan CSS yang benar diperlukan agar halaman ditampilkan sesuai harapan. Kesalahan ejaan, tanda baca, selector, dan penutupan tag dapat menyebabkan gaya tidak diterapkan atau struktur dokumen menjadi tidak valid.

---

## Part 6 — Code Review

**File hasil perbaikan:** `review-fixed.html`

| No. | Masalah kode awal | Perbaikan dan alasan |
|---|---|---|
| 1 | Tidak memiliki deklarasi doctype | Menambahkan `<!DOCTYPE html>` agar browser menggunakan mode standar |
| 2 | Tidak memiliki atribut bahasa dokumen | Menambahkan `lang="id"` |
| 3 | Tidak memiliki meta viewport | Menambahkan viewport agar halaman lebih sesuai untuk layar kecil |
| 4 | Menggunakan banyak div untuk seluruh struktur | Menggunakan elemen semantik seperti header, nav, main, section, article, dan footer |
| 5 | Judul utama bukan elemen h1 | Menggunakan `<h1>` untuk judul utama |
| 6 | Menggunakan inline style | Memindahkan aturan visual ke CSS |
| 7 | Menggunakan `!important` | Menghapusnya dan mengatur selector serta cascade dengan tepat |
| 8 | Warna teks kurang kontras | Memilih warna teks yang lebih mudah dibaca |
| 9 | Lebar halaman tetap 1200px | Menggunakan lebar fleksibel dan batas maksimum |
| 10 | Memiliki aturan sidebar yang tidak digunakan | Menghapus CSS yang tidak diperlukan |
| 11 | Gambar tidak memiliki alt | Menambahkan teks alternatif yang bermakna |
| 12 | Formulir tidak memiliki label yang sesuai | Menambahkan label dan menghubungkannya ke input |
| 13 | Input email memakai `type="text"` | Menggunakan `type="email"` |
| 14 | Tombol memakai JavaScript alert yang tidak memproses pendaftaran | Menggunakan tombol submit formulir |
| 15 | Tautan menggunakan `href="#"` sebagai placeholder | Mengarahkan tautan ke bagian halaman yang sesuai |
| 16 | Menggunakan `<br>` untuk mengatur jarak | Menggunakan margin dan padding CSS |
| 17 | Footer menggunakan div biasa | Menggunakan elemen `<footer>` |

### Refleksi Code Review

**1. Mengapa HTML semantik penting?**

HTML semantik membuat struktur halaman lebih jelas bagi pengembang, browser, dan teknologi bantu. Elemen seperti `<nav>`, `<main>`, dan `<footer>` menjelaskan fungsi bagian halaman, bukan hanya tampilannya.

**2. Mengapa desain responsif penting?**

Desain responsif membantu halaman tetap mudah dibaca dan digunakan pada berbagai ukuran layar, termasuk ponsel, tablet, dan laptop. Lebar fleksibel serta gambar yang tidak melebihi lebar kontainer membantu mencegah halaman meluber secara horizontal.

**3. Apa risiko menggunakan `!important` secara berlebihan?**

Penggunaan `!important` secara berlebihan membuat cascade CSS lebih sulit dipahami dan aturan lebih sulit ditimpa. Lebih baik menyusun selector dengan tepat dan menjaga struktur stylesheet tetap konsisten.

---

## Part 7 — Exit Ticket

### 1. Apa itu CSS rule?

CSS rule adalah aturan yang menentukan elemen HTML mana yang diberi gaya dan bagaimana tampilannya. Sebuah rule umumnya terdiri dari selector dan blok deklarasi yang berisi property serta value.

### 2. Konsep apa yang masih membingungkan?

[Isi berdasarkan pengalaman belajar sendiri. Contoh: Saya masih perlu berlatih memahami specificity ketika beberapa selector mengatur property yang sama.]

### 3. Apa yang sekarang bisa dilakukan tanpa mencari tutorial?

[Isi berdasarkan kemampuan yang benar-benar dikuasai. Contoh: Saya sudah bisa membuat struktur HTML semantik dan menghubungkan file CSS eksternal.]

---

## Checklist Pengumpulan

- [ ] `answers.md`
- [ ] `profile.html`
- [ ] `style.css`
- [ ] `selector-golf.html`
- [ ] `selector-golf.css`
- [ ] `debug.html`
- [ ] `review-fixed.html`
- [ ] `checkpoints/part2-profile.html`
- [ ] `checkpoints/part3-selector-golf.css`
- [ ] `checkpoints/part4-profile.html`
- [ ] `checkpoints/part4-style.css`
- [ ] `checkpoints/part5-debug-fixed.html`
- [ ] `checkpoints/validator.png`
- [ ] Hasil validasi W3C sudah diperiksa
- [ ] Nama dan NIM sudah benar
- [ ] Semua file sudah disimpan
- [ ] Folder tugas sudah dikompres menjadi ZIP
