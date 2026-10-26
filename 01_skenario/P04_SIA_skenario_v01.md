Tugas ini berbeda dari tugas pertemuan sebelumnya. Tugas Pertemuan 2 adalah jadwal kuliah dan tugas Pertemuan 3 adalah pengajuan KRS. Tugas Pertemuan 4 adalah layanan hasil studi, dengan teknik generalization dan collaboration yang sama seperti studi kasus, tetapi diterapkan pada skenario baru tanpa contoh jawaban. Skenario tugas berikut fiktif untuk praktikum dan berbeda dari tugas Pertemuan 2 (jadwal kuliah) dan Pertemuan 3 (pengajuan KRS). Mahasiswa dan dosen sama-sama merupakan Civitas Akademika yang dapat melihat kalender akademik. Dosen menginput nilai mata kuliah yang diampunya setelah masa perkuliahan berakhir. Mahasiswa melihat Kartu Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Admin Akademik mengelola data mahasiswa: menambah data mahasiswa baru, mengubah data mahasiswa, dan menghapus data mahasiswa. Dua use case utama, Input Nilai Mata Kuliah dan Lihat KHS, ditunjukkan realisasinya oleh collaboration yang bersesuaian.


 <!-- Aktor -->
| Aktor | Kedudukan | Tujuan terhadap sistem |
|---|---|---|
| Civitas Akademika | Umum, **baru** P4 | Peran umum; mewariskan fungsi bersama (kalender akademik) |
| Mahasiswa | Khusus dari Civitas Akademika | Lihat kalender akademik (diwarisi); lihat jadwal kuliah, ajukan KRS, unduh bukti KRS (tetap P2/P3); **lihat KHS** (baru, khusus) |
| Dosen | Khusus dari Civitas Akademika, **baru** P4 | Lihat kalender akademik (diwarisi); **input nilai mata kuliah** (khusus) |
| Admin Akademik | Tetap | Kelola jadwal kuliah (P2); kelola data mahasiswa (P4) |
| Dosen Wali | Tetap | Proses keputusan KRS (P3) |

<!-- Katalog use case -->
| ID | Nama | Aktor terkait | Sumber kebutuhan |
|---|---|---|---|
| SIA-UC01 | Lihat Jadwal Kuliah | Mahasiswa | SIA-R01 | 
| SIA-UC02 | Kelola Jadwal Kuliah | Admin Akademik | SIA-R02 | 
| SIA-UC03 | Ajukan KRS | Mahasiswa; «include» UC04 | SIA-R03 | 
| SIA-UC04 | Validasi KRS | (disertakan UC03) | SIA-R04 | 
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Mahasiswa; «extend» UC03 | SIA-R05 | 
| SIA-UC06 | Proses Keputusan KRS | Dosen Wali | SIA-R06 | 
| SIA-UC07 | Lihat Kalender Akademik | Civitas Akademika | SIA-R07 | 
| SIA-UC08 | Input Nilai Mata Kuliah | Dosen; realisasi SIA-CO01 | SIA-R08, R12 |
| SIA-UC09 | Lihat KHS | Mahasiswa; realisasi SIA-CO02 | SIA-R09, R12 | 
| SIA-UC10 | Kelola Data Mahasiswa | Admin Akademik; UMUM bagi UC11–13 | SIA-R10, R11 | 
| SIA-UC11 | Tambah Data Mahasiswa | (khusus UC10) | SIA-R11 |
| SIA-UC12 | Ubah Data Mahasiswa | (khusus UC10) | SIA-R11 |
| SIA-UC13 | Hapus Data Mahasiswa | (khusus UC10) | SIA-R11 |


<!-- Generalization aktor -->
- **Hierarki:** Mahasiswa → Civitas Akademika; Dosen → Civitas Akademika (segitiga kosong pada Civitas Akademika).
- **Fungsi diwarisi:** SIA-UC07 Lihat Kalender Akademik (digambar satu kali dari Civitas Akademika).
- **Alasan:** (1) keduanya memakai fungsi yang sama persis; (2) kesamaan itu berlaku tetap (kalender institusi untuk seluruh civitas); (3) nama peran umum membuat diagram lebih jelas. Ketiga pertanyaan keputusan terjawab ya.
- **Asosiasi khusus (tidak diwariskan):** Mahasiswa → UC01, UC03, UC05, UC09; Dosen → UC08.

<!-- Generalization use case -->
Umum: **SIA-UC10 Kelola Data Mahasiswa** (hasil sejenis: data mahasiswa terkelola).
| Khusus | Perilaku pembeda |
|---|---|
| SIA-UC11 Tambah Data Mahasiswa | Menghasilkan data mahasiswa baru yang tersimpan. |
| SIA-UC12 Ubah Data Mahasiswa | Menghasilkan data mahasiswa yang berubah. |
| SIA-UC13 Hapus Data Mahasiswa | Menghasilkan data mahasiswa yang terhapus, hanya bila tidak memiliki data akademik aktif. |

Admin Akademik hanya dihubungkan ke SIA-UC10, bukan ke ketiga use case khusus.

 <!-- Collaboration dan realization -->
| ID | Nama (sama persis dengan use case) | Use case yang direalisasikan |
|---|---|---|
| SIA-CO01 | Input Nilai Mata Kuliah | SIA-UC08 Input Nilai Mata Kuliah |
| SIA-CO02 | Lihat KHS | SIA-UC09 Lihat KHS |

Alasan: keduanya use case utama layanan hasil studi. Collaboration untuk use case lain tidak digambar. Tidak ada garis aktor → collaboration.


