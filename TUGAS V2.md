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
    PROGRAM KasirTokoBukuKita
    DEKLARASI:
    is_member: boolean
    jumlah_buku: integer
    total_awal: real
    persen_diskon: real
    nominal_diskon: real
    total_bayar: real
    ALGORITMA:
    REPEAT
        INPUT(is_member)
        IF (is_member <> "TRUE") AND (is_member <> "FALSE") THEN
            OUTPUT("Input tidak valid. Ketik TRUE atau FALSE.")
        ENDIF
    UNTIL (is_member = "TRUE") OR (is_member = "FALSE")
    REPEAT
        INPUT(total_awal)
        INPUT(jumlah_buku)
        IF (total_awal < 0) OR (jumlah_buku < 1) THEN
            OUTPUT("Input tidak valid. Total belanja tidak boleh negatif dan jumlah buku minimal 1. Silakan masukkan ulangi.")
        ENDIF
    UNTIL (total_awal >= 0) AND (jumlah_buku >= 1)

    persen_diskon <= 0

    IF (is_member = "TRUE") THEN
        persen_diskon <= 0.10
        IF (total_awal >= 200000) AND (jumlah_buku >= 3) THEN
            persen_diskon <= 0.15
        ENDIF
    ELSE
        IF (total_awal >= 300000) THEN
            persen_diskon <= 0.05
        ELSE
            persen_diskon <= 0
        ENDIF
    ENDIF

    nominal_diskon <= total_awal * persen_diskon
    total_bayar <= total_awal - nominal_diskon

    OUTPUT(nominal_diskon)
    OUTPUT(total_bayar)

# Uji Logika / Trace Table
