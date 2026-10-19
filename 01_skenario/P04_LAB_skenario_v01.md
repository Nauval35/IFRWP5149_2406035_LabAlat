| ID | Nama Use Case | Peran dalam Model | Sumber Kebutuhan |
|---|---|---|---|
| LAB-UC01 | Lihat Ketersediaan Peralatan | Tetap dari Pertemuan 3; fungsi aktor umum Peminjam | LAB-R01, LAB-R07 |
| LAB-UC02 | Kelola Data Peralatan | Tetap dari Pertemuan 3; use case UMUM bagi LAB-UC08, LAB-UC09, LAB-UC10 | LAB-R02, LAB-R08 |
| LAB-UC03 | Ajukan Peminjaman | Tetap dari Pertemuan 3; fungsi aktor umum Peminjam; menyertakan LAB-UC04; direalisasikan LAB-CO01 | LAB-R03, LAB-R07 |
| LAB-UC04 | Periksa Ketersediaan | Tetap dari Pertemuan 3; perilaku yang disertakan LAB-UC03 | LAB-R03 |
| LAB-UC05 | Cetak Bukti Pengajuan | Tetap dari Pertemuan 3; tambahan bersyarat pada LAB-UC03 melalui «extend» | LAB-R04 |
| LAB-UC06 | Proses Keputusan Peminjaman | Tetap dari Pertemuan 3; fungsi utama petugas | LAB-R05 |
| LAB-UC07 | Lihat Laporan Peminjaman | Tetap dari Pertemuan 3; fungsi utama kepala laboratorium | LAB-R06 |
| LAB-UC08 | Tambah Data Peralatan | Baru pada Pertemuan 4; use case KHUSUS dari LAB-UC02 | LAB-R08 |
| LAB-UC09 | Ubah Data Peralatan | Baru pada Pertemuan 4; use case KHUSUS dari LAB-UC02 | LAB-R08 |
| LAB-UC10 | Hapus Data Peralatan | Baru pada Pertemuan 4; use case KHUSUS dari LAB-UC02 | LAB-R08 |
| LAB-UC11 | Catat Pengembalian Peralatan | Baru pada Pertemuan 4; fungsi utama petugas; direalisasikan LAB-CO02 | LAB-R09 |
| LAB-UC12 | Periksa Kondisi Peralatan | Baru pada Pertemuan 4; perilaku yang disertakan LAB-UC11 | LAB-R10 |

| Aktor | Kedudukan | Tujuan terhadap Sistem |
|---|---|---|
| Petugas Laboratorium | Tetap dari Pertemuan 3 | Mengelola data peralatan, memproses keputusan peminjaman, dan mencatat pengembalian peralatan. |
| Kepala Laboratorium | Tetap dari Pertemuan 3 | Melihat laporan peminjaman. |

## Tetapkan generalization aktor ##
| No. | Ketentuan |
|---|---|
| 1 | Mahasiswa adalah bentuk khusus dari Peminjam, dan Dosen adalah bentuk khusus dari Peminjam. |
| 2 | Alasan: Mahasiswa dan Dosen berbagi fungsi yang sama, yaitu melihat ketersediaan peralatan dan mengajukan peminjaman. |
| 3 | Asosiasi ke LAB-UC01 dan LAB-UC03 digambar satu kali, yaitu dari aktor Peminjam. |
| 4 | Jangan menggambar garis asosiasi yang sama dari Mahasiswa dan dari Dosen ke LAB-UC01 dan LAB-UC03. |
| 5 | Asosiasi Mahasiswa ke LAB-UC05 — Cetak Bukti Pengajuan tetap dipertahankan dan tidak dihapus karena fungsi tersebut khusus untuk mahasiswa. |
| 6 | Asosiasi Mahasiswa ke LAB-UC05 merupakan contoh asosiasi tambahan milik aktor khusus. |
| 7 | Arah panah generalisasi harus diperhatikan: ujung segitiga kosong harus menempel pada Peminjam, bukan pada Mahasiswa dan bukan pada Dosen. |
| 8 | Karena Peminjam digambar di tengah, panah generalisasi Mahasiswa → Peminjam mengarah ke bawah. |
| 9 | Panah generalisasi Dosen → Peminjam mengarah ke atas. |
| 10 | Kedua panah generalisasi berakhir pada aktor Peminjam. |

## Perbandingan diagram ##
| Kelompok | Isi |
|---|---|
| Tetap sama dari Pertemuan 3 | Aktor Mahasiswa, Petugas Laboratorium, dan Kepala Laboratorium; use case LAB-UC01 sampai LAB-UC07; relasi «include» LAB-UC03 ke LAB-UC04; relasi «extend» LAB-UC05 ke LAB-UC03 lengkap dengan condition [mahasiswa memilih cetak] dan extension point Bukti pengajuan tersedia; asosiasi Petugas Laboratorium ke LAB-UC02 dan LAB-UC06; asosiasi Kepala Laboratorium ke LAB-UC07; asosiasi Mahasiswa ke LAB-UC05. |
| Berubah karena generalization aktor | Asosiasi ke LAB-UC01 dan LAB-UC03 yang pada Pertemuan 3 digambar dari Mahasiswa kini digambar satu kali dari Peminjam. Fungsi mahasiswa tidak hilang: mahasiswa mewarisinya dari Peminjam. Inilah satu-satunya perubahan garis pada diagram lama, dan alasannya adalah aturan generalization, bukan penghapusan fungsi. |
| Ditambah pada Pertemuan 4 | Aktor Peminjam dan Dosen; dua generalization aktor; use case LAB-UC08, LAB-UC09, LAB-UC10 beserta tiga generalization use case ke LAB-UC02; use case LAB-UC11 dan LAB-UC12 beserta relasi «include» di antara keduanya dan asosiasi Petugas Laboratorium ke LAB-UC11; collaboration LAB-CO01 dan LAB-CO02 beserta dua relasi realization. |

## Langkah 5: Tetapkan generalization use case ##
• LAB-UC08, LAB-UC09, dan LAB-UC10 adalah bentuk khusus dari LABUC02 Kelola Data Peralatan. Alasan: ketiganya adalah bentuk khusus
pengelolaan data peralatan.
• Tuliskan untuk setiap use case khusus satu kalimat perilaku pembedanya.
Tambah menghasilkan data peralatan baru. Ubah menghasilkan data
peralatan yang berubah. Hapus menghasilkan data peralatan yang
terhapus dengan syarat pada aturan studi kasus.