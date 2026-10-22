# Pertemuan 4 — Sistem Informasi Akademik, Layanan Hasil Studi

## Langkah 1 — Mencatat Kebutuhan dan Batas Sistem

Tugas pada Pertemuan 4 memiliki pembahasan yang berbeda dari pertemuan sebelumnya. Pada Pertemuan 2, pembahasan berfokus pada jadwal kuliah, sedangkan Pertemuan 3 membahas proses pengajuan Kartu Rencana Studi (KRS). Adapun Pertemuan 4 berfokus pada layanan hasil studi dengan menerapkan teknik *generalization* dan *collaboration* pada skenario baru.

Skenario yang digunakan dalam praktikum ini bersifat fiktif dan dibuat untuk menerapkan konsep pemodelan sistem. Mahasiswa dan dosen termasuk dalam kelompok Civitas Akademika yang memiliki hak untuk melihat kalender akademik. Dosen bertugas memasukkan nilai untuk mata kuliah yang diampunya setelah kegiatan perkuliahan selesai. Sementara itu, mahasiswa dapat melihat Kartu Hasil Studi (KHS) apabila nilai pada semester yang dipilih telah dipublikasikan.

Admin Akademik memiliki tanggung jawab untuk mengelola data mahasiswa, meliputi penambahan data mahasiswa baru, perubahan data, dan penghapusan data sesuai ketentuan. Selain itu, use case **Input Nilai Mata Kuliah** dan **Lihat KHS** perlu direalisasikan melalui collaboration yang sesuai.

### A. Kebutuhan Tugas

| ID | Kebutuhan Tugas |
|---|---|
| SIA-R07 | Mahasiswa dan Dosen sebagai bagian dari Civitas Akademika dapat mengakses dan melihat kalender akademik. |
| SIA-R08 | Dosen dapat memasukkan nilai untuk mata kuliah yang menjadi tanggung jawabnya. |
| SIA-R09 | Mahasiswa dapat melihat Kartu Hasil Studi (KHS) pada semester yang nilai akhirnya telah dipublikasikan. |
| SIA-R10 | Admin Akademik dapat melakukan pengelolaan terhadap data mahasiswa. |
| SIA-R11 | Pengelolaan data mahasiswa mencakup tiga fungsi utama, yaitu menambahkan, mengubah, dan menghapus data mahasiswa. |
| SIA-R12 | Model sistem menunjukkan adanya collaboration yang merealisasikan proses Input Nilai Mata Kuliah dan Lihat KHS. |

### B. Batas Sistem

Sistem yang menjadi fokus analisis pada tugas ini adalah Sistem Informasi Akademik (SIA). Kalender akademik yang tersedia di dalam sistem mengacu pada agenda resmi yang telah ditetapkan oleh institusi.

Penginputan nilai hanya dapat dilakukan oleh dosen yang mengampu mata kuliah terkait. Mahasiswa hanya diperbolehkan melihat KHS pada semester yang nilai akhirnya sudah dipublikasikan.

Penghapusan data mahasiswa dibatasi pada mahasiswa yang tidak memiliki data akademik aktif. Proses pengajuan KRS tetap dicantumkan sebagai bagian dari diagram kumulatif yang telah disusun pada Pertemuan 3.

Sementara itu, proses pembayaran dan perancangan basis data tidak termasuk dalam cakupan pembahasan tugas ini.

### C. Asumsi

Dalam pemodelan ini, setiap pengguna diasumsikan sudah masuk ke sistem dan memiliki hak akses sesuai dengan perannya masing-masing.

Informasi kalender akademik telah tersedia di dalam sistem dan dapat diakses oleh pengguna yang berwenang. Data mata kuliah serta dosen pengampu juga sudah tersedia sebelum proses penginputan nilai dimulai.

Nilai yang dimasukkan dosen belum dianggap resmi sebelum dipublikasikan berdasarkan ketentuan institusi. KHS yang ditampilkan kepada mahasiswa hanya mencakup semester yang nilainya telah dipublikasikan.

