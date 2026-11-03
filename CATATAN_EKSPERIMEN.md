# Catatan eksperimen DSCO 2026

**Fungsi berkas:** log utama yang terus diperbarui dari hari ke hari, di luar folder `main`, `main 2`, dan folder kerja berikutnya. Catat setiap temuan, keputusan, kombinasi eksperimen, hasil validasi, serta skor submission yang nanti diberikan pengguna. Bagian hari sebelumnya tetap disimpan sebagai riwayat.

## Status terbaru — 29 Oktober 2026

**Champion public leaderboard tetap Main 4 / M4-03, `submission_m4_03_tuned.csv`, F1 Kaggle 0,78502** (skor yang dilaporkan pengguna). Submission M5-00 GPU memperoleh **0,78460**, dan ensemble 3 seed M7-01 memperoleh **0,78462**. Hasil Main 6 dan Main 8 masih **validasi lokal, belum ada Kaggle submission baru yang dikonfirmasi**. Audit M8-00 selesai; dua eksperimen representasi aktivitas M8-02A dan M8-02B sama-sama gagal mengungguli champion lokal. Hasil terperinci Main 6–8 ditambahkan setelah riwayat Main 5. **Koreksi krusial:** meskipun tabel evaluasi M4-03 memilih *global threshold* 0,375 untuk F1 cross-fit, **file submission champion aktual memakai threshold grup 0,420 (`has_score=0`) dan 0,375 (`has_score=1`)**; direproduksi identik oleh M6-00 dan M7 seed 42. Snapshot lama yang masih menyebut global 0,375 tidak lagi berlaku sebagai aturan submission.

| Urutan submission yang dikonfirmasi | File | Kaggle F1 | Selisih terhadap champion kini |
| --- | --- | ---: | ---: |
| Main 2 / M2-06 | `submission_main2.csv` | 0,77757 | −0,00745 |
| Main 3 / M3-02 | `submission_m3_02_group.csv` | 0,78393 | −0,00109 |
| Main 4 / M4-02 fixed | `submission_m4_02_fixed_m3.csv` | 0,78317 | −0,00185 |
| **Main 4 / M4-03 tuned** | **`submission_m4_03_tuned.csv`** | **0,78502** | **0,00000** |
| Main 5 GPU / M5-00 reproduction | `submission_m5_00_champion_reproduction.csv` | 0,78460 | −0,00042 |
| Main 7 / M7-01 3 seed | `submission_m7_01_3seed.csv` | **0,78462** | −0,00040 |

> Catatan: nilai Kaggle di atas diberikan pengguna. Ini bukan nilai private leaderboard dan tidak membuktikan perubahan tertentu menyebabkan kenaikan generalisasi. **Main 6 dan Main 8 belum memiliki skor Kaggle baru yang dikonfirmasi.**

## Cara memperbarui log

1. Setiap hari, tambahkan bagian baru dengan tanggal dan nama folder kerja (`main 3`, dan seterusnya). Jangan membuat log utama baru atau menghapus hasil hari sebelumnya.
2. Untuk tiap temuan, tulis **bukti → pilihan yang dicoba → hasil uji → keputusan akhir → alasan**. Bedakan rencana dari langkah yang benar-benar sudah dijalankan.
3. Setiap kombinasi mendapat ID run sendiri. Catat F1 validasi, threshold, nama file submission, dan skor leaderboard. Skor leaderboard diisi setelah pengguna memberikan nilainya.
4. Saat membuat ZIP harian, arsipkan notebook, EDA, dan submission hari tersebut. Log utama ini tetap di folder proyek agar dapat terus diperbarui.

## Progres lintas hari

| Hari / folder | Tahap terakhir yang tercatat | Run terpilih | Submission / skor leaderboard |
| --- | --- | --- | --- |
| 7–8 Oktober 2026 — `main 2` | EDA, FE, 7 variasi cleaning 3-fold, model 5-fold, audit OULAD, submission | M2-06; blend LightGBM 75% + CatBoost 25% | `main 2/submission_main2.csv` → Kaggle F1 **0,77757** |
| 8 Oktober 2026 — audit sumber | Tujuh tabel OULAD dicocokkan dengan data lomba; ditemukan 145 kode modul train yang bergeser | Model Main 2 belum dijalankan ulang | Lihat `main 2/temuan_sumber_oulad.md` |
| 23 Oktober 2026 — `main 3` | Lima eksperimen skor 77 dan missingness, 5-fold CV, threshold per grup, submission | **M3-02**; missingness interactions, threshold berdasarkan `has_score` | `main 3/submission_m3_02_group.csv` → Kaggle F1 **0,78393** (**terbaik yang terkonfirmasi**) |
| 23 Oktober 2026 — `main 4` | Notebook disiapkan untuk optimasi mahasiswa `has_score=1` | Belum ada run dieksekusi/dikonfirmasi | `Main4_DSCO_2026.ipynb`; CV dan leaderboard **belum ada** |
| 23 Oktober 2026 — `main 4` (hasil berikutnya) | Empat model CV; dua submission dinilai Kaggle | **M4-03 tuned**, 65% spesialis pada `has_score=1` | `submission_m4_03_tuned.csv` → **0,78502**; `M4-02 fixed` → 0,78317 |
| 24 Oktober 2026 — `main 5 GPU` | Enam run GPU/CPU campuran; audit imputasi dan 3 grup; satu Kaggle submission | **M5-00** terbaik F1 cross-fit lokal; champion Kaggle tetap M4-03 | `submission_m5_00_champion_reproduction.csv` → **0,78460**; M5-01–05 belum ada LB |
| 24 Oktober 2026 — `main 6` | Lima run assessment-aware, native missing CatBoost, normalisasi cohort; reproduksi baseline CPU | **M6-00** fixed OOF F1 **0,775934**; semua M6-01–04 lebih rendah | Belum ada submission Kaggle baru |
| 25 Oktober 2026 — `main 7` | Ensemble 1, 2, 3 seed; audit diversity komponen | **M7-00** fixed OOF F1 **0,775934**; ensemble 3 seed **0,774825** | `submission_m7_01_3seed.csv` → Kaggle **0,78462** |
| 29 Oktober 2026 — `main 8 new_version` | M8-00 audit semantik; M8-02A raw vs recompute; M8-02B full activity masking | **M8-BASE** F1 **0,775934**; M8-02A **0,772787**; M8-02B **0,774382** | Tidak ada submission M8, kedua varian gagal screening |


## 7 Oktober 2026 — Main 2

**Fokus hari ini:** memahami data mentah dan menyiapkan pilihan cleaning untuk dibandingkan.

> **Status awal bagian ini:** EDA sudah dilakukan, tetapi eksperimen cleaning dan model saat itu belum dijalankan. Hasil aktual setelahnya dicatat di tabel run dan pembaruan 8 Oktober di bawah.

### Ringkasan keputusan Main 2

| Temuan | Bukti singkat | Pilihan kerja Main 2 | Status |
| --- | --- | --- | --- |
| `imd_band` berisi `-`/`?`; `highest_education` berisi `-` | Train: 3.696 dan 279 baris. Test: 928 dan 68 baris. | Samakan token tersebut menjadi kategori `Missing`. Jangan isi dengan kategori mayoritas. | Diputuskan; implementasi belum dicatat |
| Penulisan kategori berbeda | `A Level`/`A level`; `region2`/`Region 3`/`Region6`. | Standarkan ejaan dan format secara identik pada train dan test. Contoh: `A level` → `A Level`, `region2` → `Region2`, `Region 3` → `Region3`. | Diputuskan; implementasi belum dicatat |
| `highest_education` yang hilang mungkin terkait kolom lain | Uji sederhana menebak pendidikan: akurasi 48,2% vs tebakan kategori mayoritas 43,4%. Ini **bukan** skor prediksi `at_risk`. | Tetap gunakan kategori `Missing`; jangan menebak pendidikan per mahasiswa pada Main 2. | Diputuskan; implementasi belum dicatat |
| `code_module=GGG` hanya di test | 372 baris; 366 berada di antara baris `M07` menurut urutan ID, enam lainnya di tepi blok yang sama. Pola presentation, durasi, dan `has_score` cocok dengan `M07`. | Gunakan pemetaan `GGG` → `M07`. Tabel OULAD yang ditemukan 8 Oktober mengonfirmasi bahwa GGG adalah kode sumber untuk M07. | Sudah dipakai pada Main 2 |
| `has_score=0`, tetapi kolom skor terisi | Semua 10.046 baris train dan 2.636 baris test dalam kelompok ini mempunyai `avg_score=77`; kolom skor lain juga berulang. | **Pertahankan `has_score=0`.** Angka skor pada kelompok ini diuji sebagai kandidat nilai pengisi; angka 77 pada `has_score=1` tetap skor yang mungkin asli. | Flag diputuskan; perlakuan skor belum final |
| Agregat aktivitas tidak cocok dengan mingguannya | 3.737 baris train dan 947 baris test punya `interaction_volume=182`, tetapi 36+31+46+28=141. Beberapa agregat lain tidak cocok pada baris yang sama. | Buat penanda `activity_inconsistent` dari ketidaksamaan volume dan jumlah minggu. Bandingkan perlakuan terhadap agregat melalui F1. Jangan langsung mengganti 182 dengan 141. | Perlu eksperimen |
| Day 28 muncul meski deskripsi menyebut Day 0–27 | `last_activity_day=28` pada 6.451 baris train dan 1.626 baris test; tidak tumpang tindih dengan profil aktivitas bermasalah di atas. | Biarkan nilai Day 28 untuk saat ini. Jangan hapus baris. | Diputuskan sementara |
| Dua kolom selalu bernilai 1 | `submitted_Assessment_1` dan `submitted_Assessment_2` konstan di train dan test. | Keluarkan keduanya dari fitur model. | Diputuskan; implementasi belum dicatat |

