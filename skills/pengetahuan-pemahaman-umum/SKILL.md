---
name: pengetahuan-pemahaman-umum-r13
description: "Gunakan skill ini saat pengguna menyebut \"pengetahuan dan pemahaman umum\", \"PPU\", \"latihan PPU\", \"soal PPU\", \"latihan TOBK PPU\", \"latihan UTBK PPU\", atau frasa serupa yang menandakan ingin latihan subtes Pengetahuan dan Pemahaman Umum. Skill ini membuat 20 soal pilihan ganda (soal mandiri, bacaan pendek, bacaan panjang) mencakup semua tipe soal PPU (relasi makna, analogi, afiksasi, konjungsi, frasa, kalimat efektif, makna kata, gaya bahasa/majas, gejala perubahan makna, sikap penulis, ilustrasi teks, mengurai paragraf, bahasa hipotesis, dll.), disajikan sebagai widget interaktif tertanam di chat dengan timer 10 menit, intro screen, skoring otomatis, dan pembahasan lengkap dengan navigasi penuh di mode review. Kode PPU tidak tampil saat mengerjakan soal; hanya muncul di pembahasan. Panjang teks dikalibrasi per tipe soal berdasarkan analisis korpus asli. Exp-box: pill tag + huruf opsi + SVG ikon.\n"
---

# Pengetahuan & Pemahaman Umum r13 — TOBK/UTBK Practice

