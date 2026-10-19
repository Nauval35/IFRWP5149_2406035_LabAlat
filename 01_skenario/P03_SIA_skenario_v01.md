# Kebutuhan Sistem Informasi Akademik

## 1. Kebutuhan Fungsional

| ID | Kebutuhan |
|---|---|
| SIA-R03 | Mahasiswa dapat melakukan pengajuan KRS. |
| SIA-R04 | Sistem melakukan pemeriksaan dan validasi terhadap KRS yang diajukan. |
| SIA-R05 | Mahasiswa dapat mengunduh bukti pengajuan apabila memilih opsi tersebut pada tahap konfirmasi. |
| SIA-R06 | Dosen wali dapat memberikan keputusan berupa persetujuan atau penolakan terhadap pengajuan KRS. |

## 2. Kebutuhan dari Pertemuan Sebelumnya

| ID | Kebutuhan |
|---|---|
| SIA-R01 | Mahasiswa dapat mengakses dan melihat jadwal perkuliahan. |
| SIA-R02 | Admin akademik dapat melakukan pengelolaan terhadap jadwal perkuliahan. |

## 3. Batasan dan Asumsi

1. Pengguna sudah melakukan autentikasi sebelum menggunakan sistem.
2. Informasi mengenai mata kuliah, prasyarat, serta jadwal perkuliahan telah tersedia di dalam sistem.
3. Apabila proses validasi tidak berhasil, pengajuan KRS tidak dianggap berhasil tersimpan.
4. Pengunduhan bukti pengajuan bersifat opsional dan tidak menentukan keberhasilan pengajuan KRS.
5. KRS yang telah berhasil disimpan masih berstatus menunggu persetujuan dosen wali.
6. Fitur pembayaran, penginputan nilai, serta penerapan atau implementasi basis data tidak termasuk dalam ruang lingkup tugas.

## 4. Alur Utama

1. Mahasiswa menentukan mata kuliah yang ingin dimasukkan ke dalam KRS.
2. Sistem melakukan validasi terhadap kelengkapan data, prasyarat mata kuliah, serta kemungkinan terjadinya benturan jadwal.
3. Apabila seluruh validasi berhasil, sistem menyimpan pengajuan KRS dengan status menunggu persetujuan dosen wali.
4. Sistem memberikan informasi bahwa pengajuan telah berhasil disimpan.
5. Mahasiswa menentukan apakah ingin mengunduh bukti pengajuan.
6. Dosen wali dapat memberikan keputusan terhadap KRS berupa persetujuan atau penolakan disertai catatan keputusan.

# Langkah 2 — Identifikasi Aktor dan Use Case

## A. Daftar Aktor

| No. | Nama Aktor | Deskripsi |
|---|---|---|
| 1 | Mahasiswa | Bertugas mengajukan KRS serta dapat memilih untuk mengunduh bukti pengajuan. |
| 2 | Dosen Wali | Bertugas memeriksa dan memberikan persetujuan atau penolakan terhadap pengajuan KRS serta mencatat alasan atau catatan keputusan. |

## B. Katalog Use Case

| ID | Nama Fungsi | Aktor Terkait | Sumber Kebutuhan |
|---|---|---|---|
| UC-01 | Ajukan KRS | Mahasiswa | SIA-R03 |
| UC-02 | Validasi KRS | Sistem, sebagai bagian dari proses pengajuan Mahasiswa | SIA-R04 |
| UC-03 | Unduh Bukti Pengajuan | Mahasiswa | SIA-R05 |
| UC-04 | Proses Keputusan KRS | Dosen Wali | SIA-R06 |

## C. Batasan Identifikasi

Proses identifikasi aktor dan use case dibatasi pada aktivitas pengajuan KRS, pemeriksaan atau validasi pengajuan, pengunduhan bukti, serta pemberian keputusan oleh dosen wali. Sementara itu, SIA-R01 dan SIA-R02 tetap dicatat sebagai kebutuhan yang berasal dari Pertemuan 2, tetapi tidak dijadikan fungsi utama dalam katalog use case pada pembahasan ini.

# Langkah 3 — Menentukan Include

## Relasi Include

- **Sumber:** UC-01 — Ajukan KRS
- **Tujuan:** UC-02 — Validasi KRS
- **Aktivitas yang disertakan:** Melakukan pemeriksaan kelengkapan pengajuan, pengecekan prasyarat mata kuliah, serta pemeriksaan kemungkinan benturan jadwal.

## Alasan Penggunaan Relasi