**Catatan penting:** angka pada kolom `at_risk` hanya dipakai untuk audit dan validasi. Aturan cleaning tidak boleh memakai label baris test atau hasil target encoding yang dihitung di luar fold.

### Kombinasi yang dibandingkan

Semua variasi cleaning memakai **3 fold, seed 42, LightGBM, FE, dan prosedur pemilihan threshold OOF yang sama**. Angka tabel adalah hasil yang sudah dijalankan; skor leaderboard belum diberikan pengguna. Angka 3 fold di sini tidak dibandingkan langsung dengan hasil model akhir 5 fold.

| Run | Perubahan dibanding run sebelumnya | F1 OOF | Threshold | File submission | Skor leaderboard | Status / catatan |
| --- | --- | ---: | ---: | --- | ---: | --- |
| M2-00 | Baseline: data sebagaimana dibaca dari CSV. | 0,7731 | 0,380 | — | — | Baseline raw; test memiliki GGG yang tidak dikenal model |
| M2-01 | M2-00 + token `Missing`, format kategori, `GGG` → `M07`, hapus dua fitur konstan. | 0,7713 | 0,415 | — | — | Sudah diuji |
| M2-02 | M2-01 + saat `has_score=0`, perlakukan kolom skor sebagai missing; pertahankan `has_score`. | 0,7719 | 0,405 | — | — | Sudah diuji |
| M2-03 | M2-01 + fitur `activity_inconsistent`; biarkan angka aktivitas asli. | 0,7719 | 0,370 | — | — | Sudah diuji |
| M2-04 | M2-02 + fitur `activity_inconsistent`; biarkan angka aktivitas asli. | 0,7721 | 0,380 | — | — | Sudah diuji |
| M2-05 | M2-04 + perlakukan agregat aktivitas yang tidak konsisten sebagai missing, tanpa mengubah empat angka mingguan. | 0,7707 | 0,425 | — | — | Sudah diuji |
| M2-06 | M2-04 + hitung ulang hanya agregat yang dapat diperoleh dari hitungan mingguan. | 0,7729 | 0,370 | `main 2/submission_main2.csv`* | — | Terpilih untuk model akhir; *submission memakai model/threshold 5 fold, bukan angka pada baris ini |

### Cara mengambil keputusan akhir hari kedua

1. Bandingkan F1 OOF pada fold yang sama; periksa juga variasi F1 antar-fold dan jumlah prediksi kelas 1.
2. Pilih run yang hasilnya stabil. Jika selisih F1 kecil, utamakan aturan yang lebih sederhana dan mudah dijelaskan.
3. Tulis **run terpilih, alasan, F1 OOF, threshold, nama submission, dan skor leaderboard** di bawah ini. Jangan mengganti hasil lama; tambah baris jika mencoba kombinasi baru.

**Run terpilih Main 2:** M2-06.  
**Alasan:** F1 3 fold 0,7729, hanya 0,0002 di bawah baseline raw; cleaning ini menyamakan GGG test dengan M07 dan menangani profil aktivitas yang tidak konsisten. FE menambah F1 3 fold dari 0,7717 menjadi 0,7729.  
**Model akhir:** blend 75% LightGBM + 25% CatBoost, F1 OOF 5 fold **0,7728**, threshold **0,355**, precision **0,7148**, recall **0,8411**.  
**Submission / leaderboard:** `main 2/submission_main2.csv` (6.502 baris); skor leaderboard belum diberikan pengguna.

### Jejak artefak Main 2

| Artefak | Lokasi saat ini | Status |
| --- | --- | --- |
| Notebook Main 2 | `main 2/main2.ipynb` | **0 byte di disk saat diperiksa**; kemungkinan belum tersimpan. Simpan dari IDE sebelum membuat ZIP. |
| EDA Phase 1 | `main 2/eda_phase1.md` | Sudah berada di folder Main 2 untuk arsip hari kedua. |
| Audit nilai mencurigakan | `main 2/eda_phase1_uji_lanjutan.md` | Sudah berada di folder Main 2 untuk arsip hari kedua. |
| EDA Phase 2 | `main 2/eda_phase2.md` | Sudah dibuat dari cleaning dasar M2-01 yang direkonstruksi dari CSV. |
| Diagram EDA Phase 2 | `main 2/eda_phase2_figures/` | Tujuh PNG tersimpan untuk dibuka dari laporan Markdown dan diarsipkan. |
| Sumber CELL EDA Phase 2 | `main 2/eda_phase2_analysis.py` | Dapat dijalankan dari notebook setelah CELL 3 untuk menampilkan grafik dan memperbarui laporan. |
| Catatan keputusan dan eksperimen | `CATATAN_EKSPERIMEN.md` | Log utama di folder proyek; terus diperbarui lintas hari. |
| Pipeline dan notebook pendamping | `main 2/fe_to_submission.py`; `main 2/main2_fe_submission.ipynb` | Sudah dibuat dan script dijalankan sampai submission. Notebook utama tetap perlu disimpan dari IDE. |
| Laporan FE/model dan hasil CV | `main 2/fe_model_main2.md`; `hasil_variants_main2.csv`; `hasil_models_main2.csv` | Hasil aktual tersedia, termasuk OOF dan threshold. |
| Audit sumber OULAD | `main 2/temuan_sumber_oulad.md` | Tujuh file sumber dicocokkan; ditemukan 145 kode modul train yang tampak bergeser. Belum diterapkan ke submission Main 2. |
| Submission Main 2 | `main 2/submission_main2.csv` | Sudah dibuat; 6.502 baris dan urutan ID sesuai sample submission. |

Sebelum membuat ZIP hari kedua, pastikan notebook tersimpan, laporan EDA yang sesuai sudah ikut disalin, tabel run di atas terisi berdasarkan hasil nyata, dan submission yang diarsipkan berasal dari run terpilih. Lanjutkan hari berikutnya dengan **bagian baru dalam log utama ini**.

### Temuan EDA Phase 2 dan keputusan sementara

- Fitur numerik terkuat menurut mutual information adalah `no_submission_by_cutoff` (0,1125), diikuti beberapa fitur aktivitas. Model cepat juga memberi importance sangat besar pada `no_submission_by_cutoff` (0,4169). **Tindakan:** pertahankan untuk baseline dan periksa kestabilannya pada CV; ini belum bukti leakage.
- Pada `has_score=0`, kelompok dengan aktivitas tidak konsisten memiliki risk rate 96,1% (3.666 baris), sedangkan kelompok yang konsisten 57,9% (6.380 baris). **Tindakan:** uji `activity_inconsistent` sebagai fitur, lalu bandingkan strategi raw/mask/recompute pada fold yang sama.
- Ada 18 pasangan numerik dengan korelasi Spearman absolut minimal 0,90; `avg_score` dan `median_score` bernilai 1,00. **Tindakan:** jangan menghapus fitur redundan sebelum uji CV.
- ExtraTrees pada satu holdout 80/20 menghasilkan F1 0,7458 dengan threshold 0,5 dan ROC AUC 0,8452. **Status:** hanya sanity check EDA; bukan F1 OOF, run terpilih, atau skor submission.

## Pembaruan berikutnya

Tambahkan catatan baru di bawah bagian ini saat pekerjaan berlanjut, termasuk jika masih menggunakan folder `main 2`:

