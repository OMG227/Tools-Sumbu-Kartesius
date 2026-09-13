# Tools-Sumbu-Kartesius
# Sumbu Kartesius — Alat Bantu Mengajar

Alat bantu mengajar matematika berbasis web (satu file HTML, jalan langsung di browser tanpa instalasi apa pun) untuk menjelaskan konsep sistem koordinat kartesius: titik, garis, bangun datar, dan fungsi.

## Cara pakai

Buka file `sumbu-kartesius.html` di browser (Chrome, Edge, Safari, dsb). Tidak perlu server, tidak perlu koneksi internet setelah dibuka pertama kali (kecuali fitur fungsi matematika yang memuat pustaka MathJS dari CDN saat pertama load).

Cocok dibuka di laptop untuk ditampilkan lewat proyektor, atau di tablet/HP untuk dipakai langsung oleh siswa.

## Navigasi dasar

| Aksi | Cara |
|---|---|
| Geser tampilan | Mode **Geser** → klik-tahan & seret, atau dua jari di layar sentuh |
| Perbesar/perkecil | Scroll mouse, tombol **+ / −** di pojok kanan bawah, atau cubit dua jari |
| Reset tampilan | Tombol **Reset tampilan** di header |

## Fitur

### Tampilan
- Grid tak terhingga dengan sumbu x/y hitam tebal, garis grid hitam tipis di atas latar putih
- Angka sumbu selalu bilangan bulat (tidak pernah pecahan seperti 0.5)
- Toggle: tampilkan/sembunyikan grid, angka sumbu, garis bantu halus
- **Mode sembunyikan koordinat** — untuk kuis: titik tetap terlihat, label angkanya disembunyikan

### Titik
- Mode **Titik**: klik di kanvas untuk menambah titik
- Titik yang sudah ada bisa **digeser** (drag) untuk dipindah, atau **diklik singkat** untuk dihapus
- **Tambah titik manual**: isi nama (opsional) + nilai x + nilai y lewat panel, mendukung angka negatif dan koma sebagai desimal
- **Refleksi titik**: cerminkan titik yang sudah ada terhadap sumbu X, sumbu Y, garis y = x, atau titik asal — otomatis membuat titik baru

### Garis & bangun datar
- **Garis penghubung**: hubungkan dua titik lewat nama atau koordinatnya, lengkap dengan toggle tampil/sembunyi dan label panjang garis di tengahnya
- **Bangun datar (poligon)**: ketik urutan titik (nama atau koordinat, pisahkan koma) untuk membentuk poligon terisi warna, lengkap luas dan keliling otomatis

### Fungsi y = f(x)
- Ketik ekspresi seperti `x^2`, `sin(x)`, `2x+1` untuk menggambar grafiknya
- **Titik potong sumbu x & y** dihitung dan ditandai otomatis pada rentang yang terlihat
- **Arsir**: centang untuk mengarsir daerah antara kurva dan sumbu x
- **Parameter geser (slider)**: gunakan huruf `a, b, c, k, m, n, p, q` di dalam rumus (mis. `a*x + b`) — slider untuk mengubah nilainya secara realtime otomatis muncul

### Pengukuran
- Mode **Ukur**: klik dua titik di kanvas untuk melihat jarak, Δx, Δy, dan kemiringan (m)

### Kelas & administrasi
- **Ekspor**: simpan semua titik, garis, bangun datar, dan fungsi ke file `.json`
- **Impor**: muat kembali file `.json` yang sudah disimpan
- **Cetak**: mencetak tampilan kanvas bersih tanpa toolbar/panel (untuk lembar latihan)
- **Bersihkan semua**: menghapus seluruh titik, garis, bangun datar, dan fungsi

## Struktur file

Semuanya ada dalam satu file `sumbu-kartesius.html` (HTML + CSS + JavaScript), memakai [MathJS](https://mathjs.org/) (via CDN) untuk mem-parsing dan menghitung ekspresi fungsi. Tidak ada dependensi build atau instalasi.

## Batasan yang perlu diketahui

- Titik potong fungsi hanya dihitung pada rentang x yang sedang terlihat di layar (bergerak zoom/geser akan menghitung ulang)
- Slider parameter mendeteksi huruf `a, b, c, k, m, n, p, q` sebagai variabel — huruf `x` selalu dianggap variabel utama
- Fitur ekspor/impor menyimpan data di file lokal (unduhan), bukan di cloud — simpan filenya sendiri jika ingin dipakai lagi nanti