Relasi `<<include>>` diterapkan karena proses validasi merupakan tahapan yang wajib dilakukan setiap kali mahasiswa melakukan pengajuan KRS. Pengajuan tidak dapat dianggap berhasil apabila proses validasi tidak memenuhi persyaratan yang telah ditentukan.

# Langkah 4 — Menentukan Extend

## Relasi Extend

- **Sumber:** UC-03 — Unduh Bukti Pengajuan
- **Tujuan:** UC-01 — Ajukan KRS
- **Kondisi:** Pengajuan KRS telah berhasil disimpan, sistem telah menampilkan konfirmasi, dan mahasiswa memilih opsi untuk mengunduh bukti.
- **Aktivitas tambahan:** Sistem menyediakan bukti pengajuan KRS agar dapat diunduh oleh mahasiswa.

## Alasan Penggunaan Relasi

Relasi `<<extend>>` digunakan karena aktivitas mengunduh bukti bukan merupakan bagian wajib dari proses pengajuan KRS. Setelah pengajuan berhasil, mahasiswa memiliki pilihan untuk mengunduh bukti atau melewati aktivitas tersebut. Dengan demikian, pengajuan tetap dinyatakan berhasil meskipun mahasiswa tidak melakukan pengunduhan.


# Langkah 6 — Diagram Use Case

Diagram use case akan menggunakan dua aktor dan empat use case utama, yaitu:

| Jenis | Nama |
|---|---|
| Aktor | Mahasiswa |
| Aktor | Dosen Wali |
| Use Case | UC-01 — Ajukan KRS |
| Use Case | UC-02 — Validasi KRS |
| Use Case | UC-03 — Unduh Bukti Pengajuan |
| Use Case | UC-04 — Proses Keputusan KRS |

Pada diagram, UC-02 memiliki relasi `<<include>>` terhadap UC-01 karena proses validasi wajib dilakukan ketika KRS diajukan. Sementara itu, UC-03 memiliki relasi `<<extend>>` terhadap UC-01 karena pengunduhan bukti hanya dilakukan apabila mahasiswa memilih opsi tersebut setelah pengajuan berhasil.

# Langkah 7 — Pengujian Konsistensi

## a. Validasi Berhasil dan Mahasiswa Tidak Mengunduh Bukti

Ketika seluruh persyaratan KRS terpenuhi, proses validasi dinyatakan berhasil. Sistem kemudian menyimpan pengajuan KRS dengan status menunggu persetujuan dosen wali dan menampilkan konfirmasi kepada mahasiswa. Apabila mahasiswa tidak memilih opsi untuk mengunduh bukti, proses pengunduhan tidak dijalankan.

**Hasil pengujian:** Konsisten. UC-01 — Ajukan KRS tetap dapat dinyatakan berhasil meskipun UC-03 — Unduh Bukti Pengajuan tidak dijalankan. Hal tersebut sesuai dengan sifat `<<extend>>` yang menunjukkan bahwa pengunduhan bukti merupakan aktivitas tambahan atau opsional.

## b. Validasi Gagal

Apabila ditemukan ketidaksesuaian, seperti benturan jadwal atau prasyarat mata kuliah yang belum terpenuhi, sistem menyatakan bahwa proses validasi gagal. Sistem kemudian menampilkan informasi mengenai penyebab kegagalan dan pengajuan tidak disimpan sebagai pengajuan yang berhasil.

**Hasil pengujian:** Konsisten. UC-02 — Validasi KRS merupakan proses wajib yang diikutsertakan melalui relasi `<<include>>` dalam UC-01 — Ajukan KRS. Oleh karena itu, kegagalan validasi menyebabkan proses pengajuan tidak dilanjutkan ke tahap penyimpanan yang berhasil. Mahasiswa juga tidak dapat memperoleh bukti dari pengajuan yang belum berhasil.

## c. Validasi Berhasil dan Mahasiswa Mengunduh Bukti

Setelah seluruh validasi berhasil, sistem menyimpan pengajuan KRS dengan status menunggu persetujuan dosen wali dan menampilkan konfirmasi kepada mahasiswa. Jika mahasiswa memilih opsi unduh, sistem kemudian menyediakan bukti pengajuan untuk diunduh.

**Hasil pengujian:** Konsisten. UC-03 — Unduh Bukti Pengajuan dapat dijalankan sebagai aktivitas tambahan melalui relasi `<<extend>>` setelah UC-01 berhasil dilakukan dan mahasiswa memilih opsi untuk mengunduh bukti.

## Kesimpulan Pengujian Konsistensi

Berdasarkan ketiga skenario pengujian tersebut