# REFLECTION

## COMMIT 1

Handle Connection:
- Handle connection mengambil referensi mutable ke TcpStream dan membuat bufreader
- Menghandle pembacaan yang telah di buffer
- Membaca baris-baris yang telah di buffer sampai mencapai baris kosong
- Mewakili permintaan hrrp dengan mengumpulkan baris-baris tersebut menjadi vektor
- Mencetak permintaan HTTP untuk inspeksi. handle_connection membaca aliran TCP masuk baris per-baris sampai menemukan baris kosong yang menandakan akhir dari header permintaan HTTP. Lalu, mencetak baris-baris yang terkumpul sebagai permintaan HTTP.
