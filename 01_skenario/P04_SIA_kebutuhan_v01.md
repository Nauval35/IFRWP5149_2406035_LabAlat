# Pertemuan 4 — Sistem Informasi Akademik, Layanan Hasil Studi

## 1. Kebutuhan Tugas

| ID | Kebutuhan Tugas |
|---|---|
| SIA-R07 | Mahasiswa dan Dosen sebagai bagian dari Civitas Akademika dapat mengakses dan melihat kalender akademik. |
| SIA-R08 | Dosen dapat memasukkan nilai untuk mata kuliah yang menjadi tanggung jawabnya. |
| SIA-R09 | Mahasiswa dapat melihat Kartu Hasil Studi (KHS) pada semester yang nilai akhirnya telah dipublikasikan. |
| SIA-R10 | Admin Akademik dapat melakukan pengelolaan terhadap data mahasiswa. |
| SIA-R11 | Pengelolaan data mahasiswa mencakup tiga fungsi utama, yaitu menambahkan, mengubah, dan menghapus data mahasiswa. |
| SIA-R12 | Model sistem menunjukkan adanya collaboration yang merealisasikan proses Input Nilai Mata Kuliah dan Lihat KHS. |

## 2. Batas Sistem

Sistem yang menjadi fokus analisis dalam tugas ini adalah **Sistem Informasi Akademik (SIA)**. Kalender akademik yang ditampilkan melalui sistem mengacu pada agenda resmi yang telah ditetapkan oleh institusi.

Proses penginputan nilai hanya dapat dilakukan oleh dosen yang mengampu mata kuliah terkait. Mahasiswa hanya diberikan akses untuk melihat Kartu Hasil Studi (KHS) pada semester yang nilai akhirnya telah dipublikasikan.

Penghapusan data mahasiswa hanya dapat dilakukan terhadap mahasiswa yang tidak memiliki data akademik yang masih aktif. Proses pengajuan Kartu Rencana Studi (KRS) tetap ditampilkan sebagai bagian dari diagram kumulatif yang telah dibuat pada Pertemuan 3.

Adapun proses pembayaran serta perancangan basis data tidak termasuk dalam ruang lingkup analisis pada tugas ini.

## 3. Asumsi

Dalam analisis ini diasumsikan bahwa setiap pengguna telah melakukan login ke dalam sistem dan memiliki hak akses sesuai dengan peran masing-masing.

Data mengenai kalender akademik diasumsikan telah tersedia di dalam sistem sehingga dapat diakses oleh civitas akademika. Selain itu, data mata kuliah dan dosen pengampu telah tersedia sebelum proses penginputan nilai dilakukan.

Nilai yang dimasukkan oleh dosen belum dianggap sebagai nilai resmi atau final sebelum melalui proses publikasi sesuai dengan ketentuan yang berlaku di institusi. KHS yang dapat diakses oleh mahasiswa hanya menampilkan nilai dari semester yang telah dipublikasikan.

Admin Akademik diasumsikan memiliki kewenangan untuk menambahkan, mengubah, dan menghapus data mahasiswa sesuai dengan aturan serta batas kewenangan yang telah ditetapkan.