Admin Akademik diasumsikan memiliki kewenangan untuk menambahkan, memperbarui, dan menghapus data mahasiswa sesuai dengan aturan serta batas kewenangan yang berlaku.

---

## Langkah 2 — Identifikasi Aktor dan Use Case

### A. Katalog Use Case

| ID | Nama Use Case | Aktor Terkait | Sumber Kebutuhan | Status |
|---|---|---|---|---|
| SIA-UC01 | Lihat Jadwal Kuliah | Mahasiswa | SIA-R01 | Tetap |
| SIA-UC02 | Kelola Jadwal Kuliah | Admin Akademik | SIA-R02 | Tetap |
| SIA-UC03 | Ajukan KRS | Mahasiswa | SIA-R03 | Tetap |
| SIA-UC04 | Validasi KRS | Sistem (bagian dari pengajuan) | SIA-R04 | Tetap |
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Mahasiswa | SIA-R05 | Tetap |
| SIA-UC06 | Proses Keputusan KRS | Dosen Wali | SIA-R06 | Tetap |
| SIA-UC07 | Lihat Kalender Akademik | Civitas Akademika | SIA-R07 | Baru |
| SIA-UC08 | Input Nilai Mata Kuliah | Dosen | SIA-R08 | Baru |
| SIA-UC09 | Lihat KHS | Mahasiswa | SIA-R09 | Baru |
| SIA-UC10 | Kelola Data Mahasiswa | Admin Akademik | SIA-R10 | Baru |
| SIA-UC11 | Tambah Data Mahasiswa | Admin Akademik | SIA-R11 | Baru |
| SIA-UC12 | Ubah Data Mahasiswa | Admin Akademik | SIA-R11 | Baru |
| SIA-UC13 | Hapus Data Mahasiswa | Admin Akademik | SIA-R11 | Baru |

### B. Daftar Aktor

| Nama Aktor | Jenis | Keterangan |
|---|---|---|
| Civitas Akademika | Aktor umum | Memiliki akses untuk melihat kalender akademik. |
| Mahasiswa | Aktor khusus | Dapat melihat jadwal kuliah, mengajukan KRS, mengunduh bukti pengajuan, serta melihat KHS. |
| Dosen | Aktor khusus | Dapat memasukkan nilai mata kuliah yang diampu dan mengakses kalender akademik. |
| Admin Akademik | Aktor utama | Bertanggung jawab atas pengelolaan jadwal kuliah dan data mahasiswa. |
| Dosen Wali | Aktor utama | Bertugas memproses keputusan terkait pengajuan KRS mahasiswa. |

### C. Catatan Identifikasi

Katalog use case pada Pertemuan 4 menggabungkan fungsi yang telah dibuat pada Pertemuan 2 dan Pertemuan 3 dengan beberapa fungsi baru. ID SIA-UC01 hingga SIA-UC06 tetap dipertahankan, sedangkan fungsi tambahan menggunakan ID SIA-UC07 hingga SIA-UC13.

SIA-UC10 Kelola Data Mahasiswa merupakan use case umum. Adapun SIA-UC11 Tambah Data Mahasiswa, SIA-UC12 Ubah Data Mahasiswa, dan SIA-UC13 Hapus Data Mahasiswa merupakan use case khusus. Hubungan generalization antara fungsi-fungsi tersebut ditentukan pada langkah berikutnya.

---

## Langkah 3 — Menentukan Generalization Aktor

### A. Hierarki Aktor

| Aktor Umum | Aktor Khusus | Fungsi yang Diwarisi | Dasar Pemodelan |
|---|---|---|---|
| Civitas Akademika | Mahasiswa | Lihat Kalender Akademik | Mahasiswa merupakan bagian dari civitas akademika dan memiliki hak melihat kalender akademik. |
| Civitas Akademika | Dosen | Lihat Kalender Akademik | Dosen termasuk civitas akademika dan dapat menggunakan fungsi melihat kalender akademik. |

### B. Penjelasan Generalization