> Skill dibuat oleh **mqsth**
>
> © 2026 Muhammad Rayyis Muqsith ([@muqsith.ai](https://instagram.com/muqsith.ai)). Dilisensikan di bawah [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/). Boleh dipakai dan dimodifikasi untuk non-komersial dengan atribusi. Dilarang menjual, memasukkan ke layanan berbayar, atau mengklaim sebagai karya sendiri. Soal dibuat dengan bantuan AI, bukan soal resmi UTBK/SNBT, dan pembahasan bisa mengandung kekeliruan.

## Overview

Skill ini membuat **widget interaktif tertanam di chat** (bukan file download) berupa ujian **20 soal** Pengetahuan dan Pemahaman Umum selama **10 menit**. Setiap kali dipanggil, buat soal **baru yang berbeda** (jangan ulangi soal yang sama).

### Deskripsi Resmi Subtes (Sumber: SNPMB)

Subtes Pengetahuan dan Pemahaman Umum bertujuan untuk mengukur kemampuan kognitif melalui pengetahuan leksikal, informasi, dan pengetahuan umum yang dianggap penting dalam lingkup sosial budaya Indonesia, serta mengukur perkembangan bahasa. Tes ini dirancang dengan menekankan pada keterkaitan antara permasalahan dan bacaan untuk menilai kemampuan menganalisis, menghubungkan, dan menyimpulkan berbagai bentuk kata, frasa, serta kalimat sesuai dengan konteks dalam bacaan. Subtes ini memuat pertanyaan singkat, bacaan pendek dengan satu pertanyaan, dan bacaan panjang yang mencakup beberapa pertanyaan.

> Implikasi untuk pembuatan soal: **variasikan topik teks** tiap sesi. Bacaan panjang dipilih dari topik sosial budaya, sains, teknologi, ekonomi, atau lingkungan hidup. Soal mandiri berupa pengetahuan leksikal murni (relasi makna, analogi, afiksasi).

---

## Format Soal Autentik UTBK PPU

PPU menggunakan **tiga format soal** dalam satu sesi:

| Format | Deskripsi | Jumlah Target |
|---|---|---|
| **Soal mandiri** | Pertanyaan singkat tanpa teks bacaan. Menguji pengetahuan leksikal: relasi makna, analogi kata, frasa sepola, afiksasi, pola kalimat. | ~6 soal |
| **Bacaan pendek** | Teks 100–140 kata (minimal 7 kalimat; JANGAN di bawah 100 kata) diikuti **1 soal**. Menguji pemahaman makna kata/kalimat, konjungsi, atau kalimat rumpang dalam konteks. | ~4 soal (2–3 teks pendek) |
| **Bacaan panjang** | Teks 150–260 kata (minimal 10 kalimat; JANGAN di bawah 150 kata) diikuti **5–8 soal**. Menguji sikap penulis, pola kalimat, frasa, mengurai paragraf, kalimat efektif, ilustrasi teks, dll. | ~10 soal (1–2 teks panjang) |

> ⚠️ **Format soal mandiri TIDAK menggunakan teks.** Set `passageId: null` untuk soal ini. `renderQ()` harus mengecek `passageId === null` sebelum merender passage.

> ⚠️ **Teks bacaan (pendek maupun panjang) WAJIB diberi nomor kalimat** — format `(1) Kalimat pertama. (2) Kalimat kedua.` — karena banyak soal mengacu ke nomor kalimat tertentu.

### Kalibrasi Panjang Teks per Kelompok Tipe Soal (Baru di r9)

Analisis statistik terhadap korpus soal asli (lihat dokumen "Analisis Pola Struktur Teks per Topik") menunjukkan bahwa panjang teks yang ideal **berbeda tergantung tipe soal yang akan diujikan di atasnya**. Gunakan tabel ini untuk mengalibrasi panjang setiap teks yang dibuat:

| Kelompok Tipe Soal | Kode PPU Terkait | Target Kata (median korpus asli) | Target Kalimat | Target Paragraf |
|---|---|---|---|---|
| Morfologi (imbuhan, konjungsi, kata berpasangan tetap) | PPU-13, PPU-14, PPU-15 | ~120–140 kata | ~7 kalimat | 1 paragraf |
| Sintaksis (pola kalimat, frasa sepola, kalimat efektif) | PPU-2, PPU-4, PPU-8 | ~110–130 kata | ~6–7 kalimat | 1 paragraf |
| Semantik (relasi makna, makna kalimat, gaya bahasa, perubahan makna) | PPU-3, PPU-5, PPU-6, PPU-7, PPU-11 | ~150–170 kata | ~10 kalimat | 2 paragraf |
| Paragraf & Pragmatik (sikap penulis, mengurai paragraf, analogi, ilustrasi teks) | PPU-1, PPU-9, PPU-12, PPU-16 | ~180–200 kata | ~10–11 kalimat | 1–2 paragraf. Untuk soal mengurai paragraf: paragraf yang akan diurai harus panjang (≥ 8 kalimat) dan ditampilkan sebagai SATU blok tanpa jeda (lihat aturan di PPU-9) |

> Catatan: Bahasa Hipotesis (PPU-10) tidak memakai passage biasa — ia memakai tabel/daftar kalimat berpasangan bahasa asli–bahasa sandi (lihat bagian PPU-10), bukan teks naratif bernomor kalimat.

> Jika satu teks panjang dipakai untuk beberapa tipe soal sekaligus (umum terjadi — satu bacaan bisa menyertai soal imbuhan, konjungsi, DAN sikap penulis), pilih target panjang dari kelompok soal yang paling menuntut (biasanya kelompok Paragraf & Pragmatik) agar teksnya cukup kaya untuk semua tipe soal yang menyertainya.

**Aturan jumlah paragraf per sesi (WAJIB):**
- Kolom "Target Paragraf" pada tabel di atas berlaku untuk **teks panjang**. **Teks pendek (1 soal) selalu 1 paragraf.**
- **Minimal satu dari dua teks panjang WAJIB tampil 2 paragraf** (dipisah baris kosong `\n\n` pada `passages[].text`, nomor kalimat tetap berlanjut, mis. paragraf pertama (1)-(5) dan paragraf kedua (6)-(13)). Teks panjang lainnya boleh 1 paragraf. Jangan membuat semua teks satu paragraf: korpus asli memiliki median 2 paragraf (Semantik) dan 1,5 paragraf (Paragraf & Pragmatik).
- Teks 2 paragraf: paragraf pertama 4–5 kalimat, paragraf kedua ≥ 8 kalimat, dengan pergantian subtopik yang jelas di antara keduanya (mis. masalah → upaya/solusi).
- Soal Mengurai Paragraf diutamakan memakai teks 2 paragraf ini dengan bentuk *"Paragraf kedua teks tersebut sebenarnya terdiri atas dua paragraf. Penguraian yang tepat untuk paragraf kedua adalah..."*; paragraf kedua itu sendiri harus tetap satu blok tanpa jeda (lihat aturan penyajian di PPU-9).

### Kalibrasi Kompleksitas Soal & Opsi Jawaban per Kelompok (Baru di r9)

Panjang teks bacaan bukan satu-satunya dimensi yang perlu dikalibrasi — **bentuk dan kerumitan opsi jawaban (A–E)** juga berbeda nyata antar kelompok tipe soal di korpus asli. Gunakan tabel ini supaya opsi jawaban yang dibuat tidak terlalu sederhana atau terlalu rumit dibanding soal aslinya:

| Kelompok Tipe Soal | Bentuk Opsi Jawaban Khas | Panjang Opsi | Langkah Penalaran | Contoh dari Korpus |
|---|---|---|---|---|
| Morfologi (PPU-13, 14, 15) | Satu kata atau frasa pendek (kata berimbuhan, konjungsi, kata berpasangan) | 1–3 kata | 1 langkah — cocokkan makna imbuhan/konjungsi dengan definisi yang sudah dihapal | `(A) peristirahatan (B) pertanian (C) pemakaman (D) persatuan (E) perkotaan` |
| Sintaksis (PPU-2, 4, 8) | Frasa pendek (frasa sepola) **atau** kalimat utuh (pola kalimat sepola; kalimat efektif/perbaikan) | 2–6 kata untuk frasa; 1 kalimat utuh (±10–20 kata) untuk perbaikan kalimat | 1–2 langkah — kenali pola struktur dahulu, baru cocokkan; untuk kalimat efektif perlu identifikasi letak kesalahan dulu | `(A) induk burung (B) pengaruh budaya (C) pernyataan kontroversial (D) kostum penari (E) riasan wajah` |
| Semantik (PPU-3, 5, 6, 7, 11) | Campuran: kata tunggal (sinonim/antonim/majas) **atau** kalimat utuh (kalimat semakna) **atau** pasangan kata (kalimat rumpang, mis. `hutan dan jenazah`) | 1 kata untuk relasi makna; 1 kalimat utuh (±15–25 kata) untuk kalimat semakna | 1 langkah untuk relasi makna sederhana; 2–3 langkah untuk kalimat semakna (perlu bandingkan makna inti, bukan kemiripan kata per kata) | `(A) Eksploitasi sumber daya alam dan budaya yang bertujuan menarik wisatawan merugikan komunitas global. (B) ...acapkali merugikan masyarakat setempat. (C)...` |
| Paragraf & Pragmatik (PPU-1, 9, 12, 16) | Kombinasi nomor kalimat (mengurai paragraf), kata sentimen tunggal (sikap penulis), peribahasa (analogi), atau frasa jenis ilustrasi | Kombinasi angka (mis. `(1,2,3) dan (4,...,10)`) untuk mengurai paragraf; 1 kata untuk sikap penulis; 1 peribahasa pendek untuk analogi | 2–3 langkah — perlu membaca & memahami keseluruhan teks (bukan satu kalimat saja), lalu menyimpulkan secara holistik (pergantian topik, nada emosi, atau kecocokan makna kias) | `(A) (1, 2, 3, 4) dan (5, 6, 7, 8, 9, 10, 11) (B) (1, 2, 3, 4, 5) dan (6, 7, 8, 9, 10, 11) (C)...` |

**Aturan distraktor (pengecoh) per kelompok:**
- **Morfologi/Sintaksis**: distraktor berupa kata/frasa dengan pola gramatikal mirip tapi makna imbuhan/fungsi sintaksis berbeda (mis. keempat opsi salah tetap memakai imbuhan yang sama tapi bermakna lain: tempat vs proses vs hasil).
- **Semantik**: minimal satu distraktor adalah "jebakan dekat" — kata yang mirip tapi beda kategori (mis. hiponim dipasangkan seolah hipernim, atau sinonim yang sebenarnya hanya mirip rasa/nuansa tapi beda makna inti).
- **Paragraf & Pragmatik**: distraktor untuk soal mengurai-paragraf harus berupa kombinasi nomor yang **masuk akal tapi salah** (memecah di kalimat yang terlalu awal/terlalu akhir, bukan di titik pergantian topik yang sebenarnya); distraktor sikap-penulis harus berupa kata sentimen yang berlawanan arah atau terlalu ekstrem (mis. jawaban benar "prihatin", distraktor "apatis"/"antusias"/"bangga").

---

## Cakupan Tipe Soal

Distribusikan 20 soal dari tipe-tipe berikut (variasikan tiap sesi). **Aturan komposisi (WAJIB): ke-16 tipe soal (PPU-1 s.d. PPU-16) muncul minimal 1 soal setiap sesi**, termasuk PPU-10 Bahasa Hipotesis dan PPU-16 Ilustrasi Teks. Kolom Target adalah rentang variasi di atas minimum itu. 16 tipe × 1 soal = 16 soal; 4 soal sisanya dipakai untuk Analogi Kata ke-2 (wajib) dan 3 slot tambahan yang dirotasi dari Kalimat Efektif, Relasi Makna, Makna Kalimat, Konjungsi, atau Sikap Penulis (jangan memilih kombinasi yang sama dengan sesi sebelumnya). Bahasa Hipotesis tidak boleh tersingkir oleh kuota mandiri: tipe yang bisa berbasis bacaan (Gejala Perubahan Makna, Kata Majemuk, Pola Kalimat) dipindahkan ke teks. Gunakan kode PPU sesuai catatan:

| Kode | Tipe Soal | Format Soal | Target |
|---|---|---|---|
| PPU-1 | Sikap Penulis (pandangan, opini, ide pokok) | Bacaan panjang | 1–2 soal |
| PPU-2 | Kalimat Efektif (identifikasi / perbaikan / kelogisan / keparalelan / kecermatan) | Bacaan panjang/pendek | 2–3 soal |
| PPU-3 | Relasi Makna (sinonim, antonim, hipernim, hiponim, homonim, homofon, homograf, polisemi) | Mandiri / bacaan | 2–3 soal |
| PPU-4 | Pola Kalimat (S+P+O+K+Pel, transformasi aktif-pasif) | Mandiri / bacaan | 1–2 soal |
| PPU-5 | Gaya Bahasa / Majas (metafora, personifikasi, eufimisme, hiperbola, asosiasi/simile) | Bacaan pendek/panjang | 1–2 soal |
| PPU-6 | Gejala Perubahan Makna (ameliorasi, peyorasi, meluas, menyempit, asosiasi, sinestesia) | Mandiri / bacaan | 1 soal |
| PPU-7 | Makna Kalimat (konotasi / denotasi) | Bacaan pendek/panjang | 2–3 soal |
| PPU-8 | Frasa Sepola (D-M, M-D, jenis kata, frasa endosentris/eksosentris) | Mandiri / bacaan | 1–2 soal |
| PPU-9 | Mengurai Paragraf (memilah paragraf, situasi teks) | Bacaan panjang | 1–2 soal |
| PPU-10 | Bahasa Hipotesis / Bahasa Panda | Mandiri | **wajib 1 soal** |
| PPU-11 | Kalimat Rumpang (melengkapi kalimat kosong) | Bacaan pendek/panjang | 1–2 soal |
| PPU-12 | Analogi Kata (hubungan logis antara dua pasang kata) | Mandiri | **minimal 2 soal (wajib)**, maks. 3 |
| PPU-13 | Konjungsi (intrakalimat, antarkalimat, korelatif — pemilihan / perbaikan kata hubung) | Bacaan pendek/panjang | 1–2 soal |
| PPU-14 | Pemajemukan / Kata Berpasangan Tetap | Mandiri / bacaan | 1 soal |
| PPU-15 | Afiksasi (makna imbuhan pe(N)-an, pe(R)-an, ke-an, me-i, me-kan, me(N)-) | Mandiri | 1–2 soal |
| PPU-16 | Ilustrasi Teks (grafik, tabel, skema/bagan, gambar/foto yang paling tepat melengkapi teks) | Bacaan panjang | **wajib 1 soal** |

> Semua kode PPU kini memiliki materi (PPU-5 dan PPU-6 sudah aktif di r9). Jangan buat lebih dari 16 tipe di atas.

---

## Materi Konten (Pengetahuan Inti)

> Gunakan sebagai acuan membuat soal dan pembahasan. Materi berikut diperluas dari korpus asli sehingga contoh kata/frasa jauh lebih kaya dibanding r8.

### PPU-1 — Sikap Penulis dalam Bacaan

Sikap penulis adalah emosi atau nada penulis terhadap permasalahan yang dibahas dalam teks (topik) — bagaimana penulis mengekspresikan tulisannya melalui kata-kata yang dipilihnya. Ini berbeda dari "tujuan teks", karena sikap penulis khusus mendefinisikan posisi emosional/evaluatif penulis terhadap subjek tulisan.

Sikap penulis mencerminkan perasaan, pendapat, dan sudut pandang yang memengaruhi cara pembaca menafsirkan isi teks. Cara menentukan sikap penulis:
1. **Identifikasi gaya penulisan** — emosional, argumen logis, retorika, atau kreatif.
2. **Identifikasi gagasan utama teks** untuk menentukan sifat/sentimen yang berhubungan dengan sikap penulis.
3. **Identifikasi sentimen/emosi tulisan** — positif (menghargai/optimis/bangga), negatif (mengkritik/kecewa/prihatin/cemas), atau netral (tidak mendukung maupun menentang). Sentimen dilihat dari kata emotif, kata sifat, atau penguatan tindakan partisipan dalam teks.

Kosakata sikap penulis yang sering muncul sebagai kunci jawaban: *cemas, prihatin, khawatir, optimis, antusias, kecewa, apatis, apresiatif, skeptis, analitis, senang, bangga, ragu, pesimis, kesal*.

Pola umum: kalimat penutup atau kalimat awal paragraf utama biasanya paling eksplisit menyiratkan sikap ini (contoh: "Hal ini tentu saja sangat mengkhawatirkan...", "Hal ini tentunya hal yang patut kita sambut dengan baik...", "Hadirnya X dapat menjadi titik balik...").

### PPU-2 — Kalimat Efektif

Kalimat efektif adalah kalimat yang disusun berdasarkan kaidah bahasa yang berlaku: memiliki unsur penting (S dan P), memperhatikan ejaan yang disempurnakan, serta cermat dan tepat dalam pilihan kata.

Syarat kalimat efektif:
1. **Hemat kata** — tidak ada kata mubazir.
2. **Logis** — masuk akal, hubungan antarunsur bernalar. Kalimat tidak logis biasanya disebabkan kesalahan pemilihan verba (mis. *"tujuan menulis buku ini adalah diberikan dasar pemahaman"* seharusnya *"memberikan"*; *"dampak Covid-19 juga turut merasakan pada bidang ekonomi"* seharusnya *"dirasakan"*).
3. **Baku** — menggunakan bahasa baku.
4. **Minimal S + P** — struktur kalimat lengkap.
5. **Paralelisme (keparalelan)** — imbuhan sejajar/kesamaan bentuk pada unsur setara dalam satu kalimat. Contoh tidak paralel: *"untuk menganalisis, menentukan, dan simpulkan..."* → paralel: *"untuk menganalisis, menentukan, dan menyimpulkan..."*.
6. **Cermat** — tidak menimbulkan pengertian ganda dan tepat pilihan kata. Contoh tidak efektif: *"Perampok berhasil ditangkap oleh polisi"* → efektif: *"Polisi berhasil menangkap perampok."*
7. **EYD** — sesuai ejaan yang disempurnakan.
8. **Tanpa bahasa asing & daerah** yang tidak perlu.

Kaidah mengubah kalimat aktif menjadi pasif:
- **Kaidah I** (subjek bukan kata ganti orang): tukar S dengan O; ganti *me(N)-* dengan *di-* pada predikat; boleh tambahkan *oleh* (manasuka). Contoh: *Danu menulis puisi* → *Puisi ditulis (oleh) Danu.*
- **Kaidah II** (subjek berupa kata ganti *aku, saya, kami, kita, engkau, kamu, Anda, kalian*): pola S-P-O berubah jadi S-P atau P-S; awalan *me(N)-* dihilangkan; kata keterangan (*akan, dapat, sudah, sedang*) diletakkan sebelum pelaku. Contoh: *Saya sedang membaca buku* → *Buku sedang saya baca.*

Contoh pola soal:
- "Kalimat manakah yang merupakan kalimat efektif/tidak logis?" → cek semua syarat di atas.
- Soal paralelisme: frasa berpemerian yang salah satu unsurnya tidak sejajar bentuknya.
- Soal aktif-pasif: transformasi kalimat sesuai kaidah I atau II.

### PPU-3 — Relasi Makna

- **Sinonim**: persamaan makna kata. Contoh: *baik = bagus*, *manifestasi = perwujudan*, *bohong = dusta*, *bertemu = berjumpa*, *miskin = melarat*.
- **Antonim**: perlawanan makna kata. Contoh: *mahal >< murah*, *gelap >< terang*, *baik >< buruk*, *rampung >< mulai*, *makmur >< susah*.
- **Hipernim**: kata umum (lebih luas maknanya). Contoh: *buah-buahan* (hipernim dari apel, pisang, kiwi); *penyakit* (hipernim dari obesitas); *media sosial* (hipernim dari Facebook, TikTok, X).
- **Hiponim**: kata khusus (lebih sempit maknanya) di bawah satu hipernim. Contoh: *apel, pisang, kiwi* (hiponim dari buah-buahan); *Mei, Juni, Juli* (hiponim dari bulan).
- **Homonim**: bentuk & bunyi sama, makna beda, dibedakan oleh konteks. Contoh: *Badan Ani mengurus (menyusut) beberapa kilogram setelah mengurus (merawat) ibunya yang sakit.*
- **Homofon**: bunyi sama, ejaan/makna beda. Contoh: *Bang* (panggilan) Amril bekerja di *Bank* (lembaga keuangan).
- **Homograf**: ejaan sama, makna & pengucapan bisa beda tergantung konteks. Contoh: *apel* (buah) vs *apel* (upacara).
- **Polisemi**: satu kata, banyak makna terkait dari satu makna pokok. Contoh: *kepala* pada *kepala sekolah, kepala keluarga, kepala desa, kepala paku, kepala botak*.

Makna lebih sempit = hiponim | Makna lebih luas = hipernim.

Kalimat yang semakna: dapat dicapai dengan (a) mengganti kata dengan sinonimnya, (b) mengubah aktif↔pasif (me- ↔ di-), (c) mengubah posisi anak kalimat yang mendahului induk kalimat (ditandai koma) tanpa mengubah makna inti.

Hubungan Kata (untuk analogi berbasis relasi makna):
- Pola [antonim]: *mental : fisik* = *haus : gagah* (tidak selalu berpasangan sempurna — periksa dahulu jenis hubungannya).
- Pola [hiponim]: *nikel : logam* = *anggar : olahraga*.

Hubungan Asosiasi (persamaan sifat/karakteristik, bukan makna langsung):
- *kerikil* → hambatan (mis. "kerikil serius" = masalah/kendala serius).
- *biang* → asal/sumber (mis. "biang kerok" = sumber masalah).
- *tikus berdasi* → koruptor (pejabat yang licik/curang).
- *akal bulus* → kelicikan/tipu muslihat.
- *wadah* → tempat/pendukung.
- *bola mata* → perhatian orang banyak.
- *segudang* → banyak.

Sinonim kata waktu yang sering muncul: *tulat* = dua hari setelah besok; *langkat* = tiga hari setelah hari ini; *tubin* = empat hari setelah hari ini.

### PPU-4 — Pola Kalimat

Pola dasar: S-P, S-P-O, S-P-K, S-P-Pel, S-P-O-Pel.

**Subjek**: biasanya di awal kalimat (bukan konjungsi); dapat berupa kata/frasa benda maupun kata kerja (mis. *"Membakar sampah merupakan kegiatan yang dilarang..."*).

**Predikat**: umumnya kata kerja berimbuhan *me(N)-, ber-, di-, ter-*; bisa juga verba relasional (*adalah, ialah, merupakan, menjadi*) atau kata benda/sifat/bilangan langsung (*Dia pintar*; *Temannya seorang arsitek*; *Mereka berlima*). Predikat tidak boleh didahului konjungsi bertingkat.

**Objek** vs **Pelengkap**:
| Objek | Pelengkap |
|---|---|
| Kategori kata: nomina. Contoh: *Rizal menggambar gedung.* | Bisa nomina, verba, atau adjektiva. Contoh: *Syifa bermain boneka* (nomina); *Dia pergi bertamasya* (verba); *Kerudungnya berwarna hijau* (adjektiva). |
| Letak langsung di belakang verba aktif transitif (ber-*me(N)-*, dapat dipasifkan) tanpa preposisi. | Letak di belakang verba intransitif (tak dapat dipasifkan) atau di belakang objek pada verba dwitransitif. Contoh: *Ibu membelikan adik kue.* |

**Keterangan**: kehadirannya manasuka (opsional); letak bebas kecuali di antara P dan O/Pel; sering didahului kata depan (*di, ke, dari, oleh, pada, bagi, tentang, kepada*) atau konjungsi bertingkat (kecuali *yang* dan *bahwa*).

Jenis kalimat aktif berdasarkan hubungan P dengan pendamping kanan:
- **Aktif transitif**: predikat perlu objek. Contoh: *Kakak sedang meminum susu.* (S-P-O)
- **Aktif semitransitif**: objek boleh ditanggalkan. Contoh: *Dia makan (roti).*
- **Aktif dwitransitif**: perlu objek dan pelengkap. Contoh: *Kakak meminjami kawannya sebuah novel.* (S-P-O-Pel)
- **Aktif intransitif**: tak perlu objek, bisa diikuti pelengkap/keterangan. Contoh: *Ibu memasak di dapur.* (S-P-K)

**Kalimat pasif** ditandai predikat berawalan *di-, te(R)-, ke-an*, atau tanpa afiks. Contoh: *Pameran itu akan dibuka oleh Pak Bupati.*

Contoh pola soal:
- *"Karena geopolitik sangat memengaruhi stabilitas ekonomi global."* → ini bukan kalimat lengkap, hanya frasa Keterangan (K) tanpa S-P.
- *"Analisis dan pemahaman geopolitik dibutuhkan pemerintah"* → S | P | Pel.

**Bentuk soal Pola Kalimat (WAJIB mengikuti korpus asli):**
- Pertanyaan: *"Kalimat dalam teks yang sepola dengan kalimat (n) adalah..."* atau *"Kalimat yang sepola dengan kalimat berikut: [kalimat] adalah kalimat..."*.
- **Opsi = 5 kalimat/nomor kalimat utuh** dengan pola berbeda-beda (mis. S-P-O, K-S-P-O, S-P-K, S-P-Pel, kalimat majemuk). Peserta harus memetakan fungsi tiap unsur (2 langkah), bukan sekadar menyebut label.
- **DILARANG** membuat opsi berupa label pola (`S-P-K`, `S-P-O`, dst.). Label pola hanya boleh ditulis di pembahasan.

### PPU-5 — Gaya Bahasa / Majas (BARU AKTIF di r9)

Menurut KBBI, gaya bahasa (majas) adalah pemanfaatan kekayaan bahasa untuk memperoleh efek/kesan tertentu. Majas yang sering diujikan di PPU:

1. **Metafora** — memperbandingkan suatu benda dengan benda lain yang punya sifat sama, tanpa kata pembanding. Contoh: *"Raja siang"* (matahari) bersinar di ufuk timur.
2. **Personifikasi** — benda mati diperbandingkan dengan makhluk bernyawa. Contoh: *"Tangkai penaku menari-nari di atas kertas."*
3. **Eufimisme** — mengganti kata agar terdengar lebih sopan / menghindari tabu. Contoh: *tunawisma* (untuk gelandangan), *tunakarya* (untuk pengangguran); *"Para tunawisma diberikan bantuan oleh pemerintah setempat."*
4. **Hiperbola** — pernyataan berlebihan. Contoh: *"Harga-harga sekarang sangat mencekik leher."*; *"membuat air liur menetes"*; *"tengkorak sangat besar dan lebar yang bisa menampung isi dunia"*; *"membuat bumi gonjang-ganjing tidak karuan"*.
5. **Asosiasi/Simile/Perumpamaan** — membandingkan dua hal dengan kata pembanding eksplisit (*bagai, bagaikan, seperti, bak, ibarat, laksana*) atau implisit. Contoh: *"mukanya pucat bagai mayat"*; *"sampah sudah menggunung"*; *"kepemilikan perangkat digital antara perempuan dan laki-laki seperti langit dan bumi"*; *"seperti tangan yang siap menangkap burung"*.

Tips membedakan dari kalimat bermakna sebenarnya (denotatif): cari kata yang digunakan secara kias/tidak literal dalam konteks kalimat (mis. kata *angin* dalam *"membawa angin perubahan"* bukan bermakna udara bergerak).

### PPU-6 — Gejala Perubahan Makna (BARU AKTIF di r9)

1. **Ameliorasi** — makna sekarang dirasakan lebih baik/lebih halus dari makna lama. Contoh: *gelandangan → tunawisma*; *pengangguran → tunakarya*; *pembantu → asisten rumah tangga*.
2. **Peyorasi** — makna sekarang dirasakan kurang baik dari makna lama. Contoh: *gerombolan, kaki tangan, penjilat, oknum*.
3. **Meluas** — cakupan makna sekarang lebih luas dari makna lama. Contoh: *berlayar* (dulu khusus perahu layar, sekarang mencakup semua jenis kapal); *Saudara, Bapak, Ibu* (dulu sebutan kekerabatan, sekarang juga sapaan umum).
4. **Menyempit** — cakupan makna sekarang lebih sempit dari makna lama. Contoh: *madrasah* (dulu 'sekolah' secara umum, sekarang khusus sekolah agama Islam); *sarjana* (dulu 'orang pandai' secara umum, sekarang gelar akademik); *pendeta* (dulu 'orang bijaksana', sekarang pemuka agama Kristen).
5. **Asosiasi** — makna muncul karena persamaan sifat (lihat juga materi Relasi Makna PPU-3 bagian Hubungan Asosiasi). Contoh: *gulung tikar* (bangkrut), *menumbangkan* (mengalahkan), *pelicin* (uang suap), *amplop* (uang suap).
6. **Sinestesia** — makna muncul karena pertukaran tanggapan dua indra berbeda. Contoh: *"Kata-katanya sangat kasar"* (peraba dipakai untuk pendengaran); *"Dia tersenyum manis"* (pengecap dipakai untuk penglihatan).

Catatan tambahan — **Apelativa** (penamaan berdasarkan): onomatope/peniruan bunyi (*tokek, mendesis*); bahan (*celana jin, karung goni*); tempat (*tahu Sumedang, dodol Garut*); penemu (*ikan mujair*).

### PPU-7 — Makna Kalimat

- **Konotasi** = makna kiasan, ungkapan, idiomatis, tidak sebenarnya. Contoh: *"Kakak menjadi bintang kelas"* (bermakna 'siswa terbaik', bukan benda langit); *"menikmati indahnya warna-warni kehidupan"*; *"kibar angin"* = informasi yang belum jelas kebenarannya.
- **Denotasi** = makna lugas, apa adanya, sebenarnya. Contoh: *"Adik sedang mengamati bintang di langit"* (benda langit yang sesungguhnya).

Cara menentukan kalimat bermakna lain (konotatif) dalam sebuah teks: cari kalimat yang memakai kata/ungkapan kias, biasanya di kalimat penutup paragraf sebagai penegasan atau simpulan bernuansa emosional.

Kalimat semakna:
- a) Cari kata bersinonim.
- b) Ubah kata aktif menjadi pasif (*me-* → *di-*) atau sebaliknya.
- c) Ubah posisi anak kalimat yang mendahului induk kalimat (ditandai koma) tanpa mengubah inti makna.
- Pastikan tidak ada kata pengganti yang mengubah makna asli (mis. mengganti "merugikan masyarakat setempat" dengan "merugikan komunitas global" mengubah cakupan makna → salah).