| Tanggal / folder | Run atau temuan baru | Hasil yang benar-benar diperoleh | Keputusan dan alasan | Status |
| --- | --- | --- | --- | --- |
| 7 Oktober 2026 / `main 2` | CELL 3 cleaning disiapkan untuk kategori `Missing`, penyeragaman kategori, `GGG` → `M07`, dan fitur konstan. Perlakuan skor serta aktivitas disediakan sebagai variasi. | Transformasi dan pemeriksaan ID mencapai bagian ringkasan, lalu `KeyError` karena `NUMERIC_COLS` masih mencakup dua fitur konstan yang telah dihapus. Belum ada F1 atau submission. | Pada ringkasan, pakai hanya kolom numerik yang masih ada di `train_clean` dan `test_clean`; aturan cleaning tidak berubah. | Perbaikan cell diperlukan |
| 7 Oktober 2026 / `main 2` | FE, tujuh variasi cleaning, LightGBM/CatBoost 5 fold, dan tiga blend. | M2-06 F1 3 fold 0,7729; blend 75/25 F1 OOF 5 fold 0,7728, threshold 0,355. File `main 2/submission_main2.csv` dibuat. | Pilih M2-06 karena hampir sama dengan baseline raw dan menyamakan GGG test; pilih blend dengan F1 OOF 5 fold tertinggi. | Selesai; leaderboard menunggu pengguna |
| 8 Oktober 2026 / audit sumber | Tujuh file OULAD di folder proyek dibandingkan dengan train/test. | `studentInfo.csv` memiliki 10 nama kolom identik dan 32.588/32.588 baris cocok sebagai multiset pada tujuh kolom stabil setelah pemetaan kode. Ada 372 test berkode GGG asli, 145 train tampak salah kode modul, dan lima baris BBB tidak ada di kompetisi. | Simpan pemetaan dan bukti di `main 2/temuan_sumber_oulad.md`. Submission Main 2 tetap tercatat sebagai hasil sebelum temuan ini; koreksi 145 kode belum diuji CV. | Temuan baru; perlu eksperimen berikutnya |
| 8 Oktober 2026 / audit skor | Distribusi target pada `has_score=0` dihitung langsung dari `train.csv`. | Dari 10.046 baris, 7.216 (71,83%) `at_risk=1` dan 2.830 (28,17%) `at_risk=0`. Sebagai pembanding, kelompok `has_score=1` memiliki 6.537/16.040 (40,75%) berisiko. Seluruh `has_score=0` memiliki `avg_score=77`. | `has_score=0` kuat berkaitan dengan risiko, tetapi bukan aturan target pasti. Pertahankan indikator saat membandingkan imputasi skor melalui CV. | Bukti dicatat; imputasi lanjutan belum diuji |
| 8 Oktober 2026 / skor leaderboard | Submission Main 2 dari blend M2-06 dikirim ke Kaggle. | Skor leaderboard **0,77757**. Ini dibandingkan dengan F1 OOF 5 fold 0,77285; selisih leaderboard–OOF sekitar **+0,00472**. | Simpan `main 2/submission_main2.csv` sebagai baseline submission. Eksperimen berikutnya harus dibandingkan dengan skor 0,77757 dan dicatat sebagai submission baru. | Selesai; baseline leaderboard tersedia |
| 8 Oktober 2026 / statistik skor | Lima kolom selalu bernilai 77 saat `has_score=0`: `avg_score`, `median_score`, `max_score`, `min_score`, dan `score_Assessment_2`. | Pada 16.040 baris `has_score=1`, `avg_score`: mean 72,20, median 77, Q1 64, Q3 87. Menurut target: `at_risk=1` mean 65,46, median 70, Q1 55; `at_risk=0` mean 76,83, median 80, Q1 70. Rincian lima kolom disampaikan kepada pengguna. | Jangan mengganti skor berdasarkan `at_risk`: label test tidak tersedia dan aturan itu menyebabkan target leakage. Alternatif yang masih layak diuji adalah imputasi memakai fitur yang tersedia saat prediksi, dipelajari hanya pada training fold, dibandingkan dengan M2-06 yang membiarkan skor placeholder menjadi missing. | Keputusan metode; imputasi lanjutan belum dijalankan |

## 23 Oktober 2026 — Main 3 (`main 3`) — Penanganan skor 77

**Status:** Lima run training dan validasi **selesai**; submission terpilih **sudah dikirim ke Kaggle** dan hasilnya **diberikan pengguna: 0,78393**. Angka leaderboard ini berasal dari informasi pengguna, bukan dari hasil membaca ground-truth test. Main 2 tetap menjadi riwayat dan tidak ditimpa.

### Bukti → hipotesis → pilihan eksperimen

- **Bukti:** Pada `has_score=0`, sebanyak **10.046 train** dan **2.636 test** memiliki `avg_score=77`; `median_score`, `min_score`, `max_score`, dan `score_Assessment_2` juga konsisten bernilai 77 pada kelompok tersebut. Pada `has_score=1`, nilai 77 bisa menjadi skor asli. **Hipotesis:** angka 77 yang berulang di kelompok tanpa skor adalah placeholder/imputasi, belum terbukti sebagai nilai observasi.
- **Bukti risiko:** Pada train, `has_score=0` memiliki risk rate **71,83%**, sedangkan `has_score=1` **40,75%**. Ketika `has_score=0` dan `activity_inconsistent=1`, risk rate **96,10%** (3.666 baris); pada kelompok `has_score=0` konsisten **57,88%** (6.380 baris). **Pilihan:** pertahankan flag status skor dan lakukan interaksi fitur serta optimasi threshold berbasis grup, bukan imputasi berdasarkan label target.
- **Keputusan kebersihan data:** Pertahankan cleaning **M2-06** (masking skor ketika `has_score=0`, pemetaan `GGG` → `M07`, penanda aktivitas dan recompute agregat tertentu); gunakan **5-fold stratified CV, seed 42** pada semua run M3.
- **Masalah teknis yang dialami:** Saat training di Windows, LightGBM menghasilkan `OSError: access violation` pada `fit()`. Solusi teknis yang dipakai pada notebook M3 mencakup **one-hot/numerical encoding untuk LightGBM dan pembatasan thread**; kernel/env Python DSCO dikonfigurasi. Penyebab native crash tidak diisolasi secara pasti. Karena pipeline LightGBM direkonstruksi, **M3-00 tidak identik secara terverifikasi dengan Main 2**, jadi perbandingan F1 antarkeduanya tidak boleh dianggap uji satu-variabel yang sepenuhnya terkontrol.

### Definisi run yang benar-benar dieksekusi

| Run | Fitur | Strategi | Status |
| --- | ---: | --- | --- |
| M3-00 | 88 | Baseline rekonstruksi M2-06: skor ter-mask ketika `has_score=0` | Diuji 5-fold |
| M3-01 | 95 | Hybrid skor mentah dan masked sebagai fitur terpisah | Diuji 5-fold |
| M3-02 | 93 | Interaksi missingness/status skor dan aktivitas | Diuji 5-fold; dipilih |
| M3-03 | 93 | Model terpisah untuk `has_score=0` dan `has_score=1` | Diuji 5-fold |
| M3-04 | — | *Group-specific threshold optimization* | **Lapisan keputusan**, bukan model training terpisah |
| M3-05 | 95 | Estimasi skor berbasis fitur tanpa menggunakan `at_risk` dan dilatih **hanya dalam training fold** | Diuji 5-fold |

### Hasil validasi Main 3 (dari `hasil_models_main3.csv`)

| Run | Fitur | ROC AUC OOF | F1 global OOF* | F1 grup OOF* | F1 cross-fit terpilih | Decision | Threshold global | Threshold grup 0 / 1 |
| --- | ---: | ---: | ---: | ---: | ---: | --- | ---: | --- |
| M3-02 | 93 | 0.84542 | 0.77364 | 0.77440 | 0.77292 | group | 0.375 | 0.420 / 0.370 |
| M3-01 | 95 | 0.84527 | 0.77354 | 0.77411 | 0.77282 | group | 0.380 | 0.415 / 0.380 |
| M3-00 | 88 | 0.84503 | 0.77366 | 0.77403 | 0.77269 | global | 0.375 | 0.375 / 0.355 |
| M3-05 | 95 | 0.84521 | 0.77227 | 0.77282 | 0.77158 | group | 0.360 | 0.425 / 0.385 |
| M3-03 | 93 | 0.84204 | 0.77121 | 0.77156 | 0.77020 | global | 0.385 | 0.425 / 0.385 |

**Definisi metrik:** `F1 global OOF` dan `F1 grup OOF` dioptimasi langsung pada seluruh OOF sehingga **optimistis**. `F1 cross-fit terpilih` memakai threshold yang dipilih dengan menahan fold tertentu dari proses pemilihan threshold; **bukan estimasi benar-benar unbiased** karena model CV train antar-fold bertumpang tindih. Precision/recall pada `hasil_models_main3.csv` dihitung dari prediksi OOF dengan threshold pilihan keseluruhan, bukan precision/recall test Kaggle.

### Run terpilih dan skor Kaggle

