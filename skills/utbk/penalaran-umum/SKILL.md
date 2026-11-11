---
name: penalaran-umum-r12
description: "Gunakan skill ini saat pengguna menyebut \"Penalaran Umum\", \"PU\", \"latihan PU\", \"soal PU\", \"latihan UTBK PU\", \"latihan TPS PU\", atau frasa serupa yang menandakan ingin latihan subtes Penalaran Umum. Skill ini membuat 30 soal pilihan ganda mencakup tiga tipe soal PU (Penalaran Induktif, Penalaran Deduktif, Penalaran Kuantitatif) dan menyajikannya sebagai widget interaktif tertanam langsung di chat dengan timer hitung mundur 25 menit (1500 detik), intro screen deskripsi resmi UTBK, sistem skoring otomatis (benar = 1 poin), dan pembahasan lengkap di mode review. Tipe soal (kode PU) TIDAK ditampilkan saat mengerjakan soal; hanya muncul di bagian pembahasan setelah submit. Dot navigator: grid 5 per baris, dot berbentuk persegi (bukan persegi panjang). Blok \"Nomor Soal\" + angka di pojok kanan header, angka align center. Exp-box format opsi B: pill tag + huruf opsi + SVG ikon, border warna pill, body teks putih/transparan. Rendering matematika (pecahan, akar, dll) memakai KaTeX, bukan MathJax.\n"
---

# Penalaran Umum r12 — UTBK/TPS Practice

