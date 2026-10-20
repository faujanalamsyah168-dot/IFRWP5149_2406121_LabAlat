 <!-- 1. LAB-UC01: Lihat Ketersediaan Peralatan -->
| Bagian | Isi / Keterangan |
| ----- | ----- |
| **ID dan Nama** | LAB-UC01 Lihat ketersediaan peralatan |
| **Sumber Kebutuhan** | LAB-R01 |
| **Tujuan** | Menampilkan daftar peralatan beserta informasi ketersediaannya |
| **Aktor Utama** | Mahasiswa |
| **Pemicu** | Mahasiswa memilih menu ketersediaan peralatan |
| **Prasyarat** | Mahasiswa telah terautentikasi |
| **Pascakondisi Berhasil** | Informasi daftar ketersediaan peralatan berhasil ditampilkan |
| **Pascakondisi Gagal** | Informasi ketersediaan peralatan gagal ditampilkan |
| **Alur Utama** | 1. Mahasiswa memilih menu ketersediaan peralatan.<br>2. Sistem mengambil data ketersediaan peralatan.<br>3. Sistem menampilkan daftar peralatan beserta status ketersediaannya. |
| **Alur Alternatif** | **2a. Data Kosong:** Sistem menampilkan pesan bahwa belum ada data peralatan yang terdaftar. |

<!-- 2. LAB-UC02: Kelola Data Peralatan -->
| Bagian | Isi / Keterangan |
| ----- | ----- |
| **ID dan Nama** | LAB-UC02 Kelola data peralatan |
| **Sumber Kebutuhan** | LAB-R02 |
| **Tujuan** | Menambah, mengubah, atau menghapus data peralatan laboratorium |
| **Aktor Utama** | Petugas laboratorium |
| **Pemicu** | Petugas memilih menu kelola data peralatan |
| **Prasyarat** | Petugas laboratorium telah terautentikasi |
| **Pascakondisi Berhasil** | Data peralatan berhasil diperbarui di dalam sistem |
| **Pascakondisi Gagal** | Data peralatan tidak mengalami perubahan |
| **Alur Utama** | 1. Petugas membuka menu kelola data peralatan.<br>2. Petugas memilih jenis aksi (tambah, edit, atau hapus).<br>3. Petugas mengisikan atau memperbarui data peralatan.<br>4. Petugas menyimpan perubahan.<br>5. Sistem memvalidasi dan meng-update data peralatan. |
| **Alur Alternatif** | **4a. Data Tidak Valid:** Sistem menampilkan pesan kesalahan isian data dan meminta petugas melengkapi kembali. |

 <!-- 3. LAB-UC03: Ajukan Peminjaman -->
| Bagian | Isi / Keterangan |
| ----- | ----- |
| **ID dan Nama** | LAB-UC03 Ajukan peminjaman |
| **Sumber Kebutuhan** | LAB-R03, LAB-R04 |
| **Tujuan** | Menghasilkan pengajuan peminjaman yang tersimpan |
| **Aktor Utama** | Mahasiswa |
| **Pemicu** | Mahasiswa memilih fungsi pengajuan peminjaman |
| **Prasyarat** | Mahasiswa telah terautentikasi; data peralatan tersedia |
| **Include** | LAB-UC04 Periksa ketersediaan |
| **Extension Point** | Bukti pengajuan tersedia, pada langkah 6 |
| **Extend** | LAB-UC05 jika `[mahasiswa memilih cetak]` |
| **Pascakondisi Berhasil** | Pengajuan tersimpan dengan nomor pengajuan dan status "Menunggu keputusan" |
| **Pascakondisi Gagal** | Tidak ada pengajuan baru yang berhasil tersimpan |
| **Alur Utama** | 1. Mahasiswa membuka form pengajuan peminjaman.<br>2. Mahasiswa memilih alat, jumlah, rentang waktu, dan tujuan peminjaman.<br>3. Mahasiswa mengirim pengajuan peminjaman.<br>4. Sistem menjalankan **LAB-UC04 (Periksa ketersediaan)**.<br>5. Jika ketersediaan valid, sistem menyimpan pengajuan dan menerbitkan nomor pengajuan.<br>6. Mahasiswa melihat konfirmasi (menampilkan nomor & status; mencapai *extension point*).<br>7. Mahasiswa mengakhiri pengajuan. |
| **Alur Alternatif** | **4a. Peralatan Tidak Tersedia / Data Inkomplet:** Sistem menampilkan pesan kegagalan ketersediaan dan kembali ke Langkah 2. Pengajuan tidak disimpan. |

 <!-- 4. LAB-UC04: Periksa Ketersediaan -->
