<!-- Skenario -->
Mahasiswa mengajukan KRS dengan memilih mata kuliah.Setiap pengajuan menjalankan validasi KRS yang memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil, sistem menyimpan pengajuan berstatus menunggu persetujuan dosen wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS dan memberikan catatan keputusan.

<!-- Tabel Kebutuhan -->
| ID      | Kebutuhan tugas                                                          |
| ------- | ------------------------------------------------------------------------ |
| SIA-R01 | Mahasiswa dapat melihat jadwal kuliah                                    |
| SIA-R02 | Admin akademik dapat mengelola jadwal kuliah                             |
| SIA-R03 | Mahasiswa dapat mengajukan KRS                                           |
| SIA-R04 | Sistem memvalidasi KRS sebagai bagian pengajuan                          |
| SIA-R05 | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasipengajuan |
| SIA-R06 | Dosen wali dapat memproses persetujuan atau penolakan KRS                |

<!-- Batasan Sistem -->
Batas dan asumsi:
• Pengguna telah terautentikasi.
• Data mata kuliah, prasyarat, dan jadwal tersedia.
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
• KRS tersimpan belum berarti disetujui.
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas.

<!-- Identifikasi Aktor -->
| Aktor      | Tujuan terhadap sistem                                                       |
| ---------- | ---------------------------------------------------------------------------- |
| Mahasiswa  | Melihat jadwal kuliah, mengajukan KRS, dan mengunduh bukti pengajuan         |
| Dosen Wali | Memproses persetujuan atau penolakan KRS serta memberikan catatan keputusan. |

<!-- Tabel Katalog use case -->
|   ID   |      Nama use case      |      Peran dalam model       |
|--------|-------------------------|------------------------------|
|LAB-UC01|   Lihat jadwal kuliah   |    Fungsi utama mahasiswa    |
|LAB-UC02|  Kelola jadwal kuliah   | Fungsi utama admin akademik  |
|LAB-UC03|       Ajukan KRS        |    Fungsi utama mahasiswa    |
|LAB-UC04|      Validasi KRS       |Perilaku yang disertakan UC03 |
|LAB-UC05|Unduh bukti pengajuan KRS| Tambahan bersyarat pada UC03 |
|LAB-UC06|  Proses keputusan KRS   |   Fungsi utama Dosen Wali    |



<!-- relasi include -->
SIA-UC03 «include» SIA-UC04
Alasan: Sistem memvalidasi KRS (memeriksa kelengkapan data, prasyarat mata kuliah, dan benturan jadwal) sebagai bagian wajib dari proses pengajuan KRS sebelum data pengajuan dapat tersimpan.

<!-- relasi extend -->
SIA-UC05 «extend» SIA-UC03
Extension point: Konfirmasi penyimpanan KRS.
Kondisi: [mahasiswa memilih mengunduh bukti].
Alasan: Pengunduhan bukti pengajuan bersifat opsional dan tidak menjadi syarat keberhasilan pengajuan KRS (pengajuan tetap berhasil tersimpan tanpa mengunduh bukti).