### PPU-8 — Frasa

**Jenis frasa berdasarkan distribusi unsur inti:**
- **Frasa endosentris** — unsur pembentuknya bisa menggantikan kedudukan frasa secara keseluruhan. Terbagi tiga:
  - *Koordinatif* (setara, bisa disisipi *dan/atau*): *tua muda*, *baca tulis*.
  - *Atributif* (satu unsur menjelaskan unsur lain; ada Diterangkan-Menerangkan/D-M atau M-D): *sepatu bola* (D-M), *sedang membaca* (M-D), *sekuntum mawar merah* (M-D-M).
  - *Apositif* (unsur saling menggantikan, bisa disisipi *adalah/ialah*): *Rocky, putraku, kini berusia 17 tahun.*
- **Frasa eksosentris** — unsur tak bisa saling menggantikan kedudukan keseluruhan frasa; didahului kata depan (direktif) atau berobjek. Contoh: *di perpustakaan*; *membaca buku*.

**Jenis frasa berdasarkan kelas kata inti:** frasa verbal (*sedang menggambar*), frasa adjektival (*sangat tinggi*), frasa nominal (*gedung mewah*), frasa numeralia (*satu pasangan*).

**Jenis frasa berdasarkan makna:** frasa idiomatis/konotasi (*adu lengan* = mengadu kekuatan; *akal bulus* = tipu muslihat licik); frasa ambigu/bermakna ganda (*buku gambar baru* = 'bukunya baru' atau 'gambarnya baru').