> Skill dibuat oleh **mqsth**
>
> © 2026 Muhammad Rayyis Muqsith ([@muqsith.ai](https://instagram.com/muqsith.ai)). Dilisensikan di bawah [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/). Boleh dipakai dan dimodifikasi untuk non-komersial dengan atribusi. Dilarang menjual, memasukkan ke layanan berbayar, atau mengklaim sebagai karya sendiri. Soal dibuat dengan bantuan AI, bukan soal resmi UTBK/SNBT, dan pembahasan bisa mengandung kekeliruan.

## Overview

Skill ini membuat **widget interaktif tertanam di chat** (bukan file download) berupa ujian **30 soal** Penalaran Umum selama **25 menit**. Setiap kali dipanggil, buat soal **baru yang berbeda** (jangan ulangi soal yang sama).

**Skoring**: Benar = 1 poin, Salah/Kosong = 0 poin.

### Deskripsi Resmi Subtes

Subtes Penalaran Umum bertujuan untuk menilai kemampuan seseorang untuk secara terarah dan terkendali menggunakan prosedur-prosedur untuk memecahkan masalah-masalah baru yang tidak dapat diselesaikan hanya dengan menggunakan kebiasaan-kebiasaan yang sudah dipelajari sebelumnya. Kemampuan yang diujikan terdiri atas:

- **Penalaran Induktif**: kemampuan mengamati fakta-fakta atau kejadian-kejadian untuk menemukan prinsip-prinsip atau aturan-aturan yang mendasarinya.
- **Penalaran Deduktif**: kemampuan bernalar secara logis dengan menggunakan premis-premis dan prinsip-prinsip yang telah diketahui sebelumnya.
- **Penalaran Kuantitatif**: kemampuan berpikir yang melibatkan kuantitas, hubungan matematika sederhana, serta penggunaan operator aritmetika dasar (penjumlahan, pengurangan, perkalian, pembagian).

---

## Tipe Soal & Distribusi (30 Soal)

| Kode | Tipe Soal | Cakupan | Jumlah |
|------|-----------|---------|--------|
| PU-IND | Penalaran Induktif | Deret angka, deret huruf, analogi verbal, pengelompokan (odd one out), pola hubungan antar konsep, analisis wacana/teks (menguatkan, melemahkan, asumsi yang tepat, berlawanan teks) | 10 |
| PU-DED | Penalaran Deduktif | Modus Ponens (p→q + p → q), Modus Tollens (p→q + ~q → ~p), Silogisme (rantai p→q→r→s), Dilema (konstruktif: q∨s / destruktif: ~p∨~r), pernyataan dan negasi (~p), kalimat berkuantor, kualitas kesimpulan (Benar / Salah / Mungkin benar / Tidak Relevan) | 10 |
| PU-KUA | Penalaran Kuantitatif | Deret angka kuantitatif, perbandingan besaran, operasi aritmetika dasar dalam konteks penalaran, menyajikan dan mengolah data dalam bentuk tabel | 10 |

> Semua soal bersifat mandiri (`passageId: null`). Tidak ada soal berbasis wacana panjang.
>
> Ekspresi matematika: gunakan **KaTeX** (bukan MathJax) dengan delimiter inline `\(` dan `\)`. **KRITIS**: di dalam data soal/opsi/pembahasan (`Qs = [...]`, `exps[]`), tulis backslash sebagai HTML numeric entity `&#92;` — bukan backslash literal (`\`) dan bukan double-backslash (`\\`) — karena backslash mentah terbukti hilang saat dikirim lewat tool `visualize:show_widget`. Contoh benar: `"&#92;( &#92;dfrac{3}{4} &#92;)"`. Config JS delimiter (`delimiters: [{left: '\\(', right: '\\)', ...}]`) tetap ditulis pakai double-backslash biasa, tidak perlu entity.
>
> Soal PU-KUA dengan tabel data: embed tabel via HTML `<table class="q-table">` langsung di `q.q`.

---

## Bank Soal (10 Soal — Referensi Pola Saja)

> **PENTING**: HANYA untuk dipelajari polanya. JANGAN gunakan soal ini di widget. Setiap sesi harus menghasilkan 30 soal yang 100% baru dan orisinal.

---

**PU01 [PU-IND — Deret Angka]** `ans:3`
Perhatikan deret berikut: 3, 6, 12, 24, 48, ...
Suku selanjutnya adalah...
A. 72
B. 84
C. 90
D. 96
E. 108
*(Pola: tiap suku dikali 2. 48 × 2 = 96)*

---

**PU02 [PU-IND — Deret Huruf]** `ans:1`
Perhatikan deret huruf: B, D, G, K, P, ...
Huruf selanjutnya adalah...
A. U
B. V
C. W
D. X
E. Y
*(Selisih indeks: +2, +3, +4, +5, +6. P adalah huruf ke-16. 16+6=22 → V)*

---

**PU03 [PU-IND — Analogi Verbal]** `ans:2`
Buku : Perpustakaan :: Lukisan : ...
A. Kanvas
B. Galeri
C. Museum
D. Pameran
E. Seniman
*(Buku disimpan di perpustakaan; lukisan dipajang/disimpan di galeri)*

---

**PU04 [PU-IND — Pengelompokan]** `ans:4`
Manakah yang tidak termasuk satu kelompok dengan yang lain?
A. Demokrasi
B. Oligarki
C. Monarki
D. Aristokrasi
E. Birokrasi
*(Demokrasi, Oligarki, Monarki, Aristokrasi = sistem pemerintahan/bentuk kekuasaan. Birokrasi = sistem tata laksana pemerintahan, bukan bentuk pemerintahan)*

---

**PU05 [PU-DED — Silogisme Kategorikal]** `ans:0`
Semua pegawai negeri mendapat tunjangan. Budi adalah pegawai negeri.
Kesimpulan yang paling tepat adalah...
A. Budi mendapat tunjangan
B. Budi mungkin mendapat tunjangan
C. Budi adalah pegawai yang berprestasi
D. Semua orang yang mendapat tunjangan adalah pegawai negeri
E. Tidak dapat disimpulkan
*(Premis mayor + premis minor → modus ponens: Budi mendapat tunjangan)*

---

**PU06 [PU-DED — Silogisme Kondisional]** `ans:2`
Jika nilai ujian di atas 80, maka siswa dinyatakan lulus. Rini tidak dinyatakan lulus.
Kesimpulan yang benar adalah...
A. Nilai ujian Rini tepat 80
B. Rini tidak mengikuti ujian
C. Nilai ujian Rini tidak di atas 80
D. Rini mengikuti ujian tapi tidak serius
E. Rini lulus dengan nilai pas-pasan
*(Modus tollens: ~lulus → ~(nilai > 80))*

---

**PU07 [PU-DED — Penarikan Kesimpulan]** `ans:3`
Premis 1: Semua atlet profesional berlatih setiap hari.
Premis 2: Sebagian atlet profesional mengikuti olimpiade.
Kesimpulan yang sah adalah...
A. Semua yang berlatih setiap hari adalah atlet profesional
B. Semua peserta olimpiade berlatih setiap hari
C. Tidak ada atlet profesional yang tidak berlatih
D. Sebagian atlet profesional berlatih setiap hari dan mengikuti olimpiade
E. Semua atlet olimpiade adalah atlet profesional
*(Dari P1: semua atlet pro → latih tiap hari. Dari P2: sebagian atlet pro → ikut olimpiade. Irisan keduanya: sebagian atlet pro berlatih tiap hari DAN ikut olimpiade)*

---

**PU08 [PU-KUA — Deret Angka Kuantitatif]** `ans:1`
2, 5, 10, 17, 26, 37, ...
Suku berikutnya adalah...
A. 48
B. 50
C. 52
D. 54
E. 56
*(Selisih: +3, +5, +7, +9, +11, +13 → 37+13=50)*

---

**PU09 [PU-KUA — Perbandingan Besaran]** `ans:0`
Sebuah persegi panjang memiliki panjang 12 cm dan lebar 8 cm. Persegi dengan luas yang sama memiliki sisi sepanjang...
A. \\(4\\sqrt{6}\\) cm
B. 9 cm
C. 10 cm
D. \\(4\\sqrt{5}\\) cm
E. \\(6\\sqrt{2}\\) cm
*(Luas persegi panjang = 12×8 = 96. Sisi persegi = √96 = 4√6)*

---

**PU10 [PU-KUA — Operasi Aritmetika]** `ans:2`
Jika \\(3x - 7 = 14\\), maka nilai dari \\(6x + 5\\) adalah...
A. 42
B. 44
C. 47
D. 49
E. 51
*(3x=21 → x=7. 6(7)+5 = 42+5 = 47)*

---

**PU11 [PU-IND — Analisis Teks]** `ans:1`
Perhatikan wacana berikut:
*"Penggunaan tabir surya secara rutin terbukti mengurangi jumlah bintik hitam di wajah. Sebelum pemakaian, rata-rata pengguna memiliki 6 bintik; setelah tiga bulan pemakaian rutin, jumlahnya turun menjadi 1 bintik."*
Pernyataan manakah yang paling mendukung kesimpulan di atas?
A. Tabir surya mengandung bahan kimia berbahaya
B. Pemakaian tabir surya secara konsisten berkorelasi dengan berkurangnya bintik hitam
C. Semua produk perawatan kulit dapat mengurangi bintik hitam
D. Penurunan bintik hitam disebabkan oleh perubahan pola makan
E. Tabir surya hanya efektif jika digunakan di pagi hari
*(Pernyataan B langsung mendukung klaim bahwa pemakaian rutin → bintik berkurang, sesuai data yang tersaji)*

---

**PU12 [PU-DED — Modus Tollens]** `ans:2`
Jika sensor inframerah mendeteksi objek dalam jarak 1,5 meter, maka pintu geser akan terbuka otomatis. Pintu geser tidak terbuka otomatis.
Kesimpulan yang paling tepat adalah...
A. Sensor inframerah rusak
B. Tidak ada objek yang mendekati pintu
C. Sensor tidak mendeteksi objek dalam jarak 1,5 meter
D. Pintu geser sedang dalam perbaikan
E. Tidak dapat disimpulkan
*(Modus Tollens: p→q, ~q → ~p. ~q = pintu tidak buka → ~p = sensor tidak mendeteksi objek dalam 1,5 m)*

---

**PU13 [PU-DED — Kualitas Kesimpulan]** `ans:0`
Syarat mendapat promosi jabatan: nilai kinerja di atas 85, menyelesaikan minimal 3 proyek, dan mendapat rekomendasi atasan. Andi memperoleh nilai kinerja 88, menyelesaikan 4 proyek, dan mendapat rekomendasi atasan.
Kesimpulan "Andi mendapat promosi jabatan" adalah...
A. Benar
B. Salah
C. Mungkin benar
D. Tidak relevan
E. Tidak dapat dinilai
*(Semua syarat terpenuhi: nilai 88 > 85 ✓, 4 proyek ≥ 3 ✓, rekomendasi ✓ → kesimpulan Benar)*

---

**PU14 [PU-DED — Dilema]** `ans:3`
Jika regulasi tumpang tindih, maka izin usaha sulit diperoleh. Jika izin sulit diperoleh, maka investor kabur.
Pemerintah belum membereskan regulasi tumpang tindih.
Kesimpulan yang paling tepat adalah...
A. Investor pasti tidak kabur
B. Izin usaha mudah diperoleh
C. Regulasi sudah diperbaiki
D. Investor berpotensi kabur
E. Tidak dapat disimpulkan
*(Silogisme: p→q, q→r → p→r. p = regulasi tumpang tindih (belum dibereskan = p masih terjadi) → q → r = investor kabur / berpotensi kabur)*


---

**PU15 [PU-IND — Analisis Teks]** `ans:1`
Perhatikan wacana berikut:
*"Beberapa tahun lalu, A-Phone merupakan merek ponsel terlaris di pasaran. Namun, saat ini penjualan A-Phone terus merosot dan kalah bersaing."*
Pernyataan manakah yang paling tepat menjelaskan kondisi tersebut?
A. A-Phone menaikkan harga jual secara drastis
B. Merek lain menghadirkan fitur yang lebih unggul dari A-Phone
C. Pengguna A-Phone beralih ke merek yang lebih murah
D. A-Phone mengurangi jumlah varian produknya
E. Distribusi A-Phone terbatas di kota-kota besar
*(Penyebab paling logis merosotnya penjualan A-Phone adalah keunggulan fitur kompetitor — menguatkan narasi persaingan pasar)*

---

**PU16 [PU-DED — Silogisme]** `ans:3`
Mahasiswa program D4 wajib melaksanakan praktik kerja lapangan. Seseorang yang ingin terjun ke dunia kerja harus memiliki ijazah D4.
Kesimpulan yang paling tepat adalah...
A. Semua yang punya ijazah D4 sudah terjun ke dunia kerja
B. Praktik kerja lapangan hanya ada di program D4
C. Ijazah D4 tidak diperlukan jika sudah berpengalaman
D. Seseorang yang ingin terjun ke dunia kerja wajib melaksanakan praktik kerja lapangan
E. Tidak dapat disimpulkan
*(Silogisme: p = ingin terjun ke dunia kerja → q = harus ijazah D4 → r = wajib praktik kerja lapangan. Maka p → r)*

---

**PU17 [PU-DED — Kualitas Kesimpulan]** `ans:2`
Syarat boarding maskapai domestik: penumpang wajib menunjukkan salah satu identitas — KTP Elektronik, Paspor, atau KITAS yang masih berlaku (maksimal 5 tahun). Rico tinggal menetap di Indonesia. Rico berhasil boarding menggunakan KTP Elektronik.
Kesimpulan: Rico adalah Warga Negara Indonesia (WNI).
Kualitas kesimpulan tersebut adalah...
A. Benar
B. Salah
C. Mungkin benar
D. Tidak relevan
E. Tidak dapat disimpulkan
*(Premis tidak secara eksplisit menyatakan KTP Elektronik = WNI. Kesimpulan mungkin benar tapi tidak dapat dipastikan dari premis yang tersedia)*

---

**PU18 [PU-DED — Modus Ponens]** `ans:0`
Sebuah sekolah memberlakukan aturan: jika siswa tidak melunasi utang sekolah pada tanggal jatuh tempo, maka dikenakan denda 2% per hari. Pak Haji melunasi utang sekolah 1 hari setelah tanggal jatuh tempo.
Kesimpulan yang paling tepat adalah...
A. Pak Haji dikenakan denda 2% per hari
B. Pak Haji tidak dikenakan denda
C. Sekolah membebaskan denda Pak Haji
D. Pak Haji membayar lebih dari jumlah utang pokok
E. Tidak dapat disimpulkan
*(Modus Ponens: p = tidak melunasi tepat waktu = BENAR (1 hari terlambat), p→q, maka q = dikenakan denda 2% per hari)*

---

**PU19 [PU-DED — Modus Tollens]** `ans:0`
Gula aren produksi Desa P selalu memiliki ciri: warna karamel atau coklat tua, dan warna yang seragam. Sebuah sampel gula aren yang ditemukan berwarna madu, coklat terang, dan tidak seragam.
Kesimpulan yang paling tepat adalah...
A. Gula aren tersebut bukan berasal dari Desa P
B. Gula aren tersebut sudah kadaluarsa
C. Gula aren tersebut merupakan produk palsu
D. Warna gula aren Desa P bervariasi
E. Tidak dapat disimpulkan
*(Modus Tollens: p→q, ~q → ~p. ~q = warna tidak karamel/coklat tua/tidak seragam → ~p = bukan produksi Desa P)*

---

**PU20 [PU-DED — Silogisme]** `ans:0`
Jika jaring penangkap dipasang, maka kondensasi uap air akan terjadi. Jika kondensasi terjadi, maka air dapat diadirkan. Jika air dapat diadirkan, maka warga tidak akan kesulitan mendapatkan air bersih.
Kesimpulan yang paling tepat adalah...
A. Jika jaring penangkap dipasang, warga tidak akan kesulitan mendapat air bersih
B. Jika warga tidak kesulitan mendapat air, berarti jaring sudah dipasang
C. Kondensasi hanya terjadi jika jaring penangkap dipasang
D. Air bersih tersedia tanpa perlu jaring penangkap
E. Tidak dapat disimpulkan
*(Silogisme 3 premis: p→q, q→r, r→s → p→s. p=jaring dipasang, q=kondensasi, r=air diadirkan, s=tidak kesulitan air)*

---

**PU21 [PU-DED — Modus Tollens]** `ans:3`
Jika ada pelatih bintang yang melatih tim, maka supporter akan hadir ramai. Jika tidak ada pelatih yang melatih tim, maka supporter akan sepi. Pertandingan berlangsung dan supporter terlihat sangat sepi.
Kesimpulan yang paling tepat adalah...
A. Pertandingan hari ini tidak menarik bagi supporter
B. Supporter tidak tertarik dengan olahraga ini
C. Pelatih bintang hadir melatih tim hari ini
D. Pelatih bintang tidak melatih tim hari ini
E. Tim tidak membutuhkan pelatih bintang
*(Modus Tollens dari premis 1: p→q, ~q = supporter sepi → ~p = pelatih bintang tidak melatih tim)*

---

---

## Catatan Materi

*Source 1: Papan Tulis | By: MT, 3B | ☑ UTBK H-98 | ☑ TOBK 16-18 Jan 26*
*Source 2: Paket 2 Penalaran Deduktif | By: MI/PU | 27/01/26*

---

### A. Penalaran Induktif

> Menganalisis Wacana/Teks

**1. Sesuai Teks**
- YG Menguatkan
- Asumsi yg tepat

**2. Tidak Sesuai**
- YG Melemahkan
- YG berlawanan Teks

*(Uji Teks)*

---

### B. Penalaran Deduktif

> Penarikan kesimpulan dari khusus ke umum

#### Cara Baca Simbol

| Simbol | Arti |
|--------|------|
| p → q | Jika p maka q |
| p ∨ q | Jika p atau q |
| p ∧ q | Jika p dan q |
| ~p | Negasi p / Ingkaran P (Antonim) atau kalimat negatif |

---

#### 1. Metode Ponens

```
p → q          p → q
p              q
——             ————————————————
q              ≠ tidak ada kesimpulan
```

**Contoh:**
- p = Ingin lulus SNBT
- q = Rajin belajar

> Jika ingin lulus SNBT, maka harus rajin belajar
> Andi ingin lulus SNBT *(p)*
> ∴ **q** (rajin belajar)

```
p → q
p
——
q (harus rajin belajar)
```

**Contoh 2:**
- p = Hari ini hujan
- q = Ayah naik mobil ke kantor

> Jika hari ini hujan, maka ayah naik mobil ke kantor
> Hari ini ayah naik mobil ke kantor *(q)*

```
p → q
q
——
≠ tidak ada kesimpulan
```

---

#### 2. Metode Tollens

```
p → q
~q
——
~p
```

**Contoh:**
- p = Ingin masuk PTN 2026
- q = Belajar di bimbel

> Jika ingin masuk PTN 2026, maka harus belajar di bimbel
> Ica tidak belajar di bimbel *(~q)*

```
p → q
~q
——
~p  ∴ (tidak ingin masuk PTN)
```

---

#### 3. Silogisme

```
p → q        p → q
q → R        q → r
——————       ——————
p → R        p → R

             p → q  ⎫
             q → r  ⎬ → p → s
             R → s  ⎭
```

**Contoh:**
- p = Hari ini hujan
- q = Kakak jajan di warung
- s = Adik tidur

> Jika hari ini hujan, maka kakak jajan di warung *(q)*
> Jika kakak jajan di warung *(q)*, maka adik tidur *(s)*

```
p → q
q → s
——————
p → s  ∴ (Jika hari ini hujan maka adik tidur)
```

---

#### 4. Dilema

| **Konstruktif** | **Destruktif** |
|-----------------|----------------|
| p → q | p → q |
| R → s | R → s |
| p ∨ R | ~q ∨ ~s |
| —— | —— |
| **q ∨ s** | **~p ∨ ~R** |

---

#### 5. Kualitas Kesimpulan

- Benar
- Salah
- Mungkin benar
- Tidak Relevan

---

## Struktur Data JavaScript

Semua soal menggunakan `passageId: null` (mandiri). Format standar:

```javascript
const Qs = [
  {
    passageId: null,
    cat: "Penalaran Induktif",
    sub: "Deret Angka",
    q: "Perhatikan deret: 1, 4, 9, 16, 25, ... Suku ke-7 deret ini adalah...",
    opts: ["36", "42", "49", "56", "64"],
    ans: 2,
    exps: [
      "Letak kesalahan: 36 = 6² adalah suku ke-6, bukan ke-7||Pola: suku ke-n = n²||Suku ke-7: \\(7^2 = 49\\)",
      "Letak kesalahan: 42 bukan bilangan kuadrat sempurna||Pola yang benar: 1, 4, 9, 16, 25, 36, 49||Suku ke-7 = \\(7^2 = 49\\)",
      "Diketahui: deret 1, 4, 9, 16, 25, ...||Identifikasi pola: \\(1^2, 2^2, 3^2, 4^2, 5^2\\)||Pola: suku ke-n = \\(n^2\\)||Suku ke-7: \\(7^2 = 49\\)||Kesimpulan: suku ke-7 adalah 49",
      "Letak kesalahan: 56 bukan bilangan kuadrat||Suku ke-7 = \\(7^2 = 49\\), bukan 56",
      "Letak kesalahan: 64 = \\(8^2\\) = suku ke-8, bukan ke-7||Hitung yang benar: suku ke-7 = \\(7^2 = 49\\)"
    ]
  },
  {
    passageId: null,
    cat: "Penalaran Deduktif",
    sub: "Silogisme",
    q: "Semua burung memiliki sayap. Semua makhluk bersayap bisa terbang. Kelelawar memiliki sayap.\nKesimpulan yang paling tepat adalah...",
    opts: [
      "Kelelawar adalah burung",
      "Kelelawar bisa terbang",
      "Semua burung adalah kelelawar",
      "Hanya kelelawar yang bisa terbang",
      "Tidak dapat disimpulkan"
    ],
    ans: 1,
    exps: [
      "Letak kesalahan: tidak ada premis yang menyatakan kelelawar = burung||Premis hanya menyatakan kelelawar bersayap||Dari P2: bersayap → bisa terbang → kelelawar bisa terbang",
      "Diketahui: P1: semua burung bersayap; P2: semua bersayap bisa terbang; P3: kelelawar bersayap||Terapkan P2 ke P3: kelelawar bersayap → kelelawar bisa terbang||Kesimpulan: kelelawar bisa terbang (modus ponens)||Catatan: dalam logika formal, P2 berlaku universal meski secara biologis tidak semua benar",
      "Letak kesalahan: tidak ada dasar untuk menyimpulkan kelelawar = burung||Premis P1 menghubungkan burung dengan sayap, bukan sebaliknya",
      "Letak kesalahan: generalisasi berlebihan||Premis hanya bicara tentang kelelawar, bukan 'hanya kelelawar'",
      "Letak kesalahan: kesimpulan bisa ditarik dari rantai silogisme||P3 + P2 → kelelawar bisa terbang"
    ]
  }
];
```

> **Catatan**:
> - `q.cat`: gunakan nama tipe soal persis — `"Penalaran Induktif"`, `"Penalaran Deduktif"`, `"Penalaran Kuantitatif"`. Hanya tampil di review mode.
> - `q.sub`: sub-materi soal — wajib diisi, dipakai untuk breakdown result screen. Nilai yang valid:
>   - PU-IND: `"Deret Angka"` / `"Deret Huruf"` / `"Analogi Verbal"` / `"Pengelompokan"` / `"Analisis Teks"`
>   - PU-DED: `"Modus Ponens"` / `"Modus Tollens"` / `"Silogisme"` / `"Dilema"` / `"Pernyataan & Negasi"` / `"Kalimat Berkuantor"` / `"Kualitas Kesimpulan"`
>   - PU-KUA: `"Deret Angka"` / `"Perbandingan Besaran"` / `"Operasi Aritmetika"` / `"Tabel Data"`
> - Interleave urutan: IND, DED, KUA, IND, DED, KUA, ... (10 putaran × 3 tipe = 30 soal).
> - Soal PU-IND mencakup variasi: deret angka, deret huruf, analogi verbal, pengelompokan (odd one out), pola hubungan, analisis wacana/teks (teks pendek → tanya yang menguatkan/melemahkan/asumsi tepat/berlawanan). Pastikan setiap sesi punya campuran variasi ini.
> - Soal PU-DED mencakup variasi: Modus Ponens, Modus Tollens, Silogisme (rantai premis), Dilema (konstruktif/destruktif), pernyataan dan negasi, kalimat berkuantor, kualitas kesimpulan (4 opsi baku: Benar/Salah/Mungkin benar/Tidak Relevan). Hindari fallacy — hanya tawarkan kesimpulan yang sahih secara logis ATAU sengaja memasukkan opsi "tidak dapat disimpulkan" sebagai jawaban valid pada kasus tertentu.
> - Soal PU-KUA mencakup variasi: deret angka (pola selisih/rasio bertingkat), perbandingan dua besaran, operasi aritmetika dasar dalam konteks penalaran angka, menyajikan dan mengolah data tabel (baca, hitung, dan simpulkan dari tabel data).

---

## Format Output

**WAJIB** gunakan `visualize:show_widget`. Panggil `visualize:read_me` dengan `["interactive"]` diam-diam sebelumnya.

---

## CSS Template

```css
* { box-sizing: border-box; margin: 0; padding: 0; }
#qw { font-family: var(--font-sans, system-ui, sans-serif); padding: 1rem 0; max-width: 720px; }
#qw, #qw * { -webkit-user-select: none; -moz-user-select: none; -ms-user-select: none; user-select: none; }
.intro-wrap { max-width: 340px; margin: 0 auto; padding: 1rem 0; text-align: center; }
.intro-utbk { font-size: 10.4px; font-weight: 600; text-transform: uppercase; letter-spacing: .08em; color: var(--color-text-tertiary, #94A3B8); margin-bottom: 6px; }
.intro-title { font-size: 20.3px; font-weight: 500; color: var(--color-text-primary, #1E293B); margin-bottom: 16px; }
.intro-stats-row { display: flex; justify-content: space-around; padding: 0 1rem; }
.intro-stat-key { font-size: 10.4px; color: var(--color-text-tertiary, #94A3B8); }
.intro-stat-val { font-size: 25.4px; font-weight: 500; color: var(--color-text-primary, #1E293B); }
.intro-divider { border: none; border-top: 0.5px solid var(--color-border-tertiary, #E2E8F0); margin: 12px 0; }
.top-bar { display: flex; justify-content: flex-end; align-items: center; margin-bottom: 10px; }
.content-header { display: flex; align-items: center; margin-bottom: 1rem; padding-bottom: 10px; border-bottom: 0.5px solid var(--color-border-tertiary, #E2E8F0); }
.content-header-label { font-size: 10.4px; font-weight: 600; color: var(--color-text-tertiary, #94A3B8); text-transform: uppercase; letter-spacing: .06em; line-height: 1.4; }
.content-header-center { margin-left: auto; text-align: center; }
.q-num-label { font-size: 8.3px; font-weight: 600; text-transform: uppercase; letter-spacing: .08em; color: var(--color-text-tertiary, #94A3B8); }
.q-num-val { font-size: 20.3px; font-weight: 500; color: var(--color-text-primary, #1E293B); text-align: center; }
.timer-box { display: flex; align-items: center; gap: 6px; font-size: 13px; font-weight: 500; color: var(--color-text-secondary, #64748B); }
.timer-box.warn { color: #D85A30; }
.nav-dots { display: grid; grid-template-columns: repeat(5, 26px); gap: 4px; flex-shrink: 0; }
.dot { width: 26px; height: 26px; border-radius: 0; border: 0.5px solid var(--color-border-tertiary, #E2E8F0); background: var(--color-background-primary, #fff); font-size: 10.4px; font-weight: 500; cursor: pointer; display: flex; align-items: center; justify-content: center; color: var(--color-text-secondary, #64748B); transition: all 0.15s; }
.dot.active { border: 1.5px solid var(--color-text-primary, #1E293B); color: var(--color-text-primary, #1E293B); }
.dot.answered { background: var(--color-text-primary, #1E293B); color: var(--color-background-primary, #fff); border-color: var(--color-text-primary, #1E293B); }
.dot.done-correct { background: #E1F5EE; border-color: #1D9E75; color: #085041; }
.dot.done-wrong { background: #FAECE7; border-color: #D85A30; color: #4A1B0C; }
.quiz-body { display: flex; gap: 12px; align-items: flex-start; }
.quiz-main { flex: 1; min-width: 0; }
.q-area { margin-bottom: 1rem; }
.q-meta { font-size: 10.4px; color: var(--color-text-tertiary, #94A3B8); text-transform: uppercase; letter-spacing: .05em; margin-bottom: 6px; }
.q-text { font-size: 16.3px; color: var(--color-text-primary, #1E293B); line-height: 1.65; margin-bottom: 1.25rem; font-weight: 500; }
.opts { display: flex; flex-direction: column; gap: 8px; }
.opt { background: var(--color-background-primary, #fff); border: 0.5px solid var(--color-border-tertiary, #E2E8F0); border-radius: 10px; padding: 11px 14px; cursor: pointer; font-size: 13px; color: var(--color-text-primary, #1E293B); text-align: left; display: flex; gap: 10px; align-items: flex-start; transition: border-color 0.12s; font-family: inherit; }
.opt:hover:not(:disabled) { background: var(--color-background-secondary, #F8FAFC); border-color: var(--color-border-secondary, #CBD5E1); }
.opt-radio { width: 14px; min-width: 14px; height: 14px; border-radius: 50%; border: 1.5px solid var(--color-border-secondary, #CBD5E1); margin-top: 3px; flex-shrink: 0; display: flex; align-items: center; justify-content: center; }
.opt.selected .opt-radio { border-color: var(--color-text-primary, #1E293B); }
.opt.selected .opt-radio::after { content: ''; width: 6px; height: 6px; border-radius: 50%; background: var(--color-text-primary, #1E293B); display: block; }
.opt.selected { border-color: var(--color-border-primary, #CBD5E1); }
.opt.correct { border-color: #1D9E75; background: #E1F5EE; }
.opt.correct .opt-radio { border-color: #1D9E75; }
.opt.correct .opt-radio::after { content: ''; width: 6px; height: 6px; border-radius: 50%; background: #1D9E75; display: block; }
.opt.wrong { border-color: #D85A30; background: #FAECE7; }
.opt.wrong .opt-radio { border-color: #D85A30; }
.opt.wrong .opt-radio::after { content: ''; width: 6px; height: 6px; border-radius: 50%; background: #D85A30; display: block; }
.opt:disabled { cursor: default; }
.exp-box { margin-top: 10px; display: flex; flex-direction: column; gap: 6px; font-size: 13px; line-height: 1.6; }
.exp-block { border-radius: 8px; overflow: hidden; }
.exp-block.exp-wrong-block { border: 0.5px solid #F0997B; }
.exp-block.exp-correct-block { border: 0.5px solid #5DCAA5; }
.exp-head { display: flex; align-items: center; gap: 6px; padding: 6px 10px; }
.exp-block.exp-wrong-block .exp-head { background: #FAECE7; }
.exp-block.exp-correct-block .exp-head { background: #E1F5EE; }
.exp-pill { font-size: 9px; font-weight: 700; letter-spacing: .06em; text-transform: uppercase; padding: 2px 7px; border-radius: 3px; flex-shrink: 0; }
.exp-block.exp-wrong-block .exp-pill { background: #F0997B; color: #4A1B0C; }
.exp-block.exp-correct-block .exp-pill { background: #5DCAA5; color: #04342C; }
.exp-opt-lbl { font-size: 13px; font-weight: 600; flex-shrink: 0; }
.exp-block.exp-wrong-block .exp-opt-lbl { color: #4A1B0C; }
.exp-block.exp-correct-block .exp-opt-lbl { color: #085041; }
.exp-svg { flex-shrink: 0; display: flex; align-items: center; }
.exp-body { padding: 8px 10px; background: var(--color-background-primary, #fff); color: var(--color-text-secondary, #64748B); font-size: 13px; line-height: 1.6; }
.exp-steps { display: flex; flex-direction: column; gap: 4px; margin-top: 4px; }
.exp-step { display: flex; gap: 8px; align-items: flex-start; }
.exp-step-num { flex-shrink: 0; font-weight: 600; color: #1D9E75; min-width: 18px; }
.exp-block.exp-wrong-block .exp-step-num { color: #D85A30; }
.exp-step-txt { flex: 1; line-height: 1.7; }
.sub-inline { display: inline-block; vertical-align: top; }
.bottom-nav { display: flex; gap: 8px; margin-top: 1.25rem; align-items: center; justify-content: flex-start; }
.btn-nav { background: var(--color-background-primary, #fff); border: 0.5px solid var(--color-border-tertiary, #E2E8F0); border-radius: 8px; padding: 9px 18px; font-size: 13px; cursor: pointer; font-family: inherit; color: var(--color-text-primary, #1E293B); }
.btn-nav:hover { background: var(--color-background-secondary, #F8FAFC); }
.btn-primary { background: var(--color-text-primary, #1E293B); color: var(--color-background-primary, #fff); border: none; border-radius: 8px; padding: 9px 18px; font-size: 13px; cursor: pointer; font-family: inherit; }
.btn-primary:hover { opacity: 0.85; }
.review-banner { font-size: 10.4px; color: var(--color-text-tertiary, #94A3B8); text-align: center; padding: 6px 0; margin-bottom: 8px; letter-spacing: .04em; text-transform: uppercase; }
.result-wrap { padding: 1rem 0; }
.r-hero { text-align: center; margin-bottom: 1.5rem; }
.r-score-big { font-size: 62px; font-weight: 500; line-height: 1; color: var(--color-text-primary, #1E293B); }
.r-of { font-size: 16.3px; color: var(--color-text-tertiary, #94A3B8); margin-bottom: 6px; }
.r-grade { font-size: 16.3px; font-weight: 500; margin-bottom: 4px; }
.r-msg { font-size: 13px; color: var(--color-text-secondary, #64748B); }
.r-stats { display: grid; grid-template-columns: repeat(2, 1fr); gap: 10px; margin-bottom: 1.5rem; }
.r-stat { background: var(--color-background-secondary, #F8FAFC); border-radius: 8px; padding: 12px; text-align: center; }
.r-stat-val { font-size: 20.3px; font-weight: 500; color: var(--color-text-primary, #1E293B); }
.r-stat-lbl { font-size: 10.4px; color: var(--color-text-tertiary, #94A3B8); margin-top: 2px; }
.r-breakdown { margin-bottom: 1.5rem; }
.r-bd-title { font-size: 10.4px; color: var(--color-text-tertiary, #94A3B8); text-transform: uppercase; letter-spacing: .05em; margin-bottom: 10px; }
.r-bd-group { border-bottom: 0.5px solid var(--color-border-tertiary, #E2E8F0); padding-bottom: 8px; margin-bottom: 8px; }
.r-bd-group:last-child { border-bottom: none; margin-bottom: 0; padding-bottom: 0; }
.r-bd-row { display: flex; justify-content: space-between; align-items: center; padding: 6px 0; font-size: 13px; }
.r-bd-cat { color: var(--color-text-primary, #1E293B); font-weight: 500; }
.r-bd-score { font-weight: 500; }
.r-bd-sub-row { display: flex; justify-content: space-between; align-items: center; padding: 3px 0 3px 12px; font-size: 11.5px; }
.r-bd-sub-cat { color: var(--color-text-tertiary, #94A3B8); }
.r-bd-sub-score { color: var(--color-text-secondary, #64748B); }
.r-actions { display: flex; gap: 8px; margin-bottom: 2rem; }
.r-credit { text-align: left; }
.r-credit-built { font-size: 8.3px; font-weight: 600; letter-spacing: .1em; text-transform: uppercase; color: var(--color-text-tertiary, #94A3B8); margin-bottom: 4px; }
.r-credit-handle { display: flex; align-items: center; gap: 5px; font-size: 13px; font-weight: 500; color: var(--color-text-primary, #1E293B); }
.r-credit-handle a { color: inherit; text-decoration: none; }
.r-credit-fb { font-size: 10.4px; color: var(--color-text-tertiary, #94A3B8); margin-top: 3px; }
table.q-table { width: 100%; border-collapse: collapse; margin: 0.5rem 0 1rem; font-size: 13px; }
table.q-table th { background: var(--color-background-secondary, #F8FAFC); font-weight: 600; text-align: center; border: 0.5px solid var(--color-border-secondary, #CBD5E1); padding: 6px 8px; }
table.q-table td { border: 0.5px solid var(--color-border-tertiary, #E2E8F0); padding: 6px 8px; text-align: center; }
```

---

## HTML Skeleton Widget

```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.16.9/katex.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.16.9/katex.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/KaTeX/0.16.9/contrib/auto-render.min.js"></script>
<style>/* CSS di atas */</style>
<div id="qw">
  <div id="intro-screen">
    <div class="intro-wrap">
      <div class="intro-utbk">UTBK / TPS</div>
      <div class="intro-title">Penalaran Umum</div>
      <div class="intro-stats-row">
        <div><div class="intro-stat-key">Soal</div></div>
        <div><div class="intro-stat-key">Waktu</div></div>
      </div>
      <hr class="intro-divider">
      <div class="intro-stats-row">
        <div><div class="intro-stat-val">30</div></div>
        <div><div class="intro-stat-val">25:00</div></div>
      </div>
      <hr class="intro-divider" style="margin-bottom:1.5rem">
      <button class="btn-primary" style="width:100%;padding:10px 0" onclick="startQuiz()">Mulai ujian</button>
    </div>
  </div>
  <div id="quiz-screen" style="display:none">
    <div class="top-bar">
      <div class="timer-box" id="timer-el">
        <svg width="13" height="13" viewBox="0 0 13 13" fill="none"><circle cx="6.5" cy="6.5" r="5.5" stroke="currentColor" stroke-width="1"/><path d="M6.5 3.5V6.5L8.5 8" stroke="currentColor" stroke-width="1" stroke-linecap="round"/></svg>
        <span id="timer-txt">25:00</span>
      </div>
    </div>
    <div class="quiz-body">
      <div class="nav-dots" id="nav-dots"></div>
      <div class="quiz-main">
        <div class="content-header">
          <div class="content-header-label">Penalaran<br>Umum</div>
          <div class="content-header-center">
            <div class="q-num-label">Nomor Soal</div>
            <div class="q-num-val" id="q-num-val">1</div>
          </div>
        </div>
        <div class="review-banner" id="review-banner" style="display:none">MODE REVIEW</div>
        <div class="q-area" id="q-area"></div>
        <div class="bottom-nav">
          <button class="btn-nav" id="btn-prev" onclick="goTo(cur-1)">Prev</button>
          <button class="btn-primary" id="btn-next" onclick="handleNext()">Next</button>
        </div>
      </div>
    </div>
  </div>
  <div id="result-screen" style="display:none"></div>
</div>
<script>/* Qs[] + JS template */</script>
```

---

## Template JS Lengkap

```javascript
// Qs[] di sini (30 soal baru setiap sesi)

function shuffleArray(arr) {
  for (let i = arr.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [arr[i], arr[j]] = [arr[j], arr[i]];
  }
}

let cur = 0, answers = new Array(Qs.length).fill(null);
let revealed = new Array(Qs.length).fill(false);
let totalSec = 1500, timerInt, quizDone = false, reviewMode = false;

function startQuiz() {
  shuffleArray(Qs);
  document.getElementById('intro-screen').style.display = 'none';
  document.getElementById('quiz-screen').style.display = 'block';
  startTimer(); renderQ();
}

function buildDots() {
  const wrap = document.getElementById('nav-dots'); wrap.innerHTML = '';
  Qs.forEach((_, i) => {
    const d = document.createElement('div');
    d.className = 'dot' + (i === cur ? ' active' : '');
    if (answers[i] !== null && revealed[i]) d.classList.add(answers[i] === Qs[i].ans ? 'done-correct' : 'done-wrong');
    else if (answers[i] !== null) d.classList.add('answered');
    d.textContent = i + 1;
    d.onclick = () => goTo(i);
    wrap.appendChild(d);
  });
}

function goTo(i) { cur = i; renderQ(); }

function handleNext() {
  if (quizDone || reviewMode) {
    if (cur === Qs.length - 1) { showResult(); return; }
    goTo(cur + 1); return;
  }
  if (cur === Qs.length - 1) { finalSubmit(); return; }
  goTo(cur + 1);
}

function renderQ() {
  const q = Qs[cur];
  document.getElementById('q-num-val').textContent = cur + 1;
  buildDots();
  let html = '';
  if (revealed[cur]) html += `<div class="q-meta">${q.cat} · ${q.sub||''}</div>`;
  html += `<div class="q-text">${q.q.replace(/\n/g,'<br>')}</div><div class="opts">`;
  q.opts.forEach((o, i) => {
    let cls = 'opt';
    if (answers[cur] === i) cls += ' selected';
    if (revealed[cur]) {
      if (i === q.ans) cls += ' correct';
      else if (answers[cur] === i) cls += ' wrong';
    }
    const dis = (revealed[cur] || quizDone) ? 'disabled' : '';
    html += `<button class="${cls}" onclick="selectOpt(${i})" ${dis}><span class="opt-radio"></span><span>${o}</span></button>`;
  });
  html += '</div>';
  if (revealed[cur]) {
    const userAns = answers[cur];
    const optLabels = ['A','B','C','D','E'];
    const svgX = `<svg width="14" height="14" viewBox="0 0 14 14" fill="none"><circle cx="7" cy="7" r="6.5" stroke="#D85A30" stroke-width="1"/><path d="M4.5 4.5L9.5 9.5M9.5 4.5L4.5 9.5" stroke="#D85A30" stroke-width="1.4" stroke-linecap="round"/></svg>`;
    const svgC = `<svg width="14" height="14" viewBox="0 0 14 14" fill="none"><circle cx="7" cy="7" r="6.5" stroke="#1D9E75" stroke-width="1"/><path d="M4 7L6.2 9.2L10 5" stroke="#1D9E75" stroke-width="1.4" stroke-linecap="round" stroke-linejoin="round"/></svg>`;
    let expContent = '';
    function renderSteps(text) {
      const splitSubs = s => {
        const items = s.split(/\s*(?:⇒|=>|→|;)\s*/).map(x => x.trim()).filter(Boolean);
        if (items.length <= 1) return items[0] || '';
        return `<span class="sub-inline">${items.join('<br>')}</span>`;
      };
      const parts = text.split('||').map(s => s.trim()).filter(Boolean);
      if (parts.length <= 1) return `<div class="exp-step-txt">${splitSubs(parts[0] || '')}</div>`;
      return `<div class="exp-steps">${parts.map((p, i) => {
        const colonIdx = p.indexOf(':');
        let label = '', body = p;
        if (colonIdx > 0 && colonIdx < 40) {
          label = `<strong>${p.slice(0, colonIdx)}:</strong> `;
          body = p.slice(colonIdx + 1).trim();
        }
        return `<div class="exp-step"><span class="exp-step-num">${i+1}.</span><span class="exp-step-txt">${label}${splitSubs(body)}</span></div>`;
      }).join('')}</div>`;
    }
    if (userAns !== null && userAns !== q.ans && q.exps && q.exps[userAns]) {
      expContent += `<div class="exp-block exp-wrong-block"><div class="exp-head"><span class="exp-pill">Pilihanmu</span><span class="exp-opt-lbl">${optLabels[userAns]}</span><span class="exp-svg">${svgX}</span></div><div class="exp-body">${renderSteps(q.exps[userAns])}</div></div>`;
    } else if (userAns !== null && userAns !== q.ans) {
      expContent += `<div class="exp-block exp-wrong-block"><div class="exp-head"><span class="exp-pill">Pilihanmu</span><span class="exp-opt-lbl">${optLabels[userAns]}</span><span class="exp-svg">${svgX}</span></div><div class="exp-body"><div class="exp-step-txt">Lihat pembahasan jawaban benar di bawah.</div></div></div>`;
    }
    const correctExp = q.exps ? q.exps[q.ans] : q.exp;
    const correctLbl = optLabels[q.ans];
    const correctPillTxt = (userAns === q.ans) ? 'Pilihanmu' : 'Jawaban Benar';
    expContent += `<div class="exp-block exp-correct-block"><div class="exp-head"><span class="exp-pill">${correctPillTxt}</span><span class="exp-opt-lbl">${correctLbl}</span><span class="exp-svg">${svgC}</span></div><div class="exp-body">${renderSteps(correctExp || 'Lihat kembali langkah penyelesaian soal ini.')}</div></div>`;
    html += `<div class="exp-box">${expContent}</div>`;
  }
  document.getElementById('q-area').innerHTML = html;
  if (typeof renderMathInElement !== 'undefined') {
    renderMathInElement(document.getElementById('q-area'), {
      delimiters: [{left: '\\(', right: '\\)', display: false}]
    });
  }
  document.getElementById('btn-prev').style.display = cur === 0 ? 'none' : '';
  if (reviewMode) {
    document.getElementById('btn-next').textContent = cur === Qs.length-1 ? 'Lihat Hasil' : 'Next';
  } else {
    document.getElementById('btn-next').textContent = cur === Qs.length-1 ? 'Submit' : 'Next';
  }
}

function selectOpt(i) {
  if (revealed[cur] || quizDone) return;
  if (answers[cur] === i) { answers[cur] = null; } else { answers[cur] = i; }
  renderQ();
}

function finalSubmit() {
  clearInterval(timerInt); quizDone = true;
  revealed = new Array(Qs.length).fill(true); showResult();
}

function startTimer() {
  timerInt = setInterval(() => {
    totalSec--;
    const m = Math.floor(totalSec/60), s = totalSec%60;
    const el = document.getElementById('timer-el');
    if (el) document.getElementById('timer-txt').textContent = `${String(m).padStart(2,'0')}:${String(s).padStart(2,'0')}`;
    if (totalSec <= 300 && el) el.className = 'timer-box warn';
    if (totalSec <= 0) { clearInterval(timerInt); finalSubmit(); }
  }, 1000);
}

function showResult() {
  document.getElementById('quiz-screen').style.display = 'none';
  const rs = document.getElementById('result-screen'); rs.style.display = 'block';
  const correct = answers.filter((a,i) => a === Qs[i].ans).length;
  const wrong = answers.filter((a,i) => a !== null && a !== Qs[i].ans).length;
  const pct = Math.round(correct/Qs.length*100);
  const cats = {};
  Qs.forEach((q,i) => { if (!cats[q.cat]) cats[q.cat]={correct:0,total:0,subs:{}}; cats[q.cat].total++; if (answers[i]===q.ans) cats[q.cat].correct++; if (q.sub) { if (!cats[q.cat].subs[q.sub]) cats[q.cat].subs[q.sub]={correct:0,total:0}; cats[q.cat].subs[q.sub].total++; if (answers[i]===q.ans) cats[q.cat].subs[q.sub].correct++; } });
  let grade, msg;
  if (pct>=90) { grade='Excellent'; msg='Kemampuan penalaranmu sangat tajam! Siap UTBK!'; }
  else if (pct>=75) { grade='Proficient'; msg='Hasil bagus! Latih lebih lanjut tipe yang masih lemah.'; }
  else if (pct>=60) { grade='Developing'; msg='Fondasi sudah ada. Perbanyak latihan pola soal serupa.'; }
  else { grade='Perlu Latihan'; msg='Perlu lebih banyak latihan. Ulangi konsep dasar dan coba lagi.'; }
  let bdRows = '';
  ['Penalaran Induktif','Penalaran Deduktif','Penalaran Kuantitatif'].forEach(cat => {
    const d = cats[cat]; if (!d) return;
    const subRows = Object.entries(d.subs).map(([sub,sd]) => `<div class="r-bd-sub-row"><span class="r-bd-sub-cat">${sub}</span><span class="r-bd-sub-score">${sd.correct}/${sd.total}</span></div>`).join('');
    bdRows += `<div class="r-bd-group"><div class="r-bd-row"><span class="r-bd-cat">${cat}</span><span class="r-bd-score">${d.correct}/${d.total}</span></div>${subRows}</div>`;
  });
  rs.innerHTML = `<div class="result-wrap"><div class="r-hero"><div class="r-score-big">${correct}</div><div class="r-of">/ 30 benar</div><div class="r-grade">${grade}</div><div class="r-msg">${msg}</div></div><div class="r-stats"><div class="r-stat"><div class="r-stat-val">${correct}</div><div class="r-stat-lbl">Benar</div></div><div class="r-stat"><div class="r-stat-val">${wrong}</div><div class="r-stat-lbl">Salah</div></div></div><div class="r-breakdown"><div class="r-bd-title">Breakdown per kategori</div>${bdRows}</div><div class="r-actions"><button class="btn-nav" onclick="reviewAnswers()">Review jawaban</button><button class="btn-primary" onclick="restartQuiz()">Coba lagi</button></div><div class="r-credit"><div class="r-credit-built">BUILT BY</div><div class="r-credit-handle"><svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="2" width="20" height="20" rx="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="1" fill="currentColor" stroke="none"/></svg><a href="https://www.instagram.com/muqsith.ai/" target="_blank">@muqsith.ai</a></div><div class="r-credit-fb">Feedback &amp; saran? DM aja 👋</div></div></div>`;
}

function reviewAnswers() {
  reviewMode = true;
  document.getElementById('quiz-screen').style.display = 'block';
  document.getElementById('result-screen').style.display = 'none';
  document.getElementById('review-banner').style.display = 'block';
  cur = 0; renderQ();
}

function restartQuiz() {
  shuffleArray(Qs);
  cur = 0; answers = new Array(Qs.length).fill(null);
  revealed = new Array(Qs.length).fill(false);
  totalSec = 1500; quizDone = false; reviewMode = false;
  document.getElementById('quiz-screen').style.display = 'block';
  document.getElementById('result-screen').style.display = 'none';
  document.getElementById('review-banner').style.display = 'none';
  const te = document.getElementById('timer-el'); if (te) te.className = 'timer-box';
  clearInterval(timerInt); startTimer(); renderQ();
}

document.addEventListener('DOMContentLoaded', function() {
  var qw = document.getElementById('qw');
  if (qw) {
    qw.addEventListener('copy', function(e) { e.preventDefault(); });
    qw.addEventListener('contextmenu', function(e) { e.preventDefault(); });
  }
});
```

---

## Instruksi Tambahan

- **Timer**: 1500 detik (25:00). Warn merah saat `totalSec <= 300` (5 menit tersisa).
- **Soal**: 30 soal mandiri, semua `passageId: null`. Tidak ada passages[].
- **Distribusi wajib**: 10 soal per tipe (IND, DED, KUA). Interleave urutan: IND, DED, KUA, IND, DED, KUA, ... (10 putaran).
- **PU-IND** harus mencakup minimal 4 variasi berbeda dalam satu sesi: deret angka, deret huruf, analogi verbal, pengelompokan. Variasi opsional: analisis wacana/teks (sajikan teks pendek 2–4 kalimat, tanya pernyataan mana yang menguatkan, melemahkan, atau merupakan asumsi yang tepat). Dilarang seluruh 10 soal bertipe sama.
- **PU-DED** harus mencakup minimal 3 metode berbeda per sesi: Modus Ponens (p→q + p → q), Modus Tollens (p→q + ~q → ~p), Silogisme (rantai ≥2 premis). Variasi tambahan: Dilema konstruktif (p∨r + p→q + r→s → q∨s) atau destruktif (~q∨~s → ~p∨~r), pernyataan dan negasi (~p = ingkaran/antonim), kalimat berkuantor (semua/sebagian/tidak ada). Soal Kualitas Kesimpulan wajib menggunakan 4 opsi baku: **Benar / Salah / Mungkin benar / Tidak Relevan**. Simbol yang boleh dipakai di teks soal: `→` (jika-maka), `∨` (atau), `∧` (dan), `~` (negasi). Penarikan kesimpulan "tidak dapat disimpulkan" boleh dipakai sebagai jawaban valid tapi tidak lebih dari 2 soal per sesi.
- **PU-KUA** harus mencakup minimal 3 variasi: deret angka (pola selisih atau rasio bertingkat), operasi/perbandingan angka, dan tabel data (menyajikan dan mengolah data dalam bentuk tabel — baca nilai, hitung rata-rata/selisih/total dari data tabel). Soal boleh menggunakan KaTeX untuk ekspresi aljabar dan `<table class="q-table">` untuk embed tabel.
- **KaTeX**: setelah `renderQ()` set innerHTML, panggil `renderMathInElement(q-area, {delimiters: [{left: '\(', right: '\)', display: false}]})`. Delimiter inline `\(`/`\)`. Backslash LaTeX di dalam data soal/opsi/pembahasan (`Qs = [...]`, `exps[]`) WAJIB ditulis sebagai `&#92;` (HTML entity) — bukan backslash literal atau double-backslash.
- **Tabel**: untuk soal dengan data kuantitatif, embed `<table class="q-table">` di dalam `q.q`.
- **q.cat**: nama tipe soal persis — `"Penalaran Induktif"`, `"Penalaran Deduktif"`, `"Penalaran Kuantitatif"`. Hanya tampil di review mode.
- **q.sub**: sub-materi soal — **WAJIB** diisi tiap soal. Nilai valid per kategori:
  - PU-IND: `"Deret Angka"` / `"Deret Huruf"` / `"Analogi Verbal"` / `"Pengelompokan"` / `"Analisis Teks"`
  - PU-DED: `"Modus Ponens"` / `"Modus Tollens"` / `"Silogisme"` / `"Dilema"` / `"Pernyataan & Negasi"` / `"Kalimat Berkuantor"` / `"Kualitas Kesimpulan"`
  - PU-KUA: `"Deret Angka"` / `"Perbandingan Besaran"` / `"Operasi Aritmetika"` / `"Tabel Data"`
- **Opsi jawaban**: TIDAK diawali prefix huruf. Langsung teks. 5 opsi per soal, index 0–4.
- **Pembahasan (exps[]) wajib berbentuk langkah-langkah**: `exps` adalah array 5 elemen (index 0–4). Pisahkan tiap langkah dengan `||`. Minimum: `exps[ans]` minimal 3 langkah, `exps[i]` opsi salah minimal 2 langkah. DILARANG satu blok teks panjang tanpa `||`.
  - Format tiap langkah: `Label singkat: penjelasan` — teks sebelum titik dua pertama akan di-**bold** otomatis. Contoh label: `Diketahui`, `Identifikasi pola`, `Hitung`, `Periksa premis`, `Terapkan aturan`, `Kesimpulan`, `Letak kesalahan`.
  - Opsi salah WAJIB punya langkah `Letak kesalahan: ...` yang menjelaskan spesifik di mana penalarannya meleset.
  - **DILARANG duplikasi penuh derivasi jawaban benar di exps opsi salah**: `Letak kesalahan` cukup 1-2 langkah fokus menjelaskan miskonsepsi spesifiknya saja. JANGAN tulis ulang seluruh langkah pola/hitung yang sudah ada di exps jawaban benar — itu sudah tampil terpisah di mode review, jadi tidak perlu diulang.
  - DILARANG awali exps dengan "✓ Benar." atau "✗ Salah."
  - DILARANG pakai simbol `@` sebagai shorthand.
  - **DILARANG menggunakan bahasa ragu-ragu atau hedging** di pembahasan: frasa seperti "jika pembuat soal", "kemungkinan", "mungkin maksudnya", "tergantung interpretasi", "bisa jadi" TIDAK BOLEH muncul di exps. Pembahasan harus tegas dan langsung.
  - **DILARANG menampilkan proses verifikasi internal** di `exps[]`: kata-kata seperti "Tunggu", "Cek ulang", "Periksa lagi", "Hmm", atau bentuk self-correction apapun TIDAK BOLEH muncul. Pembahasan harus bersih dan student-facing, bukan stream of thought.
  - **DILARANG tulis pembagian dengan slash** (`330/4`, `250/3`, `(85+90+75)/3`, dst.) di dalam ekspresi matematika. WAJIB gunakan `&#92;(&#92;frac{}{} &#92;)` agar tampil sebagai pecahan atas-bawah via KaTeX. Contoh benar: `&#92;(&#92;frac{250}{3} &#92;approx 83{,}33&#92;)`. Contoh salah: `250/3 ≈ 83,33` atau `(85+90+75)/3`. Aturan ini berlaku untuk SEMUA pembagian di seluruh `exps[]`, tanpa pengecualian.
  - **WAJIB LaTeX untuk SEMUA ekspresi matematika**, bukan cuma pembagian: persamaan (`2x+3y=17`), substitusi (`2(y+1)+3y=17`), hasil aljabar (`5y=15`), nilai variabel (`y=3`), dsb. SEMUA harus dibungkus `&#92;( ... &#92;)`. Contoh benar: `&#92;(2x+3y=17&#92;)` dan `&#92;(x-y=1&#92;)`. Contoh salah (DILARANG): teks polos `2x + 3y = 17 dan x - y = 1` tanpa delimiter KaTeX, atau menulis backslash literal/double-backslash (`\(2x+3y=17\)`, `\\(2x+3y=17\\)`) yang akan hilang saat dikirim ke widget. Berlaku di semua bagian exps, termasuk langkah substitusi dan hitung.
  - **DILARANG kontradiksi antara langkah hitung dan kesimpulan**: nilai akhir yang disebut di langkah "Kesimpulan" WAJIB sama dengan hasil yang sudah dihitung di langkah sebelumnya. Sebelum menulis exps final, cek ulang secara internal bahwa angka di "Kesimpulan" identik dengan hasil hitung terakhir — jangan munculkan angka baru yang tidak pernah dihitung sebelumnya (misal hasil hitung menyatakan 15 lalu kesimpulan menyebut 13). Jika ada keraguan saat menyusun langkah, selesaikan keraguan itu SEBELUM menulis exps — jangan tuliskan proses keraguannya ke dalam exps.
  - **Soal tabel data**: pastikan hanya ada SATU jawaban yang benar secara matematis. Jika dua opsi ternyata identik, buang soal itu dan buat ulang dengan nilai yang menghasilkan jawaban tunggal.
  - **SEMUA 5 INDEKS WAJIB DIISI**: tidak boleh ada index yang kosong atau undefined.
- **Fisher-Yates shuffle**: gunakan fungsi `shuffleArray(arr)`. Panggil di `startQuiz()` dan `restartQuiz()` agar urutan berbeda setiap kali mulai maupun restart. JANGAN gunakan inline loop di awal script.
- **Toggle deselect**: klik opsi yang sudah dipilih → set ke `null`.
- **Anti-copy**: CSS `user-select: none` pada `#qw` + JS listener `copy` dan `contextmenu`.
- **Credit block**: tampil di result screen — `@muqsith.ai` dengan link `https://www.instagram.com/muqsith.ai/`, label "BUILT BY", teks feedback "Feedback & saran? DM aja 👋".
- Setelah widget muncul, tambahkan pesan singkat di chat dengan format berikut (tanpa bold/italic): baris 1 `LATIHAN SOAL PENALARAN UMUM`, baris 2 `{tanggal} {bulan} {tahun}`, baris kosong, lalu `30 soal siap! Timer 25 menit jalan setelah kamu tekan Mulai. Selamat mengerjakan!` — tanggal/bulan/tahun sesuai hari ini.
- **Exp-box format (r9)**: JANGAN gunakan `.exp-wrong` / `.exp-correct` dengan border-left. Gunakan struktur blok baru: `.exp-box` (flex column, gap 6px) berisi `.exp-block.exp-wrong-block` (border #F0997B) dan `.exp-block.exp-correct-block` (border #5DCAA5). Tiap blok punya `.exp-head` berisi: `.exp-pill` (pill tag), `.exp-opt-lbl` (huruf opsi A-E), `.exp-svg` (SVG X merah / centang hijau). Body ada di `.exp-body` (background putih). Fungsi `renderSteps()` dengan `||` splitter TETAP dipertahankan di dalam `.exp-body`. Step numbers warna merah di blok salah via `.exp-block.exp-wrong-block .exp-step-num { color: #D85A30; }`.