Civitas Akademika digunakan sebagai aktor umum karena fungsi melihat kalender akademik dapat digunakan oleh mahasiswa maupun dosen. Kedua aktor tersebut menjadi aktor khusus yang mewarisi fungsi dari aktor umum.

Dengan menggunakan generalization, hubungan dengan use case Lihat Kalender Akademik cukup dihubungkan melalui aktor Civitas Akademika. Mahasiswa dan Dosen tetap dapat menggunakan fungsi tersebut melalui hubungan pewarisan sehingga asosiasi yang sama tidak perlu digambarkan berulang kali.

---

## Langkah 4 — Menentukan Generalization Use Case

### A. Hierarki Use Case

| Use Case Umum | Use Case Khusus | Fungsi yang Diwarisi | Dasar Pemodelan |
|---|---|---|---|
| SIA-UC10 Kelola Data Mahasiswa | SIA-UC11 Tambah Data Mahasiswa | Fungsi umum pengelolaan data mahasiswa | Penambahan data termasuk salah satu kegiatan dalam pengelolaan data mahasiswa. |
| SIA-UC10 Kelola Data Mahasiswa | SIA-UC12 Ubah Data Mahasiswa | Fungsi umum pengelolaan data mahasiswa | Perubahan informasi merupakan bagian dari pengelolaan data mahasiswa. |
| SIA-UC10 Kelola Data Mahasiswa | SIA-UC13 Hapus Data Mahasiswa | Fungsi umum pengelolaan data mahasiswa | Penghapusan data merupakan salah satu bentuk pengelolaan data mahasiswa. |

### B. Penjelasan Generalization

SIA-UC10 Kelola Data Mahasiswa ditetapkan sebagai use case umum karena mencakup pengelolaan data mahasiswa secara menyeluruh. Use case tersebut memiliki tiga fungsi khusus, yaitu SIA-UC11 Tambah Data Mahasiswa, SIA-UC12 Ubah Data Mahasiswa, dan SIA-UC13 Hapus Data Mahasiswa.

Ketiga fungsi khusus tersebut menjelaskan kegiatan pengelolaan data secara lebih terperinci. Generalization digunakan untuk menunjukkan hubungan antara fungsi umum dan fungsi khusus agar struktur model lebih mudah dipahami serta mengurangi pengulangan konsep yang sama.

### C. Ketentuan Penggambaran

| No. | Ketentuan |
|---|---|
| 1 | SIA-UC10 Kelola Data Mahasiswa digunakan sebagai use case umum. |
| 2 | SIA-UC11 Tambah Data Mahasiswa, SIA-UC12 Ubah Data Mahasiswa, dan SIA-UC13 Hapus Data Mahasiswa ditempatkan sebagai use case khusus. |
| 3 | Hubungan generalization digambarkan menggunakan garis utuh dengan ujung segitiga kosong yang mengarah ke use case umum SIA-UC10 Kelola Data Mahasiswa. |

---

## Langkah 5 — Menentukan Collaboration

### A. Daftar Collaboration

| ID Collaboration | Nama Collaboration | Use Case yang Direalisasikan | Aktor Terkait |
|---|---|---|---|
| SIA-CO01 | Input Nilai Mata Kuliah | SIA-UC08 Input Nilai Mata Kuliah | Dosen |
| SIA-CO02 | Lihat KHS | SIA-UC09 Lihat KHS | Mahasiswa |

### B. Penjelasan Collaboration

#### 1. SIA-CO01 — Input Nilai Mata Kuliah

Collaboration ini digunakan untuk menggambarkan pelaksanaan use case Input Nilai Mata Kuliah. Dosen memilih mata kuliah yang diampunya, kemudian memasukkan nilai mahasiswa. Sistem selanjutnya memeriksa data yang dimasukkan dan menyimpannya sesuai dengan ketentuan yang berlaku.

Nilai yang telah disimpan belum dapat dianggap resmi apabila belum melalui proses publikasi. Oleh karena itu, nilai tersebut belum dapat ditampilkan sebagai hasil studi resmi dalam KHS mahasiswa.