- **Run:** `M3-02` (93 fitur; missingness interaction). **ROC AUC OOF 0,84542; F1 group OOF 0,77440; F1 cross-fit terpilih 0,77292**. F1 global OOF 0,77364.
- **Model:** Blend **75% LightGBM + 25% CatBoost**, 5-fold stratified CV. Implementasi LightGBM M3 telah menggunakan numeric one-hot untuk kestabilan Windows; jangan klaim hasilnya persis sama dengan Main 2.
- **Keputusan threshold:** `has_score=0` → **0,420**, `has_score=1` → **0,370**. Threshold global sebagai kandidat pembanding **0,375**; keputusan akhir M3-02 memakai threshold **grup**.
- **Diagnostik OOF dengan threshold grup terpilih:** kelompok `has_score=0` (**10.046** train) F1 **0,89247**, precision **0,87364**, recall **0,91214**; kelompok `has_score=1` (**16.040** train) F1 **0,65394**, precision **0,59684**, recall **0,72311**. Diagnostik ini adalah F1 pada label OOF dengan threshold dipilih dari OOF, **bukan skor leaderboard per grup**.
- **Submission:** `main 3/submission_m3_02_group.csv` (`id`, `at_risk`) — **6.502 baris**, seluruh ID unik, tanpa missing; prediksi `at_risk=1`: **3.813** (**58,64%**), prediksi `0`: **2.689**.
- **Skor Kaggle yang diberikan pengguna (23 Oktober 2026): F1 0,78393**. Sebagai pembanding, Main 2 `submission_main2.csv` F1 Kaggle **0,77757**; peningkatan absolut **+0,00636** (sekitar **+0,82% relatif**). Tidak ada informasi private leaderboard.
- **Perbandingan lokal dengan Main 2:** F1 OOF Main 2 **0,77285** vs F1 group OOF M3-02 **0,77440**; metode pemilihan threshold serta implementasi LightGBM berbeda, sehingga **jangan langsung menyimpulkan seluruh kenaikan itu dari fitur baru saja**.

### Keputusan setelah Main 3

**Keputusan akhir yang didukung hasil:** Simpan `M3-02` sebagai **submission publik terbaik yang diketahui** dengan F1 Kaggle **0,78393**. M3-01 dekat dalam CV, tetapi belum ada skor leaderboard yang diberikan. M3-03 (model dipisah) dan M3-05 (imputasi) kalah pada F1 cross-fit terhadap M3-02. Tidak ada bukti bahwa estimasi skor 77 meningkatkan model pada setup ini. **Tidak mengubah atau mengganti submission Main 2.**

**Alasan arah Main 4:** Kesenjangan F1 diagnostik antara `has_score=0` (**0,89247**) dan `has_score=1` (**0,65394**) mendukung **hipotesis** bahwa perbaikan kelompok scored perlu diuji lebih lanjut. Kesenjangan ini tidak menjamin model scored terpisah akan meningkatkan metrik keseluruhan. Waspadai pemilihan run berdasarkan public LB yang berulang.

### Artefak Main 3

| Artefak | Lokasi / nama | Status |
| --- | --- | --- |
| Notebook hasil eksperimen | `main.ipynb` (unggahan pengguna; output Main 3 terlihat) | Training dan evaluasi tersedia |
| Notebook rancangan Main 3 | `Main3_Eksperimen_Skor77.ipynb` | Artefak pendamping; evaluasi nyata dilihat dari `main.ipynb` dan CSV |
| Tabel hasil | `hasil_models_main3.csv` | Sudah diverifikasi dari file unggahan |
| Submission terpilih | `submission_m3_02_group.csv` | 6.502 baris; skor Kaggle disampaikan pengguna |
| Log tambahan yang dibuat notebook | `main 3/catatan_eksperimen_main3.md` | Dibuat oleh kode notebook tetapi **masih bertuliskan 'leaderboard menunggu'** jika tidak dijalankan ulang; log utama ini adalah pembaruan final yang berlaku |

## 23 Oktober 2026 — Main 4 (`main 4`) — Persiapan eksperimen scored students

**Status:** Notebook **dibuat**, tetapi **belum ada bukti run Main 4 dijalankan**, belum ada F1 OOF M4 dan belum ada submission/hasil leaderboard M4. Bagian ini hanya **rencana**; jangan salah catat sebagai eksperimen yang sudah berhasil.

**Notebook:** `Main4_DSCO_2026.ipynb` (27 cell termasuk markdown; disusun berdasarkan Main 3). File Main 3 dan Main 2 dipertahankan.

| Rencana | Hipotesis / perlakuan | Bukti hasil saat ini |
| --- | --- | --- |
| M4-00 | Reproduksi M3-02 sebagai baseline Main 4 | **Belum dijalankan**; skor referensi Kaggle M3-02 = 0,78393 |
| M4-01 | Fitur khusus mahasiswa `has_score=1` | **Belum dijalankan** |
| M4-02 | Ensemble model global dan specialist scored (bobot specialist 35%) | **Belum dijalankan** |
| M4-03 | Ensemble model global dan specialist scored (bobot specialist 65%) | **Belum dijalankan** |
| M4-04 | Analisis dan tuning threshold global/per-grup berbasis OOF | **Belum dijalankan** |

**Evaluasi rencana:** gunakan 5-fold stratified CV/seed 42 yang konsisten, simpan F1 global/grup OOF, cross-fit, AUC, precision, recall dan threshold; evaluasi kesesuaian reproduksi baseline M3-02 sebelum mengklaim improvement. Skor leaderboard **hanya** diisi setelah pengguna memberikan hasil Kaggle. Jika ada submission baru, catat nama file dan jumlah prediksi positif/negatif; **jangan menimpa** submission Main 2/3.

### Rekap keputusan terakhir (23 Oktober 2026)

| Indikator | Main 2 | Main 3 terbaik | Main 4 |
| --- | --- | --- | --- |
| Run | M2-06, blend 75/25 | **M3-02, blend 75/25** | Belum dipilih |
| F1 OOF tercatat | **0,77285** (5-fold) | **0,77440** (group-optimized; cross-fit **0,77292**) | — |
| ROC AUC OOF | **0,84542** (hasil `hasil_models_main2.csv`) | **0,84542** | — |
| Kaggle F1 | **0,77757** | **0,78393** | — |
| Status | Arsip baseline | **Terbaik sementara berdasarkan public LB yang dilaporkan** | Siap diuji, hasil belum ada |

**Pembaruan log ini bersifat append-only untuk riwayat eksperimen:** keterangan lama seperti “leaderboard menunggu” dibaca sebagai **status saat itu**, bukan status terbaru. Bagian 23 Oktober 2026 dan tabel rekap terakhir merupakan sumber status terkini.

---

## 23 Oktober 2026 — Main 4 (`main 4`) — Hasil aktual **setelah** catatan persiapan

**Status: SELESAI.** Bagian “Main 4 — Persiapan eksperimen scored students” di atas adalah snapshot sebelum run dijalankan; bagian ini memperbarui status **tanpa menghapus sejarah rencana**. Bukti lokal: `hasil_models_main4.csv` dan notebook `Main4_DSCO_2026.ipynb`. Bukti Kaggle berasal dari nilai yang pengguna berikan langsung.

### Bukti → metode → hasil → keputusan

- **Bukti/hipotesis:** pada Main 3, F1 diagnostik `has_score=1` sekitar **0,65394**, jauh di bawah kelompok `has_score=0` (sekitar **0,89247**). Hipotesis: pembelajaran khusus mahasiswa dengan nilai asli dapat memperbaiki prediksi kelompok scored.
- **Metode:** model global `M3-02` tetap dipakai. Tambahkan scored-specific feature engineering (`M4-01`) dan model spesialis yang **hanya dilatih pada `has_score=1`** dalam setiap training fold; untuk `has_score=0`, prediksi tetap dari model global. `M4-02` memberi bobot **35%** pada spesialis, `M4-03` memberi bobot **65%** pada spesialis. Semua memakai 5-fold CV dengan split yang sebanding.
- **Evaluasi:** bandingkan F1 cross-fit (pemilihan threshold lintas fold), F1 OOF yang dihitung dengan threshold tetap Main 3, ROC AUC OOF, dan hasil submission. Jangan menganggap optimasi threshold atas OOF sebagai estimasi unbiased.

### Hasil validasi lokal (angka persis dari `hasil_models_main4.csv`)

| Run | ROC AUC OOF | F1 cross-fit terbaik | F1 fixed M3 cutoffs | Keputusan threshold dari CV | Threshold global | Threshold grup 0 / 1 |
| --- | ---: | ---: | ---: | --- | ---: | --- |
| M4-00 — reproduce M3-02 | 0,845422 | 0,772923 | 0,774403 | group | 0,375 | 0,420 / 0,370 |
| M4-01 — scored FE | 0,845784 | 0,774202 | 0,774611 | group | 0,395 | 0,400 / 0,380 |
| M4-02 — 35% scored specialist | 0,845788 | 0,774879 | **0,775618** | group | 0,375 | 0,420 / 0,365 |
| **M4-03 — 65% scored specialist** | 0,845603 | **0,775519** | 0,775320 | **global** | **0,375** | 0,420 / 0,375 |

