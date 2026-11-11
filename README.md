# Project elmyr

[English](README.en.md) · **Indonesia**

> ⚠️ **Work in progress** — Project ini masih terus disempurnakan. UTBK dan SKD belum semuanya sempurna, sedangkan TKA segera hadir.

Skill Claude untuk latihan soal UTBK, SKD (CPNS), dan TKA. **Gratis**, tanpa syarat apa pun: tidak perlu bayar, tidak perlu tag teman, tidak perlu follow Instagram. Dibuat oleh [@mqsth](https://www.instagram.com/muqsith.ai/).

> Project ini alternatif gratis, bukan pengganti bimbel. Soal dibuat dengan bantuan AI sebagai bahan latihan, bukan soal resmi UTBK/SNBT maupun CPNS. Pembahasan bisa mengandung kekeliruan, jadi cek ulang ke sumber resmi.

---

## Status

| Ujian | Folder | Status |
|---|---|---|
| UTBK | `skills/utbk/` | Work in progress |
| SKD (CPNS) | `skills/skd/` | Work in progress |
| TKA | `skills/tka/` | Upcoming (segera hadir) |

---

## Preview

<!-- Ganti dengan screenshot kamu sendiri, taruh file-nya di folder /assets/ -->

| Tampilan Soal | Hasil & Breakdown |
|---|---|
| ![Tampilan Soal](assets/screenshot-soal.png) | ![Hasil](assets/screenshot-hasil.png) |

| Mode Review |
|---|
| ![Mode Review](assets/screenshot-review.png) |

---

## Cara Pakai

1. Buka folder ujian yang kamu mau (`skills/utbk/`, `skills/skd/`, atau `skills/tka/`)
2. Pilih versi sesuai perangkatmu: `desktop/` untuk laptop/komputer, `mobile/` untuk HP
3. Download folder skill-nya. Di dalamnya ada `SKILL.md`
4. Upload ke Claude via **Settings > Skills**
5. Ketik salah satu pemicu skill tersebut, misalnya:

```
literasi bahasa inggris
latihan PK
latihan PU
latihan TIU
latihan TWK
```

> Nama file di dalam setiap folder selalu `SKILL.md`. Yang membedakan antar skill adalah nama foldernya, jadi jangan ditumpuk dalam satu folder. Versi mobile namanya berakhiran `-mobile`. Pasang salah satu versi saja untuk satu skill, karena pemicunya sama.

---

## Fitur

- Soal pilihan ganda per sesi, selalu baru setiap dipanggil
- Widget interaktif langsung tertanam di chat, tidak perlu download file
- Timer hitung mundur sesuai durasi subtes
- Navigasi soal satu per satu dengan dot navigator
- Tombol Prev / Skip / Next
- Sistem skoring otomatis
- Halaman hasil: skor, grade, pesan, breakdown per kategori
- Mode review: highlight jawaban benar/salah + pembahasan tiap soal
- Tombol "Coba lagi" untuk sesi baru
- Otomatis menyesuaikan tema terang/gelap Claude

---

## Daftar Skill

**SNBT / UTBK**
| Kode | Subtes |
|---|---|
| PPU | Pengetahuan dan Pemahaman Umum |
| PM | Penalaran Matematika |
| PK | Pengetahuan Kuantitatif |
| LBI | Literasi Bahasa Indonesia |
| LBE | Literasi Bahasa Inggris |
| PBM | Pemahaman Bacaan dan Menulis |
| PU | Penalaran Umum |

**CPNS / SKD**
| Kode | Subtes |
|---|---|
| TIU | Tes Inteligensi Umum |
| TWK | Tes Wawasan Kebangsaan |
| TKP | Tes Karakteristik Pribadi |

---

## Pengaturan yang Disarankan

Gunakan **Claude Sonnet 5.5** dengan mode **Extra**, dan **nyalakan Thinking**.

- Sonnet 5.5 dipilih karena itu versi terbaru saat ini.
- Kalau nanti ada Sonnet yang lebih baru dari 5.5, pakai yang lebih baru. Tapi tetap harus **Sonnet**, tetap mode **Extra**, dan Thinking tetap menyala.

---

## Kompatibilitas

Berjalan di [claude.ai](https://claude.ai) dengan fitur Skills aktif.

> **Catatan:** Skill ini menggabungkan fitur **Skills** dan **Visualizer** milik Claude. Keduanya berjalan penuh di perangkat desktop dan browser — widget interaktif muncul langsung di dalam chat. Untuk perangkat mobile, gunakan versi `mobile/` yang tampilannya disesuaikan dengan layar kecil.

Sederhananya, Skills bertugas memahami permintaan kamu dan menyiapkan soal, sementara Visualizer yang menampilkannya sebagai tampilan interaktif langsung di dalam chat. Karena keduanya butuh ruang layar yang cukup untuk bekerja dengan baik, penggunaan lewat browser di laptop atau komputer akan memberikan pengalaman terbaik.

---

## Lisensi dan Kontribusi

Project elmyr dilisensikan di bawah [CC BY-NC 4.0](LICENSE.md).

- Boleh dipakai, dibagikan, dan dimodifikasi untuk **non-komersial**, dengan mencantumkan atribusi ke @muqsith.ai.
- **Dilarang menjual** atau mengklaim sebagai karya sendiri. Baca [NOTICE.md](NOTICE.md).
- Mau berkontribusi? Baca [CONTRIBUTING.md](CONTRIBUTING.md).

**Project ini gratis. Kalau kamu membelinya dari orang lain, kamu kemungkinan sedang ditipu.** Temukan pelanggaran? Laporkan ke [@muqsith.ai](https://www.instagram.com/muqsith.ai/).

---

Dibuat oleh **mqsth** · [@muqsith.ai](https://www.instagram.com/muqsith.ai/)