Frasa Sepola — pola D-M atau M-D dengan jenis kata (nomina/n, adjektiva/a, verba/v, adverbia/adv):
- D-M contoh: *mobil listrik* (n:a) sepola dengan *peran penting* (n:a); *teori konspirasi* (n:n) sepola dengan *buku sejarah* (n:n); *halaman rumah* (n:n) sepola dengan *pekarangan rumah* (n:n).
- M-D contoh: *selalu membangun* (adv:v) sepola dengan *lebih menghargai* (adv:v); *sangat menggiurkan* (adv:v).

### PPU-9 — Mengurai Paragraf

Syarat paragraf yang baik:
1. **Kesatuan** — satu paragraf hanya membahas satu gagasan/ide pokok.
2. **Kepaduan makna (koherensi)** — antarkalimat punya hubungan timbal balik, membahas satu gagasan sama.
3. **Kepaduan bentuk (kohesi)** — dibangun lewat kata rujukan, kata ganti, kata hubung, hiponimi, sinonim.

Langkah mengurai paragraf:
(a) Minimal paragraf ideal terdiri atas 3–4 kalimat.
(b) Cari kalimat yang topiknya sudah berbeda dari kalimat sebelumnya.
(c) Jadikan kalimat berbeda topik itu sebagai awal paragraf baru.

Ciri tambahan: hindari memulai paragraf baru dengan kata rujukan (*ini, itu, tersebut*) atau konjungsi antarkalimat — kalimat pembuka paragraf baru sebaiknya berdiri sendiri secara topik.

Kata hubung yang tepat untuk menghubungkan dua paragraf hasil pengurain: *di sisi lain, akan tetapi, namun, selanjutnya, sebagai contoh, dengan demikian, jadi, sesungguhnya, sehingga* (pilih sesuai hubungan logis antarparagraf — pertentangan, penambahan, atau simpulan).

Situasi teks: kata yang menggambarkan situasi/simpulan teks biasanya tersirat di kalimat akhir paragraf terakhir; identifikasi lewat pilihan diksi dan suasana keseluruhan teks (lihat juga materi PPU-1 Sikap Penulis, karena kedua tipe soal ini sering memakai kosakata sentimen yang sama).

**Aturan penyajian teks soal Mengurai Paragraf (WAJIB — mencegah jawaban bocor):**
- Widget menampilkan jeda paragraf setiap ada `\n\n` di `passages[].text`. Karena itu, **paragraf yang akan diurai HARUS ditulis sebagai SATU blok tanpa `\n\n`** di dalamnya (minimal 8 kalimat). Jangan pernah menaruh jeda paragraf di titik yang menjadi kunci jawaban.
- Format korpus asli: teks satu blok lalu *"Paragraf tersebut sebenarnya terdiri atas dua paragraf. Penguraian yang tepat adalah..."*, **atau** teks 2 paragraf tampil terpisah lalu *"Paragraf kedua teks tersebut sebenarnya terdiri atas dua paragraf. Penguraian yang tepat untuk paragraf kedua adalah..."* (nomor kalimat pada opsi mengacu ke paragraf yang ditanyakan saja). **Prioritaskan bentuk kedua (teks 2 paragraf, tanya paragraf kedua)** bila ada teks panjang 2 paragraf pada sesi tersebut; bentuk teks satu blok dipakai bila hanya tersedia teks panjang satu paragraf.
- Jangan bertanya *"Teks tersebut sebenarnya terdiri atas dua paragraf..."* jika teks yang tampil sudah terpisah menjadi dua paragraf tepat di titik jawaban.

### PPU-10 — Bahasa Hipotesis (Bahasa Panda/Bahasa Sandi)

Diberikan beberapa kalimat beserta terjemahan dalam "bahasa baru"; peserta harus menyimpulkan makna/urutan tiap kata dari pola yang berulang antar-kalimat.

Strategi:
1. Identifikasi kata yang muncul di dua kalimat berbeda untuk menyimpulkan artinya (kata yang sama dalam bahasa sandi = kata yang sama dalam terjemahan Indonesia).
2. Perhatikan **urutan kata** — bahasa sandi sering membalik urutan S-P-O dari bahasa Indonesia (pola A-B menjadi B-A saat berubah dari aktif ke pasif, dsb).
3. Perhatikan pola imbuhan/akhiran pada bahasa sandi untuk membedakan aktif vs pasif, atau kalimat tanya (biasanya ditandai oleh partikel/awalan khusus, mis. huruf awal berbeda seperti "C-" untuk pernyataan dan "D-" untuk pertanyaan).

Contoh tabel pola (adaptasi dari korpus):

| Kalimat | Pola Bahasa Sandi |
|---|---|
| Ayah mengelap kaca | imsah gighe mrisi |
| Taman dibersihkan ayah | amdif mrisi krap |
| Ibu membersihkan kaca | imdif gighe mmo |
| Taman ibu dibereskan | mrisi imdif gighe |

Contoh lain (pola aktif/pasif dan objek tempat berbeda):

| Kalimat | Pola Bahasa Sandi |
|---|---|
| Kuda memakan rumput | S'ari fere's! b!lan |
| Sapi meminum air | Wih'a lam! b!ton |
| Sapi memakan daun | K'it'eli lam! b!lan |