`F1 fixed M3 cutoffs` memakai threshold M3 yang sudah ditetapkan (**`has_score=0: 0,420`, `has_score=1: 0,370`**), bukan threshold yang dituning per M4. F1 cross-fit tertinggi dimiliki `M4-03`, sedangkan skor fixed tertinggi `M4-02`. Semua angka pada tabel adalah evaluasi lokal, **bukan nilai Kaggle**.

### Submission dan keputusan

| Urutan | Run / file | Konfigurasi submission | F1 Kaggle | Keputusan |
| --- | --- | --- | ---: | --- |
| 1 | `M4-02` — `submission_m4_02_fixed_m3.csv` | 35% spesialis; threshold grup **0,420/0,370** | **0,78317** | Turun dari M3-02 (0,78393); bukan champion |
| 2 | **`M4-03` — `submission_m4_03_tuned.csv`** | **65% spesialis** untuk scored; **threshold grup aktual 0,420/0,375** (dikoreksi hasil audit Main 6–7) | **0,78502** | **CHAMPION public LB baru**; +0,00109 vs Main 3; +0,00745 vs Main 2 |

**Koreksi yang dipastikan setelah Main 6–7:** label `submission_m4_03_tuned.csv` identik dengan reproduksi M6-00 dan M7-00 (0 dari 6.502 label berbeda), yaitu **threshold grup 0,420/0,375**. Tabel hasil M4-03 memang mencatat *decision = global* karena F1 cross-fit global 0,775519 sedikit di atas cross-fit grup 0,775194; namun **kode ekspor menggunakan threshold grup**. F1 OOF dengan grup tetap adalah **0,775934**. Dengan demikian, atribusi selisih M4 vs M5 hanya pada CPU/GPU tidak sah.

**Keputusan:** simpan `submission_m4_03_tuned.csv` sebagai submission terbaik yang diketahui. Jangan mengganti file champion dengan hasil yang hanya lebih tinggi pada satu metrik lokal. **Catatan kausal:** antara dua submission M4 yang diuji, bobot spesialis **dan** threshold berubah sekaligus; hasil tidak bisa diklaim sebagai efek bobot saja atau threshold saja. Tidak ada hasil private LB yang dicatat.

**Artefak:** `Main4_DSCO_2026.ipynb`, `hasil_models_main4.csv`, delapan file `submission_m4_00/01/02/03_{fixed_m3,tuned}.csv` disebut pengguna melalui screenshot folder. Hanya dua submission di tabel atas yang diketahui telah dinilai Kaggle.

## 23 Oktober 2026 — Audit tambahan: nilai `77` dan reliabilitas aktivitas (pra-Main 5)

### Bukti

- Pada **10.046 train** `has_score=0`, skor `avg_score=77` seragam; pada kelompok `has_score=1`, 77 masih dapat menjadi skor riil. **Hipotesis kuat, bukan fakta asal-usul data:** 77 pada `has_score=0` adalah nilai pengisi. Cleaning terpilih tetap me-*mask* kolom skor relevan menjadi `NaN` pada `has_score=0`; flag `has_score` tetap dipertahankan.
- Audit variasi non-skor pada `has_score=0`: **50 kolom kandidat**, **35** lolos kriteria variasi sederhana, **15** di antaranya memiliki lebih dari 100 nilai unik. Banyak nilai unik **tidak otomatis berarti** fitur informatif atau tepercaya.
- Dari 10.046 mahasiswa tanpa skor, **6.380** memiliki profil aktivitas konsisten, sedangkan **3.666** memiliki profil aktivitas tidak konsisten. Pada **seluruh 3.666** baris: `interaction_volume=182`, `week1_interactions=36`, `week4_interactions=28`, `active_days=10` (masing-masing **1 nilai unik**). Jumlah empat minggu 36+31+46+28=141, berbeda dari volume 182. Kolom aktivitas ini tidak dapat membedakan individu dalam subkelompok tersebut.
- Kolom yang **masih bervariasi** pada kelompok anomali: `registration_days_from_start` **275** nilai unik; `studied_credits` **39**; `region` **13**; `code_module` **7**; `highest_education` **5**; dan `no_submission_by_cutoff` **2**. Kode `region2` yang belum dinormalisasi pada pemeriksaan mentah bukan kategori wilayah baru.
- Pada kelompok konsisten vs anomali, `no_submission_by_cutoff=1`: **2.669/6.380** (41,83%) vs **3.045/3.666** (83,06%). Ini asosiasi observasional; audit ketersediaan fitur pada cutoff masih penting untuk mencegah leakage.
- Audit mendalam terakhir: **35** fitur diperiksa, **5** memenuhi kriteria label *variable-in-inconsistent-group*, **21** diberi flag *suspicious/near-constant*, **26** lolos penyaringan kandidat kelompok konsisten. Angka-angka adalah hitungan berdasarkan **aturan audit**, bukan bukti fitur yang tersisa bebas placeholder.

### Keputusan metodologis

- **Jangan** mengganti 77 dengan 0 atau mengisi skor berdasarkan `at_risk` (target leakage). `has_score=0` tidak berarti pasti `at_risk=1`.
- **Rencana diuji:** (A) *reliability-aware score imputation* hanya untuk mahasiswa `has_score=0` dengan aktivitas konsisten, sementara skor kelompok aktivitas anomali tetap missing; (B) spesialis dan/atau threshold untuk tiga segmen: tanpa skor-konsisten, tanpa skor-anomali, dan memiliki skor.
- Model regresi imputasi harus dilatih hanya pada **training fold** dan dievaluasi pada data yang benar-benar memiliki skor; estimasi skor mahasiswa belum dinilai **bukan skor yang benar-benar teramati**. Peningkatan F1 belum terbukti pada tahap audit ini.

**Jejak audit:** output cell `audit_score_imputation_main5.csv` dilaporkan pengguna tersimpan di folder lokal `main 4/` (file CSV itu belum diunggah ke percakapan); angka audit yang dicatat di sini berasal dari output cell yang pengguna kirim.

## 24 Oktober 2026 — Main 5 GPU (`main 5 GPU`) — Hasil aktual

**Status: enam run CV selesai (M5-00 s.d. M5-05); satu submission Kaggle yang diketahui, yaitu reproduksi baseline `M5-00`.** Bukti lokal: `hasil_models_main5.csv` yang diunggah pengguna; rancangan/implementasi: `Main5_DSCO_2026_GPU.ipynb`. Data leaderboard dari pengguna.

### Setup eksperimen

- GPU terdeteksi pada laptop pengguna: **NVIDIA RTX 4060 Laptop (dedicated 8 GB VRAM)**. Dalam notebook M5 GPU, **CatBoost classifier/regressor menggunakan GPU**; **LightGBM tetap CPU** setelah pengalaman crash Windows di Main 3. Hasil perangkat di CSV: `catboost_device = GPU` pada semua run.
- M5-00 mereproduksi logika **M4-03 champion** dengan backend baru. `M5-01` hanya mencoba threshold 3 kelompok atas **probabilitas yang sama** dengan M5-00. `M5-02/M5-03` menggabungkan model spesialis untuk kelompok tanpa skor (35%/65%). `M5-04` menguji imputasi skor berbasis reliabilitas; `M5-05` menggabungkan imputasi dengan spesialis. Imputasi dilatih per training fold; kelompok tanpa skor dengan aktivitas anomali tidak diisi skor artifisial.
- Pembagian tiga kelompok ditentukan berdasarkan aktivitas **mentah sebelum** rekalkulasi agregat M2-06. Evaluasi menggunakan 5-fold dan berbagai threshold global/dua/tiga kelompok; bandingkan dengan run GPU **M5-00** agar efek metode tak tercampur perubahan backend.

### Hasil validasi lokal Main 5 (dari `hasil_models_main5.csv`)

| Run | Strategi | ROC AUC OOF | F1 cross-fit terbaik | Threshold global | F1 pada threshold tetap 0,375 | Kaggle F1 |
| --- | --- | ---: | ---: | ---: | ---: | --- |
| **M5-00** | Reproduksi M4-03 dengan GPU | 0,845464 | **0,775153** | 0,380 | 0,774674 | **0,78460** |
| M5-01 | Threshold 3 grup atas probabilitas M5-00 | 0,845464 | **0,775153** | 0,380 | 0,774674 | **Belum ada** |
| M5-02 | +35% no-score specialist | **0,845606** | 0,774275 | 0,380 | 0,774512 | Belum ada |
| M5-03 | +65% no-score specialist | 0,845328 | 0,773751 | 0,380 | 0,773825 | Belum ada |
| M5-04 | Reliability-aware score imputation | 0,845109 | 0,774307 | 0,390 | 0,773370 | Belum ada |
| M5-05 | Imputation + specialist | 0,845467 | 0,774127 | 0,390 | 0,773930 | Belum ada |

