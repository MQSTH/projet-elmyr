---
name: literasi-dalam-bahasa-inggris-r27
description: >
  Gunakan skill ini saat pengguna menyebut "literasi dalam bahasa inggris", "soal literasi", "latihan TOBK", "latihan UTBK", "latihan inggris", "minta soal inggris", atau frasa serupa yang menandakan ingin latihan soal Literasi dalam Bahasa Inggris. Skill ini membuat 20 soal pilihan ganda berbasis teks bacaan autentik (23 tipe soal dalam Variasi A/B/C) dan menyajikannya sebagai widget interaktif tertanam di chat dengan timer 15 menit (900 detik), intro screen deskripsi resmi UTBK, skoring otomatis (benar = 1 poin), pembahasan bilingual (English + Indonesia), dan navigasi penuh di mode review. Tipe soal TIDAK ditampilkan saat mengerjakan; hanya muncul di pembahasan setelah submit. Teks thread/email dirender sebagai tabel 2 kolom (Pengirim + Isi). Layout header seperti PM e4. Exp-box format opsi B.
---

# Literasi dalam Bahasa Inggris r27 — TOBK/UTBK Practice

> Skill dibuat oleh **mqsth**
>
> © 2026 Muhammad Rayyis Muqsith ([@muqsith.ai](https://instagram.com/muqsith.ai)). Dilisensikan di bawah [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/). Boleh dipakai dan dimodifikasi untuk non-komersial dengan atribusi. Dilarang menjual, memasukkan ke layanan berbayar, atau mengklaim sebagai karya sendiri. Soal dibuat dengan bantuan AI, bukan soal resmi UTBK/SNBT, dan pembahasan bisa mengandung kekeliruan.

## Overview

Skill ini membuat **widget interaktif tertanam di chat** (bukan file download) berupa ujian **20 soal** Literasi dalam Bahasa Inggris selama **15 menit**. Setiap kali dipanggil, buat soal **baru yang berbeda** (jangan ulangi soal yang sama).

**Skoring**: Benar = 1 poin, Salah/Kosong = 0 poin. Skor ditampilkan sebagai `score / 20 poin` di result screen.

### Deskripsi Resmi Subtes (Sumber: SNPMB)

Literasi dalam Bahasa Inggris merupakan subtes dalam UTBK yang bertujuan untuk mengukur kemampuan literasi ilmu pengetahuan dalam teks berbahasa Inggris. Dengan tujuan tersebut, subtes ini bukan semata-mata merupakan ujian penguasaan bahasa Inggris. Literasi dalam Bahasa Inggris menghadapkan peserta UTBK pada aktivitas menemukan, memahami, menilai, dan merefleksi informasi dalam teks berbahasa Inggris.

Teks-teks yang disajikan berkonteks saintek, sosial humaniora, dan personal:
- **Saintek**: domain khusus kimia, fisika, dan biologi
- **Sosial humaniora**: domain khusus ekonomi, sejarah, dan sosiogeografi
- **Personal**: domain khusus apresiasi sastra

Keluasan dan kedalaman materi domain khusus tersebut berkesesuaian dengan bahan ajar dalam kurikulum SMA/sederajat yang berlaku. Keseluruhan subtes Literasi dalam Bahasa Inggris berisi butir-butir yang terdiri atas butir soal berkonteks saintek, butir soal berkonteks sosial humaniora, dan soal berkonteks personal.

> Implikasi untuk pembuatan soal: **variasikan topik teks** -- satu sesi harus mencakup minimal dua dari tiga konteks (saintek, sosial humaniora, personal). Jangan semua teks bertopik sains atau semua bertopik sosial.

---

## Format Teks Bacaan

Setiap sesi WAJIB mencakup ketiga format teks berikut:

> **Acuan panjang teks (r26).** Batas panjang merujuk statistik korpus 180 teks latihan (5 file materi): rata-rata berbobot ≈ 220 kata, ≈ 10 kalimat, ≈ 3 paragraf per teks. Rata-rata per file 177-246 kata (median 178-254), dan ≈ 19-21 kata per kalimat di File 1-4. Batas 300-450 kata di r25 berada di ekor atas sebaran (di File 5 hanya 9 dari 34 teks yang masuk rentang itu).
>
> **Batasan yang belum divalidasi:** statistik korpus mencampur single, paired, dan thread (tidak dipisah per format), dan rata-rata File 5 (26,7 kata/kalimat) diduga terdistorsi penghitung kalimat. Karena rentang single 220-320 (tengah 270) berada di atas rata-rata korpus, angka paired (130-200) dan thread (180-260) adalah **usulan**, bukan hasil ukur. Validasi dengan menghitung ulang statistik per format, lalu sesuaikan rentang di sini.

### 1. Single Text
Satu teks bacaan **220-320 kata** (target ±260), **3-4 paragraf**, **10-15 kalimat** dengan rata-rata 18-24 kata/kalimat. Hubungkan jumlah kalimat dengan panjang: kalimat ≈ kata ÷ 21 (220 kata ≈ 10-11 kalimat; 260 ≈ 12; 320 ≈ 15). Jangan memadatkan 320 kata ke 10 kalimat. Format paling umum.
- **Minimal 3 paragraf.** Soal Topic of Paragraph, Finding Paragraph, dan paragraph relation membutuhkan struktur antarparagraf. JANGAN membuat single text satu paragraf.
- Paragraf dihitung dari pemisah baris kosong. Jangan menyisipkan baris kosong ekstra, karena soal yang menyebut "paragraph N" merujuk ke urutan ini.
- Bila akan ada soal **Irrelevant Sentence** atau sentence relation, satu paragraf target (5-7 kalimat) diberi penanda `(1)`, `(2)`, ... di awal tiap kalimat. Paragraf lain TIDAK diberi nomor.
- Variasikan struktur kalimat sesuai "Aturan Variasi Sintaksis".

### 2. Paired Text (Text A & Text B)
Dua teks pendek-sedang (**130-200 kata per teks**, masing-masing 2 paragraf, 6-9 kalimat) yang membahas topik yang sama dari sudut pandang berbeda. Disimpan dalam **satu objek passage** dengan `type: "paired"` dan dua field terpisah: `textA` dan `textB`. Semua soal yang mengacu ke pasangan ini (baik tentang A saja, B saja, maupun perbandingan keduanya) menggunakan **satu `passageId` yang sama** -- sehingga Text A dan Text B selalu tampil bersama di layar saat soal dikerjakan. Widget merender keduanya stacked dengan label "Text A" dan "Text B".

### 3. Thread / Email
Rangkaian postingan forum atau email. **Panjang total 180-260 kata, 5-6 postingan**, tiap postingan 1-4 kalimat. **Format plain text yang harus disimpan di `p.text`**:
```
[Username1 - Tanggal]
Isi postingan pertama (biasanya berupa pertanyaan atau permintaan pendapat/saran).

[Username2 - Tanggal]
Respons dari user kedua.

[Username3 - Tanggal]
Respons dari user ketiga.
```

**Penanda passage thread**: tambahkan `type: "thread"` pada objek passage di array `passages`. Widget akan otomatis merender teks tersebut sebagai **tabel HTML 2 kolom** (Pengirim | Isi) -- bukan paragraf biasa.

> Postingan pertama adalah fokus utama untuk soal Purpose of Thread dan Tone. Soal Least Reliable Response hampir selalu muncul di teks thread.

**Aturan isi thread (r26):**
- Sisipkan **tepat satu** respons yang jelas paling tidak bisa diandalkan (iklan/promosi dengan nomor telepon atau website, lowongan kerja, tidak menjawab, candaan, atau cerita pribadi tanpa saran) agar soal Least Reliable Response punya satu jawaban tegas.
- Sisipkan 1-2 respons yang berisi opini eksplisit (kata bias/kualifier) agar dapat dipakai untuk Fact vs Opinion dan Tone.

### Distribusi Format Per Sesi
Dari 3-4 teks total, susunannya:
- 1 teks thread/email
- 1 pasang teks (A & B)
- 1-2 single text

> Jangan buat semua teks dalam format single text. Format thread dan paired text wajib hadir setiap sesi.

---

Format asli UTBK Literasi dalam Bahasa Inggris adalah:
- **3-4 teks bacaan** (panjang mengikuti kalibrasi di atas)
- Setiap teks diikuti oleh **5-7 soal** yang mengacu ke teks tersebut
- Total **tepat 20 soal** -- tidak boleh lebih, tidak boleh kurang
- Soal **tidak punya passage sendiri-sendiri** -- semuanya merujuk ke teks bacaan bersama

> JANGAN buat soal dengan mini-passage per soal. Teks bacaan ditampilkan sekali di atas, lalu soal-soal menyusul. Ini format asli UTBK. (Pengecualian: soal Cloze / Conditional boleh mengutip satu kalimat dari teks di dalam pertanyaan.)

---

## Cakupan Tipe Soal

**TOTAL SOAL WAJIB PERSIS 20.** Jangan lebih, jangan kurang. Ada **23 tipe soal**; setiap sesi memakai salah satu dari tiga variasi distribusi tetap (A, B, C) di bawah. Gabungan A + B + C mencakup ke-23 tipe.

### Daftar 23 Tipe Soal (nilai `q.cat`) dan Format Teks yang Cocok

| # | q.cat (nama tipe) | Format teks yang cocok |
|---|---|---|
| 1 | Synonym / Antonym Word | semua |
| 2 | Synonym / Antonym Phrase | single, paired |
| 3 | Reference | semua |
| 4 | Tone / Attitude | semua (thread: postingan pertama) |
| 5 | Detail Information | thread, paired, satu paragraf |
| 6 | Stated Detail | single |
| 7 | Unstated Detail | thread (least reliable), single |
| 8 | Topic of Paragraph (Preceding / Following) | single |
| 9 | Topic of Two Texts | paired |
| 10 | Similarities / Differences | paired |
| 11 | Prediction | single, paired |
| 12 | Inference | single, paired |
| 13 | Main Idea | single |
| 14 | Synthesis | single, paired |
| 15 | Restatement | single |
| 16 | Finding Paragraph | single (min. 3 paragraf), paired |
| 17 | Purpose of the Writer | thread, single |
| 18 | Fact vs Opinion | thread, single, paired |
| 19 | Course of the Reading | paired, single ilmiah |
| 20 | Irrelevant Sentence | single (paragraf bernomor) |
| 21 | Analogy | single, paired (hubungan X-Y eksplisit) |
| 22 | Positive Attitude | single, paired (teks evaluatif/sastra) |
| 23 | Cloze / Conditional | single |

> Finding Line (mencari nomor baris) TIDAK dipakai karena teks di widget tidak bernomor baris. Gunakan Finding Paragraph ("paragraph N" atau "paragraph N, sentence M").

### Distribusi Fixed (pilih salah satu variasi tiap sesi)

**Variasi A** (3 teks: thread + paired + 1 single; alokasi 6 / 7 / 7 soal):
| Tipe Soal | Jumlah Soal |
|---|---|
| Synonym / Antonym Word | 2 |
| Reference | 2 |
| Tone / Attitude | 2 |
| Synonym / Antonym Phrase | 1 |
| Detail Information | 1 |
| Stated Detail | 1 |
| Unstated Detail | 1 |
| Topic of Paragraph (Preceding / Following) | 1 |
| Topic of Two Texts | 1 |
| Prediction | 1 |
| Inference | 1 |
| Main Idea | 1 |
| Synthesis | 1 |
| Restatement | 1 |
| Purpose of the Writer | 1 |
| Course of the Reading | 1 |
| Irrelevant Sentence | 1 |
| **TOTAL** | **20** (3 tipe x 2 + 14 tipe x 1) |

Peta alokasi saran Variasi A:
- Thread (6): Purpose of the Writer, Tone / Attitude, Unstated Detail (least reliable), Detail Information, Reference, Synonym / Antonym Word
- Paired (7): Topic of Two Texts, Course of the Reading, Prediction, Inference (paragraph relation), Synthesis, Synonym / Antonym Word, Reference
- Single (7): Main Idea, Topic of Paragraph, Stated Detail, Irrelevant Sentence, Restatement, Synonym / Antonym Phrase, Tone / Attitude

**Variasi B** (4 teks: thread + paired + 2 single; 5 soal per teks):
| Tipe Soal | Jumlah Soal |
|---|---|
| Synonym / Antonym Word | 2 |
| Reference | 2 |
| Tone / Attitude | 2 |
| Topic of Paragraph (Preceding / Following) | 1 |
| Detail Information | 1 |
| Unstated Detail | 1 |
| Stated Detail | 1 |
| Topic of Two Texts | 1 |
| Prediction | 1 |
| Similarities / Differences | 1 |
| Inference | 1 |
| Main Idea | 1 |
| Synthesis | 1 |
| Restatement | 1 |
| Finding Paragraph | 1 |
| Synonym / Antonym Phrase | 1 |
| Positive Attitude | 1 |
| **TOTAL** | **20** (3 tipe x 2 + 14 tipe x 1) |

> Perbaikan r26: di r25 tabel Variasi B hanya berjumlah 19 (3x2 + 13x1) walau berlabel 20. Slot ke-20 kini diisi Positive Attitude.

Peta alokasi saran Variasi B:
- Thread (5): Tone / Attitude, Detail Information, Unstated Detail, Reference, Synonym / Antonym Word
- Paired (5): Topic of Two Texts, Similarities / Differences, Prediction, Inference, Synthesis
- Single 1 (5): Main Idea, Stated Detail, Finding Paragraph, Synonym / Antonym Word, Reference
- Single 2 (5): Topic of Paragraph, Restatement, Synonym / Antonym Phrase, Tone / Attitude, Positive Attitude

**Variasi C** (4 teks: thread + paired + 2 single; 5 soal per teks; fokus analitis):
| Tipe Soal | Jumlah Soal |
|---|---|
| Synonym / Antonym Word | 2 |
| Tone / Attitude | 2 |
| Reference | 1 |
| Cloze / Conditional | 1 |
| Fact vs Opinion | 1 |
| Positive Attitude | 1 |
| Analogy | 1 |
| Irrelevant Sentence | 1 |
| Purpose of the Writer | 1 |
| Course of the Reading | 1 |
| Topic of Paragraph (Preceding / Following) | 1 |
| Similarities / Differences | 1 |
| Inference | 1 |
| Main Idea | 1 |
| Stated Detail | 1 |
| Unstated Detail | 1 |
| Prediction | 1 |
| Restatement | 1 |
| **TOTAL** | **20** (2 tipe x 2 + 16 tipe x 1) |

Peta alokasi saran Variasi C:
- Thread (5): Purpose of the Writer, Tone / Attitude, Fact vs Opinion, Reference, Unstated Detail
- Paired (5): Similarities / Differences, Course of the Reading, Inference, Prediction, Synonym / Antonym Word
- Single 1 (5): Main Idea, Irrelevant Sentence, Topic of Paragraph (Preceding), Stated Detail, Cloze / Conditional
- Single 2 (5): Analogy, Positive Attitude, Tone / Attitude, Synonym / Antonym Word, Restatement

**Aturan pemilihan variasi:**
- Sesi pertama dalam percakapan: pakai Variasi A. Jika pengguna meminta sesi baru, pakai variasi yang BERBEDA dari sesi sebelumnya (A, B, C, A, ...). Jika pengguna menyebut fokus tertentu (misal "soal analogi dan irrelevant"), pakai Variasi C.
- Peta alokasi bersifat saran; boleh dipindah antarteks asalkan (a) total per variasi tetap tepat seperti tabel, (b) tiap teks mendapat 5-7 soal, dan (c) tipe ditempatkan pada teks yang mendukungnya (lihat kolom "Format teks yang cocok").

> Sebelum menulis soal pertama, hitung total distribusimu = 20 DAN jumlah soal per teks = 5-7. Kalau tidak pas, ulangi sampai tepat.

---

## Materi Konten (Pengetahuan Inti)

> Semua 23 tipe soal aktif (dipakai bergantian lewat Variasi A/B/C -- lihat Cakupan Tipe Soal). Tipe baru r26 ada di bagian akhir seksi ini.

### Topic Of Paragraph (Preceding / Following)
- **Paragraph Preceding** = paragraf yang mendahului (paragraf awal). Stem: "The paragraph preceding the passage probably discusses...", "What was mentioned in the paragraph before this one?". Jawaban ada di **kalimat pertama teks**: cari kata penghubung ke belakang (However, This, These, Therefore, Unlike most...) lalu simpulkan gagasan yang pasti sudah diperkenalkan sebelumnya.
- **Paragraph Following** = paragraf yang mengikuti / paragraf akhir (lebih dalam/spesifik). Stem: "The paragraph following the passage will probably discuss...". Jawaban ada di **kalimat terakhir teks**: cari gagasan yang baru diperkenalkan atau dijanjikan ("...the restaurant industry can make a positive impact by implementing zero waste policies" -> paragraf berikutnya membahas dampak kebijakan itu).
- Pengecoh: topik yang sudah dibahas penuh di dalam teks, topik terlalu umum, atau topik terlalu jauh dari petunjuk di kalimat pertama/terakhir.
- Perhatikan hubungan antar paragraf / antar kalimat
- **End the sentence**: kaitkan kalimat terakhir di paragraf terakhir dengan kalimat pertamanya (dalam paragraf terakhir itu)
- Contoh soal real (Set 2 no.19): "End the sentence" -- jawaban A

### Detail Information Based On The Two Texts / One Of The Two Texts
- **Thread/Email** -- baca & pahami postingan pertama
- **Single Text** -- baca & pahami paragraf awal & akhir (kalimat pertama & terakhir)
- **Both Texts (A&B)** -- baca & pahami paragraf awal & akhir di kedua teks
- **One Paragraph** -- baca & pahami kalimat pertama & terakhir
- **Bedakan dari Stated Detail (r26)**: Detail Information menanyakan informasi spesifik dari sumber tertentu -- thread, pasangan teks, atau satu paragraf ("According to Text B...", "Who suggested...?", "What does the second poster recommend?"). Stated Detail menanyakan pernyataan benar dari single text lewat keyword. JANGAN membuat dua soal yang menguji kalimat yang sama.

### Synonym / Antonym Of A Word
- Synonym/Similar/Closest -- cari makna yang mirip/sama
- Antonym/Opposite -- cari makna yang berbeda
- **Modal meanings**:
  - Can/Could -- Ability / Permission
  - May/Might -- Possibility
  - Shall/Should / Ought to -- Suggestion
  - Must / Has/Have to (present) / Had to (past) -- Obligation
  - Will -- Willingness/Intention
  - Must + not -- Prohibition
- Contoh Obligation: "You must wear school uniform." / "She has to go home now." / "I had to work overtime last night."
- Contoh Suggestion: "You ought to consume a lot of vitamin."
- Contoh Willingness: A: "I heard someone is knocking the door." B: "I will open it."
- Contoh Prohibition: "You must not park in this area."
- Contoh soal real (Set 1 no.4): "The meaning of can" -- can = ability/permission -- jawaban D
- Contoh soal real (Set 1 no.9): "The meaning of fundamental" -- dasar/hal yang utama -- jawaban A
- **Akhiran yang membentuk adjective**:
  - -ial: critical, initial (cenderung noun benda)
  - -ive: creative (cenderung person)
  - -ious: serious
  - -able: stable, capable
- **Akhiran yang membentuk noun**:
  - -ion: nation, expansion
  - -ance: romance
  - -ence: dependence
  - -ment: department
  - -ty: beauty
  - -th: growth

### Unstated Detail Question
- Soal bertanya informasi yang TIDAK disebutkan / TIDAK didukung teks
- **Least reliable response** = jawaban yang paling tidak bisa diandalkan:
  - Tidak memberikan saran
  - Tidak menjawab pertanyaan
  - Komentar yang tidak relevan
  - Iklan/promosi (mencantumkan nomor telepon, website, atau lowongan kerja)
  - Candaan/sarkasme atau cerita pribadi tanpa saran yang bisa dipakai penanya
  - Klaim mutlak tanpa dasar/pengalaman ("semua X pasti gagal")
- Contoh soal real (Set 1 no.3): "Least reliable response" -- jawaban E

### Stated Detail Question
- Temukan keyword pada pertanyaan -- cari keyword tersebut di dalam teks (keyword + skim)
- **True Statement with keyword**: Keyword + skim + cocokkan pilihan jawaban dan teksnya, pilih yang sesuai konteks
- Contoh soal real (Set 1 no.5): "The reason why it is hard to figure out belly pain" -- keyword "belly pain" -- skim -- Yamini Durani -- jawaban C
- Contoh soal real (Set 1 no.10): "One benefit of tourism for local communities" -- keyword + skim -- jawaban A
- Contoh soal real (Set 2 no.20): "True Statement with keyword: precious metal prices in 2021" -- keyword + skim -- ada di paragraf 1 -- jawaban E

### Topic Of The Two Texts
- Baca & pahami paragraf awal & akhir dari kedua teks (bandingkan paragraf awal di kedua teks)
- Di pilihan jawaban, pilih pernyataan yang mencakup isi **kedua** teks (bukan hanya satu)

### Reference
- Rujukan/acuan kata -- baca dan pahami **kalimat sebelumnya** dari kata yang ditanya
- Kalimat yang disajikan lengkap, jawabannya ada di kata sebelumnya
- Subject Pronoun: I, You, They, We, He, She, It
- Object Pronoun: Me, You, Them, Us, Him, Her, It
- Possessive Adjective: My, Your, Their, Our, His, Her, Its
- Possessive Pronoun: Mine, Yours, Theirs, Ours, His, Hers, Its
- Contoh: "This is my book" -- "This book is mine"
- Contoh soal real (Set 1 no.6): Reference "they" -- jawaban B
- Contoh soal real (Set 1 no.11): Reference "its" -- jawaban B

### Prediction Based On The Text
- Hipotesis (+) = hasil (+)
- Hipotesis (-) = hasil (-)
- Soal biasanya: "What would most likely happen if...?" atau "What can be predicted from...?"

### Finding The Similarities / Differences Of The Two Texts
- Baca & pahami kalimat 1 & 2 dari masing-masing paragraf di kedua teks (perhatikan main idea)
- Perbandingan dua teks: positif vs negatif
- Stem: "What is the similarity/difference of both passages?", "How does Text B relate to Text A?" (mendukung, membantah, memperluas, kontras)
- Persamaan harus benar untuk KEDUA teks; perbedaan harus menyebut fokus tiap teks secara berpasangan ("Text A focuses on X, while Text B focuses on Y"). Pengecoh: benar hanya untuk satu teks, terlalu umum, atau terlalu spesifik.

### Inference Of The Text / Passage
- **Paragraph Relation** (How do paragraph 3 and 4 relate?):
  - Identifikasi paragraf yang ditanya
  - Baca & pahami ide pokok dari masing-masing paragraf (kalimat pertama & terakhir)
  - Temukan keterkaitan (Positif / Negatif)
  - Untuk two texts: baca paragraf 1 di kedua teks
- **Sentence Relation** (How do sentence 2 & 3 in paragraph 2 relate?):
  - Ketahui paragraf yang ditanya -- baca kalimat yang ditanya -- tentukan positif/negatif
- Contoh soal real (Set 1 no.8): "Paragraph relation between text 2A and 2B" -- baca paragraf 1 di kedua teks -- jawaban B
- **Implication/Conclusion** ("It can be inferred/implied/concluded..."): kesimpulan yang tidak dinyatakan langsung tetapi pasti benar. Cara: temukan fakta kunci -> tanya "jika ini benar, apa yang pasti benar?" -> eliminasi opsi yang hanya mengulang teks dan opsi ekstrem (completely, only, never, always, no effect).

### Topic / Main Idea Of The Text / Passage
- Memahami tentang apa yang dibaca
- Cara identifikasi: List / Subject / Mainly discuss / Mainly concerned
- **Main idea of a graph**: jika ada judulnya maka itulah main idea-nya (jawaban langsung dari judul grafik)
- Contoh soal real (Set 2 no.20): "Main idea of a graph" -- judul grafik = main idea -- jawaban B

### Synthesis Of The Text / Passage
- Gabungkan main idea + conclusion
- Di pilihan jawaban, pilih pernyataan yang mencakup isi **paragraf pertama DAN paragraf terakhir**
- Berbeda dari Main Idea (main idea saja) -- Synthesis mensintesis keseluruhan teks menjadi satu pernyataan komprehensif
- Contoh soal real (Set 1 no.13): "Topic/Main idea of both texts" -- pilih yang mencakup par. 1 dan terakhir -- jawaban C
- **Summary of the text (r26)**: ringkasan = satu pernyataan yang memuat main idea + poin pendukung utama, ditulis ulang dengan kata sendiri. Pengecoh: terlalu sempit (hanya satu paragraf), terlalu luas, mengubah makna dengan kata ekstrem (only, perfect, fully), atau menambah informasi yang tidak ada di teks.

### Writer's Attitude / Tone Towards The Text / Passage
- **Highlight Fact** (Descriptive, Report, Journal, Research Paper, News Item, Explanation) -- Tone: Informative, Objective, Neutral, Resourceful
- **Highlight Opinion** (Analytical, Hortatory, Speech, Discussion, Argumentative) -- Tone: Subjective, Concerned, Worried, Critical, Persuasive
- **Ciri opinion (Subjective)**:
  - Adjective (classify) / Adverb (more information) -- contoh: Adjective + -ly -- "slowly"
  - Modal Verbs: Can, Should, May, Will, Might, Must
  - Vague Words: Seems, Tend to / Seem, Appear, Believe, Think
- **Email Thread** -- perhatikan postingan **orang pertama**:
  - Asking for Information -- Tone: Informative
  - Asking for Opinion -- Tone: Subjective, Supportive, Suggestive, Negative, Skeptical
  - **IS3**: Informative, Subjective, Supportive, Suggestive
  - **3S + others**: Subjective, Suggestive, Supportive / atau: Informative, Helpful, Encouraging, Empathetic, Factual, Objective -- berdasarkan pengalaman pribadi penulis
- **Purpose of the thread**: fokus di orang yang pertama kali posting (bukan responder)
- Contoh soal real (Set 1 no.1): "Purpose of the thread" -- Anonymous: anaknya sakit perut, minta saran ke dokter atau cukup diperhatikan -- jawaban D
- Contoh soal real (Set 1 no.2): "Tone of the threads" -- IS3 logic -- jawaban C
- Contoh soal real (Set 1 no.14): "Determining opinion" -- adjective/adverb/modals/vague words -- jawaban A
- **Tone per paragraf/kalimat (r26)**: soal dapat menunjuk paragraf atau kalimat tertentu ("What is the author's attitude towards paragraph 2?"). Nilai hanya bagian itu, lalu cari kata evaluatif ("downplay", "continue to suffer" -> concerned). Kalimat yang menjelaskan mekanisme/definisi ilmiah -> informative. Kalimat ajakan menghubungi/berkunjung ke situs -> promotional.

### Restatement
- Cara penulisan kalimat berbeda, namun makna tetap sama
- Perhatikan konjungsi (kata hubung)
- Lihat pola kalimat (positif/negatif) dan bentuk kalimat (aktif/pasif)
- Cari kalimat jawaban yang semakna
- **Makna "due to" dan padanannya**:
  - **Due to / Owing to / Because of** + frase (noun phrase)
  - **Because / As / Since / For** + S + Verb/to be (klausa)
  - Contoh: "I was late due to heavy traffic jam." = "I was late because I got in a traffic jam."
- Contoh soal real (Set 1 no.12): "The meaning of due to" -- jawaban D
- Contoh soal real (Set 1 no.15): "Restatement of a sentence" -- pilih sinonim yang tepat -- jawaban E
- **Transformasi yang sering diuji (r26)**: aktif <-> pasif; "although/though + klausa" <-> "despite/in spite of + noun"; "It is feared that S V" <-> "That S V is feared"; "not only ... but also" <-> "both ... and"; "If ... was required" <-> "When/In case ... was demanded". Jebakan: opsi yang membalik makna (do not influence, never, only) atau mengubah kata kerja modal (could -> must).

### Finding Paragraph
- Temukan keyword dari pertanyaan -- cari ada di paragraf ke berapa (keyword + skim)
- **Fact** = Objective (based on data)
- Source (Sumber): Specific number / Name of place / Date & time / Name of person
- Contoh: "Bandung is a capital city of West Java province"
- Contoh soal real (Set 1 no.7): "Where the specific information is found" -- keyword: "Tourism is one of the fundamental pillars of the development process" -- jawaban E (paragraf 5)
- Finding Line (nomor baris) tidak dipakai; rujuk lokasi sebagai "paragraph N" atau "paragraph N, sentence M". Untuk paired text: "Text A paragraph 2". Kalimat kunci yang dicari harus tidak ambigu (hanya satu paragraf yang memuatnya).

### Synonym / Antonym Of A Phrase
- **Preposition + Verb-ing** -- setara dengan adverb / adjective + -ly
- **Phrase**: determiner + adjective + noun
- Determiner: a/an/the / this/that/these/those / his/her/my/your/our / some/many/several/a lot of / one/two/three
- **S + V2 + Object structure**: "JFK experienced..." / "It experienced a rapid..." -- pola: determiner -- adjective -- noun
- **Linking verbs** (diikuti adjective, BUKAN adverb): Look, Sound, Stay, Remain
  - Contoh: "She remained calm." (calm = adjective, bukan calmly)
- **Time signal simple past**: S + V2 + O
- Akhiran adjective: -ial, -ive, -ious, -able
- Contoh soal real (Set 2 no.10): "Before Soaring..." -- Preposition + Verb-ing -- adverb/adjective + -ly -- jawaban C
- Contoh soal real (Set 2 no.16): "JFK experienced" -- S + V2 + object -- Some + plural countable noun -- jawaban E
- Contoh soal real (Set 2 no.17): "LaGuardia airport demonstrated" -- Consistent + year on year -- object -- adjective -- noun/adverb of time -- jawaban C
- Contoh soal real (Set 2 no.18): "It experienced a rapid..." -- determiner -- adjective -- noun. Spike = melejit -- jawaban A
- Contoh soal real (Set 1 no.16): "In the ... years" -- determiner -- adjective -- noun -- jawaban C
- Contoh soal real (Set 1 no.17): "Remained + ...?" -- Linking verb diikuti adjective -- jawaban B
- Contoh soal real (Set 1 no.18): "Starting in 2016, the figure..." -- Time signal simple past -- S + V2 + O -- jawaban A

### Purpose Of The Writer (baru r26)
- Stem: "What is the author's main purpose/motive...?", "The author's purpose in writing is to...", "Why did the author write the passage?", "Which choice best states X's purpose to write the post?"
- **Tiga tujuan penulisan**: *entertain* (cerita, puisi, drama, lagu), *inform* (artikel ekspositori, instruksi, ensiklopedia), *persuade* (iklan, pidato kampanye, surat persuasif). Kata kerja opsi: to discuss, mention, persuade, summarize, compare, describe, tell how, distinguish, illustrate, advise, criticize, explain.
- **Thread/email**: tanyakan postingan tertentu. Poster pertama biasanya *meminta saran/informasi*; responden *memberi saran, berbagi pengalaman, atau menawarkan strategi*. Nilai postingan yang ditanya, bukan seluruh thread.
- **Motive (latar belakang)**: bila stem menanyakan "What likely motivates the writer...?", jawaban benar berpola kekurangan informasi: "There is limited/lack of/insufficient information about [topik]" atau "Not many people know/understand...". Pengecoh berpola berlawanan ("Many people are aware...", "There is sufficient/adequate information...") atau pola yang tidak tersirat teks ("confusing information", "controversy", "misunderstanding").
- Pengecoh umum: tujuan terlalu sempit (hanya satu paragraf), terlalu luas, atau kata kerja tujuan salah (teks menginformasikan tetapi opsi bilang *persuade*).

### Fact vs Opinion (baru r26)
- Stem: "Which of the following sentences reflects an opinion?" / "...is a fact?" / "...contains an opinion based on the passage?"
- **Fact** = dapat diverifikasi (angka, nama, tanggal, hasil studi, definisi baku). **Opinion** = perasaan, sikap, atau keyakinan penulis: posisi pada isu kontroversial, prediksi, evaluasi orang/tempat/benda. Opini ahli (*informed opinion*) tetap opini.
- **Penanda opini**: kata bias (good, better, best, worst, worthwhile, memorable, awe-inspiring, nightmare), kualifier (all, always, likely, never, might, seem, possibly, probably, should), dan kata sudut pandang seperti "considered", "believed", "arguably".
- Rancangan soal: tepat SATU opsi opini (atau tepat satu fakta); pengecoh berupa kalimat berisi angka/nama/kutipan yang bisa diverifikasi. Exp harus menunjuk kata penanda opini pada opsi benar dan bukti verifikasi pada pengecoh.

### Course Of The Reading (baru r26)
- **Empat sub-tipe**: (a) *field of study*: "The passage would be assigned reading in which course?"; (b) *target reader*: "To whom is the passage intended?"; (c) *published media*: "The passage would most likely be found in a/an..."; (d) *expert author*: "The passage was most probably written by a specialist in...".
- Cara: lihat **topik + organisasi detail**, lalu tentukan bidang dari FOKUS teks (latar masa kecil tokoh -> sejarah; pengaruh tokoh pada pemerintahan -> ilmu politik). Contoh: teks spesies invasif -> Biology; teks depresi remaja berbasis riset -> Psychology (bukan Oncology).
- Media: *journal* bila ada metode/statistik/terminologi teknis; *textbook/encyclopedia* bila definisi netral dan sistematis; *magazine/newspaper* bila ada kutipan narasumber atau kronologi berita.
- Pengecoh dari bidang tetangga (Psychology vs Psychiatry vs Sociology): bedakan lewat fokus teks (perilaku/riset vs penanganan medis vs struktur sosial). Pastikan tepat satu opsi defensible; jangan jadikan thread sebagai teks soal ini.

### Irrelevant Sentence (baru r26)
- Stem: "Which sentence in paragraph N is irrelevant to the main idea?", "The irrelevant sentence can be found in...".
- Langkah: (1) tentukan main idea paragraf; (2) uji tiap kalimat -- mendukung, menjelaskan, atau memberi contoh main idea?; (3) pilih kalimat yang menyimpang.
- **Ciri kalimat tidak relevan**: definisi istilah yang tidak dibahas paragraf (mis. "Resident can be defined as..."), detail sampingan yang beralih aspek (mis. lokasi penyimpanan CO2 di paragraf tentang kekurangan CCS), pernyataan umum tentang topik lain, atau fakta bertopik dekat tetapi bukan bagian argumen.
- **Rancangan soal**: paragraf target 5-7 kalimat dengan penanda `(1)...(n)`; tepat SATU kalimat tidak relevan; bukan kalimat pertama (topic sentence) dan bukan kalimat penutup; kalimat lain saling tersambung (konjungsi, pronoun) sehingga sisipan jelas mengganggu, tetapi tetap bertema umum yang sama (jangan absurd).

### Analogy (baru r26)
- Format A : B :: C : D. **Jenis hubungan**: part-whole, cause-effect, person-situation, synonym, antonym, geography, measurement, time; tambahan: function (alat-tujuan), protects/supports.
- Stem: "The author would apparently agree that the discussion of X and Y in the text is similar to the phenomenon between...". Opsi berupa pasangan kata.
- Langkah: (1) temukan bagaimana teks menghubungkan X dan Y (mis. hutan menyerap karbon; kurikulum menjadi pedoman guru); (2) rumuskan hubungannya dalam satu kalimat; (3) pilih pasangan dengan jenis hubungan DAN arah yang sama (urutan tidak boleh terbalik).
- Pengecoh: pasangan yang bertema sama tetapi jenis hubungannya beda, atau arah terbalik. Exp wajib menyebut jenis hubungan. Teks harus mendeskripsikan hubungan X-Y secara eksplisit.

### Positive Attitude (baru r26)
- Stem: "Which statement shows the author's positive attitude toward ...?", "What is the author's positive attitude regarding...?"
- Langkah: ambil keyword -> skim -> cari **evaluasi favorable** penulis (crucial, essential, powerful, remarkable, success, innovative; kata kerja memuji/menyoroti manfaat) -> pilih pernyataan yang mencerminkan evaluasi itu dan didukung teks.
- Beda dengan Tone: Tone menilai nada seluruh teks; Positive Attitude memilih PERNYATAAN spesifik yang positif.
- Pengecoh: fakta negatif/masalah, klaim ekstrem (only, no need, completely, always), pernyataan yang bertentangan dengan teks, atau fakta netral yang bukan evaluasi. Cocok untuk teks soshum evaluatif dan ulasan karya sastra/seni (konteks Personal).

### Cloze / Conditional In Context (baru r26)
- **Cloze**: satu kalimat dari teks ditulis di soal dengan bagian kosong (`...`); pilih kata yang tepat menurut konteks, tata bahasa, dan sinonim kata kunci di sekitar. Pertimbangkan collocation, nada, dan logika kalimat. Kalimat rumpang harus berasal dari teks.
- **Modals dalam cloze**: possibility -> may/might; obligation -> must/have to; suggestion -> should; ability -> can. Petunjuk: adverb "probably/possibly" -> may/might. Pastikan hanya satu modal yang benar.
- **Conditional**: zero (If + present, present) = fakta umum; first (If + present, will + V1) = kemungkinan masa depan; second (If + past simple/were, would + V1) = tidak nyata sekarang; third (If + past perfect, would have + V3) = tidak nyata di masa lalu. Tentukan bentuk verba di klausa if dari klausa utama, atau sebaliknya.

---

## Aturan Variasi Sintaksis (baru r26)

Sumber: Referensi Pola Kalimat (37 pola fungsi kalimat dari korpus 5 file). Pola dasar -- S-P-O, S-P-Pel, S-P(pasif)-K, K-S-P-O, eksistensial, imperatif sederhana -- cepat jenuh. Teks buatan yang hanya berisi pola dasar terasa tidak autentik dan kurang bahan untuk soal Restatement dan Synonym/Antonym Phrase.

**Pola menengah** (pilih beragam, jangan ulang pola yang sama dalam satu teks):
- Anak kalimat konsesif/kondisional di depan: "Although ..., surprisingly little is known..." / "Whether ..., if ..., you might..."
- Pasif verba *raising*: "is estimated/believed/expected to be ..."
- Ekstraposisi: "It is concluded that ..." / "It will be hard to know who ..."
- Korelatif: "not only ... but also ..."
- Pseudo-cleft: "All they need is ..."
- Dua klausa dengan tanda pisah (dash) tanpa konjungsi
- Subjek gerund/kuantifier: "Putting a price on ... seemed abhorrent."
- Klausa tujuan infinitif di depan: "To meet the demands of ..., more than 60 per cent ..."
- Klausa tereduksi: "When mixed with ..., X performed ..."
- Dua objek/komplemen infinitif: "They showed participants a video..." / "...asked the participants to walk backward."
- Korelatif komparatif: "The colder the air, the greater the temperature difference..."
- It-cleft: "It was not until his daughter came to him ... that he began to research..."
- Presentasional "Here is/are ...": "Here is the car of the future."
- Kondisional irrealis: "If the definition were precise, it would be defined differently."

**Pola langka** (terutama untuk thread dan teks naratif): kutipan langsung dengan atribusi di depan atau di belakang; pertanyaan wh- atau retoris; inversi lokatif ("Out beyond ... lies ..."); interjeksi tunggal; pertanyaan informal tanpa inversi; fragmen elips ("Interesting how that functions.").

**Kuota minimal per teks (usulan r26 -- belum diukur dari korpus; sesuaikan bila hasil pengukuran berbeda):**
| Jenis teks | Pola menengah | Pola langka |
|---|---|---|
| Single text | 3 | 1 |
| Text A / Text B | 2 per teks | 0-1 |
| Thread/email | 1 | 2 |

**Aturan:** maksimal satu pola menengah/langka per kalimat; kalimat tetap alami dan mudah dibaca, bukan dipaksakan. Pilih kalimat target soal **Restatement** dari kalimat yang berpola bisa-ditransformasi (pasif, ekstraposisi, korelatif, konsesif di depan, kondisional).

> Catatan: 37 pola adalah batas bawah -- pemindaian sumbernya representatif, bukan menyeluruh kalimat-per-kalimat. Klaim "jenuh di 37 pola" ternyata tidak sepenuhnya benar: empat pola di atas (korelatif komparatif, it-cleft, presentasional, kondisional irrealis) muncul di File 3-5 tetapi tidak tercatat di Referensi Pola Kalimat.

---

## Cara Membuat Soal

1. Tentukan dulu variasi distribusi (A, B, atau C) sesuai "Aturan pemilihan variasi", lengkap dengan peta alokasi per teks.
2. Buat teks bacaan dengan **format wajib**: 1 thread/email + 1 pasang teks (A&B) + 1-2 single text, dengan panjang sesuai kalibrasi (single 220-320 kata min. 3 paragraf; paired 130-200 kata per teks; thread 180-260 kata).
3. **WAJIB** ketiga konteks resmi SNPMB harus hadir di setiap sesi:
   - **Saintek** -- kimia, fisika, atau biologi (artikel sains, jurnal penelitian, explanation text)
   - **Sosial humaniora** -- ekonomi, sejarah, atau sosiogeografi (editorial, news item, analytical exposition)
   - **Personal / Apresiasi sastra** -- analisis atau ulasan karya sastra: cerpen, novel, puisi, drama
4. Pastikan tiap teks **mendukung tipe soal yang dialokasikan**: paragraf bernomor `(1)...(n)` untuk Irrelevant Sentence; teks ilmiah/berbidang jelas untuk Course of the Reading; hubungan X-Y eksplisit untuk Analogy; evaluasi penulis yang jelas untuk Positive Attitude; kalimat kunci tunggal untuk Finding Paragraph.
5. Terapkan **Aturan Variasi Sintaksis** (kuota pola menengah/langka per teks).
6. Paired text (A&B) menggunakan **satu objek passage** (`type: "paired"`) dengan satu `id`. Semua soal yang berkaitan dengan Text A, Text B, maupun perbandingan keduanya wajib menggunakan `passageId` yang sama -- yaitu id dari passage paired tersebut. Jangan buat dua objek passage terpisah untuk paired text.
7. Setiap teks/pasang teks menghasilkan 5-7 soal dari tipe yang berbeda-beda.
8. **Hitung ulang total soal sebelum menulis kode** -- harus persis 20, dan cocok dengan tabel variasi yang dipilih.
9. Setiap soal: **5 pilihan (A-E)**, satu jawaban benar.
10. Tentukan kunci jawaban (index 0-4) dan buat `exp` array 5 string per soal.
11. **Urutan soal WAJIB diacak** -- jangan kelompokkan soal per passage secara berurutan. Gunakan fungsi `shuffleArray(arr)` (Fisher-Yates). Panggil di `startQuiz()` dan `restartQuiz()` agar urutan berbeda setiap kali mulai maupun restart. JANGAN gunakan IIFE atau inline loop. Soal dari berbagai passage harus tercampur acak setiap sesi.

---

## Struktur Data JavaScript

### Array `passages`

```javascript
const passages = [
  {
    id: 0,
    label: "Text 1",
    type: "thread",           // <-- WAJIB untuk passage thread/email
    genre: "Forum Thread",
    text: `[Anonymous - Mon, 14 Apr]
My daughter has been complaining of stomach pain for two days. Should I take her to the doctor right away or wait and observe first?

[DrMommy - Mon, 14 Apr]
If the pain is persistent and she has a fever, I would go to the doctor immediately. Don't wait too long.

[NaturalHealer - Mon, 14 Apr]
Try warm compress on her belly first. It often helps with minor cramps. If no improvement in a day, see a doctor.

[PediatricsNurse - Tue, 15 Apr]
As a nurse, I recommend you monitor for warning signs: high fever, vomiting, or pain that moves to the lower right side. Those need urgent care.`
  },
  {
    id: 1,
    label: "Text 2",
    type: "paired",           // <-- WAJIB untuk passage paired text A & B
    genre: "Opinion Editorial",
    textA: `Isi Text A di sini. 130-200 kata, 2 paragraf.
Paragraf pertama...

Paragraf kedua...`,
    textB: `Isi Text B di sini. 130-200 kata, 2 paragraf.
Paragraf pertama...

Paragraf kedua...`
  },
  {
    id: 2,
    label: "Text 3",
    genre: "Scientific Article", // jenis teks saja -- JANGAN tambah topik/domain
    text: `Paragraf penuh teks bacaan di sini. 220-320 kata, 3-4 paragraf.
Gunakan template literal agar bisa multiline.
Bisa dibagi paragraf dengan \n\n.`
  },
];
```

> **Aturan `type: "thread"`**: Hanya tambahkan pada passage yang berisi rangkaian postingan forum atau email. Widget merender sebagai tabel 2 kolom (Pengirim | Isi).

> **Aturan `type: "paired"`**: Hanya tambahkan pada passage paired text. Gunakan field `textA` dan `textB` (bukan `text`). Semua soal yang berkaitan dengan pasangan ini -- baik tentang Text A saja, Text B saja, maupun perbandingan keduanya -- wajib memakai `passageId` yang sama. Widget merender keduanya stacked dengan label "Text A" dan "Text B".

> **Format teks thread**: setiap postingan dipisahkan oleh baris kosong (`\n\n`). Header postingan harus dalam format `[NamaPengirim - Tanggal]` -- widget memparse format ini untuk mengisi kolom Pengirim.

### Array `Qs`

```javascript
const Qs = [
  {
    passageId: 0,
    cat: "Tone / Attitude",
    q: "What is the tone of the text?",
    opts: ["Informative and objective","Subjective and critical","Persuasive and worried","Neutral and suggestive","Concerned and resourceful"],
    ans: 0,
    exp: [
      "✓ Benar. Teks menggunakan data dan fakta tanpa opini pribadi — tidak ada modal verb (kata kerja pengandaian seperti should, might) atau vague words (kata samar seperti seems, tend to) yang menunjukkan subjektivitas (pendapat pribadi). Ini ciri khas teks informative (informatif) dan objective (berdasarkan fakta).",
      "✗ Salah. Tidak ada kritik atau perspektif subjective (berisi opini/pendapat) dalam teks — penulis tidak mengevaluasi atau menghakimi informasi yang disampaikan. Seluruh isi teks hanya memaparkan fakta secara netral.",
      "✗ Salah. Tidak ada niat persuasive (membujuk/mengajak) atau ekspresi worry (kekhawatiran) — teks tidak mengajak pembaca melakukan sesuatu dan tidak menyatakan keprihatinan apapun.",
      "✗ Salah. Suggestive language (bahasa yang menyarankan) seperti modal verb (should, may) atau vague words (kata samar: seems, tend to, appear) tidak ditemukan dalam teks ini, sehingga tone (nada) 'suggestive' tidak tepat.",
      "✗ Salah. Penulis tidak mengekspresikan concern (kekhawatiran) atau emotional involvement (keterlibatan emosional) — tidak ada kata-kata yang menunjukkan perasaan pribadi penulis terhadap topik yang dibahas."
    ]
  },
];
```

> `exp` adalah array 5 string (index 0-4, sesuai urutan opsi A-E). Setiap string menjelaskan mengapa opsi tersebut benar atau salah. Wajib diisi untuk semua 5 opsi tiap soal.

---

## Format Output: Inline Widget (visualize:show_widget)

**WAJIB** gunakan tool `visualize:show_widget` -- BUKAN file HTML / `present_files`. Widget muncul langsung di chat.

Sebelum memanggil `show_widget`, panggil dulu `visualize:read_me` dengan module `["interactive"]` secara diam-diam.

### Fitur Wajib Widget
- **Intro screen** tampil sebelum ujian: deskripsi resmi subtes UTBK, chip "20 soal" & "15 menit", tombol "Mulai ujian". Timer belum berjalan sampai tombol ini ditekan.
- **Timer 15 menit (900 detik)** hitung mundur di pojok kanan atas. Mulai berjalan saat "Mulai ujian" ditekan.
- **Teks bacaan penuh** tampil di atas soal -- bukan mini snippet. Ditampilkan penuh tanpa scroll (overflow visible).
- **Thread/email dirender sebagai tabel** dengan 2 kolom: "Pengirim" (kiri) dan "Isi" (kanan). Parsing otomatis dari format `[Sender - Date]\nContent`.
- **Label passage** ("Text 1", "Text 2", dst.) tampil di atas teks/tabel. Label hanya berisi nomor teks — JANGAN tambahkan genre atau deskripsi apapun ke dalam field `label`.
- **Soal navigasi satu per satu** dengan dot navigator.
- **5 pilihan (A-E)** per soal dengan huruf lingkaran.
- **Tombol Prev / Next** untuk navigasi.
- **Halaman hasil**: skor, grade, pesan, stats, breakdown per kategori, tombol "Review jawaban" & "Coba lagi".
- **Review mode**: setelah submit, semua soal tampil dengan highlight benar/salah + pembahasan. Navigasi Prev/Next/dot TETAP AKTIF. Flag `reviewMode=true`.

#### Template CSS

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
.thread-box { background: var(--color-background-secondary, #F8FAFC); border: 0.5px solid var(--color-border-tertiary, #E2E8F0); border-radius: 10px; padding: 14px 16px; margin-bottom: 1.25rem; }
.thread-table { width: 100%; border-collapse: collapse; font-size: 13px; color: var(--color-text-secondary, #64748B); }
.thread-table thead th { text-align: left; font-size: 10.4px; font-weight: 600; text-transform: uppercase; letter-spacing: .06em; color: var(--color-text-tertiary, #94A3B8); padding: 0 10px 8px 10px; border-bottom: 0.5px solid var(--color-border-tertiary, #E2E8F0); }
.thread-table thead th:first-child { width: 28%; padding-left: 0; }
.thread-table thead th:last-child { padding-right: 0; }
.thread-table tbody tr { border-bottom: 0.5px solid var(--color-border-tertiary, #E2E8F0); }
.thread-table tbody tr:last-child { border-bottom: none; }
.thread-table tbody td { padding: 10px; vertical-align: top; line-height: 1.65; }
.thread-table tbody td:first-child { width: 28%; padding-left: 0; font-weight: 500; color: var(--color-text-primary, #1E293B); white-space: pre-line; font-size: 10.4px; }
.thread-table tbody td:last-child { padding-right: 0; }
.paired-wrap { display: flex; flex-direction: column; gap: 12px; }
.paired-block { background: none; padding: 12px 14px; }
.paired-block-label { font-size: 10.4px; font-weight: 600; text-transform: uppercase; letter-spacing: .06em; color: var(--color-text-tertiary, #94A3B8); margin-bottom: 8px; }
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

#### Template JS Lengkap

```javascript
function shuffleArray(arr) {
  for (let i = arr.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [arr[i], arr[j]] = [arr[j], arr[i]];
  }
}

let cur = 0, answers = new Array(Qs.length).fill(null);
let revealed = new Array(Qs.length).fill(false);
let totalSec = 900, timerInt, quizDone = false, reviewMode = false;

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

// Render thread text sebagai tabel 2 kolom (Pengirim | Isi)
function renderThreadTable(text) {
  const blocks = text.trim().split(/\n\n(?=\[)/);
  const rows = blocks.map(block => {
    const match = block.match(/^\[(.+?)\]\n([\s\S]+)/);
    if (!match) return '';
    const sender = match[1];
    const content = match[2].trim();
    return `<tr><td>${sender}</td><td>${content}</td></tr>`;
  }).filter(Boolean).join('');
  return `<table class="thread-table"><thead><tr><th>Pengirim</th><th>Isi</th></tr></thead><tbody>${rows}</tbody></table>`;
}

// Render paired text (Text A & Text B) stacked
function renderPairedText(p) {
  const a = p.textA.replace(/\n\n/g,'</p><p>').replace(/^/,'<p>').replace(/$/,'</p>');
  const b = p.textB.replace(/\n\n/g,'</p><p>').replace(/^/,'<p>').replace(/$/,'</p>');
  return `<div class="paired-wrap"><div class="paired-block"><div class="paired-block-label">Text A</div>${a}</div><div class="paired-block"><div class="paired-block-label">Text B</div>${b}</div></div>`;
}

function renderQ() {
  document.getElementById('q-area').style.display = 'block';
  const q = Qs[cur];
  const p = passages[q.passageId];
  document.getElementById('q-num-val').textContent = cur + 1;
  buildDots();

  // Render passage berdasarkan type
  const lbl = `<div class="passage-label">${p.label}</div>`;
  let passageHTML;
  if (p.type === 'thread') {
    passageHTML = `${lbl}<div class="thread-box">${renderThreadTable(p.text)}</div>`;
  } else if (p.type === 'paired') {
    passageHTML = `${lbl}<div class="passage-text">${renderPairedText(p)}</div>`;
  } else {
    const txt = p.text.replace(/\n\n/g,'</p><p>').replace(/^/,'<p>').replace(/$/,'</p>');
    passageHTML = `${lbl}<div class="passage-text">${txt}</div>`;
  }

  let html = passageHTML;
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
  const score = correct * 1;
  const cats = {};
  Qs.forEach((q,i) => { if (!cats[q.cat]) cats[q.cat]={correct:0,total:0}; cats[q.cat].total++; if (answers[i]===q.ans) cats[q.cat].correct++; });
  let grade, msg;
  if (score>=18) { grade='Excellent'; msg='Luar biasa — UTBK-ready!'; }
  else if (score>=15) { grade='Proficient'; msg='Hasil bagus. Asah kategori lemah dan kamu siap!'; }
  else if (score>=12) { grade='Developing'; msg='Fondasi solid. Fokus ke grammar dan inference.'; }
  else { grade='Perlu Latihan'; msg='Ulangi materi dan coba lagi. Konsistensi adalah kunci.'; }
  let bdRows = '';
  Object.entries(cats).forEach(([cat,d]) => {
    bdRows += `<div class="r-bd-row"><span class="r-bd-cat">${cat}</span><span class="r-bd-score">${d.correct}/${d.total}</span></div>`;
  });
  rs.innerHTML = `<div class="result-wrap"><div class="r-hero"><div class="r-score-big">${score}</div><div class="r-of">/ 20 poin</div><div class="r-grade">${grade}</div><div class="r-msg">${msg}</div></div><div class="r-stats"><div class="r-stat"><div class="r-stat-val">${correct}</div><div class="r-stat-lbl">Benar</div></div><div class="r-stat"><div class="r-stat-val">${wrong}</div><div class="r-stat-lbl">Salah</div></div></div><div class="r-breakdown"><div class="r-bd-title">Breakdown per kategori</div>${bdRows}</div><div class="r-actions"><button class="btn-nav" onclick="reviewAnswers()">Review jawaban</button><button class="btn-primary" onclick="restartQuiz()">Coba lagi</button></div><div class="r-credit"><div class="r-credit-built">BUILT BY</div><div class="r-credit-handle"><svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="2" width="20" height="20" rx="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="1" fill="currentColor" stroke="none"/></svg><a href="https://www.instagram.com/muqsith.ai/" target="_blank">@muqsith.ai</a></div><div class="r-credit-fb">Feedback &amp; saran? DM aja 👋</div></div></div>`;
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
  totalSec = 900; quizDone = false; reviewMode = false;
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

#### HTML Skeleton Widget

```html
<style>/* CSS template di atas */</style>
<div id="qw">
  <div id="intro-screen">
    <div class="intro-wrap">
      <div class="intro-utbk">UTBK / SNBT</div>
      <div class="intro-title">Literasi dalam Bahasa Inggris</div>
      <div class="intro-stats-row">
        <div><div class="intro-stat-key">Soal</div></div>
        <div><div class="intro-stat-key">Waktu</div></div>
      </div>
      <hr class="intro-divider">
      <div class="intro-stats-row">
        <div><div class="intro-stat-val">20</div></div>
        <div><div class="intro-stat-val">15 menit</div></div>
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
        <span id="timer-txt">15:00</span>
      </div>
    </div>
    <div class="quiz-body">
      <div class="nav-dots" id="nav-dots"></div>
      <div class="quiz-main">
        <div class="content-header">
          <div class="content-header-label">Literasi<br>Bahasa Inggris</div>
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

- Setelah widget muncul, tambahkan pesan singkat di chat dengan format berikut (tanpa bold/italic): baris 1 `LATIHAN SOAL LITERASI DALAM BAHASA INGGRIS`, baris 2 `{tanggal} {bulan} {tahun}`, baris kosong, lalu `20 soal siap! Timer 15 menit jalan setelah kamu tekan Mulai. Selamat mengerjakan!` — tanggal/bulan/tahun sesuai hari ini.
- Jika pengguna meminta pembahasan tambahan setelah ujian, jelaskan strategi tipe soal yang bersangkutan menggunakan materi dari seksi Materi Konten di atas.
- Variasikan topik teks dan soal di setiap sesi. **Ketiga konteks SNPMB wajib ada setiap sesi**.
- **TIPE SOAL (q.cat)**: tulis nama tipe soal langsung dalam bahasa Inggris, persis seperti kolom q.cat pada tabel 23 tipe (misal: `"Main Idea"`, `"Inference"`, `"Tone / Attitude"`, `"Reference"`, `"Purpose of the Writer"`, `"Course of the Reading"`, `"Irrelevant Sentence"`, `"Analogy"`, `"Positive Attitude"`, `"Fact vs Opinion"`, `"Cloze / Conditional"`, `"Topic of Paragraph (Preceding / Following)"`). Gunakan penulisan yang konsisten agar breakdown per kategori di result screen tidak terpecah. DILARANG menggunakan kode seperti `"ING-1"` atau `"ING-MI"`. TIDAK ditampilkan saat mengerjakan soal. Hanya muncul di pembahasan (review mode). Di `renderQ()`, gunakan `if (revealed[cur]) html += \`<div class="q-meta">${q.cat}</div>\`;` -- BUKAN tanpa kondisi.
- **Pembahasan (exp) — struktur wajib per opsi**:
  - **Opsi BENAR**: Mulai dengan "✓ Benar." lalu jelaskan (1) di mana buktinya di teks (kutip frasa kunci), (2) kenapa opsi ini paling tepat.
  - **Opsi SALAH**: Mulai dengan "✗ Salah." lalu jelaskan SPESIFIK kenapa opsi ini keliru — jangan cuma bilang 'not mentioned' atau 'incorrect'. Tunjukkan di mana teks BERTENTANGAN atau TIDAK MENDUKUNG opsi ini.
  - **Aturan bilingual**: boleh pakai istilah bahasa Inggris, tapi WAJIB langsung kasih terjemahannya dalam tanda kurung setelah istilah itu. Tujuannya biar semua orang paham tanpa harus ngerti bahasa Inggris dulu. Contoh penulisan istilah: `modal verbs (kata kerja pengandaian seperti should, might, can)`, `subjective (berdasarkan pendapat/perasaan)`, `objective (berdasarkan fakta, tidak memihak)`, `inference (kesimpulan yang ditarik dari teks)`, `tone (nada/sikap penulis)`, `pronoun (kata ganti seperti they, it, her)`, `vague words (kata-kata samar seperti seems, tend to, appear)`.
  - Contoh exp benar: `"✓ Benar. Paragraf 2 menyebut '...modal verbs (kata kerja pengandaian) such as should and might...' — ini ciri teks subjective (berisi opini/pendapat), bukan fakta objektif (berdasarkan data)."`
  - Contoh exp salah: `"✗ Salah. Teks tidak menunjukkan tone (nada) kritik — tidak ada kata-kata negatif atau judgmental (menghakimi). Penulis hanya memaparkan fakta secara netral."` / `"✗ Salah. Pronoun (kata ganti) 'they' di kalimat ke-3 merujuk ke 'researchers' (para peneliti), bukan 'findings' (temuan) — karena 'they' hanya bisa merujuk ke orang/benda jamak yang disebut tepat sebelumnya."`
  - **Wajib pakai materi dari seksi "Materi Konten"**: setiap pembahasan harus menyertakan rumus/strategi/ciri yang relevan dari materi di atas. Contoh: soal Reference → sebut rumus "baca kalimat sebelumnya, cari subjek/objek yang dirujuk"; soal Tone → sebut ciri Highlight Fact vs Highlight Opinion (modal verbs, vague words, adjective/adverb); soal Synonym → sebut akhiran pembentuk adjective/noun yang relevan; soal Inference → sebut cara identifikasi paragraph relation (positif/negatif). Jangan cuma jelaskan jawabannya — ajari juga cara berpikirnya supaya siswa paham polanya untuk soal berikutnya.
  - JANGAN tulis pembahasan satu bahasa saja. JANGAN hanya menulis "Incorrect" atau "Salah" tanpa penjelasan spesifik.
- **Skoring**: benar = 1 poin, salah/kosong = 0. `const score = correct * 1;`. Tampilkan sebagai `score / 20 poin`.
- **Grade threshold**: Excellent ≥18, Proficient ≥15, Developing ≥12, else Perlu Latihan.
- **INGAT**: selalu 5 opsi, index jawaban 0-4, gunakan `show_widget` bukan file HTML. **Opsi jawaban TIDAK diawali prefix huruf** (`A.`, `B.`, dst.) — langsung tulis teks opsinya saja.
- **INGAT**: panjang teks mengikuti kalibrasi r26 -- single 220-320 kata (min. 3 paragraf), paired 130-200 kata per teks, thread 180-260 kata. Jangan buat single text di bawah 220 kata atau satu paragraf, dan jangan melebihi 320 kata.
- **INGAT**: sebelum menulis kode, verifikasi total = 20 dan jumlah per tipe cocok dengan Variasi A/B/C yang dipilih.
- **Exp-box format (r25)**: JANGAN gunakan `.exp-wrong` / `.exp-correct` dengan border-left. Gunakan struktur blok baru: `.exp-box` (flex column, gap 6px) berisi `.exp-block.exp-wrong-block` (border #F0997B) dan `.exp-block.exp-correct-block` (border #5DCAA5). Tiap blok punya `.exp-head` (background tipis merah/hijau) berisi: `.exp-pill` (pill tag teks), `.exp-opt-lbl` (huruf opsi A-E), `.exp-svg` (inline SVG X merah / centang hijau). Body teks ada di `.exp-body` dengan background putih/transparan. Jika jawaban benar (userAns === q.ans), hanya tampilkan satu blok hijau (exp-correct-block) dengan pill dinamis "Pilihanmu" (bukan "Jawaban Benar", karena pilihan user = jawaban benar). Jika salah, tampilkan blok merah dulu (pill "Pilihanmu") lalu blok hijau (pill "Jawaban Benar"). Jika user skip/tidak menjawab, hanya blok hijau tampil dengan pill "Jawaban Benar".
- **Opsi**: pakai class `opt-radio` (14×14px circle) di dalam button `.opt`. State highlight benar/salah ada di level `.opt` (bukan di radio-nya): `.opt.correct` background hijau `#E1F5EE`, `.opt.wrong` background merah `#FAECE7`. Selected state: `.opt.selected`. `selectOpt(i)` toggle: jika `answers[cur] === i` maka set null (deselect), selain itu set i.
- **Passage rendering**: thread (`p.type === 'thread'`) -- label plain di luar, tabel dibungkus `.thread-box` (background + border). Single text dan paired text -- label plain, teks langsung tanpa box.
- Dot navigator TIDAK circle (border-radius: 0) dan posisinya di KIRI soal. Layout: `.quiz-body` flex row. Di `reviewAnswers()`, JANGAN set `bottom-nav` ke `display:none`. Dot onclick tidak ada guard `if(!quizDone)`.
- **Paired text**: `renderPairedText(p)`, deteksi via `p.type === 'paired'`. Semua soal paired text pakai `passageId` yang sama.
- **Header**: `content-header` -- label "Literasi\nBahasa Inggris" kiri, "NOMOR SOAL" + angka kanan. Timer di `.top-bar` pojok kanan. TIDAK ada badge pill, TIDAK ada submit-confirm dialog.
- **Result**: `r-hero` center (score, grade, msg), credit left (`text-align: left`), link Instagram `@muqsith.ai`.
