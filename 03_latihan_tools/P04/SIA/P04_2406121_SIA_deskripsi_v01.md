 <!-- A. Deskripsi Lengkap: SIA-UC08 (Input Nilai Mata Kuliah) -->
| Elemen | Detail Spesifikasi |
| :--- | :--- |
| **ID dan Nama** | SIA-UC08: Input Nilai Mata Kuliah |
| **Sumber Kebutuhan** | SIA-R08 dan SIA-R12 |
| **Tujuan** | Menyimpan nilai mata kuliah yang diampu dosen ke dalam sistem |
| **Aktor Utama** | Dosen |
| **Pemicu** | Dosen memilih menu penginputan nilai setelah perkuliahan/ujian berakhir |
| **Prasyarat** | Dosen telah terautentikasi dan terdaftar sebagai pengampu mata kuliah tersebut |
| **Pascakondisi Berhasil** | Nilai mata kuliah tersimpan di sistem |
| **Pascakondisi Gagal** | Nilai tidak tersimpan di sistem dan data nilai lama tidak berubah |
| **Collaboration** | SIA-CO01: Input Nilai Mata Kuliah |

**Alur Utama:**
1. **Dosen:** Memilih mata kuliah dan kelas yang diampu.
2. **Sistem:** Menampilkan daftar mahasiswa peserta kelas beserta form input nilai.
3. **Dosen:** Memasukkan nilai angka/huruf mahasiswa dan mengonfirmasi simpan.
4. **Sistem:** Memvalidasi bahwa nilai berada dalam rentang dan format yang sah.
5. **Sistem:** Menyimpan data nilai ke basis data dan menampilkan pesan konfirmasi berhasil.

**Alur Alternatif / Pengecualian:**
* **A1 (Bukan Dosen Pengampu):** Dosen mencoba mengakses mata kuliah yang tidak diampunya. Sistem menolak akses dan menampilkan pesan error.
* **A2 (Nilai Di Luar Rentang Sah):** Pada langkah 4, jika nilai yang dimasukkan di luar batas yang berlaku, sistem menolak penyimpanan dan meminta dosen mengoreksi isian.


<!-- B. Deskripsi Ringkas: SIA-UC09 (Lihat KHS) -->

| Elemen | Detail Spesifikasi |
| :--- | :--- |
| **ID dan Nama** | SIA-UC09: Lihat KHS |
| **Sumber Kebutuhan** | SIA-R09 dan SIA-R12 |
| **Tujuan** | Menampilkan Kartu Hasil Studi (KHS) mahasiswa untuk semester tertentu |
| **Aktor Utama** | Mahasiswa |
| **Prasyarat** | Mahasiswa telah terautentikasi di dalam sistem |
| **Pascakondisi** | Sistem berhasil menampilkan data KHS yang telah dipublikasikan |
| **Aturan Bisnis** | KHS hanya menampilkan nilai untuk semester yang nilainya sudah dinyatakan dipublikasikan secara resmi oleh bagian akademik |
| **Collaboration** | SIA-CO02: Lihat KHS |