**Perhatian pada M5-01:** F1 cross-fit **terbaik** sama dengan M5-00 karena penilaian memilih threshold **global**. Dalam CSV, F1 cross-fit **3 kelompok** untuk keduanya **0,774039**, jadi tidak ada bukti peningkatan dari tiga threshold pada validasi ini. `M5-02` memiliki **AUC OOF tertinggi**, tetapi F1 cross-fit **lebih rendah** dibanding M5-00 sebesar **0,000878**. `M5-04` (imputasi) juga di bawah baseline sebesar **0,000846**. Belum ada bukti bahwa imputasi berhasil meningkatkan F1 klasifikasi.

### Submission Kaggle dan perbandingan dengan champion

- **File yang dikirim:** `submission_m5_00_champion_reproduction.csv` (diidentifikasi dari screenshot submission Kaggle pengguna). **Skor Kaggle yang dikonfirmasi: 0,78460** pada **24 Oktober 2026**.
- **Champion sebelumnya:** `submission_m4_03_tuned.csv` Kaggle F1 **0,78502**. Selisih M5-00 − M4-03 = **−0,00042**. Ini reproduksi dengan pipeline/backend CatBoost GPU, **bukan** submission model imputasi ataupun spesialis tanpa skor.
- **Interpretasi hati-hati:** M5-00 bukan replikasi bitwise model M4-03; backend GPU dan mungkin detail pipeline dapat menyebabkan variasi prediksi. Perubahan −0,00042 **tidak membuktikan** GPU menyebabkan penurunan, maupun bahwa ide M5-01–M5-05 gagal di leaderboard.
- **Keputusan:** **pertahankan M4-03 tuned sebagai champion public leaderboard (0,78502).** Hasil M5-01–M5-05 sementara hanya lokal. Tidak ada skor Kaggle bagi kelima run tersebut dan tidak ada skor private leaderboard.

### Arahan eksperimen selanjutnya (rencana, belum dijalankan)

1. Jika ingin membandingkan secara kausal, jalankan reproduksi M4-03 pada CPU yang sama lalu ubah **satu hal per run**: konfigurasi threshold, berat spesialis, atau metode imputasi; jangan mencampur pergantian CPU/GPU dengan perubahan fitur.
2. Uji model regresi imputasi dengan evaluasi skor pada fold mahasiswa berlabel skor asli, serta pemeriksaan distribution shift untuk `has_score=0`. Hindari memaksa imputasi pada kelompok aktivitas placeholder.
3. Prioritaskan **F1 cross-fit dan kestabilan fold**; jangan memilih model semata-mata dari fluktuasi public leaderboard. Audit potensi leakage fitur pada cutoff (mis. `no_submission_by_cutoff`).

### Jejak artefak dan status akhir 24 Oktober 2026

| Artefak | Status |
| --- | --- |
| `CATATAN_EKSPERIMEN.md` | **Log utama ini; berisi riwayat Main 2–Main 5** |
| `Main4_DSCO_2026.ipynb`, `hasil_models_main4.csv` | Notebook dan hasil validasi Main 4 tersedia |
| `submission_m4_03_tuned.csv` | **Champion Kaggle: 0,78502**, sebagaimana dilaporkan pengguna; tidak ada file submission M4 yang diunggah |
| `Main5_DSCO_2026_GPU.ipynb`, `hasil_models_main5.csv` | Notebook GPU dan hasil validasi enam run tersedia |
| `submission_m5_00_champion_reproduction.csv` | Kaggle **0,78460** yang diberikan pengguna; file submission itu sendiri tidak diunggah |
| `M5-01`–`M5-05` | CV selesai; skor Kaggle **belum disampaikan**, jangan dikira nol |
| `audit_score_imputation_main5.csv` | Dibuat dan tersimpan lokal menurut pengguna; hasil audit disampaikan melalui output cell |

**Ringkasan final 24 Oktober 2026:** **M4-03 tuned = champion public leaderboard 0,78502**; **M5-00 GPU = 0,78460**, sedangkan M5-01–M5-05 belum punya hasil leaderboard. Semua catatan Main 2 dan Main 3 tetap ada sebagai riwayat; status historis “belum dijalankan” untuk Main 4 di atas telah digantikan secara kronologis oleh hasil aktual pada bagian ini.



---

## 24 Oktober 2026 — Main 6 (`main 6`) — Assessment-aware modeling

**Status: selesai diuji secara lokal (5 run), belum ada submission Kaggle Main 6 yang dikonfirmasi.** Sumber angka: `hasil_models_main6.csv`; notebook `Main6_DSCO_2026_Assessment_Aware.ipynb`; audit implementasi dan OOF oleh Astra yang dikirim pengguna pada 24 Oktober. **Semua hasil berikut OOF train (26.086 baris), bukan skor test/Kaggle.**

### Hipotesis dan perubahan terkontrol

- **M6-00:** reproduksi M4-03 CPU pada fold/fitur/parameter/bobot yang sama; threshold keputusan **grup 0,420/0,375**. Reproduksi awal menggunakan metrik lokal; audit lanjutan mengonfirmasi label submission M6-00 = champion M4-03 pada **6.502/6.502** test (0 label berbeda). Jika `reproduction_status_main6.json` yang lebih lama menyatakan belum diverifikasi, alasannya pemeriksa file tidak menelusuri ZIP Main 4, **bukan** perbedaan output.
- **M6-01:** empat flag ketersediaan/default assessment hanya pada scored specialist. Dalam audit, flag signature A1/A2 ternyata ekuivalen dengan status due yang sudah ada; informasi utama redundan.
- **M6-02:** flag M6-01 + conditional masking fitur selisih/interaksi skor **serta skor, weighted score, dan delay** pada kondisi tertentu. Efek masing-masing tidak terisolasi; hasil negatif hanya berlaku untuk **paket** ini. Belum ada bukti due=0 sama dengan skor tidak tersedia.
- **M6-03:** `NaN` numerik native pada CatBoost (bukan median filling). Implementasi berlaku pada global dan specialist.
- **M6-04:** empat fitur skor/aktivitas relatif terhadap cohort berdasarkan statistik **training fold saja**; tidak ada leakage statistik cohort yang ditemukan pada audit.

### Hasil aktual Main 6

| Run | F1 OOF dengan threshold champion tetap | Δ F1 vs M6-00 | ROC AUC OOF | Fold membaik / 5 | Kaggle F1 |
| --- | ---: | ---: | ---: | ---: | --- |
| **M6-00 — baseline CPU** | **0,775934** | — | **0,845603** | — | Tidak disubmit ulang |
| M6-01 — assessment flags | 0,774894 | −0,001040 | 0,845515 | 1/5 | Belum ada |
| M6-02 — conditional score features | 0,774688 | −0,001246 | **0,845677** | 1/5 | Belum ada |
| M6-03 — CatBoost native NaN | 0,775209 | −0,000725 | 0,845663 | 1/5 | Belum ada |
| M6-04 — cohort relative | 0,774658 | −0,001276 | 0,845375 | 0/5 | Belum ada |

F1 threshold grup tetap champion berbeda dari **F1 cross-fit global 0,775519** yang tercatat pada evaluasi M4-03; jangan mencampur kedua definisi. M6-03 merupakan alternatif terdekat tetapi masih turun pada 4/5 fold. Peningkatan AUC kecil M6-02 tidak cukup untuk meningkatkan F1.

### Error analysis champion dan lesson learned

- Confusion matrix OOF M6-00: **TP 11.291; FP 4.059; FN 2.462; TN 8.274**; precision **0,735570**, recall **0,820985**, F1 **0,775934**.
- Dari **6.521** kesalahan total, **4.935 (75,68%)** berada pada `has_score=1`. Pada kelompok `has_score=0` dengan aktivitas signature, champion memprediksi seluruh **3.666** mahasiswa positif; **143 FP, 0 FN**, F1 **0,980108**. Hal itu menjelaskan mengapa spesialisasi tambahan kelompok anomali belum menjadi prioritas.
- **6.128 dari 6.521 kesalahan** M6-00 tetap salah pada semua run M6; probabilitas run dengan champion berkorelasi **0,99790–0,99991**. Hasil lebih tepat dibaca sebagai eksperimen yang belum mengubah perilaku prediksi secara bermakna, **bukan bukti bahwa performa dataset sudah mencapai batas teoretis**.
- **80,54%** kesalahan champion berada di luar jarak probabilitas ±0,05 dari threshold grup; tuning threshold saja tidak cukup menjawab mayoritas kesalahan.
- Data assessment raw memiliki signature yang mencurigakan: `assessments_due_Assessment_1=0` bersama skor A1 **70** pada **21.464 train**, dan `assessments_due_Assessment_2=0` bersama skor A2 **77** pada **3.568 train**. **Due=0 tidak otomatis membuktikan belum submit atau belum dinilai**; asal skor perlu diverifikasi pada sumber/feature generator.

**Keputusan M6:** jangan submit M6-01–M6-04 hanya atas hasil ini. Pertahankan M4-03 sebagai champion. Jangan melanjutkan assessment masking tanpa verifikasi semantik input. Artifact: `hasil_models_main6.csv`, `Main6_DSCO_2026_Assessment_Aware.ipynb`, file OOF/group jika tersedia dalam folder lokal Main 6.