#### 2. SIA-CO02 — Lihat KHS

Collaboration ini menggambarkan proses pelaksanaan use case Lihat KHS. Mahasiswa memilih semester yang ingin dilihat, lalu sistem memeriksa status publikasi nilai pada semester tersebut.

Jika nilai sudah dipublikasikan, sistem mengambil dan menampilkan KHS mahasiswa. Sebaliknya, jika nilai belum dipublikasikan, sistem memberikan informasi bahwa KHS untuk semester tersebut belum tersedia.

### C. Hubungan Collaboration dengan Use Case

Nama setiap collaboration disesuaikan dengan use case yang direalisasikannya. SIA-CO01 merealisasikan SIA-UC08 Input Nilai Mata Kuliah, sedangkan SIA-CO02 merealisasikan SIA-UC09 Lihat KHS.

Kedua collaboration tersebut saling berkaitan karena nilai yang dimasukkan oleh dosen harus dipublikasikan terlebih dahulu sesuai dengan aturan institusi sebelum dapat dilihat mahasiswa melalui KHS.

---

## Langkah 6 — Menyusun Use Case Description

### A. SIA-UC08 — Input Nilai Mata Kuliah

| Elemen | Deskripsi |
|---|---|
| ID Use Case | SIA-UC08 |
| Nama Use Case | Input Nilai Mata Kuliah |
| Aktor Utama | Dosen |
| Tujuan | Memasukkan nilai mahasiswa pada mata kuliah yang diampu oleh dosen. |
| Prasyarat | Dosen sudah login, memiliki hak akses, serta data mata kuliah dan mahasiswa telah tersedia. |
| Pemicu | Dosen memilih menu input nilai mata kuliah. |

#### Alur Utama

| No. | Proses |
|---|---|
| 1 | Dosen membuka menu input nilai mata kuliah. |
| 2 | Sistem menampilkan daftar mata kuliah yang diampu dosen. |
| 3 | Dosen memilih mata kuliah yang akan dimasukkan nilainya. |
| 4 | Sistem menampilkan daftar mahasiswa yang mengikuti mata kuliah tersebut. |
| 5 | Dosen mengisikan nilai mahasiswa. |
| 6 | Dosen menyimpan nilai yang telah dimasukkan. |
| 7 | Sistem memeriksa kelengkapan dan keabsahan data nilai. |
| 8 | Jika data valid, sistem menyimpan nilai dan menampilkan pemberitahuan bahwa proses berhasil. |

#### Alur Alternatif

| Kondisi | Respons Sistem |
|---|---|
| Nilai yang dimasukkan belum lengkap atau tidak valid | Sistem menampilkan pesan kesalahan dan meminta dosen memperbaiki nilai tersebut. |
| Penyimpanan data mengalami kegagalan | Sistem memberi tahu bahwa nilai belum berhasil disimpan. |

#### Pascakondisi

| Kondisi | Hasil |
|---|---|
| Proses penyimpanan berhasil | Nilai tersimpan di dalam sistem. |
| Nilai telah tersimpan | Nilai belum otomatis berstatus resmi atau telah dipublikasikan. |
| Proses penyimpanan gagal | Perubahan nilai tidak dinyatakan berhasil disimpan. |

### B. SIA-UC09 — Lihat KHS

| Elemen | Deskripsi |
|---|---|
| ID Use Case | SIA-UC09 |
| Nama Use Case | Lihat KHS |
| Aktor Utama | Mahasiswa |
| Tujuan | Menampilkan Kartu Hasil Studi untuk semester yang nilainya telah dipublikasikan. |
| Prasyarat | Mahasiswa sudah login dan mempunyai data akademik pada semester yang dipilih. |
| Pemicu | Mahasiswa membuka menu Kartu Hasil Studi (KHS). |

#### Alur Utama

