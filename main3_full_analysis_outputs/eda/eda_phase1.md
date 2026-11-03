# EDA Phase 1 — audit data mentah

## Ringkasan dataset

| dataset | baris | kolom | memori_MB |
| --- | --- | --- | --- |
| train | 26086 | 64 | 94.9481 |
| test | 6502 | 63 | 23.3094 |

## Audit seluruh kolom

| dataset | kolom | peran | baris | unik_raw | missing_tersembunyi | format_spasi_Unicode | angka_tidak_valid | jumlah_temuan_semua_jenis |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| train | id | ID | 26086 | 26086 | 0 | 0 | 0 | 0 |
| train | code_module | kategorikal | 26086 | 7 | 0 | 0 | 0 | 0 |
| train | code_presentation | kategorikal | 26086 | 4 | 0 | 0 | 0 | 0 |
| train | gender | kategorikal | 26086 | 2 | 0 | 0 | 0 | 0 |
| train | region | kategorikal | 26086 | 13 | 0 | 0 | 0 | 7346 |
| train | highest_education | kategorikal | 26086 | 5 | 279 | 0 | 0 | 279 |
| train | imd_band | kategorikal | 26086 | 11 | 3696 | 0 | 0 | 3696 |
| train | age_band | kategorikal | 26086 | 3 | 0 | 0 | 0 | 0 |
| train | num_of_prev_attempts | numerik | 26086 | 7 | 0 | 0 | 0 | 0 |
| train | studied_credits | numerik | 26086 | 58 | 0 | 0 | 0 | 0 |
| train | disability | kategorikal | 26086 | 2 | 0 | 0 | 0 | 0 |
| train | module_presentation_length | numerik | 26086 | 7 | 0 | 0 | 0 | 0 |
| train | registration_days_from_start | numerik | 26086 | 322 | 0 | 0 | 0 | 0 |
| train | assessments_due_total | numerik | 26086 | 2 | 0 | 0 | 0 | 0 |
| train | assessments_due_Assessment_1 | numerik | 26086 | 2 | 0 | 0 | 0 | 0 |
| train | assessments_due_Assessment_2 | numerik | 26086 | 2 | 0 | 0 | 0 | 0 |
| train | submitted_count | numerik | 26086 | 2 | 0 | 0 | 0 | 0 |
| train | late_submission_count | numerik | 26086 | 3 | 0 | 0 | 0 | 0 |
| train | avg_score | numerik | 26086 | 163 | 0 | 0 | 0 | 0 |
| train | median_score | numerik | 26086 | 163 | 0 | 0 | 0 | 0 |
| train | max_score | numerik | 26086 | 94 | 0 | 0 | 0 | 0 |
| train | min_score | numerik | 26086 | 95 | 0 | 0 | 0 | 0 |
| train | score_std | numerik | 26086 | 46 | 0 | 0 | 0 | 0 |
| train | avg_submission_delay | numerik | 26086 | 54 | 0 | 0 | 0 | 0 |
| train | median_submission_delay | numerik | 26086 | 54 | 0 | 0 | 0 | 0 |
| train | max_submission_delay | numerik | 26086 | 42 | 0 | 0 | 0 | 0 |
| train | min_submission_delay | numerik | 26086 | 42 | 0 | 0 | 0 | 0 |
| train | weighted_score_total | numerik | 26086 | 551 | 0 | 0 | 0 | 0 |
| train | score_trend | numerik | 26086 | 90 | 0 | 0 | 0 | 0 |
| train | score_Assessment_2 | numerik | 26086 | 94 | 0 | 0 | 0 | 0 |
| train | weighted_score_Assessment_2 | numerik | 26086 | 198 | 0 | 0 | 0 | 0 |
| train | submission_delay_Assessment_2 | numerik | 26086 | 42 | 0 | 0 | 0 | 0 |
| train | submitted_Assessment_2 | numerik | 26086 | 1 | 0 | 0 | 0 | 0 |
| train | score_Assessment_1 | numerik | 26086 | 35 | 0 | 0 | 0 | 0 |
| train | weighted_score_Assessment_1 | numerik | 26086 | 35 | 0 | 0 | 0 | 0 |
| train | submission_delay_Assessment_1 | numerik | 26086 | 7 | 0 | 0 | 0 | 0 |
| train | submitted_Assessment_1 | numerik | 26086 | 1 | 0 | 0 | 0 | 0 |
| train | assessment_completion_rate_Assessment_2 | numerik | 26086 | 2 | 0 | 0 | 0 | 0 |
| train | assessment_completion_rate_Assessment_1 | numerik | 26086 | 2 | 0 | 0 | 0 | 0 |
| train | assessment_completion_rate | numerik | 26086 | 3 | 0 | 0 | 0 | 0 |
| train | no_submission_by_cutoff | numerik | 26086 | 2 | 0 | 0 | 0 | 0 |
| train | has_score | numerik | 26086 | 2 | 0 | 0 | 0 | 0 |
| train | interaction_volume | numerik | 26086 | 1542 | 0 | 0 | 0 | 3737 |
| train | active_days | numerik | 26086 | 29 | 0 | 0 | 0 | 253 |
| train | unique_sites | numerik | 26086 | 120 | 0 | 0 | 0 | 0 |
| train | unique_activity_types | numerik | 26086 | 14 | 0 | 0 | 0 | 0 |
| train | avg_daily_interactions | numerik | 26086 | 6140 | 0 | 0 | 0 | 3737 |
| train | max_daily_interactions | numerik | 26086 | 401 | 0 | 0 | 0 | 0 |
| train | interaction_variability | numerik | 26086 | 17996 | 0 | 0 | 0 | 0 |
| train | first_activity_day | numerik | 26086 | 29 | 0 | 0 | 0 | 16 |
| train | last_activity_day | numerik | 26086 | 29 | 0 | 0 | 0 | 6451 |
| train | week1_interactions | numerik | 26086 | 639 | 0 | 0 | 0 | 0 |
| train | week2_interactions | numerik | 26086 | 593 | 0 | 0 | 0 | 0 |
| train | week3_interactions | numerik | 26086 | 639 | 0 | 0 | 0 | 0 |
| train | week4_interactions | numerik | 26086 | 628 | 0 | 0 | 0 | 0 |
| train | interaction_trend | numerik | 26086 | 2146 | 0 | 0 | 0 | 0 |
| train | early_interactions | numerik | 26086 | 967 | 0 | 0 | 0 | 3737 |
| train | late_interactions | numerik | 26086 | 987 | 0 | 0 | 0 | 3737 |
| train | late_to_early_interactions_ratio | numerik | 26086 | 12640 | 0 | 0 | 0 | 0 |
| train | avg_interactions_per_active_day | numerik | 26086 | 6140 | 0 | 0 | 0 | 3737 |
| train | active_weeks | numerik | 26086 | 4 | 0 | 0 | 0 | 0 |
| train | avg_interactions_per_active_week | numerik | 26086 | 1903 | 0 | 0 | 0 | 3737 |
| train | activity_span_days | numerik | 26086 | 29 | 0 | 0 | 0 | 3737 |
| train | at_risk | target | 26086 | 2 | 0 | 0 | 0 | 0 |
| test | id | ID | 6502 | 6502 | 0 | 0 | 0 | 0 |
| test | code_module | kategorikal | 6502 | 8 | 0 | 0 | 0 | 744 |
| test | code_presentation | kategorikal | 6502 | 4 | 0 | 0 | 0 | 0 |
| test | gender | kategorikal | 6502 | 2 | 0 | 0 | 0 | 0 |
| test | region | kategorikal | 6502 | 13 | 0 | 0 | 0 | 1857 |
| test | highest_education | kategorikal | 6502 | 5 | 68 | 0 | 0 | 68 |
| test | imd_band | kategorikal | 6502 | 11 | 928 | 0 | 0 | 928 |
| test | age_band | kategorikal | 6502 | 3 | 0 | 0 | 0 | 0 |
| test | num_of_prev_attempts | numerik | 6502 | 6 | 0 | 0 | 0 | 0 |
| test | studied_credits | numerik | 6502 | 38 | 0 | 0 | 0 | 0 |
| test | disability | kategorikal | 6502 | 2 | 0 | 0 | 0 | 0 |
| test | module_presentation_length | numerik | 6502 | 7 | 0 | 0 | 0 | 0 |
| test | registration_days_from_start | numerik | 6502 | 263 | 0 | 0 | 0 | 0 |
| test | assessments_due_total | numerik | 6502 | 2 | 0 | 0 | 0 | 0 |
| test | assessments_due_Assessment_1 | numerik | 6502 | 2 | 0 | 0 | 0 | 0 |
| test | assessments_due_Assessment_2 | numerik | 6502 | 2 | 0 | 0 | 0 | 0 |
| test | submitted_count | numerik | 6502 | 2 | 0 | 0 | 0 | 0 |
| test | late_submission_count | numerik | 6502 | 3 | 0 | 0 | 0 | 0 |
| test | avg_score | numerik | 6502 | 132 | 0 | 0 | 0 | 0 |
| test | median_score | numerik | 6502 | 132 | 0 | 0 | 0 | 0 |
| test | max_score | numerik | 6502 | 84 | 0 | 0 | 0 | 0 |
| test | min_score | numerik | 6502 | 85 | 0 | 0 | 0 | 0 |
| test | score_std | numerik | 6502 | 40 | 0 | 0 | 0 | 0 |
| test | avg_submission_delay | numerik | 6502 | 44 | 0 | 0 | 0 | 0 |
| test | median_submission_delay | numerik | 6502 | 44 | 0 | 0 | 0 | 0 |
| test | max_submission_delay | numerik | 6502 | 34 | 0 | 0 | 0 | 0 |
| test | min_submission_delay | numerik | 6502 | 35 | 0 | 0 | 0 | 0 |
| test | weighted_score_total | numerik | 6502 | 299 | 0 | 0 | 0 | 0 |
| test | score_trend | numerik | 6502 | 67 | 0 | 0 | 0 | 0 |
| test | score_Assessment_2 | numerik | 6502 | 82 | 0 | 0 | 0 | 0 |
| test | weighted_score_Assessment_2 | numerik | 6502 | 175 | 0 | 0 | 0 | 0 |
| test | submission_delay_Assessment_2 | numerik | 6502 | 35 | 0 | 0 | 0 | 0 |
| test | submitted_Assessment_2 | numerik | 6502 | 1 | 0 | 0 | 0 | 0 |
| test | score_Assessment_1 | numerik | 6502 | 33 | 0 | 0 | 0 | 0 |
| test | weighted_score_Assessment_1 | numerik | 6502 | 33 | 0 | 0 | 0 | 0 |
| test | submission_delay_Assessment_1 | numerik | 6502 | 2 | 0 | 0 | 0 | 0 |
| test | submitted_Assessment_1 | numerik | 6502 | 1 | 0 | 0 | 0 | 0 |
| test | assessment_completion_rate_Assessment_2 | numerik | 6502 | 2 | 0 | 0 | 0 | 0 |
| test | assessment_completion_rate_Assessment_1 | numerik | 6502 | 2 | 0 | 0 | 0 | 0 |
| test | assessment_completion_rate | numerik | 6502 | 3 | 0 | 0 | 0 | 0 |
| test | no_submission_by_cutoff | numerik | 6502 | 2 | 0 | 0 | 0 | 0 |
| test | has_score | numerik | 6502 | 2 | 0 | 0 | 0 | 0 |
| test | interaction_volume | numerik | 6502 | 1032 | 0 | 0 | 0 | 947 |
| test | active_days | numerik | 6502 | 29 | 0 | 0 | 0 | 69 |
| test | unique_sites | numerik | 6502 | 104 | 0 | 0 | 0 | 0 |
| test | unique_activity_types | numerik | 6502 | 13 | 0 | 0 | 0 | 0 |
| test | avg_daily_interactions | numerik | 6502 | 2616 | 0 | 0 | 0 | 947 |
| test | max_daily_interactions | numerik | 6502 | 303 | 0 | 0 | 0 | 0 |
| test | interaction_variability | numerik | 6502 | 4811 | 0 | 0 | 0 | 0 |
| test | first_activity_day | numerik | 6502 | 29 | 0 | 0 | 0 | 6 |
| test | last_activity_day | numerik | 6502 | 29 | 0 | 0 | 0 | 1626 |
| test | week1_interactions | numerik | 6502 | 443 | 0 | 0 | 0 | 0 |
| test | week2_interactions | numerik | 6502 | 414 | 0 | 0 | 0 | 0 |
| test | week3_interactions | numerik | 6502 | 460 | 0 | 0 | 0 | 0 |
| test | week4_interactions | numerik | 6502 | 423 | 0 | 0 | 0 | 0 |
| test | interaction_trend | numerik | 6502 | 1327 | 0 | 0 | 0 | 0 |
| test | early_interactions | numerik | 6502 | 656 | 0 | 0 | 0 | 947 |
| test | late_interactions | numerik | 6502 | 673 | 0 | 0 | 0 | 947 |
| test | late_to_early_interactions_ratio | numerik | 6502 | 3901 | 0 | 0 | 0 | 0 |
| test | avg_interactions_per_active_day | numerik | 6502 | 2616 | 0 | 0 | 0 | 947 |
| test | active_weeks | numerik | 6502 | 4 | 0 | 0 | 0 | 0 |
| test | avg_interactions_per_active_week | numerik | 6502 | 1274 | 0 | 0 | 0 | 947 |
| test | activity_span_days | numerik | 6502 | 29 | 0 | 0 | 0 | 947 |

