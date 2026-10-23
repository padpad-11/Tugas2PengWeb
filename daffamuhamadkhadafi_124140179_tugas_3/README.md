# Pendaftaran Seminar Web Development 📝

Tugas Individu 3 — Pertemuan 4: Tabel, Formulir, Layout dan Web Media
Teknik Informatika · ITERA

## 1. Deskripsi

Dua halaman HTML sederhana untuk simulasi pendaftaran seminar:

- **`index.html`** — Halaman pendaftaran berisi informasi acara (tabel) dan
  formulir pendaftaran menggunakan `<form method="get" action="detail.html">`.
  Form ini **hanya mendesain query string** (lewat atribut `name` pada setiap
  input/select/textarea) untuk melempar data ke halaman berikutnya — data
  hasil query string **tidak ditangkap/diproses** oleh JavaScript ataupun
  server.
- **`detail.html`** — Halaman detail informasi pendaftar berisi data
  **dummy/statis** yang ditampilkan dalam bentuk tabel (data diri & status
  tiket).

## 2. Elemen Formulir yang Digunakan

| Elemen | Field |
| --- | --- |
| `input type="text"` | Nama Lengkap, NIM (dengan `pattern`) |
| `input type="email"` | Email |
| `select` + `optgroup` | Program Studi |
| `input list` + `datalist` | Angkatan |
| `input type="date"` | Tanggal Lahir |
| `input type="radio"` | Jenis Kelamin |
| `input type="checkbox"` | Minat Materi (multi pilihan) |
| `textarea` | Pesan / Pertanyaan |
| `button type="submit" / reset"` | Aksi form |

Saat form di-submit, browser otomatis membentuk query string, misal:

```
detail.html?nama=Budi&nim=123456789&email=budi%40mail.com&prodi=informatika&angkatan=2024&tanggal_lahir=2005-08-17&gender=L&minat=html-css&minat=javascript&pesan=Halo
```

## 3. Desain CSS

Dibangun murni dengan **CSS biasa** (tanpa framework), menerapkan materi
Pertemuan 4:

- **Layout**: CSS Grid untuk membagi dua kolom (`index.html`) dan Flexbox
  untuk struktur halaman (`header`, `main`, `footer`) serta tombol aksi form.
- **Box**: komponen `.box` dengan border, border-radius, dan shadow untuk
  mengelompokkan konten (informasi acara, form, data diri, status tiket).
- **Tabel**: `border-collapse`, zebra stripes (`:nth-child(even)`), hover
  effect pada baris, serta `colspan` untuk heading gabungan.
- **Selector** yang digunakan jauh lebih dari 3, di antaranya: element
  selector (`table`, `th`, `td`), class selector (`.box`, `.form-group`,
  `.hint`), id tidak dipakai langsung di CSS namun `id` pada HTML dipakai
  untuk `label[for]`, pseudo-class (`:hover`, `:nth-child`, `:focus`),
  attribute selector (`input[type="text"]`, `input[type="email"]`, dst),
  dan combinator (`.box + .box`, `tr:hover td`).

## 4. Struktur Proyek

```
daffamuhamadkhadafi_124140179_tugas3/
├── index.html
├── detail.html
├── css/
│   └── style.css
└── README.md
```

## 5. Cara Menjalankan

1. Buka folder ini di VS Code.
2. Buka `index.html` langsung di browser, atau jalankan dengan **Live
   Server**.
3. Isi formulir pendaftaran lalu klik **Daftar Sekarang** — browser akan
   mengarah ke `detail.html` beserta query string hasil isian form.
