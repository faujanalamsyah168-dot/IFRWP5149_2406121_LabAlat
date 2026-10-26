<!-- 1. SIA-UC01: Lihat Jadwal Kuliah -->
| Bagian | Isi / Keterangan |
| :--- | :--- |
| **ID dan Nama** | SIA-UC01 Lihat jadwal kuliah |
| **Sumber Kebutuhan** | SIA-R01 |
| **Tujuan** | Menampilkan informasi jadwal kuliah bagi mahasiswa |
| **Aktor Utama** | Mahasiswa |
| **Pemicu** | Mahasiswa memilih menu lihat jadwal kuliah |
| **Prasyarat** | Mahasiswa telah terautentikasi |
| **Pascakondisi Berhasil** | Informasi jadwal kuliah ditampilkan di layar |
| **Pascakondisi Gagal** | Jadwal kuliah gagal ditampilkan |
| **Alur Utama** | 1. Mahasiswa memilih menu jadwal kuliah.<br>2. Sistem mengambil data jadwal kuliah.<br>3. Sistem menampilkan daftar jadwal kuliah kepada mahasiswa. |
| **Alur Alternatif** | **2a. Data Kosong/Gagal Dimuat:** Sistem menampilkan pesan bahwa data jadwal kuliah belum tersedia. |

 <!-- 2. SIA-UC02: Kelola Jadwal Kuliah -->
| Bagian | Isi / Keterangan |
| :--- | :--- |
| **ID dan Nama** | SIA-UC02 Kelola jadwal kuliah |
| **Sumber Kebutuhan** | SIA-R02 |
| **Tujuan** | Menambah, mengubah, atau menghapus data jadwal kuliah |
| **Aktor Utama** | Admin Akademik |
| **Pemicu** | Admin memilih menu kelola jadwal kuliah |
| **Prasyarat** | Admin Akademik telah terautentikasi |
| **Pascakondisi Berhasil** | Data jadwal kuliah berhasil diperbarui di dalam sistem |
| **Pascakondisi Gagal** | Data jadwal kuliah tidak mengalami perubahan |
| **Alur Utama** | 1. Admin membuka menu kelola jadwal.<br>2. Admin memilih jenis aksi (tambah, edit, atau hapus jadwal).<br>3. Admin mengisi/memperbarui data jadwal kuliah.<br>4. Admin menyimpan perubahan.<br>5. Sistem memvalidasi dan memperbarui data jadwal. |
| **Alur Alternatif** | **4a. Data Tidak Valid:** Sistem menampilkan pesan kesalahan isian data dan meminta Admin melengkapi kembali. |

<!-- 3. SIA-UC03: Ajukan KRS -->
| Bagian | Isi / Keterangan |
| :--- | :--- |
| **ID dan Nama** | SIA-UC03 Ajukan KRS |
| **Sumber Kebutuhan** | SIA-R03, SIA-R04, SIA-R05 |
| **Tujuan** | Menghasilkan pengajuan KRS yang tersimpan dan siap diproses |
| **Aktor Utama** | Mahasiswa |
| **Pemicu** | Mahasiswa memilih fungsi pengajuan KRS |
| **Prasyarat** | Mahasiswa telah terautentikasi; data mata kuliah dan jadwal tersedia |
| **Include** | SIA-UC04 Validasi KRS |
| **Extension Point** | Konfirmasi penyimpanan KRS |
| **Extend** | SIA-UC05 jika `[mahasiswa memilih mengunduh bukti]` |
| **Pascakondisi Berhasil** | Pengajuan KRS tersimpan dengan status Menunggu Persetujuan Dosen Wali |
| **Pascakondisi Gagal** | Tidak ada pengajuan KRS baru yang tersimpan |
| **Alur Utama** | 1. Mahasiswa membuka form pengajuan KRS.<br>2. Sistem menampilkan daftar jadwal dan form pengajuan.<br>3. Mahasiswa memilih mata kuliah dan mengirim pengajuan.<br>4. Sistem menjalankan **SIA-UC04 (Validasi KRS)**.<br>5. Jika validasi berhasil, sistem menyimpan pengajuan dengan status "Menunggu Persetujuan".<br>6. Sistem menampilkan konfirmasi penyimpanan; mencapai *extension point*.<br>7. Mahasiswa mengakhiri pengajuan. |
| **Alur Alternatif** | **4a. Validasi Gagal:** Sistem menampilkan pesan error (benturan/prasyarat tidak terpenuhi) dan kembali ke Langkah 2. Pengajuan tidak disimpan. |

 <!-- 4. SIA-UC04: Validasi KRS -->