## Tipe, kardinalitas, dan missing yang tersembunyi

| kolom | dtype_pandas | peran | unik_train | rasio_dapat_dibaca_angka | missing_terbaca_pandas | missing_mentah_termasuk_placeholder |
| --- | --- | --- | --- | --- | --- | --- |
| id | int64 | ID | 26086 | 1.0000 | 0 | 0 |
| code_module | object | kategorikal | 7 | 0.0000 | 0 | 0 |
| code_presentation | object | kategorikal | 4 | 0.0000 | 0 | 0 |
| gender | object | kategorikal | 2 | 0.0000 | 0 | 0 |
| region | object | kategorikal | 13 | 0.0000 | 0 | 0 |
| highest_education | object | kategorikal | 5 | 0.0000 | 0 | 279 |
| imd_band | object | kategorikal | 11 | 0.0000 | 0 | 3696 |
| age_band | object | kategorikal | 3 | 0.0000 | 0 | 0 |
| num_of_prev_attempts | int64 | numerik | 7 | 1.0000 | 0 | 0 |
| studied_credits | int64 | numerik | 58 | 1.0000 | 0 | 0 |
| disability | object | kategorikal | 2 | 0.0000 | 0 | 0 |
| module_presentation_length | int64 | numerik | 7 | 1.0000 | 0 | 0 |
| registration_days_from_start | int64 | numerik | 322 | 1.0000 | 0 | 0 |
| assessments_due_total | int64 | numerik | 2 | 1.0000 | 0 | 0 |
| assessments_due_Assessment_1 | int64 | numerik | 2 | 1.0000 | 0 | 0 |
| assessments_due_Assessment_2 | int64 | numerik | 2 | 1.0000 | 0 | 0 |
| submitted_count | int64 | numerik | 2 | 1.0000 | 0 | 0 |
| late_submission_count | int64 | numerik | 3 | 1.0000 | 0 | 0 |
| avg_score | float64 | numerik | 163 | 1.0000 | 0 | 0 |
| median_score | float64 | numerik | 163 | 1.0000 | 0 | 0 |
| max_score | int64 | numerik | 94 | 1.0000 | 0 | 0 |
| min_score | int64 | numerik | 95 | 1.0000 | 0 | 0 |
| score_std | float64 | numerik | 46 | 1.0000 | 0 | 0 |
| avg_submission_delay | float64 | numerik | 54 | 1.0000 | 0 | 0 |
| median_submission_delay | float64 | numerik | 54 | 1.0000 | 0 | 0 |
| max_submission_delay | int64 | numerik | 42 | 1.0000 | 0 | 0 |
| min_submission_delay | int64 | numerik | 42 | 1.0000 | 0 | 0 |
| weighted_score_total | float64 | numerik | 551 | 1.0000 | 0 | 0 |
| score_trend | float64 | numerik | 90 | 1.0000 | 0 | 0 |
| score_Assessment_2 | int64 | numerik | 94 | 1.0000 | 0 | 0 |
| weighted_score_Assessment_2 | float64 | numerik | 198 | 1.0000 | 0 | 0 |
| submission_delay_Assessment_2 | int64 | numerik | 42 | 1.0000 | 0 | 0 |
| submitted_Assessment_2 | int64 | numerik | 1 | 1.0000 | 0 | 0 |
| score_Assessment_1 | int64 | numerik | 35 | 1.0000 | 0 | 0 |
| weighted_score_Assessment_1 | float64 | numerik | 35 | 1.0000 | 0 | 0 |
| submission_delay_Assessment_1 | int64 | numerik | 7 | 1.0000 | 0 | 0 |
| submitted_Assessment_1 | int64 | numerik | 1 | 1.0000 | 0 | 0 |
| assessment_completion_rate_Assessment_2 | int64 | numerik | 2 | 1.0000 | 0 | 0 |
| assessment_completion_rate_Assessment_1 | int64 | numerik | 2 | 1.0000 | 0 | 0 |
| assessment_completion_rate | float64 | numerik | 3 | 1.0000 | 0 | 0 |
| no_submission_by_cutoff | int64 | numerik | 2 | 1.0000 | 0 | 0 |
| has_score | int64 | numerik | 2 | 1.0000 | 0 | 0 |
| interaction_volume | int64 | numerik | 1542 | 1.0000 | 0 | 0 |
| active_days | int64 | numerik | 29 | 1.0000 | 0 | 0 |
| unique_sites | int64 | numerik | 120 | 1.0000 | 0 | 0 |
| unique_activity_types | int64 | numerik | 14 | 1.0000 | 0 | 0 |
| avg_daily_interactions | float64 | numerik | 6140 | 1.0000 | 0 | 0 |
| max_daily_interactions | int64 | numerik | 401 | 1.0000 | 0 | 0 |
| interaction_variability | float64 | numerik | 17996 | 1.0000 | 0 | 0 |
| first_activity_day | int64 | numerik | 29 | 1.0000 | 0 | 0 |
| last_activity_day | int64 | numerik | 29 | 1.0000 | 0 | 0 |
| week1_interactions | int64 | numerik | 639 | 1.0000 | 0 | 0 |
| week2_interactions | int64 | numerik | 593 | 1.0000 | 0 | 0 |
| week3_interactions | int64 | numerik | 639 | 1.0000 | 0 | 0 |
| week4_interactions | int64 | numerik | 628 | 1.0000 | 0 | 0 |
| interaction_trend | float64 | numerik | 2146 | 1.0000 | 0 | 0 |
| early_interactions | int64 | numerik | 967 | 1.0000 | 0 | 0 |
| late_interactions | int64 | numerik | 987 | 1.0000 | 0 | 0 |
| late_to_early_interactions_ratio | float64 | numerik | 12640 | 1.0000 | 0 | 0 |
| avg_interactions_per_active_day | float64 | numerik | 6140 | 1.0000 | 0 | 0 |
| active_weeks | int64 | numerik | 4 | 1.0000 | 0 | 0 |
| avg_interactions_per_active_week | float64 | numerik | 1903 | 1.0000 | 0 | 0 |
| activity_span_days | int64 | numerik | 29 | 1.0000 | 0 | 0 |
| at_risk | int64 | target | 2 | 1.0000 | 0 | 0 |

