---
name: pemahaman-bacaan-menulis-r16
description: "Gunakan skill ini saat pengguna menyebut \"pemahaman bacaan dan menulis\", \"PBM\", \"latihan PBM\", \"soal PBM\", \"latihan TOBK PBM\", \"latihan UTBK PBM\", atau frasa serupa yang menandakan ingin latihan subtes Pemahaman Bacaan dan Menulis. Skill ini membuat 20 soal pilihan ganda berbasis teks bacaan bahasa Indonesia bertopik beragam, mencakup semua tipe soal PBM (pemilihan, penataan, perbaikan gagasan), dan menyajikannya sebagai widget interaktif tertanam langsung di chat dengan timer hitung mundur 20 menit (1200 detik), intro screen deskripsi resmi UTBK, sistem skoring otomatis, dan pembahasan lengkap dengan navigasi penuh di mode review. Tipe soal (kode IND) TIDAK ditampilkan saat mengerjakan soal; hanya muncul di bagian pembahasan setelah submit. Exp-box format opsi B: pill tag + huruf opsi + SVG ikon, border warna pill, body teks putih/transparan.\n"
---

# Pemahaman Bacaan & Menulis r16 — TOBK/UTBK Practice

> Skill dibuat oleh **mqsth**
>
> © 2026 Muhammad Rayyis Muqsith ([@muqsith.ai](https://instagram.com/muqsith.ai)). Dilisensikan di bawah [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/). Boleh dipakai dan dimodifikasi untuk non-komersial dengan atribusi. Dilarang menjual, memasukkan ke layanan berbayar, atau mengklaim sebagai karya sendiri. Soal dibuat dengan bantuan AI, bukan soal resmi UTBK/SNBT, dan pembahasan bisa mengandung kekeliruan.

## Overview

Skill ini membuat **widget interaktif tertanam di chat** (bukan file download) berupa ujian **20 soal** Pemahaman Bacaan dan Menulis selama **20 menit**. Setiap kali dipanggil, buat soal **baru yang berbeda** (jangan ulangi soal yang sama).

### Deskripsi Resmi Subtes (Sumber: SNPMB)

Subtes Pemahaman Bacaan dan Menulis mengukur kemampuan peserta dalam memahami membaca dan kemampuan dalam menulis. Kemampuan yang diukur lebih dipusatkan pada kemampuan menulis yang didasarkan atas pemahaman terhadap bacaan. Cakupan materi soal Subtes Pemahaman Bacaan dan Menulis meliputi (1) pemilihan gagasan, (2) penataan gagasan, dan (3) perbaikan gagasan.

Materi **pemilihan gagasan**: penentuan judul bacaan, penentuan diksi yang tepat, penentuan gagasan pelengkap kalimat, dan pelengkapan gagasan paragraf.

Materi **penataan gagasan**: penentuan kalimat inti, penggabungan kalimat, penentuan gagasan bertanda baca tepat, pengurutan kalimat dalam paragraf, penempatan kalimat pada posisi yang tepat, dan pemvariasian kalimat.

Materi **perbaikan gagasan**: perbaikan penulisan kata serapan, penulisan huruf, penulisan kata gabung, perbaikan kata, perbaikan kata sambung, penentuan cara memperbaiki kalimat, penentuan kata yang mubazir, penentuan kalimat ringkas, perbaikan kalimat, dan perbaikan diksi.

> Implikasi untuk pembuatan soal: **variasikan topik teks** tiap sesi — satu sesi harus mencakup minimal dua topik berbeda (sains, sosial, lingkungan, budaya, ekonomi, teknologi, dll). Jangan semua teks bertopik sama.

---

## Format Soal Autentik UTBK PBM

Format asli UTBK PBM adalah:
- **2–3 teks bacaan** dalam bahasa Indonesia (~150–250 kata per teks)
- Setiap teks diberi **nomor urut kalimat** — misalnya `(1) Kalimat pertama. (2) Kalimat kedua.` — karena banyak soal mengacu langsung ke nomor kalimat tertentu
- Setiap teks diikuti oleh **6–10 soal** yang mengacu ke teks tersebut
- Total 20 soal
- Soal **tidak punya passage sendiri-sendiri** — teks ditampilkan sekali di atas, soal menyusul
> ⚠️ **WAJIB beri nomor kalimat pada teks.** Format: `(1) Kalimat pertama teks. (2) Kalimat kedua.` dst. Penomoran ini kritis karena soal tipe IND-2, IND-4, IND-7, IND-8, IND-11 sering merujuk "Kalimat (3) perlu diperbaiki" atau "Kesalahan ditemukan pada kalimat...".

---

## Cakupan Tipe Soal

Distribusikan 20 soal dari tipe-tipe berikut (variasikan tiap sesi). Gunakan kode IND berikut:

| Kode | Tipe Soal | Target |
|---|---|---|
| IND-1 | Gagasan Utama / Jenis Paragraf | 1–2 soal |
| IND-2 | Kalimat Rumpang (melengkapi kalimat kosong) | 1–2 soal |
| IND-4 | Konjungsi (perbaikan / pemilihan kata hubung) | 2–3 soal |
| IND-5 | Makna Kata / Diksi (sinonim, kata yang tepat) | 1–2 soal |
| IND-6 | Paragraf Rumpang (melengkapi paragraf) | 1–2 soal |
| IND-7 | Kalimat Efektif (perbaikan kalimat tidak efektif) | 2–3 soal |
| IND-8 | Huruf Kapital / Penulisan Huruf | 1–2 soal |
| IND-9 | Penempatan Kalimat (kalimat simpleks/kompleks) | 1–2 soal |
| IND-10 | Judul Teks | 1–2 soal |
| IND-11 | Penulisan Kata / Tanda Baca / Kata Baku | 2–3 soal |
| IND-12 | Kalimat Inti (S+P+O transformasi) | 1–2 soal |
| IND-13 | Menyusun / Menggabungkan Kalimat | 1–2 soal |

---

## Materi Konten

> Gunakan materi ini sebagai acuan membuat soal dan pembahasan.

### IND-1 — Gagasan Utama Paragraf / Jenis Paragraf
- **Jenis paragraf**:
  1. Deskripsi — menggambarkan objek secara rinci
  2. Eksposisi — menginformasikan, memberitahukan, memaparkan
  3. Persuasi — mengajak, membujuk
  4. Argumentasi — meyakinkan, membuktikan
  5. Narasi — menceritakan/mengisahkan
- **DEPAN** — mayoritas paragraf deduktif (gagasan utama di kalimat pertama)
- Varian soal: soal meminta gagasan utama **diurutkan** dari tiap kalimat paragraf (bukan hanya menemukan satu gagasan utama)
- Contoh: teks membahas bahaya dan sifat-sifat sianida → tujuannya menginformasikan → jenis paragraf Eksposisi
### IND-2 — Kalimat Rumpang
- **Syarat paragraf**: (1) satu kesatuan, (2) koherensi (makna sama), (3) kohesi (bentuk sama)
- Kalimat rumpang di akhir paragraf → biasanya kalimat **penyimpulan**
- Konjungsi penyimpulan/akibat: *Oleh karena itu, Dengan demikian, Jadi, Maka dari itu*
### IND-3 — Penggunaan Kata
*(Materi belum tersedia)*

### IND-4 — Konjungsi
- **Prinsip penggabungan**: konjungsi awal kalimat (antarkalimat) **semakna** dengan konjungsi intrakalimat pasangannya
- **Pertentangan** (antarkalimat): *Akan tetapi, Namun* | (intrakalimat): *tetapi, sedangkan, padahal*
- **Penambahan** (antarkalimat): *Selain itu* | (intrakalimat): *dan, serta, juga*
- **Kausalitas/Akibat** (antarkalimat): *Oleh karena itu, Oleh sebab itu* | (intrakalimat): *sehingga, karena, sebab, maka*
- **Perbandingan/Pertentangan**: *Sementara itu*
- **Konjungsi korelatif (berpasangan)** — **TiPi Bu Mela Bau Mangga**:
  - tidak hanya — tetapi juga
  - bukan hanya — melainkan juga
  - baik — maupun
  - mulai dari — hingga
- **Posisi konjungsi pertentangan**: *Namun, Akan tetapi* → awal kalimat | *tetapi, Sedangkan* → tengah kalimat
- **Posisi konjungsi kausalitas**: *Oleh karena itu, Oleh sebab itu* → awal kalimat | *Karena, Sehingga* → tengah kalimat
- **Aturan**: `serta` dan `dan` tidak boleh berdampingan dalam kalimat yang sama
- **Penggabungan** = konjungsi intrakalimat | **Pemisahan** = konjungsi antarkalimat
### IND-5 — Makna Kata / Diksi
- **Kalimat bermakna sama**: (1) gunakan kata bersinonim, (2) aktif → pasif (me- → di-)
- Kalimat aktif diawali ber-/me- | Kalimat pasif diawali ter-/di-
- **Kata berdekatan makna** tidak boleh berdampingan (mubazir): *limbah* = *racun*, *konsep* = *ide* — keduanya tidak boleh satu kalimat jika bermakna sama
- Contoh: mitigasi = mengurangi | parit = selokan
- Contoh penggantian imbuhan: *mencanangkan* → *dicanangkan*
- ⚠️ **WAJIB**: kata yang dikutip di `q.q` soal IND-5 HARUS benar-benar ada di teks passage. DILARANG menyebut kata yang tidak ada di passage. DILARANG menulis disclaimer/koreksi di dalam `q.q` (contoh SALAH: "Kata 'X' tidak ada di teks; sebagai gantinya..."). Jika ragu, pilih kata lain yang jelas ada di passage.
### IND-6 — Paragraf Rumpang
- Cari kalimat yang melengkapi paragraf dengan melihat koherensi dan kohesi paragraf
- Perhatikan kata hubung dan kata rujukan di kalimat sebelum dan sesudah lubang
- Contoh: kalimat rumpang membahas media komunikasi → isi dengan kalimat yang mencakup rentang dari awal hingga kini: *"dari menulis di dinding gua hingga mengirim pesan melalui ponsel"*
### IND-7 — Kalimat Efektif
Syarat kalimat efektif — **HeLo BuKMi Super, Pak Camat EDY Tanpa SaRah**:
1. **He**mat kata — tidak ada kata mubazir
2. **Lo**gis — masuk akal
3. **Bu**ku — menggunakan bahasa baku
4. **K**alimat min. Subjek + Predikat
5. **Mi**nimal — tidak berlebihan
6. **Su**percermat — tidak ambigu
7. **Par**alel — imbuhan sejajar (pra-, pasca-, intra-, antar-, trans-)
8. **Pak Camat EDY Tanpa SaRah** — sesuai EYD, tanpa bahasa asing/daerah tak perlu
- **"yang" = perluasan**: jika ada kata *yang* di dalam kalimat, bagian itu bukan inti kalimat. Hapus saat menyederhanakan/memperbaiki kalimat
### IND-8 — Huruf Kapital
- **Nama ilmiah**: *Santalum album* (huruf pertama kapital, sisanya kecil) — contoh: Pohon Cendana → *Santalum album*
- **Geografis**: Pulau Jawa, Kota Bandung, Solo, Lamongan, Jalan Meruya — TAPI pengecualian: *kawasan Jakarta, wilayah barat Bandung, daerah Jakarta, bangsa Mongol, bahasa Indonesia* (tidak kapital karena bersifat umum)
- **Lembaga resmi**: Konservasi Indonesia (KI), Badan Riset dan Inovasi Nasional (BRIN)
- **Jabatan + nama tempat spesifik**: Wali Kota Jakarta Barat (kapital)
- **Istilah ilmu**: *flora endemik, ekosistem* (TIDAK kapital karena bukan nama diri)
### IND-9 — Kalimat Simpleks/Kompleks (Penempatan Kalimat)
- Kalimat simpleks = kalimat tunggal (satu klausa) | kalimat kompleks = kalimat majemuk (lebih dari satu klausa)
- Cari posisi yang paling logis berdasarkan koherensi paragraf
- Kalimat dengan informasi lebih lengkap/spesifik → posisi **setelah** kalimat yang lebih umum
- Contoh: pernyataan yang tersedia = informasi yang lebih lengkap → letakkan setelah kalimat 5
### IND-10 — Judul Teks
- Cari kata yang paling sering muncul / kata kunci utama teks
- **Caka Semu** (CArikan KAta yang SEring MUnCul)
- Judul harus mencerminkan isi **keseluruhan** teks, bukan hanya satu bagian
### IND-11 — Penulisan Kata / Tanda Baca

**Tanda koma (,) digunakan:**
1. Perincian lebih dari 2 unsur: *Ayah, ibu, dan anak* (dua unsur tidak pakai koma: *Ayah dan ibu*)
2. Sebelum konjungsi intrakalimat — **aBah Lagi di TaSSek MelaYYa**: *bahkan, apalagi, tetapi, seperti, sedangkan, kecuali, melainkan, lalu, yaitu, yakni*
3. Informasi tambahan (aposisi)
4. Keterangan di awal kalimat: *Ketika hujan, aku tidak sekolah*
5. Memisahkan anak kalimat yang mendahului induk kalimat: *Karena saya ingin lulus PTN, saya rajin belajar*
6. Setelah konjungsi antarkalimat: *Oleh karena itu, / Selain itu, / Maka dari itu, / Namun,*
7. Memisahkan keterangan dari kutipan langsung: *"Rajin belajar, Nak," kata Ibu.*
- **DILARANG**: memisahkan subjek dan predikat | memisahkan dua objek
**Tanda titik dua (:) digunakan — Per Di iKut:**
1. Perincian/pemerian setelah kalimat lengkap: *Najwa membeli alat tulis: pulpen, pensil, dan penghapus.*
2. Dialog dalam naskah: *Ibu: "Jangan lupa beli beras, Nak."*
3. Kutipan/referens/identitas: surat (Nama: Habib), penerbitan (Jakarta: Gramedia), kitab (Al-Baqarah: 1), waktu (16:49:25), rasio (1:1000)
- Setelah "seperti" dalam kalimat lengkap **TIDAK** perlu titik dua
**Tanda pisah (—) digunakan:**
1. Keterangan tambahan/aposisi: *Soekarno — Proklamator RI*
2. Rentang waktu/tempat: *20.00 — 21.00 WIB*, *Jakarta — Bandung*
- **BUKAN** untuk memisahkan kata ulang: *anak-anak* (pakai tanda hubung -)
**Tanda petik tunggal ('...') digunakan:**
1. Judul sajak, puisi, lagu di dalam kalimat: *Sajak 'Pahlawanku' sangat menyentuh hati.*
2. Mengapit kutipan di dalam kutipan: *"Kau dengar bunyi 'tung-tung-tung' tadi?" kata Dimas.*
3. Mengapit makna/penjelasan kata: *tergugat 'yang tergugat'*
**Tanda petik ganda ("...") digunakan:**
1. Judul: *Ayah membaca berita berjudul "BBM Naik per April 2026" di koran Kompas.*
2. Istilah asing/ilmiah yang punya arti khusus: *Dilarang memberikan "amplop" kepada petugas bandara!*
3. Mengapit petikan langsung dari dialog/naskah/bahan tertulis: *Pasal KUHP 27 ayat 3 mengatakan "Setiap orang dilarang..."*
**Kata baku** (sering keluar di soal):
- fondasi ✓ / pondasi ✗
- analisis ✓ / analisa ✗
- hektare ✓ / hektar ✗
- konstruksi ✓ / kontruksi ✗
- urine ✓ / urin ✗
- konkret ✓ / konkrit ✗
**Kata serapan** — disesuaikan dengan EBI:
- landscape → lanskap ✓ / lansekap ✗
### IND-12 — Kalimat Inti / Transformasi
- Pola kalimat inti: **S + P (+ O/Pel)** — tanpa keterangan, tanpa klausa relatif
- **Sinti Pinti** (S inti, P inti)
- Langkah: (1) temukan subjek inti, (2) temukan predikat inti, (3) temukan objek/pelengkap jika ada, (4) hapus semua keterangan dan klausa "yang..."
**Cara menentukan S/P/O/Pel/Ket:**
- **S**: di awal kalimat, tidak didahului konjungsi
- **P**: mengandung imbuhan *me-, ber-, di-, ter-, ke-an*
- **O**: muncul setelah Predikat berimbuhan *me-* — **dapat** dipisahkan/dipasifkan
- **Pel**: muncul setelah Predikat — **tidak dapat** dipisahkan (selain imbuhan *me-*)
- **Ket**: ada konjungsi atau preposisi (*di, ke, dari*)
Contoh 1 — *"Situs ini menunjukkan adanya perencanaan ruang yang matang"*
→ S: *Situs*, P: *menunjukkan*, O: *adanya perencanaan ruang*

Contoh 2 — *"Sumur resapan dapat menampung dan menahan air hujan, baik yang mengalir dari atap rumah maupun yang langsung jatuh ke tanah"*
→ S: *Sumur resapan*, P: *dapat menampung dan menahan*, O: *air hujan...*

Contoh 3 — *"Mereka membandingkan hasil dari empat kalkulator yang..."*
→ S: *Mereka*, P: *membandingkan*, O: *hasil dari empat kalkulator...*

### IND-13 — Menyusun / Menggabungkan Kalimat
- **Penggabungan kalimat**: dua kalimat digabung menggunakan konjungsi yang tepat → gunakan konjungsi **intrakalimat**
- **Pemisahan kalimat**: satu kalimat panjang dipisah → gunakan konjungsi **antarkalimat**
- **Kata rujukan** untuk penggabungan: *ini, tersebut, itu, -nya, ber-...*
- Pastikan hasil penggabungan memenuhi syarat kalimat efektif (lihat IND-7)
- Perhatikan urutan logis: kalimat sebab mendahului akibat, kalimat umum mendahului kalimat khusus
---

## Cara Membuat Soal

1. Buat **2–3 teks bacaan** dalam bahasa Indonesia, **masing-masing 150–250 kata**.
2. **WAJIB** beri nomor kalimat pada setiap kalimat dalam teks: `(1) ... (2) ... (3) ...`
3. **Variasikan topik** tiap sesi: pilih dari sains, teknologi, lingkungan hidup, sosial-budaya, ekonomi, kesehatan, sejarah, pendidikan. Minimal 2 topik berbeda per sesi.
4. Setiap teks menghasilkan **6–10 soal** dari tipe yang berbeda-beda.
5. Total soal = 20.
6. Setiap soal: **5 pilihan (A–E)**, satu jawaban benar.
7. Tentukan kunci jawaban (index 0–4) dan buat pembahasan singkat tiap soal.
8. Soal tipe IND-7 dan IND-11: sertakan teks asli yang bermasalah di dalam soal dan tampilkan perbaikan di pilihan jawaban.
9. Soal tipe IND-2 dan IND-6: gunakan tanda `[...]` untuk menandai bagian yang kosong/rumpang di teks soal.
### Contoh Soal per Tipe

**IND-1**: "Paragraf kedua teks di atas termasuk jenis paragraf..." → opsi: Deskripsi, Eksposisi, Persuasi, Argumentasi, Narasi

**IND-2**: Kalimat (5) teks berisi `[...]` → "Kalimat yang tepat untuk melengkapi kalimat (5) adalah..."

**IND-4**: "Konjungsi yang tepat untuk menggantikan kata bergaris bawah pada kalimat (3) adalah..."

**IND-7**: "Kalimat (4) tidak efektif karena... Perbaikan yang tepat adalah..."

**IND-8**: "Penulisan huruf kapital yang tidak tepat terdapat pada kalimat..."

**IND-10**: "Judul yang paling tepat untuk teks di atas adalah..."

**IND-11**: "Penulisan kata yang tidak baku terdapat pada kalimat..."

**IND-12**: "Kalimat inti dari kalimat (6) adalah..."

---

## Struktur Data JavaScript

### Array `passages`

```javascript
const passages = [
  {
    id: 0,
    label: "Teks 1",
    text: `(1) Kalimat pertama dengan nomor. (2) Kalimat kedua. (3) Kalimat ketiga dan seterusnya.

(4) Paragraf baru dimulai di sini. (5) Kalimat kelima. (6) Kalimat penutup paragraf.`
  },
  {
    id: 1,
    label: "Teks 2",
    text: `(1) Teks kedua dimulai di sini...`
  }
];
```

> **Penting**: Setiap kalimat diberi nomor dalam tanda kurung `(1)`, `(2)`, dst. Paragraf baru dipisah dengan `\n\n`.

### Array `Qs`

```javascript
const Qs = [
  {
    passageId: 0,
    cat: "Judul Teks",
    q: "Judul yang paling tepat untuk teks di atas adalah...",
    opts: [
      "Dampak Perubahan Iklim terhadap Ekosistem",
      "Pengelolaan Limbah Industri di Indonesia",
      "Upaya Pelestarian Hutan Tropis Nusantara",
      "Krisis Air Bersih di Daerah Perkotaan",
      "Teknologi Hijau untuk Masa Depan Berkelanjutan"
    ],
    ans: 2,
    exp: [
      "✗ Salah. Teks tidak membahas dampak perubahan iklim — tidak ada pembahasan tentang cuaca atau suhu.",
      "✗ Salah. Pengelolaan limbah industri tidak disinggung dalam teks ini sama sekali.",
      "✓ Benar. Kata kunci yang paling sering muncul adalah 'hutan', 'pelestarian', dan 'tropis'. Judul C mencerminkan isi keseluruhan teks.",
      "✗ Salah. Krisis air bersih tidak dibahas dalam teks ini.",
      "✗ Salah. Teknologi hijau hanya disebut sebagai detail pendukung, bukan topik utama teks."
    ]
  }
];
```

> **Catatan**: opsi A–E ditulis langsung di dalam string termasuk hurufnya. Index `ans` menggunakan 0–4.

---

## Format Output: Inline Widget (visualize:show_widget)

**WAJIB** gunakan tool `visualize:show_widget` — BUKAN file HTML / `present_files`. Widget muncul langsung di chat.

Sebelum memanggil `show_widget`, panggil dulu `visualize:read_me` dengan module `["interactive"]` secara diam-diam.

### Fitur Wajib Widget

- **Intro screen** tampil sebelum ujian: label "UTBK / SNBT", judul subtes, stats row Soal/Waktu dengan divider, tombol "Mulai ujian" full width. Timer BELUM berjalan sampai tombol ini ditekan.
- **Timer 20 menit (1200 detik)** hitung mundur di pojok kanan atas. Mulai saat "Mulai ujian" ditekan. Berubah merah saat sisa ≤ 5 menit.
- **Teks bacaan penuh** dengan nomor kalimat tampil di atas soal.
- **Label passage** selalu tampil, baik saat mengerjakan maupun review (bukan hanya setelah submit).
- **Navigasi soal satu per satu** dengan dot navigator (20 dots).
- **5 pilihan (A–E)** per soal dengan huruf lingkaran.
- **Tombol Prev / Next**. Di soal terakhir, tombol Next berubah jadi "Submit" — langsung submit & tampilkan halaman hasil.
- **Halaman hasil**: skor, grade, pesan, stats, breakdown per kategori IND, tombol "Review jawaban" & "Coba lagi", credit block mqsth.
- **Review mode**: setelah submit, semua soal tampil dengan highlight benar/salah + pembahasan. Navigasi Prev/Next/dot TETAP AKTIF. Flag `reviewMode=true`. Next di soal terakhir berubah "Lihat Hasil".
### Perilaku Passage di Widget

Saat `renderQ()` dipanggil:
- Ambil `passages[Qs[cur].passageId]`
- Label passage (`p.label`) selalu tampil — tidak pakai kondisi `revealed[cur]`
- Teks passage ditampilkan penuh
---

## Template CSS

```css
* { box-sizing: border-box; margin: 0; padding: 0; }
#qw { font-family: var(--font-sans, system-ui, sans-serif); padding: 1rem 0; max-width: 720px; }
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
.passage-label { font-size: 10.4px; color: var(--color-text-tertiary, #94A3B8); text-transform: uppercase; letter-spacing: .07em; font-weight: 600; margin-bottom: 8px; }
.passage-text { font-size: 13px; color: var(--color-text-secondary, #64748B); line-height: 1.8; margin-bottom: 1.25rem; }
.passage-text p { margin-bottom: 0.75em; }
.passage-text p:last-child { margin-bottom: 0; }
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
.bottom-nav { display: flex; gap: 8px; margin-top: 1.25rem; align-items: center; justify-content: flex-start; }
.btn-nav { background: transparent; border: 0.5px solid var(--color-border-secondary, #CBD5E1); border-radius: 8px; padding: 9px 16px; font-size: 13px; cursor: pointer; font-family: inherit; color: var(--color-text-primary, #1E293B); }
.btn-nav:hover { background: var(--color-background-secondary, #F8FAFC); }
.btn-primary { background: var(--color-text-primary, #1E293B); color: var(--color-background-primary, #fff); border: none; border-radius: 8px; padding: 9px 18px; font-size: 13px; cursor: pointer; font-family: inherit; }
.btn-primary:hover { opacity: 0.85; }
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
.review-banner { font-size: 10.4px; color: var(--color-text-tertiary, #94A3B8); text-align: center; padding: 6px 0; margin-bottom: 8px; letter-spacing: .04em; text-transform: uppercase; }
#qw, #qw * { -webkit-user-select: none; -moz-user-select: none; -ms-user-select: none; user-select: none; }
```

---

## Template JS Lengkap

```javascript
// passages[] dan Qs[] di sini (isi dengan konten baru setiap sesi)

function shuffleArray(arr) {
  for (let i = arr.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [arr[i], arr[j]] = [arr[j], arr[i]];
  }
}

let cur = 0, answers = new Array(Qs.length).fill(null);
let revealed = new Array(Qs.length).fill(false);
let totalSec = 1200, timerInt, quizDone = false, reviewMode = false;

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

function renderPassage(p) {
  const paragraphs = p.text.split(/\n\n+/).map(para => `<p>${para.trim()}</p>`).join('');
  const lbl = `<div class="passage-label">${p.label}</div>`;
  return `${lbl}<div class="passage-text">${paragraphs}</div>`;
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
  const p = passages[q.passageId];
  document.getElementById('q-num-val').textContent = cur + 1;
  buildDots();
  let html = renderPassage(p);
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
    const optLabels = ['A','B','C','D','E'];
    const svgX = `<svg width="14" height="14" viewBox="0 0 14 14" fill="none"><circle cx="7" cy="7" r="6.5" stroke="#D85A30" stroke-width="1"/><path d="M4.5 4.5L9.5 9.5M9.5 4.5L4.5 9.5" stroke="#D85A30" stroke-width="1.4" stroke-linecap="round"/></svg>`;
    const svgC = `<svg width="14" height="14" viewBox="0 0 14 14" fill="none"><circle cx="7" cy="7" r="6.5" stroke="#1D9E75" stroke-width="1"/><path d="M4 7L6.2 9.2L10 5" stroke="#1D9E75" stroke-width="1.4" stroke-linecap="round" stroke-linejoin="round"/></svg>`;
    let expContent = '';
    if (userAns !== null && userAns !== q.ans && Array.isArray(q.exp) && q.exp[userAns]) {
      expContent += `<div class="exp-block exp-wrong-block"><div class="exp-head"><span class="exp-pill">Pilihanmu</span><span class="exp-opt-lbl">${optLabels[userAns]}</span><span class="exp-svg">${svgX}</span></div><div class="exp-body">${q.exp[userAns]}</div></div>`;
    }
    const correctLbl = optLabels[q.ans];
    const correctExp = Array.isArray(q.exp) ? q.exp[q.ans] : q.exp;
    const correctPillTxt = (userAns === q.ans) ? 'Pilihanmu' : 'Jawaban Benar';
    expContent += `<div class="exp-block exp-correct-block"><div class="exp-head"><span class="exp-pill">${correctPillTxt}</span><span class="exp-opt-lbl">${correctLbl}</span><span class="exp-svg">${svgC}</span></div><div class="exp-body">${correctExp}</div></div>`;
    html += `<div class="exp-box">${expContent}</div>`;
  }
  document.getElementById('q-area').innerHTML = html;
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
  if (pct>=90) { grade='Excellent'; msg='Luar biasa, siap UTBK!'; }
  else if (pct>=75) { grade='Proficient'; msg='Hasil bagus. Asah kategori lemah dan kamu siap!'; }
  else if (pct>=60) { grade='Developing'; msg='Fondasi solid. Fokus ke konjungsi dan kalimat efektif.'; }
  else { grade='Perlu Latihan'; msg='Ulangi materi dan coba lagi. Konsistensi adalah kunci.'; }
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
  totalSec = 1200; quizDone = false; reviewMode = false;
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

## HTML Skeleton Widget

```html
<style>/* CSS template di atas */</style>
<div id="qw">
  <div id="intro-screen">
    <div class="intro-wrap">
      <div class="intro-utbk">UTBK / SNBT</div>
      <div class="intro-title">Pemahaman Bacaan & Menulis</div>
      <div class="intro-stats-row">
        <div><div class="intro-stat-key">Soal</div></div>
        <div><div class="intro-stat-key">Waktu</div></div>
      </div>
      <hr class="intro-divider">
      <div class="intro-stats-row">
        <div><div class="intro-stat-val">20</div></div>
        <div><div class="intro-stat-val">20 menit</div></div>
      </div>
      <hr class="intro-divider" style="margin-bottom:1.5rem">
      <button class="btn-primary" style="width:100%;padding:10px 0" onclick="startQuiz()">Mulai ujian</button>
    </div>
  </div>
  <div id="quiz-screen" style="display:none">
    <div class="top-bar">
      <div class="timer-box" id="timer-el">
        <svg width="13" height="13" viewBox="0 0 13 13" fill="none">
          <circle cx="6.5" cy="6.5" r="5.5" stroke="currentColor" stroke-width="1"/>
          <path d="M6.5 3.5V6.5L8.5 8" stroke="currentColor" stroke-width="1" stroke-linecap="round"/>
        </svg>
        <span id="timer-txt">20:00</span>
      </div>
    </div>
    <div class="quiz-body">
      <div class="nav-dots" id="nav-dots"></div>
      <div class="quiz-main">
        <div class="content-header">
          <div class="content-header-label">Pemahaman<br>Bacaan & Menulis</div>
          <div class="content-header-center">
            <div class="q-num-label">Nomor Soal</div>
            <div class="q-num-val" id="q-num-val">1</div>
          </div>
        </div>
        <div class="review-banner" id="review-banner" style="display:none">MODE REVIEW</div>
        <div class="q-area" id="q-area"></div>
        <div class="bottom-nav" id="bottom-nav">
          <button class="btn-nav" id="btn-prev" onclick="goTo(cur-1)">Prev</button>
          <button class="btn-primary" id="btn-next" onclick="handleNext()">Next</button>
        </div>
      </div>
    </div>
  </div>
  <div id="result-screen" style="display:none"></div>
</div>
<script>/* passages[], Qs[], lalu semua fungsi JS di atas */</script>
```

---

## Instruksi Tambahan

- Timer mulai saat tombol "Mulai ujian" ditekan, bukan saat widget render.
- Setelah widget muncul, tambahkan pesan singkat di chat dengan format berikut (tanpa bold/italic): baris 1 `LATIHAN SOAL PEMAHAMAN BACAAN DAN MENULIS`, baris 2 `{tanggal} {bulan} {tahun}`, baris kosong, lalu `20 soal siap! Timer 20 menit jalan setelah kamu tekan Mulai. Selamat mengerjakan!` — tanggal/bulan/tahun sesuai hari ini.
- **Acak urutan soal**: gunakan fungsi `shuffleArray(arr)` (Fisher-Yates). Panggil di `startQuiz()` dan `restartQuiz()` agar urutan berbeda setiap kali mulai maupun restart. JANGAN lakukan shuffle sebagai inline loop di awal script.
- Variasikan topik teks dan soal di setiap sesi. Jangan ada dua sesi berturut-turut dengan topik yang sama.
- **WAJIB** beri nomor kalimat `(1)`, `(2)`, dst. pada setiap kalimat di semua teks. Tanpa ini, soal tipe IND-7, IND-8, IND-11 tidak bisa dibuat secara autentik.
- Soal yang menyebutkan teks bermasalah (IND-7, IND-11): kutip kalimat bermasalahnya secara lengkap di dalam teks soal agar tidak perlu bolak-balik ke teks bacaan.
- **INGAT**: selalu 5 opsi (A-E), index jawaban 0-4, gunakan `show_widget` bukan file HTML. **Opsi jawaban TIDAK diawali prefix huruf** (`A.`, `B.`, dst.) — langsung tulis teks opsinya saja.
- **Pembahasan (q.exp) — wajib array 5 string** (index 0–4, sesuai urutan opsi A–E):
  - **Opsi BENAR**: Mulai dengan `"✓ Benar."` lalu jelaskan kenapa opsi ini tepat — sertakan kata kunci dari teks atau strategi/rumus yang relevan dari materi konten.
  - **Opsi SALAH**: Mulai dengan `"✗ Salah."` lalu jelaskan SPESIFIK kenapa keliru — jangan cuma bilang "tidak tepat". Tunjukkan kontradiksi atau alasan linguistiknya.
  - Di review mode: jika user salah, blok merah (`exp-wrong-block`, pill "Pilihanmu") tampil dulu, lalu blok hijau (`exp-correct-block`, pill "Jawaban Benar"). Jika user benar, hanya blok hijau yang tampil TAPI pill-nya dinamis jadi "Pilihanmu" (bukan "Jawaban Benar") karena pilihan user = jawaban benar. Jika user skip (tidak menjawab), hanya blok hijau tampil dengan pill "Jawaban Benar" (karena bukan pilihan user).
- **Exp-box format (r12)**: JANGAN gunakan `.exp-wrong` / `.exp-correct` dengan border-left. Gunakan struktur blok baru: `.exp-box` (flex column, gap 6px) berisi `.exp-block.exp-wrong-block` (border #F0997B) dan `.exp-block.exp-correct-block` (border #5DCAA5). Tiap blok punya `.exp-head` (background tipis merah/hijau) berisi: `.exp-pill` (pill tag teks), `.exp-opt-lbl` (huruf opsi A-E), `.exp-svg` (inline SVG X merah / centang hijau). Body teks ada di `.exp-body` dengan background putih/transparan.
- **INGAT r12**: dot navigator TIDAK circle (border-radius: 0) dan posisinya di KIRI soal (vertical column), bukan di atas. Layout: `.quiz-body` flex row → `.nav-dots` kiri + `.quiz-main` kanan. Selalu gunakan struktur HTML skeleton r12.
- **TIPE SOAL (q.cat)**: Tulis nama tipe soal langsung — BUKAN kode IND. Contoh: `"Judul Teks"`, `"Konjungsi"`, `"Kalimat Efektif"`, `"Huruf Kapital"`, `"Kalimat Rumpang"`, `"Paragraf Rumpang"`, `"Makna Kata"`, `"Penempatan Kalimat"`, `"Penulisan Kata"`, `"Kalimat Inti"`, `"Gagasan Utama"`, `"Gabung Kalimat"`. DILARANG pakai format `"IND-10: Judul Teks"` atau kode apapun. TIDAK ditampilkan saat mengerjakan soal. Hanya muncul di pembahasan (review mode). Di `renderQ()`, gunakan `if (revealed[cur]) html += \`<div class="q-meta">${q.cat}</div>\`;` — BUKAN tanpa kondisi.
- **Header**: `content-header` — label "Pemahaman\nBacaan & Menulis" kiri, `content-header-center` dengan "NOMOR SOAL" + angka kanan. Timer di `.top-bar` pojok kanan. TIDAK ada badge pill lama.
- **Passage label**: selalu tampil saat mengerjakan maupun review — BUKAN hanya saat `revealed[cur]`. Implementasi: `renderPassage(p)` tanpa kondisi, label langsung dirender tanpa syarat.
- **LARANGAN dalam teks soal** — dua aturan wajib untuk `q.q`:
  1. **Jangan sebut label teks**: DILARANG menyebut "Teks 1", "Teks 2", "Teks 3", "teks pertama", "teks kedua", "teks ketiga", dst. Label passage sudah terlihat di atas soal. Cukup tulis `"teks tersebut"`, `"bacaan di atas"`, atau langsung rujuk nomor kalimat: `"Kalimat (8) yang tepat untuk melengkapi bacaan adalah..."`
  2. **Jangan referensikan posisi soal lain**: DILARANG menyebut "soal sebelumnya", "soal di atas", "pertanyaan sebelumnya", atau sejenisnya. Soal diacak setiap sesi (Fisher-Yates), jadi urutan tidak stabil. Setiap soal harus self-contained — semua konteks cukup dari teks passage dan nomor kalimat.
- **selectOpt**: toggle deselect — klik opsi yang sudah dipilih set ulang ke `null`.
- **Timer warn**: menyala merah saat `totalSec <= 300` (5 menit tersisa).
- **Credit block**: tampil di result screen — "BUILT BY @muqsith.ai" dengan link Instagram, teks "Feedback & saran? DM aja 👋".
- **Anti-copy**: CSS `user-select: none` pada `#qw, #qw *` + JS listener `copy` dan `contextmenu` di `DOMContentLoaded`.