## 25 Oktober 2026 — Main 7 (`main 7`) — Multi-seed ensemble dan component diversity

**Status: tiga realisasi seed selesai, satu submission Kaggle baru dikonfirmasi pengguna.** Sumber angka: `hasil_models_main7.csv`, `hasil_diversity_main7.csv`, notebook `Main7_DSCO_2026_MultiSeed_Champion.ipynb`, dan skor leaderboard yang diberikan pengguna pada 25 Oktober.

- Pertahankan pipeline champion CPU, fold yang sama, 75% LightGBM/25% CatBoost global, 65% scored specialist, threshold 0,420/0,375. Seed model **42, 2026, 3407**; probabilitas, bukan label, dirata-rata. Tidak mengubah fitur/cleaning.
- M7-00 seed 42 direproduksi identik dengan submission M4-03 (0/6.502 label berbeda). Untuk OOF tiap seed, prediksi fold berasal dari model tanpa label fold evaluasi.

| Run | F1 OOF fixed | Δ terhadap M7-00 | ROC AUC | Average precision | Brier (lebih kecil lebih baik) | Fold membaik | Kaggle F1 |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| **M7-00 — seed 42 champion** | **0,775934** | — | 0,845603 | 0,879161 | 0,158308 | — | Reproduksi; champion **0,78502** |
| M7-01 — 2 seed (diagnostic) | 0,775164 | −0,000770 | 0,845936 | 0,879407 | 0,158117 | 2/5 | Tidak dilaporkan |
| **M7-01 — 3 seed** | **0,774825** | **−0,001109** | **0,845948** | **0,879447** | **0,158099** | **0/5** | **0,78462** |

**Submission terkonfirmasi:** `submission_m7_01_3seed.csv` memperoleh **F1 Kaggle 0,78462** (−0,00040 vs M4-03 champion 0,78502); file 2 seed tidak dilaporkan sudah disubmit. Ensemble 3 seed mengubah **349** label OOF: **156** kesalahan diperbaiki, **193** keputusan benar menjadi salah; perubahan bersih **+29 FP, +8 FN**. Meningkatnya AUC/AP/Brier tidak berarti F1 di threshold champion membaik.

### Diversity komponen (seed 42)

| Komponen dibandingkan | Korelasi probabilitas | Disagreement label | A salah/B benar | A benar/B salah |
| --- | ---: | ---: | ---: | ---: |
| Seed 42 vs 2026 (final blend) | 0,997544 | 625 | 295 | 330 |
| Seed 42 vs 3407 (final blend) | 0,997571 | 608 | 264 | 344 |
| Global LightGBM vs CatBoost | **0,982198** | 1.686 | 836 | 850 |
| Scored specialist LightGBM vs CatBoost | **0,962812** | 1.287 | 679 | 608 |

- Antarseed sangat mirip; antar-algoritme sedikit lebih beragam. Audit komponen Astra menemukan bobot specialist LightGBM/CatBoost **65/35** memberi F1 OOF eksploratif **0,776029** (champion **0,775934**), hanya **+0,000095** pada prediksi yang sama. Hasil itu **belum dijalankan sebagai run nested independen maupun dikonfirmasi Kaggle**; bootstrap deskriptif 95% untuk ΔF1 melintasi nol (sekitar −0,000472 hingga +0,000661). Jangan dicatat sebagai champion baru.
- Stacking adaptif dinilai **NO-GO** untuk submission langsung. Jika pernah diuji, membutuhkan inner OOF yang dibuat ulang di setiap outer fold; OOF global lama tidak cukup sebagai validasi meta-model bebas leakage.

**Keputusan M7:** hentikan penambahan seed; M4-03 tetap champion. Hasil ini memotivasi pergeseran riset ke audit data yang benar-benar dapat diverifikasi, bukan langsung menambah kompleksitas model.

## 29 Oktober 2026 — Main 8 — Data-centric semantic audit (`main 8 new_version`)

### M8-00 — Semantic data audit (tanpa training)

**Status audit komputasional: `COMPLETED`; status kebenaran sumber sejumlah temuan: `UNVERIFIED` atau `BLOCKED`.** Bukti langsung: `M8_00_semantic_audit.zip` (30 entri; ZIP dapat dibaca), `ringkasan_main8.md`, `audit_issue_register_main8.csv`, `audit_score_defaults_main8.csv`, `audit_rule_label_diagnostics_main8.csv`, `data_dictionary_main8.csv` dan grafik. Tiga output yang sempat hilang pada notebook Astra lama sekarang tersedia; notebook versi bersih berhasil mengekspor laporan. Tidak ada cleaning/training pada **tahap M8-00**.

| Temuan audit mentah | Train terdampak | Test terdampak | Interpretasi / status |
| --- | ---: | ---: | --- |
| `has_score=0` tetapi `avg_score=77` | **10.046** | **2.636** | Pola teramati; asal placeholder belum dibuktikan (`UNVERIFIED`) |
| Signature aktivitas lengkap 182/36/31/46/28; `active_days=10` | **3.737** | **947** | 3.666 train tanpa skor + 71 train scored; kesamaan blok teramati, keaslian nilainya belum dibuktikan |
| A1 belum due dan score A1=70 | **21.464** | **5.387** | Kandidat default, bukan bukti tidak disubmit |
| A2 belum due dan score A2=77 | **3.568** | **866** | Kandidat default, bukan bukti tidak dinilai |
| Tanpa skor tetapi `submitted_count` positif | **10.046** | **2.636** | Definisi hitungan belum jelas; jangan mengganti ke nol |
| Tanpa skor tetapi `no_submission_by_cutoff=0` | **4.332** | **1.149** | Kondisi berbeda; membutuhkan definisi cutoff |
| Tanpa skor tetapi completion positif | **9** | **4** | Anomali kecil; jangan mengubah label atau rumus otomatis |
| Kategori `GGG` hanya di test | 0 | **372** | Pemetaan `GGG → M07` digunakan historis pada champion, **belum terverifikasi independen** dari bukti identitas terbaru |
| Dugaan sekitar 145 kode modul train salah | **Belum diketahui** | Belum diketahui | Dugaan historis; belum ada tabel mapping unik yang tersedia pada audit Main 8 |

- Raw dataset: **26.086 train (64 kolom)** dan **6.502 test (63 kolom)**; sel `NaN` asli **0**, tetapi ini tidak membuktikan seluruh fitur berisi observasi asli.
- `has_score=0` dibedakan menurut signature dan `no_submission_by_cutoff`: non-signature/no_submission=0: **3.711**, risk **35,84%**; non-signature/1: **2.669**, **88,54%**; signature/0: **621**, **83,09%**; signature/1: **3.045**, **98,75%**. Semua risk rate berasal dari **train saja**, bukan test.
- Source notebook menunjukkan **26 fitur turunan aktivitas** yang perlu ditangani jika melakukan full masking. Jangan cuma mask `interaction_volume` sementara tren, recency, density, dan skor×aktivitas tetap mengandung nilai mentah.
- Status keputusan setelah audit: **M8-01 (mask fitur selisih skor) BLOCKED** sampai availability/provenance skor dapat dibuktikan; **M8-03 (koreksi modul) UNVERIFIED**. M8-02 belum dijalankan pada file audit M8-00, lalu diuji secara terpisah berikutnya.

### M8-BASE dan M8-02A — Recompute versus raw activity

**Tanggal:** 29 Oktober 2026. Sumber angka hasil training: output notebook yang pengguna kirim pada hari yang sama; belum ada CSV terpisah M8-02A dalam berkas unggahan yang diverifikasi di sesi ini. Keduanya menggunakan champion CPU, fold sama, seed sama, 75/25 global, 65% scored specialist, threshold grup tetap **0,420/0,375**. M8-BASE direproduksi: **0/6.502 label test berbeda**, OOF F1 **0,775934**, ROC AUC **0,845603**, status `passed=True`.

| Run | Perlakuan kelompok signature | F1 OOF fixed | Δ vs baseline | ROC AUC | Precision | Recall | FP | FN | Fold membaik |
| --- | --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| **M8-BASE** | Recompute agregat tertentu seperti champion (volume 182→141) | **0,775934** | — | **0,845603** | **0,735570** | **0,820985** | **4.059** | **2.462** | — |
| M8-02A | Pertahankan raw total 182; flag yang sama; hitung ulang turunan dari data raw | **0,772787** | **−0,003147** | 0,845417 | 0,732249 | 0,818076 | 4.114 | 2.502 | **0/5** |

M8-02A mengubah **539** label OOF: **222** kesalahan diperbaiki, **317** prediksi benar menjadi salah; selisih bersih **+55 FP, +40 FN**. Kelompok `no_score_signature` (3.666 train) **0 label berubah** meskipun sebagian data input training diubah; perubahan preprocessing dapat memengaruhi struktur pohon dan prediksi mahasiswa di luar signature. Seluruh lima fold M8-02A turun (ΔF1: −0,003133; −0,002461; −0,000702; −0,003156; −0,006284).

