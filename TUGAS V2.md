# Analisis Komponen
  A. Variabel dan tipe data
  - is_member     : Boolean
  - jumlah_buku   : Integer
  - total_awal    : Real/Float
  - persen_diskon : Real/Float
  - nominal_diskon: Real/Float
  - total_bayar   : Real/Float

  B. Jenis struktur kontrol
  - percabangan
  - perulangan

# Penyusunan Pseudocode
    PROGRAM SistemKasirTokoBukuKita
    DEKLARASI:
       is_member     : boolean
       total_awal    : real
       jumlah_buku   : integer
       persen_diskon : real
       nominal_diskon: real
       total_bayar   : real
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
## Kasus A
`is_member = TRUE, total_awal = 250000, jumlah_buku = 4`

| No | Langkah | is_member | total_awal | jumlah_buku | persen_diskon | nominal_diskon | total_bayar | Keterangan / Output |
|----|---------|-----------|------------|-------------|---------------|----------------|-------------|---------------------|
| 1 | INPUT is_member | TRUE | - | - | - | - | - | |
| 2 | INPUT total_awal | TRUE | 250000 | - | - | - | - | |
| 3 | INPUT jumlah_buku | TRUE | 250000 | 4 | - | - | - | |
| 4 | Cek (250000<0) OR (4<1) | TRUE | 250000 | 4 | - | - | - | FALSE, tidak ada pesan error |
| 5 | Cek UNTIL (250000>=0) AND (4>=1) | TRUE | 250000 | 4 | - | - | - | TRUE, keluar loop |
| 6 | Cek is_member = TRUE | TRUE | 250000 | 4 | - | - | - | TRUE, masuk blok member |
| 7 | persen_diskon ← 0.10 | TRUE | 250000 | 4 | 0.10 | - | - | |
| 8 | Cek (250000>=200000) AND (4>=3) | TRUE | 250000 | 4 | 0.10 | - | - | TRUE |
| 9 | persen_diskon ← 0.10 + 0.05 | TRUE | 250000 | 4 | 0.15 | - | - | |
| 10 | nominal_diskon ← 250000 × 0.15 | TRUE | 250000 | 4 | 0.15 | 37500 | - | |
| 11 | total_bayar ← 250000 − 37500 | TRUE | 250000 | 4 | 0.15 | 37500 | 212500 | |
| 12 | OUTPUT | TRUE | 250000 | 4 | 0.15 | 37500 | 212500 | 37500 dan 212500 |

## Kasus B
`is_member = FALSE, total_awal = 350000, jumlah_buku = 2`

| No | Langkah | is_member | total_awal | jumlah_buku | persen_diskon | nominal_diskon | total_bayar | Keterangan / Output |
|----|---------|-----------|------------|-------------|---------------|----------------|-------------|---------------------|
| 1 | INPUT is_member | FALSE | - | - | - | - | - | |
| 2 | INPUT total_awal | FALSE | 350000 | - | - | - | - | |
| 3 | INPUT jumlah_buku | FALSE | 350000 | 2 | - | - | - | |
| 4 | Cek (350000<0) OR (2<1) | FALSE | 350000 | 2 | - | - | - | FALSE, tidak ada pesan error |
| 5 | Cek UNTIL (350000>=0) AND (2>=1) | FALSE | 350000 | 2 | - | - | - | TRUE, keluar loop |
| 6 | Cek is_member = TRUE | FALSE | 350000 | 2 | - | - | - | FALSE, masuk ELSE |
| 7 | Cek 350000 >= 300000 | FALSE | 350000 | 2 | - | - | - | TRUE |
| 8 | persen_diskon ← 0.05 | FALSE | 350000 | 2 | 0.05 | - | - | |
| 9 | nominal_diskon ← 350000 × 0.05 | FALSE | 350000 | 2 | 0.05 | 17500 | - | |
| 10 | total_bayar ← 350000 − 17500 | FALSE | 350000 | 2 | 0.05 | 17500 | 332500 | |
| 11 | OUTPUT | FALSE | 350000 | 2 | 0.05 | 17500 | 332500 | 17500 dan 332500 |

## Kasus C
`is_member = FALSE, input pertama total_awal = -50000, dikoreksi menjadi 100000, jumlah_buku = 1`

| No | Langkah | is_member | total_awal | jumlah_buku | persen_diskon | nominal_diskon | total_bayar | Keterangan / Output |
|----|---------|-----------|------------|-------------|---------------|----------------|-------------|---------------------|
| 1 | INPUT is_member | FALSE | - | - | - | - | - | |
| 2 | INPUT total_awal (ke-1) | FALSE | -50000 | - | - | - | - | |
| 3 | INPUT jumlah_buku (ke-1) | FALSE | -50000 | 1 | - | - | - | |
| 4 | Cek (-50000<0) OR (1<1) | FALSE | -50000 | 1 | - | - | - | TRUE, OUTPUT: "Input data tidak valid. Silakan masukkan ulang data." |
| 5 | Cek UNTIL (-50000>=0) AND (1>=1) | FALSE | -50000 | 1 | - | - | - | FALSE, ulangi loop |
| 6 | INPUT total_awal (ke-2) | FALSE | 100000 | 1 | - | - | - | Koreksi |
| 7 | INPUT jumlah_buku (ke-2) | FALSE | 100000 | 1 | - | - | - | Diasumsikan tetap 1 |
| 8 | Cek (100000<0) OR (1<1) | FALSE | 100000 | 1 | - | - | - | FALSE, tidak ada pesan error |
| 9 | Cek UNTIL (100000>=0) AND (1>=1) | FALSE | 100000 | 1 | - | - | - | TRUE, keluar loop |
| 10 | Cek is_member = TRUE | FALSE | 100000 | 1 | - | - | - | FALSE, masuk ELSE |
| 11 | Cek 100000 >= 300000 | FALSE | 100000 | 1 | - | - | - | FALSE |
| 12 | persen_diskon ← 0 | FALSE | 100000 | 1 | 0 | - | - | |
| 13 | nominal_diskon ← 100000 × 0 | FALSE | 100000 | 1 | 0 | 0 | - | |
| 14 | total_bayar ← 100000 − 0 | FALSE | 100000 | 1 | 0 | 0 | 100000 | |
| 15 | OUTPUT | FALSE | 100000 | 1 | 0 | 0 | 100000 | 0 dan 100000 |
