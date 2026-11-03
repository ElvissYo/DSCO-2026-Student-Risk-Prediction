# Uji lanjutan temuan mencurigakan — EDA Phase 1

Data asli tidak diubah oleh cell ini.

- **Skor:** 10,046 baris train memiliki `has_score=0`. `avg_score` pada kelompok ini mempunyai 1 nilai unik.

- **Aktivitas:** 3,737 baris train mempunyai volume yang tidak cocok dengan jumlah empat minggu.

- **Profil berulang:** profil interaksi yang paling sering muncul pada 3,737 baris train bermasalah.

- **Keputusan sementara:** nilai skor tetap dan agregat aktivitas yang tidak cocok adalah kandidat nilai pengisi. Jangan ubah sebelum membandingkan strategi cleaning dengan validasi F1 pada fold train yang sama.

- **Day 28:** perbedaan dengan deskripsi Day 0–27 perlu dicatat, tetapi barisnya belum boleh otomatis dihapus.

## Nilai skor saat `has_score=0`

| dataset | kolom | baris_has_score_0 | nilai_unik_saat_has_score_0 | nilai_tersering | persen_nilai_tersering | persen_nilai_ini_saat_has_score_1 |
| --- | --- | --- | --- | --- | --- | --- |
| train | avg_score | 10046 | 1 | 77.00 | 100.00 | 1.22 |
| train | median_score | 10046 | 1 | 77.00 | 100.00 | 1.22 |
| train | max_score | 10046 | 1 | 77.00 | 100.00 | 1.34 |
| train | min_score | 10046 | 1 | 77.00 | 100.00 | 1.38 |
| train | score_std | 10046 | 1 | 0.00 | 100.00 | 95.68 |
| train | weighted_score_total | 10046 | 2 | 4.25 | 99.91 | 1.81 |
| train | score_trend | 10046 | 1 | 0.00 | 100.00 | 95.57 |
| train | score_Assessment_2 | 10046 | 1 | 77.00 | 100.00 | 18.14 |
| train | weighted_score_Assessment_2 | 10046 | 2 | 6.00 | 99.91 | 17.30 |
| train | score_Assessment_1 | 10046 | 1 | 70.00 | 100.00 | 80.01 |
| train | weighted_score_Assessment_1 | 10046 | 1 | 1.40 | 100.00 | 80.01 |
| test | avg_score | 2636 | 1 | 77.00 | 100.00 | 1.16 |
| test | median_score | 2636 | 1 | 77.00 | 100.00 | 1.16 |
| test | max_score | 2636 | 1 | 77.00 | 100.00 | 1.29 |
| test | min_score | 2636 | 1 | 77.00 | 100.00 | 1.22 |
| test | score_std | 2636 | 1 | 0.00 | 100.00 | 95.71 |
| test | weighted_score_total | 2636 | 2 | 4.25 | 99.85 | 1.53 |
| test | score_trend | 2636 | 1 | 0.00 | 100.00 | 95.58 |
| test | score_Assessment_2 | 2636 | 1 | 77.00 | 100.00 | 17.46 |
| test | weighted_score_Assessment_2 | 2636 | 2 | 6.00 | 99.85 | 16.63 |
| test | score_Assessment_1 | 2636 | 1 | 70.00 | 100.00 | 80.57 |
| test | weighted_score_Assessment_1 | 2636 | 1 | 1.40 | 100.00 | 80.57 |

## Konsistensi aktivitas

| dataset | pemeriksaan | jumlah_baris | persen | juga_bermasalah_pada_volume |
| --- | --- | --- | --- | --- |
| train | volume ≠ jumlah minggu 1–4 | 3737 | 14.33 | 3737 |
| train | early ≠ minggu 1+2 | 3737 | 14.33 | 3737 |
| train | late ≠ minggu 3+4 | 3737 | 14.33 | 3737 |
| train | rata-rata per hari aktif tidak cocok | 3737 | 14.33 | 3737 |
| train | rata-rata per minggu aktif tidak cocok | 3737 | 14.33 | 3737 |
| train | rentang hari aktivitas tidak cocok | 3737 | 14.33 | 3737 |
| test | volume ≠ jumlah minggu 1–4 | 947 | 14.56 | 947 |
| test | early ≠ minggu 1+2 | 947 | 14.56 | 947 |
| test | late ≠ minggu 3+4 | 947 | 14.56 | 947 |
| test | rata-rata per hari aktif tidak cocok | 947 | 14.56 | 947 |
| test | rata-rata per minggu aktif tidak cocok | 947 | 14.56 | 947 |
| test | rentang hari aktivitas tidak cocok | 947 | 14.56 | 947 |

## Profil interaksi berulang

| dataset | jumlah | persen_dari_baris_bermasalah | interaction_volume | week1_interactions | week2_interactions | week3_interactions | week4_interactions |
| --- | --- | --- | --- | --- | --- | --- | --- |
| train | 3737 | 100.00 | 182 | 36 | 31 | 46 | 28 |
| test | 947 | 100.00 | 182 | 36 | 31 | 46 | 28 |

## Hari ke-28

| dataset | first_activity_day_28 | last_activity_day_28 | active_days_29 | day_28_dan_volume_bermasalah |
| --- | --- | --- | --- | --- |
| train | 16 | 6451 | 253 | 0 |
| test | 6 | 1626 | 69 | 0 |

## Perbandingan kelompok

| dataset | kelompok | jumlah | persen | at_risk_1_pct | has_score_0_pct |
| --- | --- | --- | --- | --- | --- |
| train | has_score=0 | 10046 | 38.51 | 71.83 | 100.00 |
| train | has_score=1 | 16040 | 61.49 | 40.75 | 0.00 |
| train | volume bermasalah | 3737 | 14.33 | 95.21 | 98.10 |
| train | volume konsisten | 22349 | 85.67 | 45.62 | 28.55 |
| test | has_score=0 | 2636 | 40.54 |  | 100.00 |
| test | has_score=1 | 3866 | 59.46 |  | 0.00 |
| test | volume bermasalah | 947 | 14.56 |  | 98.52 |
| test | volume konsisten | 5555 | 85.44 |  | 30.66 |