## Token placeholder

| dataset | kolom | jumlah | token_dan_frekuensi |
| --- | --- | --- | --- |
| train | highest_education | 279 | '-'=279 |
| train | imd_band | 3696 | '-'=2797; '?'=899 |
| test | highest_education | 68 | '-'=68 |
| test | imd_band | 928 | '-'=716; '?'=212 |

## Variasi ejaan, kapitalisasi, spasi, dan tanda baca pada kategori

| kolom | kunci_normalisasi | jumlah_variannya | nilai_dan_frekuensi |
| --- | --- | --- | --- |
| highest_education | alevel | 2 | 'A Level'=11201; 'A level'=2843 |

## Kategori baru pada test

| kolom | jumlah_baris_test | nilai_baru |
| --- | --- | --- |
| code_module | 372 | 'GGG'=372 |

## Semua temuan format dan rentang, dengan contoh ID

| dataset | kolom | masalah | jumlah | persen | contoh_ID:nilai |
| --- | --- | --- | --- | --- | --- |
| test | active_days | di luar rentang [0, 28] | 69 | 1.0612 | 26097:'29'; 26135:'29'; 26137:'29'; 26158:'29'; 26161:'29' |
| test | activity_span_days | tidak konsisten: activity_span_days = hari terakhir-pertama | 947 | 14.5647 | 26102:'24'; 26174:'24'; 26179:'24'; 26180:'24'; 26192:'24' |
| test | avg_daily_interactions | tidak konsisten: avg_daily_interactions = volume/hari aktif | 947 | 14.5647 | 26102:'18.84807692'; 26174:'18.84807692'; 26179:'18.84807692'; 26180:'18.84807692'; 26192:'18.84807692' |
| test | avg_interactions_per_active_day | tidak konsisten: avg_interactions_per_active_day = volume/hari aktif | 947 | 14.5647 | 26102:'18.84807692'; 26174:'18.84807692'; 26179:'18.84807692'; 26180:'18.84807692'; 26192:'18.84807692' |
| test | avg_interactions_per_active_week | tidak konsisten: avg_interactions_per_active_week = volume/minggu aktif | 947 | 14.5647 | 26102:'52.5'; 26174:'52.5'; 26179:'52.5'; 26180:'52.5'; 26192:'52.5' |
| test | code_module | format kategori berbeda dari pola kolom | 372 | 5.7213 | 29081:'GGG'; 29082:'GGG'; 29083:'GGG'; 29088:'GGG'; 29089:'GGG' |
| test | code_module | kategori tidak dijumpai di train | 372 | 5.7213 | 29081:'GGG'; 29082:'GGG'; 29083:'GGG'; 29088:'GGG'; 29089:'GGG' |
| test | early_interactions | tidak konsisten: early_interactions = minggu 1+2 | 947 | 14.5647 | 26102:'78'; 26174:'78'; 26179:'78'; 26180:'78'; 26192:'78' |
| test | first_activity_day | di luar rentang [0, 27] | 6 | 0.0923 | 26269:'28'; 26980:'28'; 27986:'28'; 28028:'28'; 28254:'28' |
| test | highest_education | placeholder / tanda baca sebagai missing | 68 | 1.0458 | 26357:'-'; 26388:'-'; 26678:'-'; 26679:'-'; 26720:'-' |
| test | imd_band | placeholder / tanda baca sebagai missing | 928 | 14.2725 | 26110:'-'; 26125:'?'; 26149:'-'; 26151:'-'; 26157:'?' |
| test | interaction_volume | tidak konsisten: interaction_volume = jumlah minggu | 947 | 14.5647 | 26102:'182'; 26174:'182'; 26179:'182'; 26180:'182'; 26192:'182' |
| test | last_activity_day | di luar rentang [0, 27] | 1626 | 25.0077 | 26093:'28'; 26094:'28'; 26096:'28'; 26097:'28'; 26103:'28' |
| test | late_interactions | tidak konsisten: late_interactions = minggu 3+4 | 947 | 14.5647 | 26102:'89'; 26174:'89'; 26179:'89'; 26180:'89'; 26192:'89' |
| test | region | format kategori berbeda dari pola kolom | 1857 | 28.5604 | 26095:'Region 3'; 26096:'Region 4'; 26107:'Region 4'; 26119:'Region 10'; 26121:'Region 10' |
| train | active_days | di luar rentang [0, 28] | 253 | 0.9699 | 120:'29'; 241:'29'; 417:'29'; 442:'29'; 493:'29' |
| train | activity_span_days | tidak konsisten: activity_span_days = hari terakhir-pertama | 3737 | 14.3257 | 131:'24'; 155:'24'; 200:'24'; 214:'24'; 235:'24' |
| train | avg_daily_interactions | tidak konsisten: avg_daily_interactions = volume/hari aktif | 3737 | 14.3257 | 131:'18.84807692'; 155:'18.84807692'; 200:'18.84807692'; 214:'18.84807692'; 235:'18.84807692' |
| train | avg_interactions_per_active_day | tidak konsisten: avg_interactions_per_active_day = volume/hari aktif | 3737 | 14.3257 | 131:'18.84807692'; 155:'18.84807692'; 200:'18.84807692'; 214:'18.84807692'; 235:'18.84807692' |
| train | avg_interactions_per_active_week | tidak konsisten: avg_interactions_per_active_week = volume/minggu aktif | 3737 | 14.3257 | 131:'52.5'; 155:'52.5'; 200:'52.5'; 214:'52.5'; 235:'52.5' |
| train | early_interactions | tidak konsisten: early_interactions = minggu 1+2 | 3737 | 14.3257 | 131:'78'; 155:'78'; 200:'78'; 214:'78'; 235:'78' |
| train | first_activity_day | di luar rentang [0, 27] | 16 | 0.0613 | 1737:'28'; 2335:'28'; 3103:'28'; 3658:'28'; 4135:'28' |
| train | highest_education | placeholder / tanda baca sebagai missing | 279 | 1.0695 | 873:'-'; 933:'-'; 958:'-'; 978:'-'; 990:'-' |
| train | imd_band | placeholder / tanda baca sebagai missing | 3696 | 14.1685 | 14:'?'; 15:'-'; 23:'?'; 29:'?'; 55:'-' |
| train | interaction_volume | tidak konsisten: interaction_volume = jumlah minggu | 3737 | 14.3257 | 131:'182'; 155:'182'; 200:'182'; 214:'182'; 235:'182' |
| train | last_activity_day | di luar rentang [0, 27] | 6451 | 24.7297 | 2:'28'; 4:'28'; 8:'28'; 9:'28'; 12:'28' |
| train | late_interactions | tidak konsisten: late_interactions = minggu 3+4 | 3737 | 14.3257 | 131:'89'; 155:'89'; 200:'89'; 214:'89'; 235:'89' |
| train | region | format kategori berbeda dari pola kolom | 7346 | 28.1607 | 3:'region2'; 4:'Region 10'; 8:'region2'; 17:'Region 3'; 18:'region2' |

