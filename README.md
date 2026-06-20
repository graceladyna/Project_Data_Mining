# Graph-Based Movie Recommendation System

## Deskripsi

Proyek ini merupakan implementasi sistem rekomendasi film berbasis graph menggunakan dataset MovieLens 100K. Sistem dibangun dengan memanfaatkan hubungan similarity antar pengguna (user-user graph) dan metode Weighted Recommendation Score untuk menghasilkan rekomendasi film yang lebih personal. Evaluasi dilakukan menggunakan Precision@10, Recall@10, dan Coverage untuk menganalisis pengaruh threshold similarity terhadap kualitas rekomendasi.

## Tujuan

* Membangun graph hubungan antar pengguna berdasarkan similarity.
* Menghasilkan rekomendasi film menggunakan Weighted Recommendation Score.
* Menganalisis pengaruh threshold similarity terhadap kualitas rekomendasi.
* Mengevaluasi performa sistem menggunakan Precision@10, Recall@10, dan Coverage.

## Teknologi yang Digunakan

* Python
* Pandas
* NumPy
* NetworkX
* Scikit-Learn
* Matplotlib
* Seaborn
* Jupyter Notebook

## Dataset

Dataset yang digunakan adalah [MovieLens 100K](https://grouplens.org/datasets/movielens/100k/).

| Keterangan     |  Jumlah |
| -------------- | ------: |
| User           |     943 |
| Movie          |   1.682 |
| Rating         | 100.000 |
| Rentang Rating |     1–5 |

## Metodologi

1. Data Understanding
2. Data Preprocessing
3. Similarity Matrix
4. Graph Construction
5. Community Detection
6. Recommendation System
7. Evaluation

## Graph Construction

Graph dibangun menggunakan pendekatan User-User Similarity Graph.

### Node

* User

### Edge

* Similarity antar pengguna

### Threshold Similarity

* 0.15
* 0.20
* 0.25

## Recommendation System

Metode rekomendasi menggunakan Weighted Recommendation Score:

Score(i)=Σ(sim(u,v)×rating(v,i))/Σ(sim(u,v))

dengan:

* sim(u,v): similarity antara user target dan neighbor.
* rating(v,i): rating film yang diberikan neighbor.

Sistem juga melakukan filtering terhadap film yang sudah pernah ditonton pengguna sehingga hanya film baru yang direkomendasikan.

## Top-K Neighbor

* Top-K Neighbor = 20

Rekomendasi dibentuk berdasarkan 20 neighbor dengan nilai similarity tertinggi terhadap pengguna target.

## Evaluation Metrics

### Precision@10

Mengukur proporsi film relevan yang muncul pada daftar rekomendasi.

### Recall@10

Mengukur kemampuan sistem dalam menemukan film relevan pengguna.

### Coverage

Mengukur persentase pengguna yang berhasil memperoleh rekomendasi.

## Hasil Evaluasi

| Threshold | Precision@10 | Recall@10 | Coverage |
| --------- | -----------: | --------: | -------: |
| 0.15      |       0.0452 |    0.0550 |   0.9894 |
| 0.20      |       0.0877 |    0.1133 |   0.8441 |
| 0.25      |       0.1248 |    0.1985 |   0.5536 |

## Threshold Terbaik

Threshold 0.20 dipilih sebagai threshold terbaik karena memberikan keseimbangan yang baik antara kualitas rekomendasi dan jumlah pengguna yang masih memperoleh rekomendasi.

## Visualisasi

Visualisasi yang dihasilkan pada proyek ini meliputi:

* Distribusi Rating Pengguna
* Visualisasi Graph pada Berbagai Threshold
* Distribusi Komunitas User
* Dominasi Genre pada Setiap Komunitas
* Top-10 Movie Recommendation
* Precision@10 per Threshold
* Recall@10 per Threshold
* Coverage per Threshold

## Insight Utama

* Pengguna cenderung memberikan rating 3–5.
* Struktur graph berubah seiring peningkatan threshold similarity.
* Weighted Recommendation Score memberikan bobot lebih besar kepada neighbor yang lebih mirip.
* Threshold yang lebih tinggi meningkatkan Precision@10 dan Recall@10.
* Coverage menurun ketika threshold semakin tinggi karena jumlah neighbor berkurang.
* Threshold 0.20 memberikan trade-off terbaik antara kualitas rekomendasi dan coverage.

## Anggota Kelompok

- Jeika Antama Syalom Tarigan (24031554011)
- Alifiyanti Putri Nur Azizah (24031554032)
- Grace Pinkkan Ladyna (24031554137)
- 24031554171 - Astrid Septya Regita Pramesty

## Mata Kuliah

Penambangan Data – Program Studi S1 Sains Data

Universitas Negeri Surabaya

Tahun Akademik 2025/2026
