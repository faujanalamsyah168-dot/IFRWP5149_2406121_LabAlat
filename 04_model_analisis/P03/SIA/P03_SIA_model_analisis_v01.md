|    Sumber    |Hubungan | Tujuan  |
|--------------|---------|---------|
|  Mahasiswa   |Asosiasi |SIA-UC01 |
|  Mahasiswa   |Asosiasi |SIA-UC03 |
|  Mahasiswa   |Asosiasi |SIA-UC05 |
|Admin Akademik|Asosiasi |SIA-UC02 |
|  Dosen Wali  |Asosiasi |SIA-UC06 |
|   SIA-UC03   |«include»|SIA-UC04 |
|   SIA-UC05   |«extend» |SIA-UC03 |


condition: [mahasiswa memilih mengunduh bukti]

extension point: Konfirmasi penyimpanan KRS