## Nilai numerik yang sangat dominan — kandidat default, belum otomatis missing

| dataset | kolom | nilai_dominan | jumlah | persen_dari_valid | jumlah_nilai_unik |
| --- | --- | --- | --- | --- | --- |
| train | studied_credits | 60.0000 | 13407 | 51.3954 | 58 |
| train | avg_score | 77.0000 | 10242 | 39.2624 | 163 |
| train | median_score | 77.0000 | 10242 | 39.2624 | 163 |
| train | max_score | 77.0000 | 10261 | 39.3353 | 94 |
| train | min_score | 77.0000 | 10268 | 39.3621 | 95 |
| train | score_std | 0.0000 | 25393 | 97.3434 | 46 |
| train | avg_submission_delay | -1.0000 | 13793 | 52.8751 | 54 |
| train | median_submission_delay | -1.0000 | 13793 | 52.8751 | 54 |
| train | max_submission_delay | -1.0000 | 13759 | 52.7448 | 42 |
| train | min_submission_delay | -1.0000 | 13947 | 53.4655 | 42 |
| train | weighted_score_total | 4.2500 | 10327 | 39.5883 | 551 |
| train | score_trend | 0.0000 | 25375 | 97.2744 | 90 |
| train | score_Assessment_2 | 77.0000 | 12956 | 49.6665 | 94 |
| train | weighted_score_Assessment_2 | 6.0000 | 12812 | 49.1145 | 198 |
| train | submission_delay_Assessment_2 | -1.0000 | 16649 | 63.8235 | 42 |
| train | score_Assessment_1 | 70.0000 | 22879 | 87.7060 | 35 |
| train | weighted_score_Assessment_1 | 1.4000 | 22879 | 87.7060 | 35 |
| train | interaction_volume | 182.0000 | 3775 | 14.4714 | 1542 |
| train | active_days | 10.0000 | 4828 | 18.5080 | 29 |
| train | unique_sites | 20.0000 | 4307 | 16.5108 | 120 |
| train | avg_daily_interactions | 18.8481 | 3737 | 14.3257 | 6140 |
| train | max_daily_interactions | 55.0000 | 3918 | 15.0196 | 401 |
| train | interaction_variability | 16.2025 | 3737 | 14.3257 | 17996 |
| train | first_activity_day | 0.0000 | 7559 | 28.9772 | 29 |
| train | last_activity_day | 28.0000 | 6451 | 24.7297 | 29 |
| train | week1_interactions | 36.0000 | 3896 | 14.9352 | 639 |
| train | week2_interactions | 31.0000 | 3900 | 14.9505 | 593 |
| train | week3_interactions | 46.0000 | 3860 | 14.7972 | 639 |
| train | week4_interactions | 0.0000 | 4268 | 16.3613 | 628 |
| train | interaction_trend | -0.3000 | 3886 | 14.8969 | 2146 |
| train | early_interactions | 78.0000 | 3816 | 14.6285 | 967 |
| train | late_interactions | 89.0000 | 3794 | 14.5442 | 987 |
| train | late_to_early_interactions_ratio | 0.9041 | 3737 | 14.3257 | 12640 |
| train | avg_interactions_per_active_day | 18.8481 | 3737 | 14.3257 | 6140 |
| train | avg_interactions_per_active_week | 52.5000 | 3770 | 14.4522 | 1903 |
| train | activity_span_days | 24.0000 | 5450 | 20.8924 | 29 |
| test | studied_credits | 60.0000 | 3341 | 51.3842 | 38 |
| test | avg_score | 77.0000 | 2681 | 41.2335 | 132 |
| test | median_score | 77.0000 | 2681 | 41.2335 | 132 |
| test | max_score | 77.0000 | 2686 | 41.3104 | 84 |
| test | min_score | 77.0000 | 2683 | 41.2642 | 85 |
| test | score_std | 0.0000 | 6336 | 97.4469 | 40 |
| test | avg_submission_delay | -1.0000 | 3545 | 54.5217 | 44 |
| test | median_submission_delay | -1.0000 | 3545 | 54.5217 | 44 |
| test | max_submission_delay | -1.0000 | 3538 | 54.4140 | 34 |
| test | min_submission_delay | -1.0000 | 3587 | 55.1676 | 35 |
| test | weighted_score_total | 4.2500 | 2691 | 41.3873 | 299 |
| test | score_trend | 0.0000 | 6331 | 97.3700 | 67 |
| test | score_Assessment_2 | 77.0000 | 3311 | 50.9228 | 82 |
| test | weighted_score_Assessment_2 | 6.0000 | 3275 | 50.3691 | 175 |
| test | submission_delay_Assessment_2 | -1.0000 | 4216 | 64.8416 | 35 |
| test | score_Assessment_1 | 70.0000 | 5751 | 88.4497 | 33 |
| test | weighted_score_Assessment_1 | 1.4000 | 5751 | 88.4497 | 33 |
| test | interaction_volume | 182.0000 | 960 | 14.7647 | 1032 |
| test | active_days | 10.0000 | 1213 | 18.6558 | 29 |
| test | unique_sites | 20.0000 | 1106 | 17.0102 | 104 |
| test | avg_daily_interactions | 18.8481 | 947 | 14.5647 | 2616 |
| test | max_daily_interactions | 55.0000 | 987 | 15.1799 | 303 |
| test | interaction_variability | 16.2025 | 947 | 14.5647 | 4811 |
| test | first_activity_day | 0.0000 | 1890 | 29.0680 | 29 |
| test | last_activity_day | 28.0000 | 1626 | 25.0077 | 29 |
| test | week1_interactions | 36.0000 | 979 | 15.0569 | 443 |
| test | week2_interactions | 31.0000 | 972 | 14.9492 | 414 |
| test | week3_interactions | 46.0000 | 966 | 14.8570 | 460 |
| test | week4_interactions | 0.0000 | 1105 | 16.9948 | 423 |
| test | interaction_trend | -0.3000 | 988 | 15.1953 | 1327 |
| test | early_interactions | 78.0000 | 966 | 14.8570 | 656 |
| test | late_interactions | 89.0000 | 967 | 14.8723 | 673 |
| test | late_to_early_interactions_ratio | 0.9041 | 947 | 14.5647 | 3901 |
| test | avg_interactions_per_active_day | 18.8481 | 947 | 14.5647 | 2616 |
| test | avg_interactions_per_active_week | 52.5000 | 958 | 14.7339 | 1274 |
| test | activity_span_days | 24.0000 | 1345 | 20.6859 | 29 |

