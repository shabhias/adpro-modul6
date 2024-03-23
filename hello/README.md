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



## commit 3

<a href="https://imgbb.com/"><img src="https://i.ibb.co/cJs8mCV/Screenshot-2024-03-23-211812.png" alt="Screenshot-2024-03-23-211812" border="0"></a>
<a href="https://ibb.co/6ZpSHz0"><img src="https://i.ibb.co/mBYK9k5/Screenshot-2024-03-23-212024.png" alt="Screenshot-2024-03-23-212024" border="0"></a>

Fungsi handle_connection yang dimodifikasi berperan sebagai server HTTP yang sederhana. Ia membaca baris permintaan dari klien dalam permintaan HTTP dan memeriksa apakah itu merupakan permintaan GET / HTTP/1.1, yang menandakan permintaan untuk jalur root (/). Berdasarkan pemeriksaan ini, fungsi memberikan tanggapan dengan konten yang berbeda:
1. Jika permintaan adalah untuk jalur root (GET / HTTP/1.1), fungsi akan memberikan tanggapan dengan baris status HTTP/1.1 200 OK. Selanjutnya, ia membaca konten dari file bernama hello.html, menghitung panjangnya, membuat tanggapan HTTP yang berisi konten tersebut, dan mengirimkannya kembali ke klien.
2. Jika permintaan bukan untuk jalur root (menandakan bahwa sumber daya yang diminta tidak ditemukan), fungsi akan memberikan tanggapan dengan baris status HTTP/1.1 404 NOT FOUND. Kemudian, ia membaca konten dari file bernama 404.html, menghitung panjangnya, membuat tanggapan HTTP yang berisi konten tersebut, dan mengirimkannya kembali ke klien.

Maka dari itu, fungsi handle_connection yang telah dimodifikasi ini menanggapi dengan konten yang berbeda berdasarkan permintaan yang diterima. Jika permintaan adalah untuk jalur root, server akan memberikan tanggapan dengan hello.html. Jika tidak, server akan memberikan tanggapan dengan halaman 404.html yang menunjukkan bahwa sumber daya yang diminta tidak ditemukan.




