# Langkah 5 — Deskripsi Use Case

## UC-01 — Ajukan KRS

| Elemen | Deskripsi |
|---|---|
| **Aktor** | Mahasiswa |
| **Tujuan** | Memasukkan dan mengirimkan rencana mata kuliah untuk memperoleh persetujuan dari dosen wali. |
| **Prasyarat** | 1. Mahasiswa sudah berhasil melakukan autentikasi.<br>2. Informasi mata kuliah dan jadwal perkuliahan telah tersedia. |
| **Alur Utama** | 1. Mahasiswa memilih mata kuliah yang akan dimasukkan dalam pengajuan KRS.<br>2. Mahasiswa mengirimkan pengajuan KRS.<br>3. Sistem melakukan validasi melalui UC-02.<br>4. Apabila hasil validasi memenuhi seluruh ketentuan, sistem menyimpan pengajuan KRS dengan status menunggu persetujuan dosen wali.<br>5. Sistem menampilkan notifikasi atau konfirmasi bahwa pengajuan berhasil disimpan.<br>6. Mahasiswa dapat memilih opsi untuk mengunduh bukti pengajuan melalui UC-03. |
| **Alur Alternatif** | Apabila proses validasi tidak berhasil, sistem memberikan informasi mengenai penyebab kegagalan dan pengajuan tidak disimpan sebagai pengajuan yang berhasil. |
| **Pascakondisi** | 1. Apabila proses berhasil, data pengajuan KRS tersimpan dengan status menunggu persetujuan dosen wali.<br>2. Apabila proses gagal, pengajuan KRS belum berhasil tersimpan. |

---

## UC-02 — Validasi KRS

| Elemen | Deskripsi |
|---|---|
| **Aktor** | Sistem, sebagai bagian dari UC-01 |
| **Tujuan** | Memastikan pengajuan KRS telah memenuhi seluruh persyaratan yang ditentukan. |
| **Prasyarat** | 1. Mahasiswa telah menentukan mata kuliah yang akan diajukan.<br>2. Data mata kuliah, prasyarat, dan jadwal tersedia di dalam sistem. |
| **Alur Utama** | 1. Sistem melakukan pemeriksaan terhadap kelengkapan data pengajuan.<br>2. Sistem memeriksa apakah mahasiswa telah memenuhi prasyarat mata kuliah.<br>3. Sistem memeriksa kemungkinan adanya benturan jadwal.<br>4. Jika seluruh pemeriksaan terpenuhi, sistem memberikan hasil bahwa pengajuan dinyatakan valid. |
| **Alur Alternatif** | Jika salah satu pemeriksaan tidak terpenuhi, sistem menyatakan bahwa validasi gagal dan memberikan informasi mengenai penyebab kegagalan. |
| **Pascakondisi** | Hasil validasi tersedia dan digunakan sebagai dasar untuk menentukan apakah pengajuan KRS dapat disimpan. |

---

## UC-03 — Unduh Bukti Pengajuan

| Elemen | Deskripsi |
|---|---|
| **Aktor** | Mahasiswa |
| **Tujuan** | Memperoleh dokumen atau bukti yang menunjukkan bahwa pengajuan KRS telah berhasil dilakukan. |
| **Prasyarat** | 1. Pengajuan KRS telah berhasil disimpan oleh sistem.<br>2. Sistem telah menampilkan konfirmasi keberhasilan pengajuan. |
| **Alur Utama** | 1. Sistem menampilkan pilihan untuk mengunduh bukti pengajuan.<br>2. Mahasiswa memilih opsi untuk mengunduh bukti.<br>3. Sistem menyiapkan dan menyediakan bukti pengajuan untuk diunduh. |
| **Alur Alternatif** | 1. Jika mahasiswa tidak memilih opsi unduh, proses pengajuan tetap dianggap berhasil.<br>2. Jika terjadi kegagalan dalam menyediakan bukti, pengajuan KRS yang sebelumnya telah tersimpan tetap tidak dibatalkan. |
| **Pascakondisi** | 1. Bukti pengajuan tersedia untuk diunduh apabila proses berhasil.<br>2. Aktivitas pengunduhan tidak mengubah status pengajuan KRS. |

---

## UC-04 — Proses Keputusan KRS

| Elemen | Deskripsi |
|---|---|
| **Aktor** | Dosen Wali |
| **Tujuan** | Memberikan keputusan terhadap pengajuan KRS mahasiswa berdasarkan hasil pemeriksaan. |
| **Prasyarat** | 1. Pengajuan KRS telah tersimpan di dalam sistem.<br>2. Status pengajuan masih menunggu persetujuan dosen wali. |
| **Alur Utama** | 1. Dosen wali membuka data pengajuan KRS mahasiswa.<br>2. Dosen wali memeriksa isi pengajuan.<br>3. Dosen wali menentukan keputusan berupa persetujuan atau penolakan.<br>4. Dosen wali memberikan catatan yang berkaitan dengan keputusan tersebut.<br>5. Sistem menyimpan keputusan beserta catatan dari dosen wali. |
| **Alur Alternatif** | Apabila pengajuan belum tersedia atau belum memenuhi kondisi untuk diproses, sistem tidak mencatat keputusan. |
| **Pascakondisi** | Keputusan berupa persetujuan atau penolakan beserta catatan dosen wali tersimpan pada data pengajuan KRS. |