| Bagian | Isi / Keterangan |
| :--- | :--- |
| **ID dan Nama** | SIA-UC04 Validasi KRS |
| **Sumber Kebutuhan** | SIA-R04 |
| **Tujuan** | Memeriksa kelengkapan, prasyarat, dan benturan jadwal dari mata kuliah yang dipilih |
| **Aktor Utama** | (Sistem) - *Dipanggil oleh Use Case SIA-UC03* |
| **Pemicu** | Pemanggilan `<<include>>` dari SIA-UC03 Langkah 4 |
| **Pascakondisi Berhasil** | Pemeriksaan selesai dengan hasil valid (tidak ada pelanggaran aturan) |
| **Pascakondisi Gagal** | Pemeriksaan selesai dengan hasil tidak valid (ditemukan benturan atau kurang prasyarat) |
| **Alur Utama** | 1. Sistem memeriksa kelengkapan data mata kuliah.<br>2. Sistem memverifikasi prasyarat mata kuliah.<br>3. Sistem memeriksa tidak ada benturan jadwal.<br>4. Sistem mengembalikan status berhasil ke *use case* pemanggil. |


 <!-- 5. SIA-UC05: Unduh Bukti Pengajuan KRS -->
| Bagian | Isi / Keterangan |
| :--- | :--- |
| **ID dan Nama** | SIA-UC05 Unduh bukti pengajuan KRS |
| **Sumber Kebutuhan** | SIA-R05 |
| **Tujuan** | Memberikan berkas/bukti fisik digital pengajuan KRS kepada mahasiswa |
| **Aktor Utama** | Mahasiswa |
| **Pemicu** | Mahasiswa menekan opsi unduh pada saat konfirmasi pengajuan (*extension point* tercapai) |
| **Prasyarat** | Pengajuan KRS telah berhasil tersimpan |
| **Pascakondisi Berhasil** | File bukti pengajuan berhasil diunduh ke perangkat mahasiswa |
| **Pascakondisi Gagal** | File bukti pengajuan gagal diunduh |
| **Alur Utama** | 1. Sistem menyiapkan bukti pengajuan KRS yang dapat diunduh.<br>2. Sistem mengirimkan file kepada perangkat mahasiswa. |

 <!-- 6. SIA-UC06: Proses Keputusan KRS -->
| Bagian | Isi / Keterangan |
| :--- | :--- |
| **ID dan Nama** | SIA-UC06 Proses keputusan KRS |
| **Sumber Kebutuhan** | SIA-R06 |
| **Tujuan** | Menetapkan status persetujuan atau penolakan pengajuan KRS |
| **Aktor Utama** | Dosen Wali |
| **Pemicu** | Dosen Wali membuka daftar pengajuan KRS mahasiswa |
| **Prasyarat** | Dosen Wali telah terautentikasi; terdapat pengajuan KRS dengan status menunggu persetujuan |
| **Pascakondisi Berhasil** | Pengajuan KRS berubah status menjadi Disetujui atau Ditolak dan memiliki catatan keputusan |
| **Pascakondisi Gagal** | Status pengajuan KRS tidak mengalami perubahan |
| **Alur Utama** | 1. Dosen Wali memilih pengajuan KRS mahasiswa.<br>2. Sistem menampilkan detail KRS.<br>3. Dosen Wali memberikan persetujuan beserta catatan.<br>4. Sistem menyimpan perubahan status KRS menjadi "Disetujui". |
| **Alur Alternatif** | **3a. Penolakan:** Dosen Wali memilih menolak KRS dan mengisi catatan. Sistem menyimpan perubahan status KRS menjadi "Ditolak". |