## Nilai skor terisi ketika has_score = 0

| dataset | kondisi | kolom | terisi_saat_kondisi | persen_dari_kondisi | nilai_teratas |
| --- | --- | --- | --- | --- | --- |
| train | has_score = 0 | avg_score | 10046 | 100.0000 | 77.0=10046 |
| train | has_score = 0 | median_score | 10046 | 100.0000 | 77.0=10046 |
| train | has_score = 0 | max_score | 10046 | 100.0000 | 77=10046 |
| train | has_score = 0 | min_score | 10046 | 100.0000 | 77=10046 |
| train | has_score = 0 | score_std | 10046 | 100.0000 | 0.0=10046 |
| train | has_score = 0 | weighted_score_total | 10046 | 100.0000 | 4.25=10037; 0.0=9 |
| train | has_score = 0 | score_trend | 10046 | 100.0000 | 0.0=10046 |
| train | has_score = 0 | score_Assessment_2 | 10046 | 100.0000 | 77=10046 |
| train | has_score = 0 | weighted_score_Assessment_2 | 10046 | 100.0000 | 6.0=10037; 0.0=9 |
| train | has_score = 0 | score_Assessment_1 | 10046 | 100.0000 | 70=10046 |
| train | has_score = 0 | weighted_score_Assessment_1 | 10046 | 100.0000 | 1.4=10046 |
| test | has_score = 0 | avg_score | 2636 | 100.0000 | 77.0=2636 |
| test | has_score = 0 | median_score | 2636 | 100.0000 | 77.0=2636 |
| test | has_score = 0 | max_score | 2636 | 100.0000 | 77=2636 |
| test | has_score = 0 | min_score | 2636 | 100.0000 | 77=2636 |
| test | has_score = 0 | score_std | 2636 | 100.0000 | 0.0=2636 |
| test | has_score = 0 | weighted_score_total | 2636 | 100.0000 | 4.25=2632; 0.0=4 |
| test | has_score = 0 | score_trend | 2636 | 100.0000 | 0.0=2636 |
| test | has_score = 0 | score_Assessment_2 | 2636 | 100.0000 | 77=2636 |
| test | has_score = 0 | weighted_score_Assessment_2 | 2636 | 100.0000 | 6.0=2632; 0.0=4 |
| test | has_score = 0 | score_Assessment_1 | 2636 | 100.0000 | 70=2636 |
| test | has_score = 0 | weighted_score_Assessment_1 | 2636 | 100.0000 | 1.4=2636 |

## Konsistensi antarkolom

| dataset | aturan | baris_dapat_diperiksa | tidak_konsisten | contoh_ID |
| --- | --- | --- | --- | --- |
| train | interaction_volume = jumlah minggu | 26086 | 3737 | 131, 155, 200, 214, 235, 236, 242, 374 |
| train | early_interactions = minggu 1+2 | 26086 | 3737 | 131, 155, 200, 214, 235, 236, 242, 374 |
| train | late_interactions = minggu 3+4 | 26086 | 3737 | 131, 155, 200, 214, 235, 236, 242, 374 |
| train | assessments_due_total = Assessment 1+2 | 26086 | 0 |  |
| train | activity_span_days = hari terakhir-pertama | 26086 | 3737 | 131, 155, 200, 214, 235, 236, 242, 374 |
| train | active_weeks = jumlah minggu aktif | 26086 | 0 |  |
| train | avg_daily_interactions = volume/hari aktif | 26086 | 3737 | 131, 155, 200, 214, 235, 236, 242, 374 |
| train | avg_interactions_per_active_day = volume/hari aktif | 26086 | 3737 | 131, 155, 200, 214, 235, 236, 242, 374 |
| train | avg_interactions_per_active_week = volume/minggu aktif | 26086 | 3737 | 131, 155, 200, 214, 235, 236, 242, 374 |
| test | interaction_volume = jumlah minggu | 6502 | 947 | 26102, 26174, 26179, 26180, 26192, 26199, 26207, 26217 |
| test | early_interactions = minggu 1+2 | 6502 | 947 | 26102, 26174, 26179, 26180, 26192, 26199, 26207, 26217 |
| test | late_interactions = minggu 3+4 | 6502 | 947 | 26102, 26174, 26179, 26180, 26192, 26199, 26207, 26217 |
| test | assessments_due_total = Assessment 1+2 | 6502 | 0 |  |
| test | activity_span_days = hari terakhir-pertama | 6502 | 947 | 26102, 26174, 26179, 26180, 26192, 26199, 26207, 26217 |
| test | active_weeks = jumlah minggu aktif | 6502 | 0 |  |
| test | avg_daily_interactions = volume/hari aktif | 6502 | 947 | 26102, 26174, 26179, 26180, 26192, 26199, 26207, 26217 |
| test | avg_interactions_per_active_day = volume/hari aktif | 6502 | 947 | 26102, 26174, 26179, 26180, 26192, 26199, 26207, 26217 |
| test | avg_interactions_per_active_week = volume/minggu aktif | 6502 | 947 | 26102, 26174, 26179, 26180, 26192, 26199, 26207, 26217 |

## Missing efektif per kolom