Tipsnya: baca dan perhatikan dengan saksama pola sebelum menjawab; kata yang berulang di lebih dari satu kalimat pasti punya makna yang sama, dan posisi/imbuhannya menunjukkan fungsi gramatikalnya (subjek, objek, atau penanda aktif-pasif/tanya).

### PPU-11 — Kalimat Rumpang

- Isi bagian rumpang dengan kata/frasa yang menjaga **kesatuan** (koherensi) dan **kepaduan** (kohesi) paragraf.
- Ciri kalimat rumpang di akhir paragraf → biasanya kalimat simpulan.
- Perhatikan konjungsi di kalimat sekitar rumpang sebagai petunjuk arah makna yang dibutuhkan.
- Contoh dari korpus: rumpang *"Di dalam [...] yang sering disebut sebagai tempat sempurna untuk meninggal ini banyak ditemukan [...]"* → jawaban perlu konsisten dengan topik "hutan" dan "jenazah/mayat" berdasarkan konteks sekitarnya.
- Konjungsi simpulan yang sering dipakai sebagai petunjuk: *oleh karena itu, dengan demikian, jadi*.

**Bentuk soal Kalimat Rumpang (WAJIB mengikuti korpus asli):**
- Bentuk utama: **dua rumpang `[...]` dalam satu kalimat**, pertanyaan *"Kata yang tepat untuk mengisi bagian yang rumpang pada kalimat (n) adalah..."*, opsi berupa **pasangan kata/frasa** (`kata1 dan kata2` atau `kata1; kata2`), contoh korpus: `hutan dan jenazah`, `fosil dan periode`, `menaklukkan dan menginvasi`, `sinar; celah-celah`.
- Distraktor harus **mendekati** (near-miss): salah satu kata cocok tetapi pasangannya tidak sesuai konteks, atau dua kata bersinonim yang nuansanya beda. Distraktor yang jelas absurd/tidak berhubungan dengan topik teks **dilarang**.
- Rumpang berupa kalimat utuh hanya boleh sebagai variasi (maksimal 1 dari 2 soal rumpang), dan seluruh opsi kalimat tetap harus bertema sama dengan teks serta masuk akal sebagai pelengkap.

### PPU-12 — Analogi Kata

Prinsip: pasangan kata A:B = pasangan kata C:D — hubungan logis antara keduanya harus **identik**, bukan hanya mirip.

Jenis hubungan yang sering muncul (dengan contoh dari korpus):
- **Sebab-akibat**: *gim : adiktif = gula : diabetes*; *nyamuk : malaria = tikus : pes*; *judi : sengsara = utang : stres*.
- **Bagian dari/hiponim-hipernim**: *nikel : logam = anggar : olahraga*; *Ur : Mesopotamia = Athena : Yunani* (kota kuno : peradaban asalnya).
- **Antonim/ameliorasi**: *pengangguran : tunakarya = buta huruf : tunaaksara* (kata kasar → kata halus, pola ameliorasi).
- **Fungsi/kegunaan**: *pisau : memotong = pena : menulis*; *pesawat : avtur = mobil : bensin* (kendaraan : bahan bakarnya).
- **Tempat/profesi**: *dokter : rumah sakit = hakim : pengadilan*; *sekolah : guru = galeri : seniman*.
- **Kondisi/akibat sosial**: *untung : rugi = haus : dahaga* (pasangan kondisi berlawanan yang butuh solusi/pemenuhan kebutuhan).

Ilustrasi (peribahasa) sebagai bentuk analogi dalam teks:
- **Ilustrasi menggambarkan**: menunjukkan sesuatu secara visual/konkret sesuai isi teks — contoh soal: mencari peribahasa yang paling menggambarkan situasi teks (mis. teks tentang siswa pintar tapi rendah hati → *"padi yang makin berisi, makin merunduk"*).
- **Ilustrasi mengaitkan**: menghubungkan isi teks dengan konteks/nasihat lain yang relevan secara makna (mis. teks tentang manfaat sekaligus risiko sesuatu → *"pedang bermata dua"*).

### PPU-13 — Konjungsi

**Konjungsi Intrakalimat (koordinatif)** — menghubungkan dua klausa berstatus sama/sederajat, dalam kalimat majemuk setara:
| Konjungsi | Hubungan |
|---|---|
| dan, serta | penjumlahan/penambahan |
| atau | pemilihan |
| tetapi, sedangkan, melainkan | pertentangan/perlawanan |
| lalu, kemudian | kelanjutan |

**Konjungsi Antarkalimat** — menghubungkan satu kalimat dengan kalimat sebelumnya, selalu di awal kalimat dan diikuti koma:
| Konjungsi | Makna |
|---|---|
| oleh karena itu | akibat |
| sebelum itu | kejadian yang mendahului |
| namun, akan tetapi | pertentangan dengan keadaan sebelumnya |
| kecuali itu | perwatasan/pembatasan |
| dengan demikian | simpulan |
| sesudah itu | kelanjutan peristiwa |
| selain itu | penambahan informasi/hal lain di luar yang sudah disebut |
| sebaliknya | kebalikan dari yang dinyatakan sebelumnya |
| sesungguhnya | keadaan yang sebenarnya |
| biarpun begitu | kesediaan melakukan sesuatu meski berbeda dari pernyataan sebelumnya (konsesif) |
| bahkan | penegasan |
| meskipun, walaupun | konsesif |

**Konjungsi Korelatif** — dua konjungsi berpasangan menghubungkan dua unsur sederajat: *baik ... maupun ...*; *tidak (hanya) ..., tetapi (juga) ...*; *bukan (hanya) ..., melainkan (juga) ...*; *sedemikian rupa ... sehingga ...*; *apa(kah) ... atau ...*; *entah ... entah ...*; *jangankan ..., ... pun ...*; *mulai dari ... sampai dengan/hingga ...*.

Contoh soal: "Konjungsi X pada kalimat (n) ... ide pada kalimat (n-1)" → jawab dengan salah satu dari: menegaskan, melanjutkan, menambahkan, mempertentangkan, mengakibatkan, meluaskan, merincikan.

### PPU-14 — Pemajemukan / Kata Berpasangan Tetap

Kata majemuk adalah gabungan dua kata (morfem) dasar yang menghasilkan makna baru; berbeda dari frasa karena kedua unsurnya berkedudukan sama (tidak ada unsur inti/diterangkan vs unsur menerangkan). Contoh: *kolam renang, medan tempur, daur ulang*.

Ciri kata berpasangan tetap (kolokasi tetap):
- Memisah kedua kata membuat maknanya berbeda/hilang (tidak bisa dipisahkan begitu saja).
- Tidak bisa disisipi konjungsi atau preposisi di antara kedua unsurnya.
- Diterjemahkan ke bahasa asing cenderung jadi satu kata/istilah utuh.
- Menimbulkan makna baru yang berbeda dari makna masing-masing unsur secara terpisah.
- Selalu berpasangan (satu unsur jarang berdiri sendiri dengan makna yang sama).

Contoh dari korpus: *hak veto, waktu kerja, tenaga kerja, hak cuti, kesehatan jiwa, kesehatan jasmani, hak cipta, rahasia dagang, merek dagang, penguatan budaya, meja hijau, kambing hitam, komponen utama, pemasok kobalt* (bukan pasangan tetap — hanya frasa biasa; hati-hati membedakan frasa atributif biasa dari kata berpasangan tetap yang benar-benar idiomatis/konvensional).

### PPU-15 — Afiksasi (Makna Imbuhan)

**Prefiks me(N)-**: membentuk kata kerja transitif/intransitif. Alomorf: *me-, mem-, men-, meng-, meny-, menge-* (bergantung huruf awal kata dasar). Contoh: *melatih, membelot, memukul, mendarat, menelan, menggoreng, mengoleksi, menyapu, mengebom*.

**Kombinasi me(N)-kan** (kata kerja transitif berobjek), dengan makna:
- Kausatif (membuat jadi): *meninggikan, menjatuhkan, melebarkan*.
- Benefaktif (untuk orang lain): *membukakan, membelikan, menjualkan*.
- Menuju ke: *mendaratkan, menepikan, meminggirkan*.
- Menganggap sebagai: *mendewakan, menganaktirikan, menuhankan*.

**Kombinasi me(N)-i** (kata kerja transitif berobjek), dengan makna:
- Frekuentif (berulang-ulang): *mengambili, meninjui, membuangi*.
- Memberi: *menomori* (memberi nomor), *menyampuli* (memberi sampul), *mengalasi* (memberi alas).
- Menghilangkan: *menguliti* (menghilangkan kulit), *membului* (menghilangkan bulu).
- Perbuatan: *menghadiahi, menganugerahi*.
- Lokatif (objek berupa tempat): *Dia mengelilingi stadion.*

**Konfiks pe(N)-an** (kata benda dari kata kerja *me(N)-*), alomorf: *pe-an, pem-an, pen-an, peng-an, peny-an, penge-an*. Makna:
- Tempat: *pegunungan, pedalaman, pemandian*.
- Proses: *pembelajaran, pembersihan, pemasaran, pendaratan, pengeboman, penerapan, pemahaman, pengembangan*.
- Hasil: *pengakuan, penghasilan, pendapatan*.

**Konfiks pe(R)-an** (kata benda dari kata kerja *be(R)-*), alomorf: *per-an, pe-an, pel-an*. Makna:
- Perihal/hal: *perkawinan, persediaan, pergerakan, persatuan*.
- Hasil: *pelajaran, perolehan*.
- Perbuatan: *perkelahian, perseteruan, percakapan*.
- Hal berkaitan sesuatu: *perkapalan, persuratkabaran*.
- Tempat: *peristirahatan, permukiman, permandian, pekerjaan, perkebunan, pertanian*.

