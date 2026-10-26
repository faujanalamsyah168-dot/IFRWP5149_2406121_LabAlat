|  ID   |                                                   Kebutuhan                                                    |
|-------|----------------------------------------------------------------------------------------------------------------|
|LAB-R01|                                 Mahasiswa dapat melihat ketersediaan peralatan                                 |
|LAB-R02|                                     Petugas dapat mengelola data peralatan                                     |
|LAB-R03|        Mahasiswa dapat mengajukan peminjaman; sistem memeriksa ketersediaan sebelum menyimpan pengajuan        |
|LAB-R04|                    Mahasiswa dapat mencetak bukti pada konfirmasi pengajuan jika memilihnya                    |
|LAB-R05|                         Petugas dapat menetapkan persetujuan atau penolakan pengajuan                          |
|LAB-R06|                              Kepala laboratorium dapat melihat laporan peminjaman                              |
|LAB-R07|     Mahasiswa dan Dosen, sebagai Peminjam, dapat melihat ketersediaan peralatan dan mengajukan peminjaman.     |
|LAB-R08|Petugas laboratorium mengelola data peralatan dalam tiga bentuk khusus: tambah, ubah, dan hapus data peralatan. |
|LAB-R09|      Petugas laboratorium dapat mencatat pengembalian peralatan untuk peminjaman yang berstatus Dipinjam.      |
|LAB-R10|          Sistem memeriksa dan mencatat kondisi peralatan sebagai bagian dari pencatatan pengembalian.          |
|LAB-R11|    Model menunjukkan collaboration yang merealisasikan Ajukan Peminjaman dan Catat Pengembalian Peralatan.     |

Batas sistem dan aturan
• Sistem mencatat dan menyediakan informasi; perpindahan fisik alat tidak terjadi di dalam perangkat lunak (tetap dari Pertemuan 3).
• Pengguna telah terautentikasi dan memiliki hak akses sesuai peran (tetap dari Pertemuan 3).
• Pengembalian hanya dapat dicatat untuk peminjaman berstatus Dipinjam. Peminjaman yang masih Menunggu Keputusan atau Ditolak tidak dapat dicatat pengembaliannya.
• Kondisi peralatan pada pengembalian dicatat dengan salah satu nilai: Baik, Rusak Ringan, atau Rusak Berat.
• Hapus Data Peralatan hanya untuk peralatan yang tidak sedang dipinjam dan tidak memiliki pengajuan aktif.
• Keterlambatan dan denda belum dimodelkan pada pertemuan ini. Tuliskan sebagai pertanyaan terbuka pada berkas kebutuhan, jangan mengarang aturan denda.
• Kriteria penerimaan model: semua kebutuhan LAB-R01 sampai LAB-R11 mempunyai representasi pada diagram kumulatif, arah generalization dan realization benar, dan diagram konsisten dengan deskripsinya.

<!-- Pertanyaan Terbuka (Belum Dimodelkan) -->
1. Berapa besaran denda yang dikenakan jika terjadi keterlambatan pengembalian peralatan?
2. Apakah perhitungan denda dilakukan per hari, per jam, atau flat?