| Bagian | Isi / Keterangan |
| ----- | ----- |
| **ID dan Nama** | LAB-UC04 Periksa ketersediaan |
| **Sumber Kebutuhan** | LAB-R03 |
| **Tujuan** | Memvalidasi ketersediaan alat, jumlah, dan rentang waktu yang diajukan |
| **Aktor Utama** | (Sistem) - *Dipanggil oleh Use Case LAB-UC03* |
| **Pemicu** | Pemanggilan `<<include>>` dari LAB-UC03 Langkah 4 |
| **Prasyarat** | Terpanggil dari proses pengajuan peminjaman |
| **Pascakondisi Berhasil** | Peralatan terverifikasi tersedia untuk jumlah dan rentang waktu yang diminta |
| **Pascakondisi Gagal** | Peralatan dinyatakan tidak tersedia atau stok tidak mencukupi |
| **Alur Utama** | 1. Sistem menerima data pilihan alat, jumlah, dan rentang waktu.<br>2. Sistem memeriksa ketersediaan stok alat pada periode tersebut.<br>3. Sistem mengembalikan status "tersedia" ke *use case* pemanggil. |
| **Alur Alternatif** | **2a. Stok Tidak Mencukupi / Bentrok Jadwal:** Sistem mengembalikan status "tidak tersedia" ke *use case* pemanggil. |

 <!-- 5. LAB-UC05: Cetak Bukti Pengajuan -->
| Bagian | Isi / Keterangan |
| ----- | ----- |
| **ID dan Nama** | LAB-UC05 Cetak bukti pengajuan |
| **Sumber Kebutuhan** | LAB-R04 |
| **Tujuan** | Menyiapkan dan menampilkan bukti pengajuan yang dapat dicetak oleh mahasiswa |
| **Aktor Utama** | Mahasiswa |
| **Pemicu** | Mahasiswa memilih opsi cetak bukti pada layar konfirmasi pengajuan (*extension point* tercapai) |
| **Prasyarat** | Pengajuan peminjaman telah berhasil tersimpan |
| **Pascakondisi Berhasil** | Dokumen bukti pengajuan siap dan dikirim ke fungsi cetak |
| **Pascakondisi Gagal** | Bukti pengajuan gagal diproses untuk dicetak |
| **Alur Utama** | 1. Sistem menyiapkan tata letak bukti pengajuan yang siap dicetak.<br>2. Sistem memanggil dialog cetak pada peranti/browser pengguna. |

 <!-- 6. LAB-UC06: Proses Keputusan Peminjaman -->
| Bagian | Isi / Keterangan |
| ----- | ----- |
| **ID dan Nama** | LAB-UC06 Proses keputusan peminjaman |
| **Sumber Kebutuhan** | LAB-R05 |
| **Tujuan** | Menetapkan persetujuan atau penolakan pengajuan peminjaman |
| **Aktor Utama** | Petugas laboratorium |
| **Pemicu** | Petugas membuka daftar pengajuan berstatus "Menunggu keputusan" |
| **Prasyarat** | Petugas laboratorium telah terautentikasi; terdapat pengajuan peminjaman berstatus Menunggu keputusan |
| **Pascakondisi Berhasil** | Status pengajuan berubah menjadi "Disetujui" atau "Ditolak" |
| **Pascakondisi Gagal** | Status pengajuan tidak mengalami perubahan (tetap Menunggu keputusan) |
| **Alur Utama** | 1. Petugas memilih salah satu pengajuan peminjaman.<br>2. Sistem menampilkan detail rincian pengajuan.<br>3. Petugas memberikan keputusan menyetujui pengajuan.<br>4. Sistem menyimpan perubahan status pengajuan menjadi "Disetujui". |
| **Alur Alternatif** | **3a. Penolakan:** Petugas memilih menolak pengajuan. Sistem menyimpan perubahan status pengajuan menjadi "Ditolak". |

 <!-- 7. LAB-UC07: Lihat Laporan Peminjaman -->
| Bagian | Isi / Keterangan |
| ----- | ----- |
| **ID dan Nama** | LAB-UC07 Lihat laporan peminjaman |
| **Sumber Kebutuhan** | LAB-R06 |
| **Tujuan** | Menampilkan laporan rekapitulasi peminjaman peralatan |
| **Aktor Utama** | Kepala laboratorium |
| **Pemicu** | Kepala laboratorium memilih menu lihat laporan peminjaman |
| **Prasyarat** | Kepala laboratorium telah terautentikasi |
| **Pascakondisi Berhasil** | Laporan peminjaman peralatan ditampilkan di layar |
| **Pascakondisi Gagal** | Laporan peminjaman gagal dimuat |
| **Alur Utama** | 1. Kepala laboratorium membuka menu laporan peminjaman.<br>2. Kepala laboratorium memilih filter periode (opsional).<br>3. Sistem mengompilasi data transaksi peminjaman.<br>4. Sistem menampilkan laporan rekapitulasi peminjaman. |
| **Alur Alternatif** | **3a. Data Tidak Ditemukan:** Sistem menampilkan pesan bahwa belum ada rekapitulasi peminjaman pada periode yang dipilih. |