**Keputusan:** M8-02A **tidak lolos screening**; tidak dibuat submission. Ini membuktikan bahwa raw 182 **tidak meningkatkan F1 lokal pada pipeline tersebut**, **bukan** bahwa 141 merupakan jumlah aktivitas yang benar secara faktual.

### M8-02B — Full masking pada signature aktivitas

**Tanggal:** 29 Oktober 2026. Sumber aktual: ZIP `outputs_m8_02b.zip`, berisi `hasil_models_m8_02b.csv`, `hasil_folds_m8_02b.csv`, `hasil_groups_m8_02b.csv`, `hasil_transisi_m8_02b.csv`, OOF/test probabilities, decision JSON, dan ringkasan. **Checkpoint baseline M8-BASE sebelumnya dibaca, lalu hanya varian B dilatih (20 model fitting), bukan 40 model baru.**

| Run | Perlakuan kelompok signature | F1 OOF fixed | Δ vs baseline | ROC AUC | Precision | Recall | FP | FN | Fold membaik |
| --- | --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| **M8-BASE** | Cleaning champion | **0,775934** | — | **0,845603** | **0,735570** | **0,820985** | **4.059** | **2.462** | — |
| M8-02B | Mask seluruh blok aktivitas signature dan 26 turunan; pertahankan flag reliabilitas | **0,774382** | **−0,001552** | 0,845320 | 0,733715 | 0,819821 | 4.092 | 2.478 | **1/5** |

- M8-02B mengubah **605** label OOF: **278 salah→benar** versus **327 benar→salah**; selisih bersih **+33 FP, +16 FN**. Pada kelompok tanpa skor–signature (**3.666 train**) tidak ada perubahan label; F1 tetap **0,980108**.
- F1 M8-02B turun pada 4 dari 5 fold; satu fold naik **+0,002059**. Perbandingan lokal keseluruhan masih negatif.
- Data kelompok: `no_score_other` F1 **0,809152→0,805068**; `scored_signature` **0,717949→0,707317** (n=71); `scored_other` **0,655832→0,654849**. Perubahan input lokal pada baris signature dapat mengubah model dan prediksi baris non-signature.
- Screening dalam `candidate_decision_m8_02b.json` **`passed_screening=false`**. Tidak ada submission Kaggle M8-02B. Skor untuk M8-02A maupun M8-02B **tidak boleh dicatat sebagai skor leaderboard**.

### Perbandingan final varian aktivitas Main 8

| Strategi aktivitas | Run | F1 OOF fixed champion | ROC AUC | Keputusan |
| --- | --- | ---: | ---: | --- |
| Recompute agregat tertentu (baseline) | **M8-BASE / M4-03 CPU** | **0,775934** | **0,845603** | **Tetap dipakai** |
| Pertahankan raw | M8-02A | 0,772787 | 0,845417 | Tidak lolos; 0/5 fold membaik |
| Full activity masking | M8-02B | 0,774382 | 0,845320 | Tidak lolos; 1/5 fold membaik |

**Kesimpulan:** kedua perubahan representasi aktivitas **kalah pada F1 OOF**, meskipun itu tidak memverifikasi kebenaran faktual angka 141 ataupun 182. **Jangan submit kedua varian**. Fokus berikutnya adalah **memverifikasi provenance assessment/submission/cutoff** (M8-01) atau **identitas modul dari sumber** (M8-03), tanpa membuat koreksi otomatis ketika sumber tidak tersedia. Aspek yang tersisa dapat memerlukan data dictionary, feature-generator, aturan kompetisi external data, dan mapping source yang tepercaya.

## 29 Oktober 2026 — Rekonsiliasi dan status terkini seluruh proyek

### Champion, leaderboard, dan metrik lokal yang benar

- **Champion Kaggle yang diketahui tetap `M4-03` (`submission_m4_03_tuned.csv`), F1 0,78502.** M5-00 GPU: **0,78460**; M7-01 3 seed: **0,78462**. Tidak ada skor Kaggle baru yang dilaporkan untuk M6, M8, M5-01–05, atau M7-01 2 seed.
- **Baseline OOF yang terverifikasi pada M6–M8:** F1 **0,775934** dengan **threshold grup** 0,420/0,375; ROC AUC **0,845603**; TP **11.291**, FP **4.059**, FN **2.462**, TN **8.274**. **F1 cross-fit global M4-03 = 0,775519** adalah *metrik berbeda* dari F1 OOF fixed grup dan tidak boleh dipertukarkan.
- Persentase dan angka F1 pada train OOF merupakan bukti lokal; **bukan private leaderboard**. Perbandingan antar-run bersifat post-hoc pada dataset yang telah berkali-kali dilihat sehingga selisih kecil mungkin optimistis; pertahankan cutoff champion agar efek cleaning dapat diisolasi.
- **Riwayat tabel persiapan Main 4 yang menulis “belum dijalankan” dan catatan status 24 Oktober** adalah snapshot kronologis. Hasil run setelahnya dan ringkasan 29 Oktober di bagian ini merupakan status terkini.

### Catatan keputusan yang tidak boleh tertukar

| Topik | Temuan faktual | Status keputusan |
| --- | --- | --- |
| Skor 77 dan A1=70/A2=77 | Pola nilai default teramati, asal-usul belum terverifikasi dari generator | Masking skor `has_score=0` bagian cleaning champion; masking assessment tambahan **belum disetujui** |
| Aktivitas signature 182 vs 141 | Nilai berulang dapat dideteksi; raw dan full masking diuji terkontrol | M8-02A dan M8-02B gagal menaikkan F1 lokal; recompute champion tetap acuan |
| `GGG→M07` | Dipakai pada Main 2–M8, ada bukti historis korespondensi dengan OULAD tetapi audit M8 terbaru tidak memvalidasi identitas dengan mapping unik | **Jangan ubah** mapping champion tanpa verifikasi sumber; tandai provenance sebagai belum tuntas |
| Dugaan 145 kode modul train | Klaim historis dari audit sumber, belum direproduksi ulang dengan mapping unik dalam arsip audit M8 | **UNVERIFIED** pada M8-00; jangan koreksi otomatis berdasarkan statistik/risk rate |
| M8-01 | Audit due dan skor, 15.215 scored train berpotensi membandingkan skor teramati/default; due bukan bukti submission | `BLOCKED` sampai ada bukti availability sumber |
| M8-03 | Koreksi identitas modul | `UNVERIFIED` sampai ada matching sumber non-target yang unik dan diizinkan |
| Multi-seed / stacking | Ensemble 3 seed F1 lebih rendah; complementarity komponen ada tetapi tidak berarti gate adaptif dapat dipelajari | Tidak diprioritaskan untuk submission berikutnya |

### Prioritas kerja berikutnya

1. **Data-first provenance audit:** cari dokumentasi definisi `has_score`, `submitted_count`, `completion_rate`, due, delay, weighted score, dan `no_submission_by_cutoff`; cocokkan timestamp pembentukan fitur terhadap cutoff. Bedakan *due belum terjadi*, *belum submit*, *belum dinilai*, dan *skor tidak tersedia*.
2. **Jika sumber valid:** buat perubahan dataset kecil yang dapat dibuktikan, uji satu per run dengan M4-03 CPU/fold/seed/threshold tetap; laporkan F1, precision/recall, AUC, FP/FN, transisi berpasangan, serta efek cohort besar. Kalau tidak ada bukti, pertahankan status `BLOCKED`/`UNVERIFIED`.
3. **Jangan submit M8-02A/B:** tidak ada dasar OOF untuk mengganti champion. Jangan gunakan Kaggle publik sebagai satu-satunya instrumen seleksi model.

### Sumber yang dipakai untuk memperbarui log pada 29 Oktober

- **Berkas lama:** `CATATAN_EKSPERIMEN(3).md` (311 baris, berisi Main 2–5), beserta `hasil_models_main4.csv`, `hasil_models_main5.csv`.
- **Main 6:** `hasil_models_main6.csv` dan review audit/error analysis Astra yang dibagikan pengguna.
- **Main 7:** `hasil_models_main7.csv`, `hasil_diversity_main7.csv`, serta skor Kaggle 0,78462 yang dilaporkan pengguna.
- **Main 8 audit:** `M8_00_semantic_audit.zip` (laporan/tabel mentah yang dibaca langsung).
- **Main 8 eksperimen aktivitas:** output M8-02A yang dikirim pengguna sebagai tabel dalam chat, dan `outputs_m8_02b.zip` untuk angka M8-02B.

**Status final per 29 Oktober 2026: champion M4-03 Kaggle F1 0,78502; audit data Main 8 selesai; raw activity dan full masking gagal mengungguli baseline lokal. Tidak ada submission Main 8 yang disarankan.**
