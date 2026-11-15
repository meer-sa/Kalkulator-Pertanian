# Kalkulator Pertanian

Kumpulan kalkulator sederhana untuk membantu pekerjaan di lahan, dibuat sebagai halaman web statis: tanpa instalasi, tanpa server, dan nyaman dipakai di HP.

## Daftar Kalkulator

| Kalkulator | Buka online | File | Status |
|---|---|---|---|
| Kalkulator Dosis Pestisida | [Buka](https://meer-sa.github.io/Kalkulator-Pertanian/dosis-pestisida/) | [`dosis-pestisida/index.html`](dosis-pestisida/index.html) | Tersedia |
| Kalkulator Populasi Tanaman | [Buka](https://meer-sa.github.io/Kalkulator-Pertanian/populasi-tanaman/) | [`populasi-tanaman/index.html`](populasi-tanaman/index.html) | Tersedia |

Menu semua kalkulator: https://meer-sa.github.io/Kalkulator-Pertanian/

Kalkulator lain akan ditambahkan di sini seiring waktu.

## Kalkulator Dosis Pestisida

Mengubah dosis atau konsentrasi di label kemasan menjadi kebutuhan produk untuk luasan lahan tertentu.

### Fitur

- **Formulasi**: cair (EC, SC, SL, EW, SE, ME, OD, CS, AS), padat larut air (WP, WG/WDG, DF, SP, SG), dan tabur langsung (GR, DP, RB).
- **Empat cara input sesuai data di label**:
  - dosis per liter air (ml/L, g/L, atau % b/v)
  - dosis per hektar (L/ha, kg/ha, ml/ha, g/ha)
  - target konsentrasi dalam ppm bahan aktif
  - target dosis bahan aktif (g b.a./ha)
- **Satuan luas**: hektar, m², are, dan ru (±14 m²).
- **Hasil**: total produk, konsentrasi larutan, dosis per hektar, total air, jumlah tangki, dan produk per tangki. Untuk formulasi tabur ditampilkan dosis per hektar, per m², dan per ru.
- Rumus perhitungan ditampilkan di bawah hasil, dan hasil bisa disalin dengan satu tombol.
- Tampilan terang/gelap otomatis mengikuti pengaturan perangkat.

### Rumus

| Mode | Rumus |
|---|---|
| Dosis per liter | dosis/ha = dosis per liter × volume semprot (L/ha) |
| Dosis per hektar | dosis per liter = dosis/ha ÷ volume semprot (L/ha) |
| Target ppm b.a. | produk per liter = ppm ÷ kandungan b.a. (mg/ml atau mg/g) |
| Target g b.a./ha | produk/ha = g b.a./ha × 1000 ÷ kandungan b.a. (mg/ml atau mg/g) |

Catatan konversi: 1% b/v = 10 ml/L (cair) atau 10 g/L (padat); kandungan 1 g/L sama dengan 1 mg/ml; kandungan 1% b/b sama dengan 10 mg/g.

### Contoh

Label menganjurkan 2 ml/L, volume semprot 400 L/ha, lahan 1 ha, tangki 16 L:

- total produk: 800 ml
- total air: 400 L (25 tangki)
- produk per tangki: 32 ml

## Kalkulator Populasi Tanaman

Menghitung populasi tanaman per hektare dari jarak tanam, lalu menampilkannya dalam berbagai satuan luas.

### Fitur

- **Pola tanam**: persegi panjang, segitiga sama sisi, jajar legowo (n:1), dan bedengan.
- **Isian tambahan**: tanaman per lubang, lahan efektif (%), dan cadangan sulam (%).
- **Satuan luas**: hektare, are, m², bata/ru (14 m²), dan bau (7.096,5 m²).
- **Hasil**: populasi per hektare, per m², per are, per bata/ru, per bau, total tanaman untuk luas lahan Anda, dan kebutuhan bibit termasuk sulam.

### Rumus

| Pola | Lubang tanam per hektare |
|---|---|
| Persegi panjang | 10.000 ÷ (jarak antar baris × jarak dalam baris) |
| Segitiga sama sisi | 10.000 ÷ (0,866 × jarak²) |
| Jajar legowo n:1 | 10.000 × n ÷ (((n − 1) × jarak antar baris + lebar lorong) × jarak dalam baris) |
| Bedengan | 10.000 × baris ÷ ((lebar bedengan + lebar parit) × jarak dalam baris) |

Semua jarak dalam meter. Lebar lorong bawaan pada legowo adalah 2× jarak antar baris. Populasi = lubang tanam × tanaman per lubang × lahan efektif.

Contoh: legowo 2:1 dengan jarak 25 × 12,5 cm menghasilkan 213.333 tanaman/ha, dan legowo 4:1 dengan jarak yang sama menghasilkan 256.000 tanaman/ha.

## Cara Menjalankan

Buka kalkulatornya lewat tautan di tabel **Daftar Kalkulator**, atau buka file `index.html` di folder kalkulator yang diinginkan langsung di browser. Tidak ada proses build maupun dependensi.

Repository ini dipublikasikan lewat GitHub Pages (**Settings → Pages → Deploy from a branch → `main` / `(root)`**) di alamat https://meer-sa.github.io/Kalkulator-Pertanian/.

Font dimuat dari Google Fonts. Tanpa koneksi internet, halaman tetap berfungsi dengan font bawaan perangkat.

## Struktur Repository

Setiap kalkulator dibuat sebagai satu file HTML mandiri (HTML, CSS, dan JavaScript dalam satu file) di foldernya sendiri:

```
Kalkulator-Pertanian/
├── index.html              # menu pilihan kalkulator
├── dosis-pestisida/
│   └── index.html
├── populasi-tanaman/
│   └── index.html
├── README.md
└── LICENSE
```

## Menambah Kalkulator Baru

1. Buat folder baru berisi `index.html`, misalnya `kalkulator-baru/index.html`.
2. Di `index.html` root, salin satu blok tautan kalkulator (`<a class="item" ...>`), lalu ganti `href`, judul, dan deskripsinya.
3. Perbarui tabel **Daftar Kalkulator** di atas.

## Catatan Penting

Alat ini hanya membantu berhitung. Dosis, waktu aplikasi, interval panen, alat pelindung diri, dan cara aplikasi tetap mengikuti **label resmi produk** dan anjuran penyuluh atau instansi setempat. Periksa kembali hasil hitungan sebelum digunakan, dan kalibrasi sprayer Anda agar volume semprot akurat.

## Lisensi

Dirilis dengan lisensi [MIT](LICENSE). Anda bebas memakai, menyalin, dan mengembangkan kode ini, dengan tetap mencantumkan pemberitahuan hak cipta dan lisensinya.