| kolom | missing_train_n | missing_train_pct | missing_test_n | missing_test_pct |
| --- | --- | --- | --- | --- |
| imd_band | 3696 | 14.1685 | 928 | 14.2725 |
| highest_education | 279 | 1.0695 | 68 | 1.0458 |
| code_presentation | 0 | 0.0000 | 0 | 0.0000 |
| code_module | 0 | 0.0000 | 0 | 0.0000 |
| region | 0 | 0.0000 | 0 | 0.0000 |
| gender | 0 | 0.0000 | 0 | 0.0000 |
| age_band | 0 | 0.0000 | 0 | 0.0000 |
| num_of_prev_attempts | 0 | 0.0000 | 0 | 0.0000 |
| studied_credits | 0 | 0.0000 | 0 | 0.0000 |
| disability | 0 | 0.0000 | 0 | 0.0000 |
| module_presentation_length | 0 | 0.0000 | 0 | 0.0000 |
| registration_days_from_start | 0 | 0.0000 | 0 | 0.0000 |
| assessments_due_total | 0 | 0.0000 | 0 | 0.0000 |
| assessments_due_Assessment_1 | 0 | 0.0000 | 0 | 0.0000 |
| assessments_due_Assessment_2 | 0 | 0.0000 | 0 | 0.0000 |
| submitted_count | 0 | 0.0000 | 0 | 0.0000 |
| late_submission_count | 0 | 0.0000 | 0 | 0.0000 |
| avg_score | 0 | 0.0000 | 0 | 0.0000 |
| median_score | 0 | 0.0000 | 0 | 0.0000 |
| max_score | 0 | 0.0000 | 0 | 0.0000 |
| min_score | 0 | 0.0000 | 0 | 0.0000 |
| score_std | 0 | 0.0000 | 0 | 0.0000 |
| avg_submission_delay | 0 | 0.0000 | 0 | 0.0000 |
| median_submission_delay | 0 | 0.0000 | 0 | 0.0000 |
| max_submission_delay | 0 | 0.0000 | 0 | 0.0000 |
| min_submission_delay | 0 | 0.0000 | 0 | 0.0000 |
| weighted_score_total | 0 | 0.0000 | 0 | 0.0000 |
| score_trend | 0 | 0.0000 | 0 | 0.0000 |
| score_Assessment_2 | 0 | 0.0000 | 0 | 0.0000 |
| weighted_score_Assessment_2 | 0 | 0.0000 | 0 | 0.0000 |
| submission_delay_Assessment_2 | 0 | 0.0000 | 0 | 0.0000 |
| submitted_Assessment_2 | 0 | 0.0000 | 0 | 0.0000 |
| score_Assessment_1 | 0 | 0.0000 | 0 | 0.0000 |
| weighted_score_Assessment_1 | 0 | 0.0000 | 0 | 0.0000 |
| submission_delay_Assessment_1 | 0 | 0.0000 | 0 | 0.0000 |
| submitted_Assessment_1 | 0 | 0.0000 | 0 | 0.0000 |
| assessment_completion_rate_Assessment_2 | 0 | 0.0000 | 0 | 0.0000 |
| assessment_completion_rate_Assessment_1 | 0 | 0.0000 | 0 | 0.0000 |
| assessment_completion_rate | 0 | 0.0000 | 0 | 0.0000 |
| no_submission_by_cutoff | 0 | 0.0000 | 0 | 0.0000 |
| has_score | 0 | 0.0000 | 0 | 0.0000 |
| interaction_volume | 0 | 0.0000 | 0 | 0.0000 |
| active_days | 0 | 0.0000 | 0 | 0.0000 |
| unique_sites | 0 | 0.0000 | 0 | 0.0000 |
| unique_activity_types | 0 | 0.0000 | 0 | 0.0000 |
| avg_daily_interactions | 0 | 0.0000 | 0 | 0.0000 |
| max_daily_interactions | 0 | 0.0000 | 0 | 0.0000 |
| interaction_variability | 0 | 0.0000 | 0 | 0.0000 |
| first_activity_day | 0 | 0.0000 | 0 | 0.0000 |
| last_activity_day | 0 | 0.0000 | 0 | 0.0000 |
| week1_interactions | 0 | 0.0000 | 0 | 0.0000 |
| week2_interactions | 0 | 0.0000 | 0 | 0.0000 |
| week3_interactions | 0 | 0.0000 | 0 | 0.0000 |
| week4_interactions | 0 | 0.0000 | 0 | 0.0000 |
| interaction_trend | 0 | 0.0000 | 0 | 0.0000 |
| early_interactions | 0 | 0.0000 | 0 | 0.0000 |
| late_interactions | 0 | 0.0000 | 0 | 0.0000 |
| late_to_early_interactions_ratio | 0 | 0.0000 | 0 | 0.0000 |
| avg_interactions_per_active_day | 0 | 0.0000 | 0 | 0.0000 |
| active_weeks | 0 | 0.0000 | 0 | 0.0000 |
| avg_interactions_per_active_week | 0 | 0.0000 | 0 | 0.0000 |
| activity_span_days | 0 | 0.0000 | 0 | 0.0000 |

## Hubungan antar-missing dan dengan target

| kolom | korelasi_missing_target | missing_terkait | korelasi_antar_missing |
| --- | --- | --- | --- |
| highest_education | 0.0350 | imd_band | 0.0294 |
| imd_band | 0.0096 | highest_education | 0.0294 |

Korelasi missing hanya menunjukkan asosiasi; MCAR/MAR/MNAR tidak dapat dipastikan dari data teramati saja.

## Distribusi numerik dan outlier