**Konfiks ke-an** (kata benda/kerja/sifat, tanpa alomorf). Makna:
- Tempat: *kedutaan, kediaman, kecamatan*.
- Menderita/mengalami: *kelaparan, kemalaman, keracunan, kebanjiran*.
- Terlalu/terlampau: *kesempitan, kekecilan, kebesaran*.
- Hal/perihal (abstraksi bersifat): *keadilan, kemanusiaan, kebersihan, kebebasan*.
- Mendapat: *keidean, kemimpian*.
- Ketidaksengajaan: *ketiduran, kelupaan*.
- Menyerupai: *keibuan, kemerahan*.

---

### PPU-16 — Ilustrasi Teks (BARU di r9)

Ilustrasi teks adalah gambar/visual yang menjelaskan dan memperjelas pesan atau informasi dalam teks. Empat jenis ilustrasi yang sering diujikan:

1. **Grafik** — menggambarkan pasang surut/tren suatu keadaan dengan garis/gambar (vertikal-horizontal); tepat untuk teks yang membahas data statistik yang berubah dari waktu ke waktu (mis. teks tentang penjualan kendaraan listrik, neraca perdagangan, tren deflasi).
2. **Tabel** — daftar berisi ikhtisar data (kata/bilangan) tersusun sistematis dalam lajur & deret; tepat untuk teks yang membandingkan beberapa kategori/item sekaligus (mis. daftar penghargaan film, kandungan gizi buah).
3. **Skema/Bagan** — gambaran analitik suatu proses/sistem/alur; tepat untuk teks yang menjelaskan tahapan/proses (mis. cara membuat pupuk kompos, alur penerbitan buku).
4. **Gambar/Foto** — representasi visual objek/konsep; tepat untuk teks deskriptif yang butuh visualisasi detail suatu benda/tempat/makhluk (mis. ciri-ciri fisik tanaman, wahana rumah hantu).

Strategi menjawab: identifikasi jenis informasi utama teks terlebih dahulu — **apakah teks berisi data numerik yang berubah (→ grafik), daftar kategori (→ tabel), tahapan proses (→ skema), atau deskripsi visual objek (→ gambar/foto)** — lalu cocokkan dengan pilihan yang paling spesifik dan relevan (hindari pilihan yang terlalu umum atau tidak nyambung dengan topik inti teks).

**Bentuk soal Ilustrasi Teks (WAJIB mengikuti korpus asli):**
- Pertanyaan selalu untuk **seluruh teks**: *"Ilustrasi yang tepat untuk melengkapi teks tersebut adalah..."*. **Dilarang** menunjuk satu kalimat tertentu (mis. *"ilustrasi untuk kalimat (2)"*), karena itu membuat soal cukup dijawab dari satu kalimat dan lebih mudah dari korpus.
- Teks harus punya **satu jenis konten dominan** (data berubah / daftar kategori / tahapan proses / deskripsi objek). Seluruh opsi harus bertema sama dengan teks; distraktor tidak boleh jelas tidak nyambung dengan topik, tetapi harus jenis ilustrasi yang kurang cocok untuk isi teks secara keseluruhan.

---

## Cara Membuat Soal

1. Buat **1–2 teks bacaan panjang** (150–260 kata, kalibrasi sesuai tabel "Kalibrasi Panjang Teks" di atas), **2–3 teks bacaan pendek** (100–140 kata), dan **~6 soal mandiri** tanpa teks.
2. **WAJIB** beri nomor kalimat `(1)`, `(2)`, dst. pada semua teks bacaan naratif (kecuali materi Bahasa Hipotesis PPU-10 yang memakai tabel pasangan kalimat, bukan teks bernomor).
3. **Variasikan topik** tiap sesi: pilih dari sosial budaya, teknologi, lingkungan, ekonomi, kesehatan, pendidikan, sains, sejarah. Minimal 2 topik berbeda per sesi.
4. Sesuaikan panjang teks dengan tipe soal dominan yang akan menyertainya (lihat tabel kalibrasi): teks untuk soal imbuhan/konjungsi/pola-kalimat/frasa boleh lebih pendek (~110–140 kata, 1 paragraf); teks untuk soal sikap-penulis/mengurai-paragraf/ilustrasi-teks/analogi sebaiknya lebih panjang (~180–200 kata) dan **minimal satu dari dua teks panjang WAJIB tampil 2 paragraf** (dipisah baris kosong; teks pendek tetap 1 paragraf). Khusus soal mengurai paragraf, JANGAN menampilkan teks yang akan diurai sudah terpisah menjadi dua paragraf (jawaban jadi bocor) — ikuti aturan penyajian di PPU-9.
5. Teks panjang menghasilkan **5–8 soal** | Teks pendek menghasilkan **1 soal** | Soal mandiri berdiri sendiri.
6. Total soal = 20.
7. Setiap soal: **5 pilihan (A–E)**, satu jawaban benar.
8. Tentukan kunci jawaban (index 0–4) dan buat pembahasan singkat tiap soal.
9. Soal tipe PPU-2: sertakan kalimat bermasalah di dalam teks soal.
10. Soal tipe PPU-11: gunakan `[...]` untuk menandai bagian rumpang; bentuk utama dua rumpang dengan opsi pasangan kata (lihat PPU-11).
11. Soal tipe PPU-16: pastikan teks yang menyertainya benar-benar mengandung salah satu dari empat jenis konten (data numerik berubah, daftar kategori, tahapan proses, atau deskripsi visual objek) agar jawabannya punya dasar yang jelas dari teks. Soal ilustrasi SELALU untuk seluruh teks, bukan satu kalimat tertentu.
12. **DILARANG menyalin contoh dari Materi Konten atau "Contoh Soal per Tipe" sebagai soal.** Contoh di materi hanya untuk memahami pola; buat kata/frasa/kalimat BARU dengan pola yang sama. Contoh yang sering terjiplak dan tidak boleh dipakai ulang: frasa *teori konspirasi* (kunci *buku sejarah*), *mobil listrik*, *selalu membangun*, *halaman rumah*; kata *sarjana/madrasah/pendeta* (menyempit); *ketiduran/kelupaan/kekecilan* (ke-an); *gim : adiktif = gula : diabetes*; *tikus berdasi*; kalimat tidak logis *"tujuan ... adalah diberikan..."* (Madilog). **Opsi jawaban (termasuk distraktor) juga tidak boleh seluruhnya diambil dari daftar contoh di Materi Konten** (mis. kelima opsi soal ke-an semuanya dari daftar *kecamatan, kebesaran, keadilan, keibuan, keracunan*); minimal 3 dari 5 opsi harus kata/frasa/kalimat baru.
13. **Hitung dulu sebelum menulis widget**: setelah menyusun tiap teks, hitung jumlah kata dan kalimatnya. Jika di bawah batas minimum (pendek < 100 kata / 7 kalimat, panjang < 150 kata / 10 kalimat), tambahkan kalimat sampai terpenuhi.
14. **Checklist komposisi sebelum menulis widget**: tuliskan dulu daftar 20 soal beserta tipenya dan pastikan (a) ke-16 tipe PPU muncul ≥ 1×, (b) Analogi Kata ≥ 2, (c) 6 soal mandiri + 4 soal bacaan pendek + 10 soal bacaan panjang, (d) minimal satu teks panjang tampil 2 paragraf (dipisah baris kosong) dan teks pendek 1 paragraf. Contoh pembagian yang memenuhi semuanya: **mandiri (6)** = Analogi ×2, Bahasa Hipotesis, Afiksasi, Relasi Makna, Frasa Sepola; **bacaan pendek (4)** = Gaya Bahasa, Konjungsi, Kalimat Rumpang, Gejala Perubahan Makna; **bacaan panjang (10, dua teks × 5 soal)** = Sikap Penulis, Mengurai Paragraf, Ilustrasi Teks, Pola Kalimat, Makna Kalimat, Kata Majemuk, Kalimat Efektif + 3 slot tambahan yang dirotasi.

### Contoh Soal per Tipe

**PPU-1**: "Sikap penulis terhadap fenomena yang dibahas dalam teks tersebut adalah..."

**PPU-2**: "Kalimat (4) tidak efektif karena... Perbaikan yang tepat adalah..."

**PPU-3**: "Kata yang memiliki hubungan makna yang sama dengan pasangan *miskin : haya* adalah..."

**PPU-4**: "Kalimat dalam teks yang sepola dengan kalimat (2) adalah..." (opsi: 5 kalimat utuh berpola berbeda)

**PPU-5**: "Kalimat yang mengandung majas hiperbola/personifikasi terdapat pada kalimat..."

**PPU-6**: "Kata *tunawisma* pada teks tersebut mengalami gejala perubahan makna berupa..."

**PPU-7**: "Kata *mendorong* pada kalimat (3) digunakan secara..."

**PPU-8**: "Frasa yang sepola dengan *mobil listrik* adalah..."

**PPU-9**: "Paragraf kedua teks tersebut sebenarnya terdiri atas dua paragraf. Penguraian yang tepat untuk paragraf kedua adalah..." (paragraf yang diurai ditulis satu blok)

**PPU-10**: lihat tabel pola bahasa sandi pada materi PPU-10, lalu minta peserta menerjemahkan kalimat keempat.

**PPU-11**: "Kata yang tepat untuk mengisi bagian yang rumpang pada kalimat (5) adalah..." (opsi pasangan kata, mis. `hutan dan jenazah`)

**PPU-12**: "gim : adiktif = ..." → pilih pasangan kata yang hubungannya sama.

**PPU-13**: "Konjungsi yang tepat untuk menggantikan kata bergaris bawah pada kalimat (3) adalah..."

**PPU-14**: "Kata yang termasuk kata berpasangan tetap dalam teks tersebut adalah..."

**PPU-15**: "Makna imbuhan *ke-an* pada kata *ketiduran* sama dengan makna *ke-an* pada kata..."

**PPU-16**: "Ilustrasi yang tepat untuk melengkapi teks tersebut adalah..."

