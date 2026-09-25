# BAGIAN A: RANCANGAN ALGORITMA DENGAN KARAKTERISTIK LENGKAP
## Studi Kasus: Algoritma Pemesanan Makanan Secara Online via Aplikasi.
### Langkah-langkah Melakukan Pemesanan Makanan Secara Online
- Langkah 1: User membuka aplikasi
- Langkah 2: Sistem menampilkan daftar restoran.
- Langkah 3: User memilih salah satu restoran.
- Langkah 4: User memilih satu restoran.
- Langkah 5: User melihat menu dari restoran tersebut.
- Langkah 6: User memilih menu beserta jumlahnya, tambahkan ke keranjang.
- Langkah 7: Menghitung total harga menu.
- Langkah 8: User memasukkan alamat pengiriman.
- Langkah 9: Menghitung total ongkos kirim.
- Langkah 10: Tambahkan ongkos kirim kedalam total harga.
- Langkah 11: Tampilkan total yang harus user bayar.
- Langkah 12: Pilih metode pembayaran (via transfer bank atau e-wallet).
- Langkah 13: Jika pembayaran berhasil, pesanan dikirim ke dapur restoran untuk diproses. Jika pembayaran gagal, user diperintahkan untuk mencoba ulang pembayaran atau pesanan gagal.

### Pemenuhan 5 Karakteristik Utama Algoritma:
- Input: Daftar restoran, daftar menu, pilihan restoran, pilihan menu serta jumlah, alamat, metode pembayaran.
- Output: Pesanan berhasil dikirim ke restoran beserta dengan rincian pembayaran.
- Definiteness: Setiap langkah dalam algoritma memiliki instruksi yang jelas dan bersifat pasti.
- Finiteness: Sistem akan berhenti apabila pesanan telah berhasil dikirim ke dapur restoran atau apabila transaksi dibatalkan atau gagal di tahap pembayaran.
- Effectiveness: Setiap langkah dalam algoritma dapat dipahami oleh user serta dapat dilakukan secara nyata dan menghasilkan suatu proses atau informasi yang dibutuhkan untuk langkah berikutnya.

# BAGIAN B: ANALISIS PEMILIHAN STRUKTUR DATA
## Memilih struktur data yang paling tepat (Array, Linked List, Stack, Queue, Binary Search Tree, Hash Table, atau Graph) untuk menyelesaikan 3 skenario berikut:
### Skenario 1 (Fitur Fitur Undo / Redo):
- Struktur data terpilih: Stack 
- Alasan: Karena stack mememiliki metode LIFO yaitu yang paling awal dihapus yang paling cepat bisa diakses Kembali dan cocok untuk undo / redo

### Skenario 2 (Peta Navigasi Rute Perjalanan):
- Struktur data terpilih: Graph.
- Alasan: Karena peta terdiri dari lokasi atau kota yang terhubung melalui jalanan, hal ini sangat mirip dengan struktur yang dimiliki oleh graph. Sistem graph akan mengukur jarak lalu membandingkan kemungkinan jarak atau rute yang ada pada lokasi a dan lokasi b dan memilih jarak yang paling sinkat dan cepat.

### Skenario 3 (Sistem Login Pengguna Berbasis Username):
- Struktur data terpilih: Hash Table.
- Alasan: Karena hash table dapat mengubah username menjadi kunci angka unik, angka tersebut dapat digunakan untuk menunjukkan lokasi data dengan cepat ketika kita melakukkan login. 

# BAGIAN C: EKSPLORASI ANALOGI MANDIRI
## Membuat analogi kehidupan sehari-hari dari salah satu struktur data (Array, Linked List, Stack, Queue, Tree, Graph, atau Hash Table)
### Analogi yang dipilih:
- Queue.
### Penjelasan:
### i. Nama Analogi:
- Antrian pemesanan nasi padang pada rumah makan padang.
### ii. Cara Kerja Analogi:
- Pembeli yang pertama datang dilayani lebih dulu, pembeli yang baru saja datang langsung berdiri dibelakangnya, Setelah makanan pembeli pertama selesai dibungkus dan dibayar, pembeli pertama tersebut keluar dari antrian dan pembeli dibelakangnya maju untuk dilayani.
### iii. Alasan kelebihan dan kekurangan analogi tersebut:
- Kelebihan: Dengan meniru struktur queue (LIFO)  pada analogi antrian pemesanan nasi padang pada rumah makan padang membuat pelayanan pelanggan jauh lebih teratur dan tertib.
- Kekurangan: Namun kenyataannya masih banyak kendala yang ditemukan apabila menggunakan struktur queue, seperti ada yang menyerobot antrian, pelanggan yang membatalkan pesanan.