| kolom | min | median | max | mean | std | skew | kurtosis | outlier_IQR_pct | outlier_Z3_pct |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| num_of_prev_attempts | 0.0000 | 0.0000 | 6.0000 | 0.1629 | 0.4803 | 3.8560 | 20.1593 | 0.0000 | 2.6528 |
| studied_credits | 30.0000 | 60.0000 | 655.0000 | 79.7721 | 41.0279 | 1.9485 | 8.7371 | 1.0810 | 1.5947 |
| module_presentation_length | 234.0000 | 262.0000 | 269.0000 | 256.0286 | 13.1637 | -0.4077 | -1.6388 | 0.0000 | 0.0000 |
| registration_days_from_start | -322.0000 | -57.0000 | 167.0000 | -69.3848 | 49.2186 | -1.0053 | 1.0139 | 0.9852 | 0.8817 |
| assessments_due_total | 1.0000 | 1.0000 | 2.0000 | 1.0404 | 0.1969 | 4.6684 | 19.7957 | 0.0000 | 4.0405 |
| assessments_due_Assessment_1 | 0.0000 | 0.0000 | 1.0000 | 0.1772 | 0.3818 | 1.6910 | 0.8596 | 0.0000 | 0.0000 |
| assessments_due_Assessment_2 | 0.0000 | 1.0000 | 1.0000 | 0.8632 | 0.3436 | -2.1143 | 2.4703 | 0.0000 | 0.0000 |
| submitted_count | 1.0000 | 1.0000 | 2.0000 | 1.0273 | 0.1631 | 5.7981 | 31.6206 | 0.0000 | 2.7333 |
| late_submission_count | 0.0000 | 0.0000 | 2.0000 | 0.1638 | 0.3723 | 1.8636 | 1.6375 | 0.0000 | 0.0805 |
| avg_score | 0.0000 | 77.0000 | 100.0000 | 74.0468 | 17.5917 | -2.1492 | 6.4252 | 19.4970 | 3.0898 |
| median_score | 0.0000 | 77.0000 | 100.0000 | 74.0468 | 17.5917 | -2.1492 | 6.4252 | 19.4970 | 3.0898 |
| max_score | 0.0000 | 77.0000 | 100.0000 | 74.2173 | 17.5736 | -2.1644 | 6.5256 | 23.8825 | 3.0859 |
| min_score | 0.0000 | 77.0000 | 100.0000 | 73.8763 | 17.7058 | -2.1179 | 6.1976 | 19.7424 | 3.1013 |
| score_std | 0.0000 | 0.0000 | 27.5000 | 0.1705 | 1.3017 | 9.7683 | 112.0824 | 0.0000 | 1.5794 |
| avg_submission_delay | -25.0000 | -1.0000 | 16.0000 | -1.1060 | 2.9451 | -2.1129 | 10.6444 | 26.0561 | 2.7908 |
| median_submission_delay | -25.0000 | -1.0000 | 16.0000 | -1.1060 | 2.9451 | -2.1129 | 10.6444 | 26.0561 | 2.7908 |
| max_submission_delay | -25.0000 | -1.0000 | 16.0000 | -1.0435 | 2.9706 | -2.0852 | 10.3624 | 28.4712 | 2.7831 |
| min_submission_delay | -25.0000 | -1.0000 | 16.0000 | -1.1684 | 2.9971 | -2.1134 | 10.3710 | 26.6120 | 2.3423 |
| weighted_score_total | 0.0000 | 4.2500 | 12.5000 | 4.9468 | 2.9850 | 0.6709 | -0.1200 | 5.3055 | 0.0000 |
| score_trend | -23.0000 | 0.0000 | 27.5000 | 0.0581 | 1.3115 | 5.1407 | 112.8139 | 0.0000 | 1.7136 |
| score_Assessment_2 | 0.0000 | 77.0000 | 100.0000 | 75.0128 | 15.3857 | -2.7094 | 10.7288 | 39.4158 | 2.5646 |
| weighted_score_Assessment_2 | 0.0000 | 6.0000 | 12.5000 | 6.0626 | 2.5602 | -0.0082 | 0.6936 | 47.6194 | 0.0000 |
| submission_delay_Assessment_2 | -25.0000 | -1.0000 | 16.0000 | -1.5380 | 2.7146 | -2.7239 | 14.8308 | 0.0000 | 3.2815 |
| submitted_Assessment_2 | 1.0000 | 1.0000 | 1.0000 | 1.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0000 |
| score_Assessment_1 | 0.0000 | 70.0000 | 100.0000 | 69.7852 | 8.8807 | -2.4565 | 20.3703 | 0.0000 | 4.0520 |
| weighted_score_Assessment_1 | 0.0000 | 1.4000 | 2.0000 | 1.3957 | 0.1776 | -2.4565 | 20.3703 | 0.0000 | 4.0520 |
| submission_delay_Assessment_1 | 2.0000 | 2.0000 | 9.0000 | 2.0590 | 0.2522 | 6.5599 | 96.1545 | 0.0000 | 5.7579 |
| submitted_Assessment_1 | 1.0000 | 1.0000 | 1.0000 | 1.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0000 |
| assessment_completion_rate_Assessment_2 | 0.0000 | 1.0000 | 1.0000 | 0.5117 | 0.4999 | -0.0466 | -1.9980 | 0.0000 | 0.0000 |
| assessment_completion_rate_Assessment_1 | 0.0000 | 0.0000 | 1.0000 | 0.1309 | 0.3373 | 2.1886 | 2.7901 | 0.0000 | 0.0000 |
| assessment_completion_rate | 0.0000 | 1.0000 | 1.0000 | 0.6131 | 0.4859 | -0.4644 | -1.7797 | 0.0000 | 0.0000 |
| no_submission_by_cutoff | 0.0000 | 0.0000 | 1.0000 | 0.2190 | 0.4136 | 1.3587 | -0.1540 | 0.0000 | 0.0000 |
| has_score | 0.0000 | 1.0000 | 1.0000 | 0.6149 | 0.4866 | -0.4722 | -1.7771 | 0.0000 | 0.0000 |
| interaction_volume | 1.0000 | 182.0000 | 4944.0000 | 270.1168 | 310.1409 | 3.5598 | 22.1210 | 7.5596 | 1.8937 |
| active_days | 1.0000 | 10.0000 | 29.0000 | 10.9618 | 6.6923 | 0.7034 | -0.0735 | 0.9699 | 0.0000 |
| unique_sites | 1.0000 | 20.0000 | 159.0000 | 23.4395 | 15.7750 | 1.3908 | 2.7312 | 4.9682 | 1.2804 |
| unique_activity_types | 1.0000 | 7.0000 | 14.0000 | 6.7788 | 2.0727 | -0.2561 | 0.2185 | 3.9600 | 0.0805 |
| avg_daily_interactions | 1.0000 | 18.8481 | 274.6667 | 21.7400 | 14.4269 | 2.3996 | 13.5910 | 5.1905 | 1.5947 |
| max_daily_interactions | 1.0000 | 55.0000 | 4114.0000 | 68.5816 | 62.7461 | 13.3912 | 708.7167 | 4.7727 | 1.1615 |
| interaction_variability | 0.0000 | 16.2025 | 932.6655 | 19.4962 | 16.7073 | 9.0521 | 376.7264 | 4.6922 | 1.1500 |
| first_activity_day | 0.0000 | 1.0000 | 28.0000 | 2.8285 | 4.3966 | 2.6198 | 7.4309 | 11.6384 | 2.8636 |
| last_activity_day | 0.0000 | 26.0000 | 28.0000 | 24.1525 | 5.4011 | -2.3217 | 5.4145 | 14.7627 | 2.8828 |
| week1_interactions | 0.0000 | 36.0000 | 4385.0000 | 66.8001 | 102.6051 | 6.8498 | 151.4414 | 8.4068 | 1.7634 |
| week2_interactions | 0.0000 | 31.0000 | 1350.0000 | 59.4950 | 87.2820 | 3.7059 | 22.7639 | 8.8438 | 2.0356 |
| week3_interactions | 0.0000 | 46.0000 | 1642.0000 | 77.5673 | 99.7787 | 3.0939 | 17.0906 | 6.7776 | 2.0241 |
| week4_interactions | 0.0000 | 28.0000 | 2346.0000 | 60.3809 | 95.9122 | 4.2628 | 35.6248 | 8.9895 | 2.0356 |
| interaction_trend | -1323.0000 | -0.3000 | 679.9000 | -0.0326 | 31.5737 | -2.5994 | 143.6321 | 14.9774 | 1.8286 |
| early_interactions | 0.0000 | 78.0000 | 4733.0000 | 127.8709 | 167.8811 | 4.3439 | 43.4595 | 8.1193 | 1.8746 |
| late_interactions | 0.0000 | 89.0000 | 2531.0000 | 140.0971 | 172.8406 | 3.4099 | 20.2604 | 7.4331 | 1.9627 |
| late_to_early_interactions_ratio | 0.0000 | 0.9041 | 644.0000 | 2.6629 | 11.6107 | 19.0305 | 612.9049 | 11.2359 | 1.0389 |
| avg_interactions_per_active_day | 1.0000 | 18.8481 | 274.6667 | 21.7400 | 14.4269 | 2.3996 | 13.5910 | 5.1905 | 1.5947 |
| active_weeks | 1.0000 | 4.0000 | 4.0000 | 3.4340 | 0.9200 | -1.4848 | 0.9962 | 6.7737 | 0.0000 |
| avg_interactions_per_active_week | 1.0000 | 52.5000 | 1236.0000 | 73.7238 | 77.1457 | 3.5184 | 21.8150 | 7.5404 | 1.9014 |
| activity_span_days | 0.0000 | 24.0000 | 28.0000 | 21.1808 | 7.4837 | -1.5772 | 1.5835 | 9.7984 | 0.0000 |

## Duplikat

| duplikat_baris_penuh | duplikat_ID_train | duplikat_ID_test | duplikat_fitur_tanpa_ID_target |
| --- | --- | --- | --- |
| 0 | 0 | 0 | 4 |

## Fitur konstan

submitted_Assessment_2, submitted_Assessment_1

## Fitur hampir konstan

_Tidak ada._

## Kategorikal berkardinalitas tinggi

_Tidak ada._

## Distribusi target

| at_risk | jumlah | persen |
| --- | --- | --- |
| 0 | 12333 | 47.2782 |
| 1 | 13753 | 52.7218 |

## Drift train–test