---

## Struktur Data JavaScript

### Array `passages`

```javascript
// type: 'long' = bacaan panjang, 'short' = bacaan pendek
// Untuk soal mandiri: passageId = null (tidak perlu entry di passages)
const passages = [
  {
    id: 0,
    type: 'long',
    label: "Teks 1",
    text: `(1) Kalimat pertama teks panjang. (2) Kalimat kedua. (3) Kalimat ketiga.

(4) Paragraf kedua dimulai di sini. (5) Kalimat kelima. (6) Kalimat penutup.`
  },
  {
    id: 1,
    type: 'short',
    label: "Teks 2",
    text: `(1) Teks pendek dimulai di sini. (2) Kalimat kedua. (3) Kalimat ketiga. (4) Kalimat keempat.`
  }
];
```

### Array `Qs`

```javascript
const Qs = [
  // Soal mandiri (passageId: null)
  {
    passageId: null,
    cat: "Analogi Kata",
    q: "gim : adiktif = ...",
    opts: [
      "buku : membaca",
      "gula : diabetes",
      "api : panas",
      "mobil : bensin",
      "pisau : tajam"
    ],
    ans: 1,
    exp: [
      "✗ Salah. Hubungan buku:membaca adalah fungsi/kegunaan, bukan sebab-akibat seperti gim:adiktif.",
      "✓ Benar. gim menyebabkan adiktif (sebab-akibat). Hubungan yang sama: gula menyebabkan diabetes.",
      "✗ Salah. api:panas adalah sifat/karakteristik, bukan sebab-akibat.",
      "✗ Salah. mobil:bensin adalah kebutuhan/bahan bakar, bukan sebab-akibat.",
      "✗ Salah. pisau:tajam adalah sifat benda, bukan hubungan sebab-akibat."
    ]
  },
  // Soal dari bacaan
  {
    passageId: 0,
    cat: "Sikap Penulis",
    q: "Pandangan penulis terhadap fenomena yang dibahas dalam teks adalah...",
    opts: [
      "Mendukung sepenuhnya perkembangan teknologi tanpa syarat",
      "Khawatir terhadap dampak negatif teknologi bagi masyarakat",
      "Netral dan hanya menyajikan data tanpa memberikan penilaian",
      "Menolak penggunaan teknologi di lingkungan pendidikan",
      "Optimis bahwa teknologi akan menyelesaikan semua masalah sosial"
    ],
    ans: 1,
    exp: [
      "✗ Salah. Penulis tidak mendukung tanpa syarat — ada kekhawatiran yang diungkapkan di kalimat (5) dan (9).",
      "✓ Benar. Penulis menggunakan kata 'mengkhawatirkan' dan 'perlu diwaspadai' di kalimat (5) dan (9), menunjukkan sikap khawatir.",
      "✗ Salah. Penulis tidak netral — ada penilaian eksplisit berupa kekhawatiran terhadap dampak teknologi.",
      "✗ Salah. Penulis tidak menolak teknologi di pendidikan; konteks teks tidak mendukung opsi ini.",
      "✗ Salah. Sikap optimis bertentangan dengan nada 'mengkhawatirkan' yang digunakan penulis."
    ]
  }
];
```

> **Catatan penting**: Opsi ditulis tanpa prefix huruf (A./B./dst.) — langsung tulis teks opsinya. `q.exp` adalah array 5 string, index 0–4 sesuai urutan opsi. Index `ans` menggunakan 0–4.

---

## Format Output: Inline Widget (visualize:show_widget)

**WAJIB** gunakan tool `visualize:show_widget` — BUKAN file HTML / `present_files`. Widget muncul langsung di chat.

Sebelum memanggil `show_widget`, panggil dulu `visualize:read_me` dengan module `["interactive"]` secara diam-diam.

### Fitur Wajib Widget

- **Intro screen** tampil sebelum ujian: label "UTBK / SNBT", judul subtes, stats row Soal/Waktu dengan divider, tombol "Mulai ujian" full width. Timer BELUM berjalan sampai tombol ini ditekan.
- **Timer 10 menit (600 detik)** hitung mundur di pojok kanan atas. Mulai saat "Mulai ujian" ditekan. Berubah merah saat sisa ≤ 5 menit (300 detik).
- **Teks bacaan** (jika ada) tampil penuh di atas soal. Untuk soal mandiri, area teks TIDAK dirender.
- **Label passage** (`"Teks 1"`, `"Teks 2"`, dst.) di atas teks untuk soal berteks. Selalu tampil tanpa kondisi `revealed[cur]`. Tidak ada keterangan topik.
- **Navigasi soal satu per satu** dengan dot navigator (20 dots).
- **5 pilihan (A–E)** per soal dengan radio button (`opt-radio`).
- **Tombol Prev / Next** (tidak ada tombol Skip).
- **Submit** di soal terakhir langsung memanggil `finalSubmit()`.
- **Halaman hasil**: skor, grade, pesan, stats, breakdown per kategori PPU, tombol "Review jawaban" & "Coba lagi", credit block `@muqsith.ai`.
- **Review mode**: setelah submit, semua soal tampil dengan highlight benar/salah + pembahasan per opsi. Jika user salah: `exp-wrong` (border merah) tampil dulu, lalu `exp-correct` (border hijau). Navigasi Prev/Next/dot TETAP AKTIF. Flag `reviewMode=true`. Next di soal terakhir berubah "Lihat Hasil".

### Perilaku Passage di Widget

Saat `renderQ()` dipanggil:
- Cek `Qs[cur].passageId`. Jika `=== null`, **SKIP rendering passage** (soal mandiri).
- Jika ada passageId, ambil `passages[passageId]`, tampilkan label + teks.
- Nomor kalimat `(1)`, `(2)`, dst di-render sebagai `<span class="sent-num">(1)</span>`.
- Teks passage tampil penuh — tidak ada max-height atau scroll.

---

## Template CSS

