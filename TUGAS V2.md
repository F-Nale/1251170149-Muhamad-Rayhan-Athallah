# Analisis Komponen
  A. Variabel dan tipe data
  - is_member: Boolean
  - jumlah_buku: Integer
  - total_awal: Real/Float
  - persen_diskon: Real/Float
  - nominal_diskon: Real/Float
  - total_bayar: Real/Float
  B. Jenis struktur kontroL
  - percabangan
  - perulangan

# Penyusunan Pseudocode
    PROGRAM KasirTokoBukuKitaV2
    DEKLARASI:
       is_member      : boolean
       total_awal     : real
       jumlah_buku    : integer
       persen_diskon  : real
       nominal_diskon : real
       total_bayar    : real
    ALGORITMA:
       INPUT(is_member)
       REPEAT
          INPUT(total_awal)
          INPUT(jumlah_buku)
          IF (total_awal < 0) OR (jumlah_buku < 1) THEN
             OUTPUT("Input data tidak valid. Silakan masukkan ulang data.")
          ENDIF
       UNTIL (total_awal >= 0) AND (jumlah_buku >= 1)
       IF (is_member = TRUE) THEN
          persen_diskon ← 0.10
          IF (total_awal >= 200000) AND (jumlah_buku >= 3) THEN
             persen_diskon ← persen_diskon + 0.05
          ENDIF
       ELSE
          IF (total_awal >= 300000) THEN
             persen_diskon ← 0.05
          ELSE
             persen_diskon ← 0
          ENDIF
       ENDIF
       nominal_diskon ← total_awal * persen_diskon
       total_bayar    ← total_awal - nominal_diskon
       OUTPUT(nominal_diskon)
       OUTPUT(total_bayar)

# Uji Logika / Trace Table