| kolom | metrik | statistik | delta_missing_pp | indikasi_drift |
| --- | --- | --- | --- | --- |
| highest_education | total_variation | 0.4395 | -0.0237 | True |
| code_module | total_variation | 0.0634 | 0.0000 | False |
| min_score | KS | 0.0245 | 0.0000 | False |
| avg_score | KS | 0.0241 | 0.0000 | False |
| median_score | KS | 0.0241 | 0.0000 | False |
| max_score | KS | 0.0239 | 0.0000 | False |
| weighted_score_total | KS | 0.0225 | 0.0000 | False |
| has_score | KS | 0.0203 | 0.0000 | False |
| assessment_completion_rate | KS | 0.0200 | 0.0000 | False |
| score_Assessment_2 | KS | 0.0198 | 0.0000 | False |
| interaction_trend | KS | 0.0187 | 0.0000 | False |
| imd_band | total_variation | 0.0183 | 0.1040 | False |
| weighted_score_Assessment_2 | KS | 0.0174 | 0.0000 | False |
| region | total_variation | 0.0170 | 0.0000 | False |
| late_to_early_interactions_ratio | KS | 0.0166 | 0.0000 | False |
| max_submission_delay | KS | 0.0160 | 0.0000 | False |
| median_submission_delay | KS | 0.0146 | 0.0000 | False |
| avg_submission_delay | KS | 0.0146 | 0.0000 | False |
| assessment_completion_rate_Assessment_2 | KS | 0.0132 | 0.0000 | False |
| min_submission_delay | KS | 0.0131 | 0.0000 | False |
| activity_span_days | KS | 0.0124 | 0.0000 | False |
| unique_sites | KS | 0.0122 | 0.0000 | False |
| late_interactions | KS | 0.0115 | 0.0000 | False |
| interaction_variability | KS | 0.0111 | 0.0000 | False |
| week3_interactions | KS | 0.0104 | 0.0000 | False |
| max_daily_interactions | KS | 0.0102 | 0.0000 | False |
| week4_interactions | KS | 0.0100 | 0.0000 | False |
| last_activity_day | KS | 0.0099 | 0.0000 | False |
| no_submission_by_cutoff | KS | 0.0097 | 0.0000 | False |
| unique_activity_types | KS | 0.0090 | 0.0000 | False |
| active_days | KS | 0.0089 | 0.0000 | False |
| interaction_volume | KS | 0.0084 | 0.0000 | False |
| module_presentation_length | KS | 0.0082 | 0.0000 | False |
| studied_credits | KS | 0.0081 | 0.0000 | False |
| assessment_completion_rate_Assessment_1 | KS | 0.0079 | 0.0000 | False |
| gender | total_variation | 0.0076 | 0.0000 | False |
| code_presentation | total_variation | 0.0076 | 0.0000 | False |
| avg_daily_interactions | KS | 0.0076 | 0.0000 | False |
| avg_interactions_per_active_day | KS | 0.0076 | 0.0000 | False |
| first_activity_day | KS | 0.0073 | 0.0000 | False |
| week2_interactions | KS | 0.0072 | 0.0000 | False |
| early_interactions | KS | 0.0071 | 0.0000 | False |
| avg_interactions_per_active_week | KS | 0.0069 | 0.0000 | False |
| registration_days_from_start | KS | 0.0069 | 0.0000 | False |
| submission_delay_Assessment_2 | KS | 0.0063 | 0.0000 | False |
| assessments_due_Assessment_1 | KS | 0.0057 | 0.0000 | False |
| week1_interactions | KS | 0.0053 | 0.0000 | False |
| disability | total_variation | 0.0045 | 0.0000 | False |
| score_Assessment_1 | KS | 0.0041 | 0.0000 | False |
| weighted_score_Assessment_1 | KS | 0.0041 | 0.0000 | False |
| late_submission_count | KS | 0.0040 | 0.0000 | False |
| assessments_due_Assessment_2 | KS | 0.0036 | 0.0000 | False |
| active_weeks | KS | 0.0032 | 0.0000 | False |
| assessments_due_total | KS | 0.0021 | 0.0000 | False |
| age_band | total_variation | 0.0014 | 0.0000 | False |
| score_std | KS | 0.0013 | 0.0000 | False |
| num_of_prev_attempts | KS | 0.0013 | 0.0000 | False |
| score_trend | KS | 0.0012 | 0.0000 | False |
| submitted_count | KS | 0.0010 | 0.0000 | False |
| submission_delay_Assessment_1 | KS | 0.0009 | 0.0000 | False |
| submitted_Assessment_2 | KS | 0.0000 | 0.0000 | False |
| submitted_Assessment_1 | KS | 0.0000 | 0.0000 | False |

## Rekomendasi cleaning dan imputasi per kolom

| kolom | peran | missing_efektif_pct | imputasi | indikator_missing | aksi |
| --- | --- | --- | --- | --- | --- |
| id | ID | 0.0000 | tidak perlu | False | pisahkan sebagai ID |
| code_module | kategorikal | 0.0000 | tidak perlu | False | standarkan format kategori; pertahankan kategori baru sebagai unknown |
| code_presentation | kategorikal | 0.0000 | tidak perlu | False | standarkan format kategori; pertahankan kategori baru sebagai unknown |
| gender | kategorikal | 0.0000 | tidak perlu | False | standarkan format kategori; pertahankan kategori baru sebagai unknown |
| region | kategorikal | 0.0000 | tidak perlu | False | standarkan format kategori; pertahankan kategori baru sebagai unknown |
| highest_education | kategorikal | 1.0695 | kategori Missing | False | standarkan format kategori; pertahankan kategori baru sebagai unknown |
| imd_band | kategorikal | 14.1685 | kategori Missing | True | standarkan format kategori; pertahankan kategori baru sebagai unknown |
| age_band | kategorikal | 0.0000 | tidak perlu | False | standarkan format kategori; pertahankan kategori baru sebagai unknown |
| num_of_prev_attempts | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| studied_credits | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| disability | kategorikal | 0.0000 | tidak perlu | False | standarkan format kategori; pertahankan kategori baru sebagai unknown |
| module_presentation_length | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| registration_days_from_start | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| assessments_due_total | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| assessments_due_Assessment_1 | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| assessments_due_Assessment_2 | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| submitted_count | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| late_submission_count | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| avg_score | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| median_score | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| max_score | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| min_score | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| score_std | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| avg_submission_delay | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| median_submission_delay | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| max_submission_delay | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| min_submission_delay | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| weighted_score_total | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| score_trend | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| score_Assessment_2 | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| weighted_score_Assessment_2 | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| submission_delay_Assessment_2 | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| submitted_Assessment_2 | numerik | 0.0000 | tidak perlu | False | hapus fitur konstan |
| score_Assessment_1 | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| weighted_score_Assessment_1 | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| submission_delay_Assessment_1 | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| submitted_Assessment_1 | numerik | 0.0000 | tidak perlu | False | hapus fitur konstan |
| assessment_completion_rate_Assessment_2 | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| assessment_completion_rate_Assessment_1 | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| assessment_completion_rate | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| no_submission_by_cutoff | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| has_score | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| interaction_volume | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| active_days | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| unique_sites | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| unique_activity_types | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| avg_daily_interactions | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| max_daily_interactions | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| interaction_variability | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| first_activity_day | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| last_activity_day | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| week1_interactions | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| week2_interactions | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| week3_interactions | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| week4_interactions | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| interaction_trend | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| early_interactions | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| late_interactions | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| late_to_early_interactions_ratio | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| avg_interactions_per_active_day | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| active_weeks | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| avg_interactions_per_active_week | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| activity_span_days | numerik | 0.0000 | tidak perlu | False | pertahankan; tinjau nilai dominan dan inkonsistensi |
| at_risk | target | 0.0000 | tidak perlu | False | pisahkan sebagai label |

Nilai dominan dan pelanggaran konsistensi perlu ditinjau sebelum diubah menjadi missing.