```css
* { box-sizing: border-box; margin: 0; padding: 0; }
#qw { font-family: var(--font-sans, system-ui, sans-serif); padding: 1rem 0; max-width: 720px; }
#qw, #qw * { -webkit-user-select: none; -moz-user-select: none; -ms-user-select: none; user-select: none; }

/* Intro screen */
.intro-wrap { max-width: 340px; margin: 0 auto; padding: 1rem 0; text-align: center; }
.intro-utbk { font-size: 10.4px; font-weight: 600; text-transform: uppercase; letter-spacing: .08em; color: var(--color-text-tertiary, #94A3B8); margin-bottom: 6px; }
.intro-title { font-size: 20.3px; font-weight: 500; color: var(--color-text-primary, #1E293B); margin-bottom: 16px; }
.intro-stats-row { display: flex; justify-content: space-around; padding: 0 1rem; }
.intro-stat-key { font-size: 10.4px; color: var(--color-text-tertiary, #94A3B8); }
.intro-stat-val { font-size: 25.4px; font-weight: 500; color: var(--color-text-primary, #1E293B); }
.intro-divider { border: none; border-top: 0.5px solid var(--color-border-tertiary, #E2E8F0); margin: 12px 0; }

/* Top bar */
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

/* Passage */
.passage-label { font-size: 10.4px; color: var(--color-text-tertiary, #94A3B8); text-transform: uppercase; letter-spacing: .07em; font-weight: 600; margin-bottom: 8px; }
.passage-text { font-size: 13px; color: var(--color-text-secondary, #64748B); line-height: 1.85; margin-bottom: 1.25rem; }
.passage-text p { margin-bottom: 0.75em; }
.passage-text p:last-child { margin-bottom: 0; }
.sent-num { font-size: 11px; font-weight: 600; color: var(--color-text-tertiary, #94A3B8); margin-right: 2px; }

/* Question */
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

/* Nav */
.bottom-nav { display: flex; gap: 8px; margin-top: 1.25rem; align-items: center; justify-content: flex-start; }
.btn-nav { background: transparent; border: 0.5px solid var(--color-border-secondary, #CBD5E1); border-radius: 8px; padding: 9px 16px; font-size: 13px; cursor: pointer; font-family: inherit; color: var(--color-text-primary, #1E293B); }
.btn-nav:hover { background: var(--color-background-secondary, #F8FAFC); }
.btn-primary { background: var(--color-text-primary, #1E293B); color: var(--color-background-primary, #fff); border: none; border-radius: 8px; padding: 9px 18px; font-size: 13px; cursor: pointer; font-family: inherit; }
.btn-primary:hover { opacity: 0.85; }

/* Review banner */
.review-banner { font-size: 10.4px; color: var(--color-text-tertiary, #94A3B8); text-align: center; padding: 6px 0; margin-bottom: 8px; letter-spacing: .04em; text-transform: uppercase; }

/* Result */
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
let totalSec = 600, timerInt, quizDone = false, reviewMode = false;

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
  const formatted = p.text.replace(/\((\d+)\)/g, '<span class="sent-num">($1)</span>');
  const paragraphs = formatted.split(/\n\n+/).map(para => `<p>${para.trim()}</p>`).join('');
  return `<div class="passage-label">${p.label}</div><div class="passage-text">${paragraphs}</div>`;
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
  // Hanya render passage jika passageId bukan null
  if (q.passageId !== null && q.passageId !== undefined) {
    html += renderPassage(passages[q.passageId]);
  }
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
    expContent += `<div class="exp-block exp-correct-block"><div class="exp-head"><span class="exp-pill">Jawaban Benar</span><span class="exp-opt-lbl">${correctLbl}</span><span class="exp-svg">${svgC}</span></div><div class="exp-body">${correctExp}</div></div>`;
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
  else if (pct>=60) { grade='Developing'; msg='Fondasi solid. Fokus ke analogi dan relasi makna.'; }
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
  totalSec = 600; quizDone = false; reviewMode = false;
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
      <div class="intro-title">Pengetahuan & Pemahaman Umum</div>
      <div class="intro-stats-row">
        <div><div class="intro-stat-key">Soal</div></div>
        <div><div class="intro-stat-key">Waktu</div></div>
      </div>
      <hr class="intro-divider">
      <div class="intro-stats-row">
        <div><div class="intro-stat-val">20</div></div>
        <div><div class="intro-stat-val">10 menit</div></div>
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
        <span id="timer-txt">10:00</span>
      </div>
    </div>
    <div class="quiz-body">
      <div class="nav-dots" id="nav-dots"></div>
      <div class="quiz-main">
        <div class="content-header">
          <div class="content-header-label">Pengetahuan &<br>Pemahaman Umum</div>
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
- Setelah widget muncul, tambahkan pesan singkat di chat dengan format berikut (tanpa bold/italic): baris 1 `LATIHAN SOAL PENGETAHUAN & PEMAHAMAN UMUM`, baris 2 `{tanggal} {bulan} {tahun}`, baris kosong, lalu `20 soal siap! Timer 10 menit jalan setelah kamu tekan Mulai. Selamat mengerjakan!` — tanggal/bulan/tahun sesuai hari ini.
- **Acak urutan soal**: gunakan fungsi `shuffleArray(arr)` (Fisher-Yates). Panggil di `startQuiz()` dan `restartQuiz()` agar urutan berbeda setiap kali mulai maupun restart. JANGAN lakukan shuffle sebagai inline loop di awal script.
- Variasikan topik teks dan soal di setiap sesi. Jangan ada dua sesi berturut-turut dengan topik yang sama.
- **Distribusi wajib per sesi**: ~6 soal mandiri (tanpa teks), ~4 soal dari bacaan pendek (1 soal/teks), ~10 soal dari 1–2 bacaan panjang. Komposisi tipe: ke-16 tipe PPU wajib muncul minimal 1× per sesi (lihat "Cakupan Tipe Soal" dan "Cara Membuat Soal" no. 14); jangan sampai Bahasa Hipotesis tersingkir oleh kuota mandiri.
- **WAJIB** beri nomor kalimat `(1)`, `(2)`, dst. pada setiap kalimat di semua teks bacaan naratif.
- **Kalibrasi panjang teks** sesuai tabel "Kalibrasi Panjang Teks per Kelompok Tipe Soal" — jangan membuat teks pendek (~100 kata) untuk menyertai soal mengurai-paragraf atau ilustrasi-teks yang butuh konten lebih kaya, dan jangan membuat teks terlalu panjang untuk soal imbuhan/konjungsi sederhana yang sebenarnya cukup dengan teks pendek.
- Soal mandiri (PPU-3, PPU-4, PPU-6, PPU-8, PPU-10, PPU-12, PPU-14, PPU-15): set `passageId: null`. `renderQ()` akan skip rendering passage secara otomatis.
- Soal tipe PPU-2 dan PPU-11: kutip atau tandai kalimat bermasalah/rumpang secara langsung di dalam teks soal.
- **Soal PPU-9 (Mengurai Paragraf)**: paragraf yang diurai HARUS satu blok tanpa `\n\n` di `passages[].text`; jeda paragraf tidak boleh jatuh di titik kunci jawaban. Jika teks punya 2 paragraf tampil, tanyakan paragraf mana yang diurai ("Paragraf kedua teks tersebut..."). Minimal satu teks panjang per sesi harus tampil 2 paragraf; soal Mengurai Paragraf diutamakan pada teks tersebut dengan pertanyaan "paragraf kedua".
- **Soal PPU-4 (Pola Kalimat)**: opsi selalu kalimat utuh berpola berbeda, bukan label S-P-O/S-P-K. **Soal PPU-11 (Kalimat Rumpang)**: bentuk utama dua rumpang dengan opsi pasangan kata; distraktor harus mendekati, bukan absurd.
- **DILARANG menyalin contoh dari Materi Konten/Contoh Soal per Tipe** sebagai soal (lihat daftar di "Cara Membuat Soal" no. 12). Buat kata/frasa/kalimat baru dengan pola yang sama. Berlaku juga untuk opsi/distraktor: minimal 3 dari 5 opsi harus baru, bukan daftar contoh materi.
- **Minimal 2 soal Analogi Kata (PPU-12)** per sesi dengan jenis hubungan berbeda (mis. sebab-akibat dan hiponim).
- **Panjang teks**: hitung kata dan kalimat tiap teks sebelum membuat widget; teks pendek ≥ 100 kata (≥ 7 kalimat), teks panjang ≥ 150 kata (≥ 10 kalimat).
- **Teks soal (`q.q`) DILARANG menyebut "Teks 1", "Teks 2", "Teks 3", dst.** — passage sudah tampil di atas soal, jadi referensi nomor teks redundant. Cukup tulis "teks di atas", "bacaan tersebut", atau langsung ke pertanyaan tanpa referensi nomor teks. Contoh SALAH: "Berdasarkan Teks 1, pandangan penulis adalah...". Contoh BENAR: "Pandangan penulis dalam teks tersebut adalah..."
- **INGAT**: selalu 5 opsi, index jawaban 0–4, gunakan `show_widget` bukan file HTML. **Opsi jawaban TIDAK diawali prefix huruf** (`A.`, `B.`, dst.) — langsung tulis teks opsinya saja.
- **Pembahasan (q.exp) — wajib array 5 string** (index 0–4, sesuai urutan opsi A–E):
  - **Opsi BENAR**: Mulai dengan `"✓ Benar."` lalu jelaskan kenapa opsi ini tepat — sertakan kata kunci dari teks atau strategi/rumus yang relevan dari materi konten.
  - **Opsi SALAH**: Mulai dengan `"✗ Salah."` lalu jelaskan SPESIFIK kenapa keliru — jangan cuma bilang "tidak tepat". Tunjukkan kontradiksi atau alasan linguistiknya.
  - Di review mode: jika user salah, blok merah (`exp-wrong-block`) tampil dulu, lalu blok hijau (`exp-correct-block`). Jika user benar atau skip, hanya blok hijau yang tampil.
- **Exp-box format (r9, identik r8)**: JANGAN gunakan `.exp-wrong` / `.exp-correct` dengan border-left. Gunakan struktur blok baru: `.exp-box` (flex column, gap 6px) berisi `.exp-block.exp-wrong-block` (border #F0997B) dan `.exp-block.exp-correct-block` (border #5DCAA5). Tiap blok punya `.exp-head` (background tipis merah/hijau) berisi: `.exp-pill` (pill tag teks), `.exp-opt-lbl` (huruf opsi A-E), `.exp-svg` (inline SVG X merah / centang hijau). Body teks ada di `.exp-body` dengan background putih/transparan.
- **INGAT r9**: dot navigator TIDAK circle (border-radius: 0) dan posisinya di KIRI soal (vertical column). Layout: `.quiz-body` flex row → `.nav-dots` kiri + `.quiz-main` kanan (berisi content-header, review-banner, q-area, bottom-nav). Selalu gunakan struktur HTML skeleton r9 (identik struktur r8).
- **TIPE SOAL (q.cat)**: Tulis nama tipe soal langsung — BUKAN kode PPU. Contoh: `"Sikap Penulis"`, `"Kalimat Efektif"`, `"Relasi Makna"`, `"Analogi Kata"`, `"Konjungsi"`, `"Frasa Sepola"`, `"Kalimat Rumpang"`, `"Pola Kalimat"`, `"Makna Kata"`, `"Mengurai Paragraf"`, `"Afiksasi"`, `"Kata Majemuk"`, `"Gaya Bahasa"`, `"Gejala Perubahan Makna"`, `"Ilustrasi Teks"`. DILARANG pakai format `"PPU-12: Analogi Kata"` atau kode apapun. TIDAK ditampilkan saat mengerjakan soal. Hanya muncul di pembahasan (review mode). Di `renderQ()`, gunakan `if (revealed[cur]) html += \`<div class="q-meta">${q.cat}</div>\`;` — BUKAN tanpa kondisi.
- **Header**: `content-header` — label "Pengetahuan &\nPemahaman Umum" kiri, `content-header-center` dengan "NOMOR SOAL" + angka kanan. Timer di `.top-bar` pojok kanan. TIDAK ada badge pill lama.
- **selectOpt**: toggle deselect — klik opsi yang sudah dipilih set ulang ke `null`.
- **Timer warn**: menyala merah saat `totalSec <= 300` (5 menit tersisa).
- **Credit block**: tampil di result screen — "BUILT BY @muqsith.ai" dengan link Instagram, teks "Feedback & saran? DM aja 👋".
- **Anti-copy**: CSS `user-select: none` pada `#qw, #qw *` + JS listener `copy` dan `contextmenu` di `DOMContentLoaded`.
- Jika pengguna meminta pembahasan tambahan setelah ujian, jelaskan strategi tipe soal menggunakan materi dari seksi Materi Konten di atas (termasuk PPU-5, PPU-6, dan PPU-16 yang baru aktif di r9).
- Tipe soal **PPU-10 Bahasa Panda**: buat soal dengan tabel bahasa sandi — diberikan 3–4 kalimat beserta terjemahan dalam bahasa fiktif, peserta harus menyimpulkan terjemahan kalimat keempat berdasarkan pola yang ada. Perhatikan pola pembalikan urutan kata untuk kalimat pasif/tanya seperti dicontohkan pada materi PPU-10.
- Tipe soal **PPU-16 Ilustrasi Teks**: pastikan pilihan jawaban mencakup keempat jenis ilustrasi (grafik, tabel, skema, gambar/foto) sebagai distraktor, dengan hanya satu yang benar-benar cocok dengan jenis konten dominan teks (data berubah / daftar kategori / tahapan proses / deskripsi objek). Pertanyaan harus untuk seluruh teks, bukan satu kalimat.
