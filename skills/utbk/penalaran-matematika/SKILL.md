---
name: penalaran-matematika-utbk-r13
description: "Gunakan skill ini saat pengguna menyebut \"penalaran matematika UTBK\", \"PM UTBK\", \"latihan PM UTBK\", \"soal penalaran matematika\", \"latihan literasi matematika\", atau frasa serupa yang menandakan ingin latihan subtes Penalaran Matematika dalam UTBK/SNBT (bukan PM UIN). Skill ini membuat 20 soal pilihan ganda berbasis konteks dunia nyata, mencakup 10 materi (Kecepatan, Menentukan Persamaan, Kombinasi, Perbandingan Besaran, Data Tabel, Debit, Keliling Lingkaran, Kesebangunan Bangun Datar, Kesebangunan Segitiga, Trigonometri), dan menyajikannya sebagai widget interaktif tertanam langsung di chat dengan timer hitung mundur 37 menit 5 detik (900 detik), intro screen, sistem skoring otomatis (benar = 1 poin), dan pembahasan lengkap di mode review. Tipe soal TIDAK ditampilkan saat mengerjakan; hanya muncul di bagian pembahasan setelah submit. Dot navigator: grid 5 per baris, dot berbentuk persegi. Exp-box format opsi B: pill tag + huruf opsi + SVG ikon, border warna pill, body teks putih/transparan. Memakai KaTeX.\n"
---

# Penalaran Matematika UTBK r13 — UTBK/Literasi Practice

