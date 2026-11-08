# Lancar Indonesia

> **Bahasa Indonesia yang lancar: baku tanpa kaku, jujur, dan jernih dibaca.**
> Skill untuk agen AI (Claude Code, ZCode, dll.) yang membuat naskah buatan AI terdengar seperti tulisan manusia yang cermat.

---

## Masalahnya

Teks AI berbahasa Indonesia mudah dikenali walau belum dibaca sampai bawah:

> Di era digital yang serba cepat ini, kami menghadirkan fitur parkir berbasis aplikasi yang
> memberikan dampak signifikan bagi kenyamanan Anda. Fitur ini bukan sekadar aplikasi parkir;
> fitur ini merupakan pilar utama tata kelola transportasi kota. Tak hanya itu, aplikasi ini
> juga memungkinkan Anda untuk mengeksplorasi berbagai fitur menarik lainnya. Demikianlah
> pengumuman ini kami sampaikan. Semoga bermanfaat.

Kalimatnya tidak salah secara tata bahasa. Tetapi pembaca harus menebak sendiri: apa yang
sebenarnya diberlakukan, kapan, berapa biayanya, dan untuk siapa. Nada iklan, pembuka
kosmik, penutup baku, dan penghubung ritual membuat pembaca berhenti mempercayai isinya.

## Sesudah Lancar Indonesia

> Mulai 1 Desember, parkir di lima kawasan pusat kota dibayar lewat aplikasi ParkirAyo.
> Pengguna memindai kode QR di titik parkir, dan tarif tampil di layar sebelum pembayaran:
> Rp2.000 untuk jam pertama mobil dan Rp1.000 per jam berikutnya. Pengguna tanpa ponsel
> pintar dapat memakai kartu prabayar yang dijual di kios Pasar Baru dan Alun-Alun.

Sama panjang, tetapi setiap kalimat mengonfirmasi tebakan pembaca, bukan membatalkannya.
Bentuk lain yang sering muncul dan cara panduan ini memperbaikinya:

| Kaku / khas AI | Jernih |
| --- | --- |
| `Dari hasil pengujian menunjukkan bahwa…` | Hasil pengujian menunjukkan bahwa… (kata depan tidak boleh menelan subjek) |
| `membuat analisis terhadap data` | menganalisis data |
| `memainkan peran penting` | berperan penting |
| `…di mana setiap siklus terdiri dari…` | …yang terdiri atas… (bukan "di mana" sebagai penghubung) |
| `Hal ini menunjukkan bahwa asupan kurang.` | Kadar serendah ini menunjukkan bahwa asupan kurang. (sebut subjeknya) |
| `Parkir bukan sekadar layanan.` | Parkir ini menata pemakaian jalan: tarif tampil sejak awal, dan setiap pembayaran tercatat. |
| `sistem ini mendukung kestabilan layanan` | Permintaan yang gagal dicoba ulang maksimal tiga kali, sehingga proses tetap berjalan saat jaringan sempat terputus |
| `Verifikasi dilakukan setiap malam. Pemberitahuan dikirim.` | Sistem menjalankan verifikasi setiap malam. Bila anomali ditemukan, sistem mengirim pemberitahuan ke admin jaga. |
| `Dimana kelima kawasan tersebut…` / `diantara` | Di mana… / di antara (ejaan EYD V) |
| `Secara keseluruhan, semuanya berjalan baik. Demikianlah pengumuman ini.` | (hapus — simpulan cukup sekali, penutup baku tidak menambah apa pun) |

## Hasil uji: seberapa besar bedanya?

Uji buta oleh agen AI penulis: tiga jenis naskah (berita fiktif, penjelasan populer, esai
majalah), tiap jenis ditulis dua kali — dengan dan tanpa panduan — lalu dinilai penelaah
lain yang tidak tahu mana versi mana.

| Ukuran | Tanpa panduan | Dengan panduan |
| --- | --- | --- |
| Pola K/G/AI yang terdeteksi `scripts/periksa.py` (3 naskah) | **10 temuan** | **0 temuan** |
| Klise mesin (pembuka kosmik, penghubung ritual, `Anda` berlebihan, dll.) | 16 kemunculan | **0** |
| Skor keterbacaan penelaah buta (6 kriteria) | berita 7,8 · penjelasan 7,5 · esai 8,3 | berita **8,8** · penjelasan **8,7** · esai 8,2 |

Penelaah buta menulis tentang versi panduan: *"alurnya linier tanpa perlu dibaca ulang
berkat kalimat jembatan antarparagraf yang jelas"* dan *"dasar hukum dan angkanya dapat
diperiksa, mengakui keluhan secara jujur, ditutup proyeksi data alih-alih kutipan slogan."*

Catatan: uji dilakukan satu kali per kondisi dengan agen AI, jadi angkanya gambaran, bukan
ukuran statistik.

## Apa isinya

