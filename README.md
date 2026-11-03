# DSCO 2026 — Student Risk Prediction

Analisis dan pemodelan untuk memprediksi mahasiswa yang berisiko (`at_risk`) menggunakan data aktivitas pembelajaran dan nilai assessment.

## Ringkasan

- Target: `at_risk`
- Metrik evaluasi: binary F1
- Data train: 26.086 baris, 62 fitur awal
- Data test: 6.502 baris
- Model terpilih: **M3-02**
- OOF F1: **0.774403**
- OOF ROC-AUC: **0.845422**
- Threshold grup: `0.42` untuk mahasiswa tanpa skor dan `0.37` untuk mahasiswa dengan skor

## Isi repository

| File/folder | Keterangan |
|---|---|
| `main.ipynb` | Notebook utama analisis dan pemodelan |
| `CATATAN_EKSPERIMEN.md` | Catatan eksperimen dan keputusan modeling |
| `main3_full_analysis_outputs/` | Laporan, hasil evaluasi, analisis error, figure, dan file submission |
| `main3_full_analysis_outputs/LAPORAN_MAIN3_LENGKAP.md` | Laporan lengkap Main 3 |
| `main3_full_analysis_outputs/submission_m3_02_group_rerun.csv` | Hasil prediksi model M3-02 |

## Pendekatan

Pipeline Main 3 mencakup:

1. Eksplorasi distribusi target, skor, aktivitas, dan pergeseran train-test.
2. Normalisasi fitur historis dan masking nilai skor ketika `has_score = 0`.
3. Rekonstruksi agregat skor yang tidak konsisten.
4. Penambahan fitur interaksi missingness dengan aktivitas dan volume pembelajaran.
5. Evaluasi menggunakan out-of-fold predictions dan threshold berbeda berdasarkan status skor.
6. Analisis false positive, false negative, serta performa per grup.

## Hasil utama

M3-02 menggunakan 93 fitur dan memberikan hasil rerun berikut:

| Metrik | Nilai |
|---|---:|
| ROC-AUC OOF | 0.845422 |
| F1 global OOF | 0.773641 |
| F1 group OOF | 0.774403 |
| Precision | 0.731785 |
| Recall | 0.822293 |

Lihat [laporan lengkap](main3_full_analysis_outputs/LAPORAN_MAIN3_LENGKAP.md) untuk tabel fold, EDA, error analysis, dan visualisasi.

## Reproduksi

Notebook dapat dijalankan dengan Python 3.10.11 dan dependensi utama berikut:

```text
numpy==2.2.6
pandas==2.3.3
scikit-learn==1.7.2
lightgbm==4.7.0
catboost==1.2.10
```

File data input yang digunakan adalah `train.csv`, `test.csv`, dan `sample_submission.csv`. Dataset tersebut tidak disertakan dalam repository ini; letakkan file pada root project sebelum menjalankan notebook.

## Catatan

Nilai Kaggle historis yang tercantum di laporan merupakan hasil leaderboard eksternal, bukan metrik yang dihitung dari label test di notebook. Threshold yang dipilih dari seluruh OOF juga dapat sedikit optimistis karena belum menggunakan nested validation.