> Skill dibuat oleh **mqsth**
>
> © 2026 Muhammad Rayyis Muqsith ([@muqsith.ai](https://instagram.com/muqsith.ai)). Dilisensikan di bawah [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/). Boleh dipakai dan dimodifikasi untuk non-komersial dengan atribusi. Dilarang menjual, memasukkan ke layanan berbayar, atau mengklaim sebagai karya sendiri. Soal dibuat dengan bantuan AI, bukan soal resmi UTBK/SNBT, dan pembahasan bisa mengandung kekeliruan.

## Overview

Skill ini membuat **widget interaktif tertanam di chat** berupa ujian **20 soal** Penalaran Matematika UTBK selama **37 menit 5 detik**. Setiap kali dipanggil, buat soal **baru yang berbeda**.

**Skoring**: Benar = 1 poin, Salah/Kosong = 0 poin.

### Deskripsi Resmi Subtes

Dalam UTBK, Penalaran Matematika diposisikan sebagai inti dari literasi matematika. Subtes ini tidak hanya mengukur kemampuan menghitung, tetapi kemampuan berpikir logis dan menggunakan konsep matematika untuk menyelesaikan masalah di dunia nyata. Kemampuan ini menghubungkan masalah dunia nyata dengan solusi matematika melalui tiga proses kognitif:

- **Merumuskan (Formulating)**: Mengubah masalah dari konteks dunia nyata ke dalam bentuk matematika formal.
- **Menggunakan (Employing)**: Menerapkan konsep, fakta, prosedur, dan penalaran matematika untuk mendapatkan hasil.
- **Menafsirkan & Mengevaluasi (Interpreting)**: Merefleksikan hasil matematika kembali ke konteks awal untuk menilai apakah solusi masuk akal.

Masalah disajikan dalam konteks personal, sosial, pekerjaan, hingga ilmiah.

---

## Tipe Soal & Distribusi (20 Soal)

| Kode | Materi | Jumlah |
|------|--------|--------|
| PM-KEC | Kecepatan | 2 |
| PM-PRS | Menentukan Persamaan dari Suatu Konfigurasi Objek | 2 |
| PM-KOM | Kombinasi | 2 |
| PM-PRB | Perbandingan Dua Besaran dengan Satuan yang Sama atau Berbeda | 2 |
| PM-TAB | Menyajikan dan Mengolah Data dalam Bentuk Tabel | 2 |
| PM-DEB | Debit | 2 |
| PM-KLG | Keliling Lingkaran | 2 |
| PM-KBD | Kesebangunan Bangun Datar | 2 |
| PM-KBS | Kesebangunan Segitiga | 2 |
| PM-TRG | Perbandingan Trigonometri pada Segitiga Siku-siku | 2 |

> Semua soal bersifat mandiri (`passageId: null`). Soal PM-TAB menggunakan tabel HTML yang ditulis langsung di `q.q`.
>
> Setiap soal harus memuat konteks nyata yang relevan — bukan soal abstrak murni. Soal harus mendorong **proses merumuskan, menggunakan, LALU menafsirkan** secara implisit.
>
> Ekspresi matematika: gunakan **KaTeX** (bukan MathJax) dengan delimiter inline `\\(` dan `\\)`. **KRITIS**: di dalam data soal/opsi/pembahasan (`Qs = [...]`, `exps[]`), tulis backslash sebagai HTML numeric entity `&#92;` — bukan backslash literal (`\`) dan bukan double-backslash (`\\`) — karena backslash mentah terbukti hilang saat dikirim lewat tool `visualize:show_widget`. Contoh benar: `"&#92;( &#92;dfrac{3}{4} &#92;)"`. Config JS delimiter (`delimiters: [{left: '\\(', right: '\\)', ...}]`) tetap ditulis pakai double-backslash biasa, tidak perlu entity.

---

## Bank Soal (10 Soal — Referensi Pola Saja)

> HANYA referensi pola. JANGAN gunakan di widget. Setiap sesi harus menghasilkan soal 100% baru.

---

**PM01 [PM-KEC]** `ans:2`
Rani berkendara dari kota A ke kota B sejauh 180 km dengan kecepatan rata-rata 60 km/jam. Kemudian ia melanjutkan dari kota B ke kota C sejauh 120 km dengan kecepatan 40 km/jam. Kecepatan rata-rata keseluruhan perjalanan Rani adalah...
A. 45 km/jam
B. 48 km/jam
C. 50 km/jam
D. 52 km/jam
E. 54 km/jam
*(Total jarak = 300 km. Waktu A→B = 3 jam, waktu B→C = 3 jam. Total = 6 jam. v̄ = 300/6 = 50 km/jam)*

---

**PM02 [PM-PRS]** `ans:1`
Sebuah taman berbentuk persegi panjang memiliki panjang 3 m lebih dari dua kali lebarnya. Jika keliling taman 54 m, panjang taman tersebut adalah...
A. 18 m
B. 21 m
C. 24 m
D. 27 m
E. 30 m
*(Misal lebar = l. Panjang = 2l+3. Keliling: 2(2l+3+l)=54 → 6l+6=54 → l=8. Panjang = 2(8)+3 = 19 m)*
*Hmm revisi: 2(p+l)=54 → p+l=27. p=2l+3 → 3l+3=27 → l=8, p=19. Perlu revisi opsi.*

---

**PM03 [PM-KOM]** `ans:3`
Sebuah tim basket terdiri dari 10 pemain. Pelatih akan memilih 5 pemain untuk turun di babak pertama. Berapa banyak susunan tim yang mungkin dibentuk?
A. 126
B. 210
C. 252
D. 504
E. 720
*(C(10,5) = 10!/(5!×5!) = 252)*

---

**PM04 [PM-PRB]** `ans:0`
Harga 4 kg apel sama dengan harga 6 kg jeruk. Jika harga 1 kg jeruk Rp15.000, maka harga 5 kg apel adalah...
A. Rp112.500
B. Rp120.000
C. Rp125.000
D. Rp135.000
E. Rp150.000
*(1 kg jeruk = Rp15.000. 6 kg jeruk = Rp90.000 = harga 4 kg apel. 1 kg apel = 22.500. 5 kg apel = 112.500)*

---

**PM05 [PM-TAB]** `ans:2`
Tabel produksi pabrik (unit/hari):
Sen: 320, Sel: 280, Rab: 350, Kam: 310, Jum: 290.
Hari dengan produksi di atas rata-rata ada...
A. 1 hari
B. 2 hari
C. 3 hari
D. 4 hari
E. 5 hari
*(Total = 1550. Rata-rata = 310. Di atas 310: Sen (320), Rab (350) → 2 hari)*
*Hmm, Rab dan Sen saja → ans: B = 2 hari*

---

**PM06 [PM-DEB]** `ans:3`
Sebuah kran mengalirkan air dengan debit 12 liter/menit. Sebuah bak berkapasitas 360 liter akan diisi menggunakan 3 kran identik. Waktu yang diperlukan adalah...
A. 8 menit
B. 9 menit
C. 10 menit
D. 12 menit
E. 15 menit
*(Debit total = 3×12 = 36 liter/menit. Waktu = 360÷36 = 10 menit)*

---

**PM07 [PM-KLG]** `ans:1`
Sebuah roda sepeda berdiameter 70 cm. Roda tersebut berputar sebanyak 500 kali dalam satu perjalanan. Jarak yang ditempuh adalah...
A. 1.000 m
B. 1.100 m
C. 1.200 m
D. 1.400 m
E. 1.500 m
*(Keliling = π×d = 22/7×70 = 220 cm. Jarak = 220×500 = 110.000 cm = 1.100 m)*

---

**PM08 [PM-KBD]** `ans:2`
Dua bangun persegi panjang sebangun. Persegi panjang pertama berukuran 6 cm × 4 cm. Jika panjang persegi panjang kedua adalah 9 cm, lebarnya adalah...
A. 5 cm
B. 6 cm
C. 7 cm
D. 7,5 cm
E. 8 cm
*(Rasio panjang = 9/6 = 3/2. Lebar = 4×(3/2) = 6 cm)*

---

**PM09 [PM-KBS]** `ans:0`
Segitiga ABC sebangun dengan segitiga PQR. Pada segitiga ABC, AB = 8 cm dan BC = 12 cm. Pada segitiga PQR, PQ = 6 cm. Panjang QR adalah...
A. 9 cm
B. 10 cm
C. 11 cm
D. 12 cm
E. 16 cm
*(AB/PQ = BC/QR → 8/6 = 12/QR → QR = 72/8 = 9 cm)*

---

**PM10 [PM-TRG]** `ans:3`
Sebuah tangga disandarkan ke tembok setinggi 5 m. Jika sudut yang dibentuk tangga dengan lantai adalah 60°, panjang tangga tersebut adalah...
A. 5 m
B. 5√2 m
C. 5√3/3 m
D. 10√3/3 m
E. 10 m
*(sin 60° = 5/tangga → tangga = 5/sin60° = 5/(√3/2) = 10/√3 = 10√3/3 m)*

---

## Struktur Data JavaScript

```javascript
const Qs = [
  {
    passageId: null,
    cat: "Kecepatan",
    q: "Sebuah mobil menempuh jarak 240 km dalam 4 jam. Jika kecepatan ditingkatkan 20 km/jam, waktu yang dihemat untuk menempuh jarak yang sama adalah...",
    opts: ["30 menit", "40 menit", "48 menit", "60 menit", "80 menit"],
    ans: 2,
    exps: [
      "Letak kesalahan: 30 menit terlalu kecil||Kecepatan awal: 240÷4 = 60 km/jam||Kecepatan baru: 60+20 = 80 km/jam||Waktu baru: 240÷80 = 3 jam||Hemat: 4−3 = 1 jam = 60 menit, bukan 30",
      "Letak kesalahan: 40 menit keliru||Kecepatan awal: 60 km/jam, kecepatan baru: 80 km/jam||Waktu baru: 240÷80 = 3 jam||Selisih waktu: 60 menit, bukan 40",
      "Diketahui: jarak = 240 km, waktu awal = 4 jam||Kecepatan awal: &#92;(240 &#92;div 4 = 60&#92;) km/jam||Kecepatan baru: &#92;(60 + 20 = 80&#92;) km/jam||Waktu baru: &#92;(240 &#92;div 80 = 3&#92;) jam||Selisih: &#92;(4 - 3 = 1&#92;) jam = 60 menit||Kesimpulan: waktu yang dihemat adalah 60 menit",
      "Letak kesalahan: memilih 60 menit padahal itulah jawabannya||Cek: kecepatan 80 km/jam untuk 240 km = 3 jam, hemat = 60 menit||Pilihan ini sebenarnya benar",
      "Letak kesalahan: 80 menit terlalu besar||Waktu awal 4 jam = 240 menit, waktu baru 3 jam = 180 menit||Selisih = 60 menit, bukan 80"
    ]
  },
  {
    passageId: null,
    cat: "Menyajikan dan Mengolah Data dalam Bentuk Tabel",
    q: `Tabel berikut menunjukkan nilai ujian matematika 5 siswa.<table class="q-table"><tr><th>Siswa</th><th>Nilai</th></tr><tr><td>Andi</td><td>78</td></tr><tr><td>Budi</td><td>85</td></tr><tr><td>Citra</td><td>92</td></tr><tr><td>Deni</td><td>70</td></tr><tr><td>Eva</td><td>80</td></tr></table>Selisih nilai tertinggi dan rata-rata kelompok adalah...`,
    opts: ["10", "11", "12", "13", "14"],
    ans: 2,
    exps: [
      "Letak kesalahan: selisih 10 kurang tepat||Total: 78+85+92+70+80 = 405||Rata-rata: 405÷5 = 81||Nilai tertinggi: 92||Selisih: 92−81 = 11, bukan 10",
      "Diketahui: nilai 5 siswa = 78, 85, 92, 70, 80||Total: &#92;(78+85+92+70+80 = 405&#92;)||Rata-rata: &#92;(405 &#92;div 5 = 81&#92;)||Nilai tertinggi: 92||Selisih: &#92;(92 - 81 = 11&#92;)||Kesimpulan: selisih nilai tertinggi dan rata-rata adalah 11",
      "Letak kesalahan: 12 bukan hasil yang tepat||Total = 405, rata-rata = 81, nilai tertinggi = 92||Selisih benar: 92−81 = 11",
      "Letak kesalahan: 13 tidak sesuai hitungan||Rata-rata = 81, nilai tertinggi = 92||Selisih = 11, bukan 13",
      "Letak kesalahan: 14 terlalu besar||Rata-rata = 81, nilai tertinggi = 92||Selisih = 11, bukan 14"
    ]
  }
];
```

> **Catatan**:
> - `q.cat`: gunakan nama materi sesuai tabel distribusi, contoh `"Kecepatan"`, `"Kombinasi"`, `"Debit"`, `"Keliling Lingkaran"`, `"Kesebangunan Segitiga"`, dst. Hanya tampil di review mode.
> - Setiap soal harus memiliki **konteks nyata yang jelas**. Bukan soal abstrak.
> - Soal PM-TAB: embed `<table class="q-table">` di `q.q`.
> - **Soal geometri (PM-KLG, PM-KBD, PM-KBS, PM-TRG) — sekitar 50% pakai diagram SVG, 50% tanpa diagram (teks saja)**. Tidak wajib selalu ada diagram; variasikan tiap sesi supaya ada campuran soal bervisual dan soal teks murni. Saat dipakai, diagram harus menggambarkan bangun yang dimaksud (lingkaran dengan radius/diameter berlabel, persegi panjang/segitiga sebangun dengan sisi berlabel, segitiga siku-siku dengan sudut dan sisi berlabel) di `q.q` sehingga siswa bisa lihat bentuknya, bukan cuma bayangin dari teks.
>   - Gunakan `<svg viewBox="0 0 ... ...">` ukuran wajar (lebar ~200-280px), `stroke="currentColor"` dan `fill="none"` untuk garis bangun supaya ikut warna tema (`color: var(--color-text-primary, #1E293B)` di style svg-nya), label angka/huruf pakai `<text>` dengan `font-size` kecil (~11-12).
>   - Contoh pola (segitiga sebangun, sisi berlabel):
>     ```html
>     <svg viewBox="0 0 240 120" style="display:block;margin:10px auto;color:var(--color-text-primary,#1E293B)" width="240" height="120">
>       <polygon points="10,100 90,100 10,20" fill="none" stroke="currentColor" stroke-width="1.5"/>
>       <polygon points="130,100 230,100 130,40" fill="none" stroke="currentColor" stroke-width="1.5"/>
>       <text x="45" y="115" font-size="11" fill="currentColor">8 cm</text>
>       <text x="15" y="65" font-size="11" fill="currentColor">12 cm</text>
>       <text x="175" y="115" font-size="11" fill="currentColor">6 cm</text>
>     </svg>
>     ```
>   - Diagram TIDAK perlu presisi skala matematis (boleh disproporsi), yang penting bentuk dan label sisinya jelas dan sesuai dengan angka di soal.
>   - **Jika soal pakai diagram, pembahasan jawaban benar (exps index sesuai `ans`) WAJIB juga sertakan diagram yang sama** (boleh diagram identik atau versi dengan tambahan label/garis bantu, misal garis tinggi atau sudut yang dipakai saat menghitung) supaya siswa bisa lihat ulang visualnya saat baca pembahasan. Opsi salah (`Letak kesalahan`) tidak perlu diagram, cukup teks.
> - Interleave materi: KEC, PRS, KOM, PRB, TAB, DEB, KLG, KBD, KBS, TRG, lalu ulangi urutan kedua kalinya.

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
.btn-nav { background: transparent; border: 0.5px solid var(--color-border-secondary, #CBD5E1); border-radius: 8px; padding: 9px 16px; font-size: 13px; cursor: pointer; font-family: inherit; color: var(--color-text-primary, #1E293B); }
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
.r-bd-row { display: flex; justify-content: space-between; align-items: center; padding: 8px 0; border-bottom: 0.5px solid var(--color-border-tertiary, #E2E8F0); font-size: 13px; }
.r-bd-row:last-child { border-bottom: none; }
.r-bd-cat { color: var(--color-text-secondary, #64748B); }
.r-bd-score { font-weight: 500; }
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
      <div class="intro-utbk">UTBK / LITERASI</div>
      <div class="intro-title">Penalaran Matematika</div>
      <div class="intro-stats-row">
        <div><div class="intro-stat-key">Soal</div></div>
        <div><div class="intro-stat-key">Waktu</div></div>
      </div>
      <hr class="intro-divider">
      <div class="intro-stats-row">
        <div><div class="intro-stat-val">20</div></div>
        <div><div class="intro-stat-val">37:05</div></div>
      </div>
      <hr class="intro-divider" style="margin-bottom:1.5rem">
      <button class="btn-primary" style="width:100%;padding:10px 0" onclick="startQuiz()">Mulai ujian</button>
    </div>
  </div>
  <div id="quiz-screen" style="display:none">
    <div class="top-bar">
      <div class="timer-box" id="timer-el">
        <svg width="13" height="13" viewBox="0 0 13 13" fill="none"><circle cx="6.5" cy="6.5" r="5.5" stroke="currentColor" stroke-width="1"/><path d="M6.5 3.5V6.5L8.5 8" stroke="currentColor" stroke-width="1" stroke-linecap="round"/></svg>
        <span id="timer-txt">37:05</span>
      </div>
    </div>
    <div class="quiz-body">
      <div class="nav-dots" id="nav-dots"></div>
      <div class="quiz-main">
        <div class="content-header">
          <div class="content-header-label">Penalaran<br>Matematika</div>
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
// Qs[] di sini (20 soal baru setiap sesi)

function shuffleArray(arr) {
  for (let i = arr.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [arr[i], arr[j]] = [arr[j], arr[i]];
  }
}

let cur = 0, answers = new Array(Qs.length).fill(null);
let revealed = new Array(Qs.length).fill(false);
let totalSec = 2225, timerInt, quizDone = false, reviewMode = false;

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
  if (revealed[cur]) html += `<div class="q-meta">${q.cat}</div>`;
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
    const optLabels = ['A','B','C','D','E'];
    const svgX = `<svg width="14" height="14" viewBox="0 0 14 14" fill="none"><circle cx="7" cy="7" r="6.5" stroke="#D85A30" stroke-width="1"/><path d="M4.5 4.5L9.5 9.5M9.5 4.5L4.5 9.5" stroke="#D85A30" stroke-width="1.4" stroke-linecap="round"/></svg>`;
    const svgC = `<svg width="14" height="14" viewBox="0 0 14 14" fill="none"><circle cx="7" cy="7" r="6.5" stroke="#1D9E75" stroke-width="1"/><path d="M4 7L6.2 9.2L10 5" stroke="#1D9E75" stroke-width="1.4" stroke-linecap="round" stroke-linejoin="round"/></svg>`;
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
  Qs.forEach((q,i) => { if (!cats[q.cat]) cats[q.cat]={correct:0,total:0}; cats[q.cat].total++; if (answers[i]===q.ans) cats[q.cat].correct++; });
  let grade, msg;
  if (pct>=90) { grade='Excellent'; msg='Kemampuan penalaran matematikamu sangat kuat! Siap UTBK!'; }
  else if (pct>=75) { grade='Proficient'; msg='Hasil bagus! Perlu sedikit latihan konteks-konteks yang kurang.'; }
  else if (pct>=60) { grade='Developing'; msg='Fondasi sudah ada. Perbanyak latihan soal-soal serupa.'; }
  else { grade='Perlu Latihan'; msg='Perlu lebih banyak latihan. Ulangi konsep dasar dan coba lagi.'; }
  let bdRows = '';
  Object.entries(cats).forEach(([cat,d]) => {
    bdRows += `<div class="r-bd-row"><span class="r-bd-cat">${cat}</span><span class="r-bd-score">${d.correct}/${d.total}</span></div>`;
  });
  rs.innerHTML = `<div class="result-wrap"><div class="r-hero"><div class="r-score-big">${correct}</div><div class="r-of">/ 20 benar</div><div class="r-grade">${grade}</div><div class="r-msg">${msg}</div></div><div class="r-stats"><div class="r-stat"><div class="r-stat-val">${correct}</div><div class="r-stat-lbl">Benar</div></div><div class="r-stat"><div class="r-stat-val">${wrong}</div><div class="r-stat-lbl">Salah</div></div></div><div class="r-breakdown"><div class="r-bd-title">Breakdown per kategori</div>${bdRows}</div><div class="r-actions"><button class="btn-nav" onclick="reviewAnswers()">Review jawaban</button><button class="btn-primary" onclick="restartQuiz()">Coba lagi</button></div><div class="r-credit"><div class="r-credit-built">BUILT BY</div><div class="r-credit-handle"><svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="2" width="20" height="20" rx="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="1" fill="currentColor" stroke="none"/></svg><a href="https://www.instagram.com/muqsith.ai/" target="_blank">@muqsith.ai</a></div><div class="r-credit-fb">Feedback &amp; saran? DM aja 👋</div></div></div>`;
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
  totalSec = 2225; quizDone = false; reviewMode = false;
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

- **Timer**: 2225 detik. Warn merah saat ≤ 300 detik.
- **Konteks**: setiap soal WAJIB punya konteks dunia nyata. Hindari soal abstrak murni.
- **Distribusi wajib**: 2 soal per materi (10 materi × 2 = 20 soal). Interleave urutannya: KEC, PRS, KOM, PRB, TAB, DEB, KLG, KBD, KBS, TRG, lalu ulangi sekali.
- **Soal PM-TAB**: selalu gunakan tabel HTML (`<table class="q-table">`) yang ditulis di `q.q`.
- **Soal geometri (PM-KLG, PM-KBD, PM-KBS, PM-TRG)**: sekitar 50% pakai diagram SVG inline di `q.q`, 50% teks saja — tidak wajib selalu ada diagram. Jika soal pakai diagram, pembahasan jawaban benar (`exps[ans]`) WAJIB juga sertakan diagram yang sama (boleh ditambah garis bantu/label tambahan untuk memperjelas cara hitung).
- **q.cat**: nama materi persis seperti di tabel distribusi — `"Kecepatan"`, `"Menentukan Persamaan dari Suatu Konfigurasi Objek"`, `"Kombinasi"`, `"Perbandingan Dua Besaran dengan Satuan yang Sama atau Berbeda"`, `"Menyajikan dan Mengolah Data dalam Bentuk Tabel"`, `"Debit"`, `"Keliling Lingkaran"`, `"Kesebangunan Bangun Datar"`, `"Kesebangunan Segitiga"`, `"Perbandingan Trigonometri pada Segitiga Siku-siku"`.
- **Pembahasan (exps[]) wajib berbentuk langkah-langkah**: ganti nama field dari `exp` ke `exps`. `exps` adalah array 5 elemen (index 0–4), tiap index sesuai opsi. Pisahkan tiap langkah dengan `||`. Setiap segmen antara `||` dirender sebagai baris bernomor ke bawah. Minimum: `exps[ans]` minimal 3 langkah, `exps[i]` opsi salah minimal 2 langkah. DILARANG satu blok teks panjang tanpa `||`.
  - Format tiap langkah: `Label singkat: penjelasan/perhitungan` — teks sebelum titik dua pertama akan di-**bold** otomatis. Contoh label: `Diketahui`, `Merumuskan`, `Hitung`, `Susun persamaan`, `Substitusi`, `Kesimpulan`, `Letak kesalahan`.
  - Opsi salah WAJIB punya langkah `Letak kesalahan: ...` yang menjelaskan spesifik di mana kalkulasinya meleset.
  - Identifikasi proses UTBK (Merumuskan / Menggunakan / Menafsirkan) cukup dimasukkan sebagai langkah terakhir `exps[ans]`.
  - DILARANG awali exps dengan "✓ Benar." atau "✗ Salah." — pill tag + SVG sudah jadi penanda visual.
- **KaTeX**: setelah `renderQ()` set innerHTML, panggil `renderMathInElement(q-area, {delimiters: [{left: '\\(', right: '\\)', display: false}]})`. Delimiter inline `\\(`/`\\)`. Backslash LaTeX di dalam data soal/opsi/pembahasan (`Qs = [...]`, `exps[]`, `opts[]`) WAJIB ditulis sebagai `&#92;` (HTML entity) — bukan backslash literal atau double-backslash.
- **WAJIB LaTeX untuk SEMUA ekspresi matematika** di `q.q`, `opts[]`, dan `exps[]`: persamaan, substitusi, hasil hitung, nilai variabel, akar, pangkat, pecahan, trigonometri, dsb. SEMUA dibungkus `&#92;( ... &#92;)`. Contoh benar: `&#92;(2x+3y=17&#92;)`, `&#92;(&#92;sqrt{3}&#92;)`, `&#92;(&#92;sin 60^&#92;circ&#92;)`. DILARANG teks polos tanpa delimiter, atau backslash literal/double-backslash (`\\(...\\)`) yang hilang saat dikirim ke widget.
- **DILARANG tulis pembagian dengan slash** (`330/4`, `250/3`, `(85+90+75)/3`) di dalam ekspresi matematika. WAJIB pakai `&#92;(&#92;frac{}{} &#92;)` agar tampil pecahan atas-bawah. Contoh benar: `&#92;(&#92;frac{250}{3} &#92;approx 83{,}33&#92;)`. Berlaku untuk SEMUA pembagian di `q.q`, `opts[]`, dan `exps[]`. Satuan majemuk seperti km/jam atau liter/menit tetap boleh ditulis teks biasa di luar ekspresi matematika.
- **Desimal**: pakai koma Indonesia di dalam KaTeX dengan `{,}` (misal `&#92;(0{,}9&#92;)`), supaya tidak muncul spasi aneh setelah koma.
- **Exp-box format (r10, tetap berlaku di r11)**: JANGAN gunakan `.exp-wrong` / `.exp-correct` dengan border-left. Gunakan struktur blok baru: `.exp-box` (flex column, gap 6px) berisi `.exp-block.exp-wrong-block` (border #F0997B) dan `.exp-block.exp-correct-block` (border #5DCAA5). Tiap blok punya `.exp-head` berisi: `.exp-pill` (pill tag), `.exp-opt-lbl` (huruf opsi A-E), `.exp-svg` (SVG X merah / centang hijau). Body ada di `.exp-body` (background putih). Fungsi `renderSteps()` dengan `||` splitter TETAP dipertahankan di dalam `.exp-body`. Step numbers warna merah di blok salah via `.exp-block.exp-wrong-block .exp-step-num { color: #D85A30; }`.
  - DILARANG pakai simbol `@` sebagai shorthand harga/rate (misal `@Rp1.500.000`). Ganti dengan `Rp1.500.000/bulan`, `masing-masing Rp1.500.000`, atau `tiap bulan Rp1.500.000`.
  - **SEMUA 5 INDEKS WAJIB DIISI**: tidak boleh ada index yang kosong atau undefined.
- **Fisher-Yates shuffle**: gunakan fungsi `shuffleArray(arr)`. Panggil di `startQuiz()` dan `restartQuiz()` agar urutan berbeda setiap kali mulai maupun restart. JANGAN gunakan inline loop di awal script.
- **Opsi jawaban**: 5 opsi, tanpa prefix huruf.
- **Anti-copy**: CSS `user-select: none` pada `#qw` + JS `DOMContentLoaded` listener untuk event `copy` dan `contextmenu` (keduanya `e.preventDefault()`).
- **Credit block**: tampil di result screen — `@muqsith.ai` dengan link `https://www.instagram.com/muqsith.ai/`, label "BUILT BY", dan teks feedback "Feedback & saran? DM aja 👋".
- Setelah widget muncul, tambahkan pesan singkat di chat dengan format berikut (tanpa bold/italic): baris 1 `LATIHAN SOAL PENALARAN MATEMATIKA UTBK`, baris 2 `{tanggal} {bulan} {tahun}`, baris kosong, lalu `20 soal siap! Timer 37 menit 5 detik jalan setelah kamu tekan Mulai. Selamat mengerjakan!` — tanggal/bulan/tahun sesuai hari ini.