| No. | Proses |
|---|---|
| 1 | Mahasiswa membuka menu KHS. |
| 2 | Sistem menampilkan daftar semester yang tersedia. |
| 3 | Mahasiswa memilih semester yang ingin dilihat. |
| 4 | Sistem memeriksa status publikasi nilai pada semester tersebut. |
| 5 | Jika nilai sudah dipublikasikan, sistem mengambil data hasil studi mahasiswa. |
| 6 | Sistem menampilkan KHS sesuai semester yang dipilih. |

#### Alur Alternatif

| Kondisi | Respons Sistem |
|---|---|
| Nilai semester belum dipublikasikan | Sistem menampilkan pemberitahuan bahwa KHS belum tersedia. |
| Mahasiswa belum mempunyai data akademik pada semester tersebut | Sistem memberitahukan bahwa data KHS belum tersedia. |
| Terjadi kendala saat mengambil data | Sistem menampilkan informasi bahwa KHS belum dapat ditampilkan. |

#### Pascakondisi

| Kondisi | Hasil |
|---|---|
| Proses berhasil | KHS untuk semester yang dipilih dapat dilihat oleh mahasiswa. |
| Nilai belum dipublikasikan | KHS belum ditampilkan sebagai hasil studi yang tersedia. |
| Proses melihat KHS selesai | Tidak ada perubahan terhadap nilai akademik mahasiswa. |

---

## Langkah 7 — Membuat Diagram

Pembuatan diagram kumulatif dilakukan dengan mengikuti tahapan yang sama seperti pada Langkah 8 studi kasus sebelumnya. Tahap pertama adalah membuat salinan diagram SIA dari Pertemuan 3 tanpa mengubah berkas aslinya.

Setelah itu, tambahkan elemen secara bertahap, mulai dari aktor umum dan aktor khusus beserta hubungan generalization aktor, use case layanan hasil studi, use case pengelolaan data mahasiswa beserta generalization use case, hingga dua collaboration dan hubungan realization yang sesuai.

Hasil diagram disimpan pada folder `04_model_analisis/P04/SIA/` dengan nama file:

`P04_<2406035>_SIA_notasi_usecase_v01.drawio`

Diagram tersebut kemudian diekspor ke format PNG menggunakan nama versi yang sama. Diagram akhir harus memperlihatkan gabungan fungsi jadwal kuliah, pengajuan KRS, dan layanan hasil studi dalam satu model Sistem Informasi Akademik.

---

## Langkah 8 — Uji Konsistensi, Review, dan Revisi

### A. Uji Konsistensi

#### Situasi A — Mahasiswa Melihat Kalender Akademik Tanpa Asosiasi Langsung

**Hasil Pengujian:**

Mahasiswa tetap dapat mengakses fungsi melihat kalender akademik meskipun tidak terhubung langsung dengan use case tersebut. Hal ini karena Mahasiswa merupakan aktor khusus dari Civitas Akademika sehingga mewarisi fungsi melihat kalender akademik melalui hubungan generalization.

**Kesimpulan:**

Model dinilai konsisten apabila hubungan generalization antara Civitas Akademika dan Mahasiswa telah digambarkan dengan benar sehingga fungsi melihat kalender akademik dapat diwariskan.

#### Situasi B — Dosen yang Bukan Pengampu Mencoba Memasukkan Nilai

**Hasil Pengujian:**

Sistem menolak permintaan input nilai dari dosen yang tidak mengampu mata kuliah terkait. Sistem memberikan pemberitahuan bahwa dosen tersebut tidak mempunyai hak untuk memasukkan nilai pada mata kuliah yang dipilih.

**Kesimpulan:**

Model telah sesuai dengan aturan bahwa dosen hanya diperbolehkan memasukkan nilai untuk mata kuliah yang diampunya.

#### Situasi C — Admin Menghapus Data Mahasiswa yang Masih Memiliki Data Akademik Aktif

**Hasil Pengujian:**

Sistem menolak penghapusan data mahasiswa yang masih mempunyai data akademik aktif. Sistem menampilkan alasan penolakan agar data akademik mahasiswa tetap terlindungi.

**Kesimpulan:**

Model telah memenuhi batasan sistem karena data mahasiswa yang masih memiliki data akademik aktif tidak boleh dihapus.


