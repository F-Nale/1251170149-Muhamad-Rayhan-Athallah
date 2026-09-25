# Analisis Komponen
  A. Variabel dan tipe data
  -is_member: Boolean
  -jumlah_buku: Integer
  -total_awal: Real/Float
  -persen_diskon: Real/Float
  -nominal_diskon: Real/Float
  -total_bayar: Real/Float
  B. Jenis struktur kontroL
  -percabangan
  -perulangan

# Penyusunan Pseudocode
PROGRAM KasirTokoBukuTetanggaKita
DEKLARASI:
  is_member: boolean
  jumlah_buku: integer
  total_awal: real
  diskon: real
  total_akhir: real

  ALGORITMA:
  INPUT
    (Apakah Pelanggan Member? (TRUE/FALSE))
  REPEAT
  INPUT 
       Masukkan Total Belanja Awal
       Masukkan Jumlah Buku
    IF (total_awal <= 0 OR jumlah_buku <= 0) THEN
          ("Input tidak valid! Total belanja dan jumlah buku harus lebih dari 0. Silakan coba lagi")
    ENDIF
  INPUT
     (total_awal > 0 DAN jumlah_buku > 0)
     STATUS " REMEDIAL "
    IF    (is_member = TRUE) THEN
        IF (total_awal >= 150000 DAN jumlah_buku >= 3) THEN
            diskon <- 0.15   // Diskon 15%
        ELSE
            diskon <- 0.10   // Diskon 10%
     ENDIF
           STATUS " SUKSES "
    IF      (total_awal >= 200000) THEN
            diskon <- 0.05   // Diskon 5%
        ELSE IF (total_awal >= 100000 DAN jumlah_buku >= 2) THEN
            diskon <- 0.03   // Diskon 3%
        ELSE
           STATUS " REMEDIAL "
            diskon <- 0.00   // Tidak dapat diskon
        ENDIF
           STATUS " SUKSES "
           total_akhir <- total_awal - (total_awal KALI diskon)
        OUTPUT(nominal_diskon)
        OUTPUT(total_bayar)
        SELESAI
           STATUS " SUKSES "
           
           
           

    

          
         
