# Jobsheet Review — Sistem Informasi Akademik

| No. | Temuan | Perbaikan yang Diperlukan | Alasan |
|---|---|---|---|
| 1 | Kondisi yang menjadi pemicu relasi `<<extend>>` belum ditampilkan secara jelas. | Menambahkan kondisi `[pengajuan berhasil disimpan dan mahasiswa memilih untuk mengunduh]` pada relasi `<<extend>>`. | Memberikan penjelasan mengenai kondisi ketika use case **Unduh Bukti Pengajuan** dapat dijalankan. |
| 2 | Extension point belum ditampilkan secara eksplisit pada diagram. | Menambahkan extension point pada UC-01 **Ajukan KRS** apabila hal tersebut menjadi ketentuan dalam modul pembelajaran. | Menunjukkan lokasi atau titik terjadinya perluasan perilaku opsional dalam use case. |
| 3 | Jalur asosiasi dari aktor Mahasiswa menuju UC-03 melintasi bagian tengah diagram sehingga tampilan kurang rapi. | Mengatur kembali posisi use case maupun jalur asosiasi agar garis hubungan antaraktor dan use case lebih jelas dan tidak saling mengganggu. | Meningkatkan kerapian serta mempermudah pengguna dalam memahami hubungan antara aktor dan use case. |
| 4 | Pascakondisi pada proses pengajuan perlu diselaraskan dengan alur yang telah ditentukan. | Memastikan bahwa pengajuan yang berhasil disimpan memiliki status **menunggu persetujuan dosen wali**, sedangkan kegagalan validasi tidak menghasilkan pengajuan yang berhasil tersimpan. | Memastikan kesesuaian antara diagram use case, deskripsi setiap use case, dan hasil pengujian skenario. |

## Kesimpulan Review

Berdasarkan hasil evaluasi, diagram use case pada Sistem Informasi Akademik telah mencakup aktor, batas sistem, serta penggunaan relasi `<<include>>` dan `<<extend>>` dengan tepat. Beberapa bagian masih memerlukan penyempurnaan, khususnya dalam memberikan kondisi pada relasi `<<extend>>`, memastikan keberadaan extension point sesuai dengan ketentuan modul, memperbaiki tata letak diagram, serta menyelaraskan pascakondisi pengajuan.

Setelah seluruh perbaikan tersebut diterapkan, diagram use case beserta deskripsi masing-masing use case dapat ditetapkan sebagai versi hasil revisi.