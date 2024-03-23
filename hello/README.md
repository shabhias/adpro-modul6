# REFLECTION MODULE 6

## COMMIT 1

Handle Connection:
- Handle connection mengambil referensi mutable ke TcpStream dan membuat bufreader
- Menghandle pembacaan yang telah di buffer
- Membaca baris-baris yang telah di buffer sampai mencapai baris kosong
- Mewakili permintaan hrrp dengan mengumpulkan baris-baris tersebut menjadi vektor
- Mencetak permintaan HTTP untuk inspeksi. handle_connection membaca aliran TCP masuk baris per-baris sampai menemukan baris kosong yang menandakan akhir dari header permintaan HTTP. Lalu, mencetak baris-baris yang terkumpul sebagai permintaan HTTP.


## COMMIT 2

Fungsi handle connection yang telah di update:
- Menghandle status_line yang menunjukkan bahwa respons HTTP adalah 200 OK, yang berarti permintaan telah berhasil diproses.
- Membaca konten dari file yang bernama hello.html dan mengubahnya menjadi string menggunakan fs::read_to_string(). Ini mengasumsikan bahwa file hello.html berada di direktori yang sama dengan program yang sedang berjalan.
- Menghitung panjang dari string yang berisi konten file.
- Menyiapkan format respons HTTP, yang mencakup baris status, panjang konten, dan konten dari file hello.html.
- Menulis respons tersebut kembali ke aliran TCP dan mengirimkannya ke klien menggunakan write_all().

<a href="https://ibb.co/b7d1PCy"><img src="https://i.ibb.co/qx1Bdc4/Screenshot-2024-03-23-210521.png" alt="Screenshot-2024-03-23-210521" border="0"></a>