```
lancar-indonesia/
├── SKILL.md              # titik masuk: kontrak, batas perubahan, alur kerja
├── KONTRAK.md            # kontrak kejujuran (data, rujukan, pengungkapan AI)
├── references/
│   ├── pola-ai.md        # katalog pola tulisan AI & kalke Inggris (AI-01 … AI-19 + baru)
│   ├── kalimat-efektif.md # subjek hilang, nominalisasi, pleonasme, kata tunjuk, perangkai
│   ├── membaca-lancar.md # nada masalah/perbaikan, alur pertanyaan pembaca, kamus konsep
│   ├── ejaan-eyd-v.md    # ejaan EYD V: di/di-, gabungan kata, angka, satuan, koma
│   ├── kata-baku.md      # bentuk baku KBBI
│   ├── pertahankan.md    # konvensi yang JANGAN dikoreksi (pasif Metode, hedging, dll.)
│   ├── istilah.md        # istilah asing: terjemah / serap / pertahankan
│   ├── singkatan.md      # singkatan, akronim, nama lembaga
│   ├── sitasi.md         # rujukan dan cara menyitir
│   └── alat-riset.md     # menyambungkan alat pencarian rujukan
├── contoh/
│   └── sebelum-sesudah.md # 12 contoh paragraf (ilmiah + nonilmiah)
└── scripts/
    ├── periksa.py        # saringan pola: python scripts/periksa.py naskah.md
    └── openalex.py       # cek rujukan lewat OpenAlex/Crossref
```

Dua hal yang dibedakan tegas:

- **K (kaidah)** — melanggar EYD V, KBBI, atau tata bahasa baku. Wajib diperbaiki.
- **AI (klise mesin)** — pola tulisan mesin. Diperbaiki pada pekerjaan sunting/tulis ulang;
  satu kemunculan saja biasanya belum masalah.

Yang **tidak** dilakukan: mengubah angka, hasil, atau sitasi; mengarang rujukan;
menyamarkan hasil AI dari detektor. Bila data kurang, panduan menulis
`[PERLU DATA: …]`, bukan mengisi sendiri.

## Cara pakai

**Sebagai skill agen AI:** salin folder ini ke direktori skills agen kamu
(misalnya `~/.agents/skills/lancar-indonesia` atau `~/.claude/skills/lancar-indonesia`), lalu
minta agen: *"rapikan bahasanya"* atau *"tulis latar belakang dari catatan ini"*.

**Sebagai saringan mandiri:**

```bash
python scripts/periksa.py naskah.md                   # daftar pola K/G/AI yang terdeteksi
python scripts/periksa.py --banding asli.md draf.md   # angka/sitasi berubah?
```

## Kredit

Panduan ini berdiri di atas dua karya:

- **[`naskah-id`](https://github.com/nothinx/naskah-id)** oleh [nothinx](https://github.com/nothinx) (MIT) —
  kerangka kontrak kejujuran, kaidah EYD V & KBBI, katalog pola AI, skrip `periksa.py` dan
  `openalex.py`, serta struktur skill keseluruhannya berasal dari sini. Aturan panduan ini
  mengikuti kaidah `naskah-id` bila keduanya bertentangan.
- **[`predictable-reading-japanese`](https://gist.github.com/VarYUvrc/6fe8174afa5d902fa2bc7a8a47b5484e)** oleh
  [VarYUvrc](https://gist.github.com/VarYUvrc) — gagasan "teks yang bisa diprediksi
  alurnya": nada masalah/perbaikan, alur pertanyaan pembaca, kamus konsep di muka,
  penghindaran bantahan mendadak. Diadaptasi ke bahasa Indonesia dengan contoh dan
  pola yang benar-benar muncul pada teks AI Indonesia (bukan terjemahan harfiah).

Terima kasih kepada kedua penulis aslinya.

## Lisensi

MIT — bebas dipakai, diubah, dan didistribusikan. Lihat [LICENSE](LICENSE).

---

### 日本語メモ / Japanese notes

**Lancar Indonesia** =「なめらかに読めるインドネシア語」。AIが書いたインドネシア語を、学術(EYD V / KBBI 準拠)・
一般文書の両方で「自然・標準的・誠実・読みやすい」に整えるスキル。

- 元の2スキルを統合: [naskah-id](https://github.com/nothinx/naskah-id)(EYD/KBBI・捏造禁止コントラクト、MIT)と
  [predictable-reading-japanese](https://gist.github.com/VarYUvrc/6fe8174afa5d902fa2bc7a8a47b5484e)(予測可能性ガイド)。矛盾時は naskah-id 優先。
- 効果(同条件AI比較、各1回): 規則違反・AI定型は **10件/16件 → 0件**、ブラインド判定は
  ニュース 7.8→**8.8**、解説 7.5→**8.7**、作文 8.3→8.2(ほぼ互角)。
- 使い方: skill フォルダをエージェントの skills ディレクトリにコピー。
  `python scripts/periksa.py ファイル` で単体スキャンも可能。
