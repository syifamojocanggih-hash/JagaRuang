# JagaRuang

> **Cek. Latih. Lindungi.**  
> Platform web edukasi dan mitigasi anti-penipuan digital berbasis *Privacy-First* untuk masyarakat dan generasi muda Indonesia.  
> Studi Kasus: **The Trust Trap: Navigating Digital Deception** · **MIT-Week 2026** · Tema: *Guardians of the Digital Space*.

[![Build & Check Status](https://img.shields.io/badge/build-passing-brightgreen.svg)](https://github.com/syifamojocanggih-hash/JagaRuang)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Zero Backend Server](https://img.shields.io/badge/Runtime-100%25%20Client--Side-emerald.svg)](#3-arsitektur-keamanan--privasi-100-client-side)
[![Zero Tracking](https://img.shields.io/badge/Tracking-Zero%20Cookies%20%26%20Analytics-blue.svg)](#3-arsitektur-keamanan--privasi-100-client-side)

---

## Daftar Isi
1. [Latar Belakang & Masalah](#1-latar-belakang--masalah)
2. [Kerangka Guardians (Recognize, Learn, Act)](#2-kerangka-guardians-recognize-learn-act)
3. [Fitur Utama](#3-fitur-utama)
   - [Landing Page Interaktif (Three.js 3D)](#31-landing-page-interaktif-threejs-3d)
   - [Akun On-Device & Akses Demo Penguji](#32-akun-on-device--akses-demo-penguji)
   - [Pilar 1: Cek Pesan, Link, File & Izin (Recognize)](#33-pilar-1-cek-pesan-link-file--izin-recognize)
   - [Pilar 2: Hub Belajar & 8 Simulator Kasus (Learn)](#34-pilar-2-hub-belajar--8-simulator-kasus-learn)
   - [Pilar 3: Lindungi Diri & Sekitar (Act)](#35-pilar-3-lindungi-diri--sekitar-act)
   - [Fitur Spesial: Sandi Verifikasi Keluarga](#36-fitur-spesial-sandi-verifikasi-keluarga)
   - [Transparansi & Keterbatasan Sistem](#37-transparansi--keterbatasan-sistem)
4. [Arsitektur Keamanan & Privasi (100% Client-Side)](#4-arsitektur-keamanan--privasi-100-client-side)
5. [Petunjuk Penggunaan (Alur Evaluasi / Walk-Through)](#5-petunjuk-penggunaan-alur-evaluasi--walk-through)
6. [Cara Menjalankan di Komputer Lokal](#6-cara-menjalankan-di-komputer-lokal)
7. [Struktur Monorepo & Pembagian Kerja](#7-struktur-monorepo--pembagian-kerja)
8. [Teknologi yang Digunakan](#8-teknologi-yang-digunakan)
9. [Tim Pengembang](#9-tim-pengembang)
10. [Dokumentasi Teknis Terkait](#10-dokumentasi-teknis-terkait)

---

## 1. Latar Belakang & Masalah

Penipuan digital di Indonesia telah bertransformasi menjadi industri kejahatan siber yang terorganisir. Modus penipuan modern tidak lagi sekadar pesan teks acak, melainkan menggunakan teknik **Rekayasa Sosial (Social Engineering)** tingkat tinggi—seperti file APK malware berkedok surat undangan/foto paket, pencurian akun WhatsApp, pemalsuan nomor telepon resmi bank (*Caller ID Spoofing*), manipulasi stiker QRIS di ruang publik, jeratan pinjol ilegal dengan ancaman teror kontak, hingga kloning suara berbasis kecerdasan buatan (*AI Voice Cloning*).

Masyarakat kerap berada dalam kondisi panik dan tertekan saat menghadapi insiden tersebut, sehingga sulit membedakan keaslian pesan dan tidak tahu ke mana harus melapor setelah menjadi korban.

**JagaRuang** hadir sebagai solusi komprehensif non-intrusif yang menjawab tantangan ini melalui pendekatan tiga pilar: **Cek**, **Latih**, dan **Lindungi**.

---

## 2. Kerangka Guardians (Recognize, Learn, Act)

Sesuai tema *Guardians of the Digital Space*, pengalaman pengguna di JagaRuang disusun atas 3 tahapan ketahanan mental dan teknis:

| Tahapan Guardians | Fokus Pengalaman | Implementasi Fitur JagaRuang |
|---|---|---|
| **1. Recognize** *(Kenali)* | Kenali sinyal interaksi digital yang perlu diperiksa sebelum dipercaya. | **Pilar 1: Cek Pesan, Link, File & Izin** (`/cek`) dengan 22 aturan heuristik L1–L5, sensor manipulasi psikologis, pendeteksi typosquatting, serta audit izin Android berisiko. |
| **2. Learn** *(Pelajari)* | Pelajari konteks dan bukti yang tersedia agar keputusan tidak diambil terburu-buru. | **Pilar 2: Hub Belajar** (`/belajar`) dengan 8 skenario simulator percakapan interaktif, lightbox bukti forensik, 12 modul edukasi komprehensif, kuis kilat 2 menit, dan kamus taksonomi kejahatan siber. |
| **3. Act** *(Bertindak)* | Arahkan pengguna pada tindakan aman dan langkah tindak lanjut yang jelas. | **Pilar 3: Lindungi Sekitarmu** (`/lindungi` & `/sandi`) berupa SOP darurat perbankan 5 kondisi, direktori kanal lapor resmi terverifikasi, generator kartu peringatan visual, dan generator Sandi Verifikasi Keluarga anti-AI Voice Cloning. |

---

## 3. Fitur Utama

```
                                  JAGARUANG
  ┌──────────────────┬──────────────────┬──────────────────┬──────────────────┐
     LANDING PAGE        PILAR 1: CEK      PILAR 2: BELAJAR    PILAR 3: LINDUNGI
  (3D Canvas & Stats) (Pesan/Link/File)    (8 Kasus & 12 Modul)(Pusat Darurat)
                             │                  │                  │
                             ▼ [ RECOGNIZE ]    ▼ [ LEARN ]        ▼ [ ACT ]
                    [ ARSITEKTUR 100% LOKAL: TANPA SERVER & ZERO TRACKING ]
```

### 3.1. Landing Page Interaktif (Three.js 3D)
- **3D Interactive Smartphone Canvas**: Model smartphone 3D interaktif yang dirender dengan Three.js (`@react-three/fiber` dan `@react-three/drei`), menyajikan simulasi pesan penipuan secara visual dan interaktif di layar beranda.
- **Statistik Dampak Nasional**: Menampilkan rekapitulasi data resmi penipuan digital (IASC & Satgas PASTI OJK) untuk membangun kesadaran literasi pengguna.
- **Navigasi Responsif**: Penjelajahan seksi instan (Home, Tiga Pilar, Modul Simulasi, Cerita Rekan Komunitas, dan FAQ).

### 3.2. Akun On-Device & Akses Demo Penguji
JagaRuang menerapkan otentikasi privat murni di sisi peramban (`localStorage`) tanpa server backend eksternal, sehingga data dan sesi pengguna tidak pernah terlacak.

Tersedia **Akun Demo Bawaan** untuk memudahkan pengujian evaluator/juri:

| Informasi Akun | Nilai Kredensial |
|---|---|
| **Username / Email** | `demo` *(atau `demo@jagaruang.id`)* |
| **Password** | `jagaruang2026` |
| **Opsi Masuk Cepat** | Klik tombol **"Login with Google"** di halaman login untuk langsung masuk sesi instan tanpa mengetik sandi. |

> *Catatan: Pengguna juga dapat membuat akun baru melalui halaman Registrasi (`/register`) atau masuk menggunakan nama alias apa saja.*

Pengguna juga bisa langsung tekan tombol login Gooogle yang nanti akan langsung masuk ke Web Dashboard sebagai Akun Demo

### 3.3. Pilar 1: Cek Pesan, Link, File & Izin (Recognize)
- **22 Aturan Heuristik L1–L5**: Mesin inferensi lokal cerdas yang menganalisis indikator kejanggalan pada:
  - **Pesan Teks & Chat**: Mendeteksi urgensi buatan, manipulasi emosi (ketakutan/hadiah), ancaman rekening, dan instruksi transfer sepihak.
  - **Tautan / URL Phishing**: Mendeteksi *display name spoofing*, teknik karakter `@` pengalih domain (`bca.co.id@phisher.com`), domain typosquatting, dan serangan karakter Unicode Cyrillic (*Homograph Attack*).
  - **File Lampiran & Izin Android**: Menginspeksi file APK, dokumen berekstensi ganda (`.pdf.apk`), serta peringatan izin berisiko tinggi (Akses SMS, Galeri Foto, dan Buku Kontak).
- **Redaksi Otomatis Data Pribadi (PII Masking)**: Secara otomatis menyamarkan nomor telepon, nomor rekening, NIK, dan email pengguna sebelum proses analisis.
- **Visual Risk Meter & Anotasi Red Flag**: Menampilkan tingkat kewaspadaan objektif, penyorotan teks kalimat janggal menggunakan elemen aman `<mark>`, penjelasan logis *"Kenapa Mencurigakan"*, serta rekomendasi *"Cara Verifikasi Mandiri"*.
- **Tombol "Coba Contoh"**: Memungkinkan pengujian instan dengan ragam studi kasus nyata hanya dalam satu klik.

### 3.4. Pilar 2: Hub Belajar & 8 Simulator Kasus (Learn)
Pusat pembelajaran anti-penipuan komprehensif yang dirancang interaktif tanpa membaca teks membosankan:
1. **8 Skenario Simulator Kasus Nyata Interaktif**:
   - **K1 · Undangan APK Palsu**: Rekayasa sosial file instalasi berbahaya via WhatsApp.
   - **K2 · Kurir Paket & Foto Resi**: Trik ekstensi ganda `.jpg.apk` berkedok tanda terima pengiriman barang.
   - **K3 · Loker Admin WFH**: Jebakan tugas berbayar dan pemerasan deposit uang muka.
   - **K4 · Telepon CS Palsu Bank**: Manipulasi psikologis vishing untuk mencuri kode OTP 6 digit.
   - **K5 · Investasi Kripto Bodong**: Manipulasi kedekatan emosional skema *Pig Butchering*.
   - **K6 · Penangguhan Akun Email**: Jebakan kepanikan darurat pemulihan sandi palsu.
   - **K7 · Giveaway & Hadiah Palsu**: Jebakan pajak undian dan pengalihan transfer.
   - **K8 · Toko Online Fiktif**: Pancingan harga murah dan rekening perorangan non-rekening bersama.
   - *Fitur Forensik Bukti*: Dilengkapi **Lightbox Inspeksi Bukti Gambar/Dokumen** untuk memeriksa detail kejanggalan sebelum mengambil keputusan percakapan bercabang.
2. **12 Modul Edukasi Lengkap (m1 s.d. m12)**:
   - **m1: Apa Itu Rekayasa Sosial?**: Prinsip manipulasi psikologis manusia (Otoritas, Urgensi, Ketakutan, Hadiah).
   - **m2: Anatomi Sebuah Penipuan**: 5 tahapan alur penipuan dan penentuan titik keluar aman (*Safe Exit Point*).
   - **m3: Keamanan di WhatsApp**: Membedakan akun bisnis resmi centang hijau, bahaya file APK undangan, dan tautan grup asing.
   - **m4: Keamanan Email & Phishing**: Bedah display name spoofing, URL manipulasi `@`, serangan homograph Unicode, dan mini tantangan CTF.
   - **m5: Waspada Telepon Mengaku Bank (Vishing)**: Pembongkaran teknologi *Caller ID Spoofing*, aturan verifikasi mandiri nomor fisik kartu ATM, dan simulasi percakapan.
   - **m6: 10 Ciri Pesan Phishing (Capstone)**: Kompilasi 10 red flag universal lintas kanal dan asesmen kejelian 5 pesan.
   - **m7: Checklist Sebelum Transfer**: Aturan 5 detik, pemahaman rekening penampung (nominee), dan manipulasi kode unik transfer.
   - **m8: Pola Modus Penipuan Terbanyak di Indonesia**: Visualisasi data statistik dinamis dari IASC dan Satgas PASTI OJK.
   - **m9: Pola Penipuan QRIS & E-Wallet**: Pemisahan sudut pandang Pembeli vs Penjual, simulasi hotspot meja kasir & kotak amal, poster keamanan pedagang, dan aturan penerimaan saldo tanpa PIN/OTP.
   - **m10: Pola Pinjaman Online Ilegal**: Aturan izin resmi CAMILAN (Kamera, Mikrofon, Lokasi), simulator izin Android, tabel komparasi fintech legal vs ilegal, pemeriksa offline 3 langkah, dan templat pesan penangkal teror kontak.
   - **m11: Pusat Darurat - Cara Lapor Jika Sudah Jadi Korban**: Wizard darurat 3 langkah (mendukung parameter `?jalur=bank|ewallet|qris|kripto|whatsapp|apk|pinjol`), penegasan domain resmi tunggal `iasc.ojk.go.id`, generator draf kronologi 100% lokal di browser, dan mitigasi penipuan lapis kedua (*Recovery Scam*).
   - **m12: Cara Mendampingi Keluarga yang Kena Tipu**: Pendampingan psikologis 3 fase trauma korban, chat bubble perbandingan dialog suportif vs menghardik, urutan prioritas teknis (mode pesawat vs cabut SIM card), dan integrasi fitur Sandi Keluarga.
3. **Kuis Kilat 2 Menit (Reflex Drill)**:
   - Micro-learning menguji refleks deteksi 10 pesan acak dalam batasan waktu 120 detik dengan evaluasi akurasi instan.
4. **Kamus Jebakan & Modus Populer**:
   - Ensiklopedia taksonomi penipuan digital (APK Sniffer, Quishing, Fake Job, Romance Scam, SIM Swap, dsb.) lengkap dengan pertolongan pertama 15 menit dan langkah pencegahan.

### 3.5. Pilar 3: Lindungi Diri & Sekitar (Act)
- **Checklist Panduan Tindakan 5 Kondisi**: Penanganan terstruktur untuk kondisi *Darurat Terpapar*, *Waspada*, *Kritis*, *Pemulihan*, dan *Edukasi*.
- **Portal Kanal Lapor Resmi Terverifikasi**: Direktori kontak terverifikasi (IASC OJK, Satgas PASTI, Bank Indonesia, Kepolisian SPKT 110, AduanKonten Komdigi, CS WhatsApp).
- **Generator Kartu Peringatan Bahaya**: Menghasilkan kartu grafis digital siap unduh dan siap sebar untuk mengingatkan grup keluarga atau komunitas.

### 3.6. Fitur Spesial: Sandi Verifikasi Keluarga
- **Penangkal Kloning Suara AI (*AI Voice Cloning*)**: Memandu keluarga membuat kata sandi rahasia verbal yang disepakati bersama secara langsung (tatap muka). Ketika ada panggilan darurat mencurigakan yang meminta uang tebusan, penanya cukup menanyakan kata sandi ini untuk memastikan keaslian penelpon.

### 3.7. Transparansi & Keterbatasan Sistem
- Menjelaskan batasan sistem secara jujur: JagaRuang adalah platform edukasi berbasis heuristik offline, bukan perangkat antivirus dan bukan saluran pelaporan aparat penegak hukum.
- Dilengkapi tombol **"Hapus Semua Data Lokal"** untuk menghapus progres modul, catatan notifikasi, dan preferensi tersimpan di peramban seketika.

---

## 4. Arsitektur Keamanan & Privasi (100% Client-Side)

JagaRuang dibangun dengan prinsip **Privacy-First Architecture**:

```
[ PENGGUNA ] ────► [ PERAMBAN (BROWSER) ] ────► [ LOCAL STORAGE (OPSIONAL) ]
                          │
                          ▼
            [ ANALYZER HEURISTIK LOKAL ]
            - Tanpa server aplikasi (Zero Backend Server)
            - Tanpa database eksternal
            - Tanpa cookies pelacak (Zero Cookies)
            - Tanpa skrip analitik pihak ketiga
            - Tanpa pemanggilan jaringan (Zero Runtime Network Requests)
```

1. **Zero Runtime Network Calls**: Seluruh proses analisis teks, tautan, ekstensi file, kuis, simulasi, dan generator kronologi dieksekusi murni di mesin JavaScript peramban pengguna.
2. **Data Isolation**: Tidak ada data yang dikirim ke server. Tautan mencurigakan **tidak pernah dibuka** oleh sistem; isi file lampiran **tidak pernah diunggah**.
3. **Strict Content Security Policy (CSP)**: Mencegah eksekusi skrip jahat pihak ketiga dan kebocoran data.
4. **Offline Capability**: Aplikasi dapat dioperasikan secara penuh tanpa koneksi internet aktif setelah aset halaman dimuat.

---

## 5. Petunjuk Penggunaan (Alur Evaluasi / Walk-Through)

Bagi juri, penguji, atau pengguna yang ingin mencoba seluruh kapabilitas JagaRuang, ikuti skenario penelusuran berikut:

### Skenario A: Menguji Deteksi Pesan & File Phishing (Pilar Cek)
1. Buka menu **Cek Pesan & Berkas** (`/cek`).
2. Klik tombol **"Coba Contoh"** pada tab Pesan untuk memuat pesan rekayasa sosial kurir paket APK.
3. Perhatikan hasil analisis: perhatikan bagaimana sistem menyamarkan nomor telepon otomatis, menampilkan meter risiko, menyoroti kalimat pancingan dengan `<mark>`, dan memaparkan penjelasan *"Kenapa"* dan *"Cara Verifikasi"*.
4. Pindah ke tab **Cek File & Izin**, pilih contoh berkas `.pdf.apk` untuk melihat inspeksi ekstensi ganda dan bahaya izin Android.

### Skenario B: Menjalankan Simulasi Kasus Nyata (Pilar Latih)
1. Buka menu **Belajar** (`/belajar`) dan pilih tab **Simulator**.
2. Pilih skenario *Skenario #1: Tagihan Pajak Ekstensi Ganda* atau *Skenario #2: Kurir Paket Misterius*.
3. Masuk ke antarmuka chat WhatsApp interaktif:
   - Ketuk gambar lampiran untuk membuka **Modal Lightbox Inspeksi Bukti**.
   - Pilih keputusan terbaik saat berhadapan dengan pancingan penipu.
   - Amati konsekuensi keputusan dan baca hasil evaluasi *Debrief* di akhir kasus.

### Skenario C: Menjelajahi Modul Edukasi & Pusat Darurat (Pilar Belajar)
1. Buka tab **Modul** di halaman Belajar.
2. Buka modul **m10: Pola Pinjaman Online Ilegal**:
   - Coba **Simulator Izin Aplikasi** untuk menguji izin Kontak, Galeri, Kamera, dan Lokasi.
   - Uji alat mandiri **Pemeriksa 3 Langkah: Cek Sebelum Mengajukan**.
   - Beralih ke tab *"Aku Sedang Diteror"* untuk menyalin templat klarifikasi keluarga.
3. Buka modul **m11: Pusat Darurat (Cara Lapor Jika Sudah Jadi Korban)**:
   - Coba **Wizard Darurat** untuk menentukan kanal transaksi.
   - Gunakan **Generator Kronologi Lokal** untuk membuat draf laporan siap salin ke portal resmi `iasc.ojk.go.id`.
4. Buka modul **m12: Cara Mendampingi Keluarga yang Kena Tipu**:
   - Lihat kontras kalimat pada *Chat Bubble Dialog*.
   - Jalankan mini simulasi respons empati terhadap korban.

### Skenario D: Membuat Sandi Verifikasi Keluarga & Kartu Peringatan (Pilar Lindungi)
1. Buka menu **Sandi Keluarga** (`/sandi`), buat 2–3 kata sandi rahasia keluarga, dan pahami cara penggunaannya saat menghadapi telepon darurat.
2. Buka menu **Lindungi** (`/lindungi`), pilih tab **Kartu Peringatan**, pilih salah satu template modus, dan unduh atau bagikan kartu peringatan visual ke media sosial/grup chat.

---

## 6. Cara Menjalankan di Komputer Lokal

### Prasyarat Sistem
- **Node.js**: Versi `20.x` atau yang lebih baru.
- **npm**: Versi `10.x` atau yang lebih baru.
- **Git**: Untuk kloning repositori.

### Langkah Instalasi & Menjalankan

1. **Kloning Repositori:**
   ```bash
   git clone https://github.com/syifamojocanggih-hash/JagaRuang.git
   cd JagaRuang
   ```

2. **Instalasi Dependensi Monorepo:**
   ```bash
   npm install
   ```

3. **Konfigurasi Lingkungan (Opsional):**
   Aplikasi sudah memiliki konfigurasi default yang siap pakai tanpa perlu konfigurasi `.env`. Jika ingin kustomisasi, Anda dapat menyalin file template:
   ```bash
   # Linux / macOS
   cp apps/web/.env.example apps/web/.env.local

   # Windows (PowerShell)
   Copy-Item apps/web/.env.example apps/web/.env.local
   ```

4. **Menjalankan Server Pengembangan Lokal:**
   ```bash
   npm run dev
   ```
   Buka peramban di alamat: `http://localhost:5173`.

5. **Menjalankan Pengujian & Pengecekan Kualitas Kode (Check Suite):**
   ```bash
   npm run check
   ```
   *Perintah ini secara otomatis menjalankan TypeScript typecheck di seluruh workspace, rangkaian unit test Vitest, dan kompilasi build produksi Vite.*

6. **Membangun Bundel Produksi & Pratinjau:**
   ```bash
   npm run build
   npm run preview -w @jagaruang/web
   ```

---

## 7. Struktur Monorepo & Pembagian Kerja

Proyek ini menggunakan arsitektur **npm workspaces** untuk memisahkan domain logika dan domain tampilan secara bersih:

```
JagaRuang/
├── apps/
│   └── web/                         # [Domain Frontend] Aplikasi Web React 18 + Vite
│       ├── public/                  # Aset statis & ikon
│       ├── src/
│       │   ├── components/          # Komponen UI modular
│       │   │   ├── landing/         # Komponen 3D Canvas Three.js & Beranda
│       │   │   ├── modul/           # 12 Halaman modul pembelajaran interaktif (m1-m12)
│       │   │   ├── simulator/       # Simulator chat & voice call interaktif
│       │   │   └── ui/              # Atom UI (Card, Button, RiskMeter, Modal, dsb.)
│       │   ├── data/                # Dataset modul pembelajaran & referensi resmi
│       │   ├── pages/               # Halaman utama (Beranda, Dashboard, Cek, Belajar, Lindungi, Sandi, Keterbatasan)
│       │   ├── lib/                 # coreClient.ts (pintu gerbang tunggal konsumsi core)
│       │   └── mocks/               # Mock data untuk pengujian antarmuka
│       ├── index.html
│       └── vite.config.ts
├── packages/
│   ├── core/                        # [Domain Backend] Logika inferensi heuristik & deteksi
│   │   ├── src/
│   │   │   ├── analyzer/            # Aturan heuristik L1-L5, normalisasi, & kalkulasi skor
│   │   │   ├── data/                # Data referensi taksonomi malware & modus
│   │   │   └── scoring.test.ts      # Pengujian unit test logika penilaian
│   │   └── package.json
│   └── contracts/                   # [Domain Bersama] Definisi antarmuka tipe TypeScript bersama
│       ├── src/
│       │   └── index.ts             # Tipe AnalysisResult, RedFlag, Severity, dsb.
│       └── package.json
├── docs/                            # Dokumentasi teknis & arsitektur proyek
│   ├── universal/                   # Kontrak global, keputusan arsitektur (ADR), & alur git
│   ├── frontend/                    # Panduan frontend, design system, & changelog UI
│   ├── backend/                     # Panduan backend, data model, & task guide logika
│   └── development/                 # Panduan deployment & konfigurasi GitHub
├── scripts/                         # Skrip otomatisasi & verifikasi batas cakupan git
├── package.json                     # Konfigurasi root monorepo
├── vercel.json                      # Konfigurasi deployment & Security Headers (CSP)
└── README.md                        # Berkas dokumentasi utama proyek
```

---

## 8. Teknologi yang Digunakan

| Kategori | Teknologi / Pustaka | Penggunaan |
|---|---|---|
| **Core Framework** | React 18 & TypeScript 5 | Antarmuka komponen interaktif berbasis tipe ketat |
| **Build Tool** | Vite 6 | Bundler super cepat dengan Hot Module Replacement (HMR) |
| **Styling & Design** | Tailwind CSS v4 & Lucide React | Utilitas styling modern, ikonografi konsisten, dan desain responsif |
| **3D Rendering** | Three.js, `@react-three/fiber`, `@react-three/drei` | Visualisasi model 3D smartphone di Landing Page |
| **Typography** | Fontsource (Plus Jakarta Sans & Inter) | Tipografi self-hosted tanpa permintaan jaringan eksternal |
| **Testing** | Vitest | Pengujian unit test logika inferensi heuristik |
| **Hosting & CI** | Vercel | Hosting statis global dengan konfigurasi CSP ketat |

---

## 9. Tim Pengembang

Proyek **JagaRuang** dikembangkan oleh:

| Nama | Peran | Tanggung Jawab Utama |
|---|---|---|
| **Ahmad Syifa'ul Falakhul Khayyi** | Frontend & UI/UX Engineer | Arsitektur UI, Three.js 3D Canvas, Hub Belajar & 12 Modul Pembelajaran |
| **Mutiara Dewanda Prisvilla** | Frontend & Interaction Engineer | Fake Chat Simulator, Lightbox Forensik Bukti, & Halaman Navigasi |
| **Raffi Azzaky Ramadhani** | Backend & Logic Engineer | Mesin Inferensi Heuristik 22 Aturan, Normalisasi Teks, & Kontrak Data |
| **Ahmad Syafi'al Anam** | Quality Assurance & Testing | Verifikasi Skenario Kasus, Pengujian Aksesibilitas, & Review Keamanan |

---

## 10. Dokumentasi Teknis Terkait

Untuk pemahaman mendalam mengenai arsitektur sistem, aturan kode, dan riwayat pengembangan, silakan baca dokumentasi teknis pendukung berikut:

- 📑 [**Indeks Dokumentasi Repositori**](docs/README.md)
- 🎨 [**Panduan Sistem Desain & Aksesibilitas (DESIGN_SYSTEM.md)**](docs/frontend/DESIGN_SYSTEM.md)
- 🗺️ [**Spesifikasi Rute & Alur Pengguna (PAGES_AND_FLOWS.md)**](docs/frontend/PAGES_AND_FLOWS.md)
- 📝 [**Catatan Perubahan Frontend (CHANGELOG.md)**](docs/frontend/CHANGELOG.md)
- 🏛️ [**Catatan Keputusan Arsitektur / ADR (DECISIONS.md)**](docs/universal/DECISIONS.md)
- 🔌 [**Spesifikasi Kontrak & Antarmuka Data (INTERFACES.md)**](docs/universal/INTERFACES.md)
- 🚀 [**Panduan Deployment Produksi (DEPLOY.md)**](docs/development/DEPLOY.md)

---

<p align="center">
  <strong>JagaRuang — Cek. Latih. Lindungi.</strong><br>
  <em>Guardians of the Digital Space · MIT-Week 2026</em>
</p>
