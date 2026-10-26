 <!-- Spesifikasi hubungan diagram kumulatif -->
| # | Sumber | Hubungan | Tujuan |
|---|---|---|---|
| 1 | Civitas Akademika | Association | SIA-UC07 |
| 2 | Mahasiswa | Association (tetap) | SIA-UC01 |
| 3 | Mahasiswa | Association (tetap) | SIA-UC03 |
| 4 | Mahasiswa | Association (tetap) | SIA-UC05 |
| 5 | Mahasiswa | Association (khusus) | SIA-UC09 |
| 6 | Dosen | Association (khusus) | SIA-UC08 |
| 7 | Mahasiswa | Generalization → | Civitas Akademika |
| 8 | Dosen | Generalization → | Civitas Akademika |
| 9 | Admin Akademik | Association | SIA-UC02 |
| 10 | Admin Akademik | Association | SIA-UC10 |
| 11 | Dosen Wali | Association | SIA-UC06 |
| 12 | SIA-UC03 | «include» | SIA-UC04 |
| 13 | SIA-UC05 | «extend» | SIA-UC03 |
| 14–16 | SIA-UC11 / UC12 / UC13 | Generalization → | SIA-UC10 |
| 17 | SIA-CO01 | Realization → | SIA-UC08 |
| 18 | SIA-CO02 | Realization → | SIA-UC09 |

Catatan: nomor 2–4 dan 9, 11 serta condition/extension point bergantung pada diagram P3 asli; sesuaikan bila berbeda.