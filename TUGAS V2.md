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
    PROGRAM KasirTokoBukuKitaV2
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
### Kasus A ###
INPUT: is_member = True, total_awal = 250000, jumlah_buku = 4

|Urutan|Instruksi|is_member|jumlah_buku|total_awal|presentase_diskon|nominal_diskon|total_bayar|
| ---- | ------- | ------- | --------- |-------- | --------------- | ------------ | --------- |
|1|INPUT (is_member), INPUT (jumlah_buku), INPUT (total_awal)|TRUE|4|250000|-|-|-|
|2|cek validasi data (total_awal > 0) AND (jumlah_buku >= 1 )|TRUE|4|250000|-|-|-|
|3|hasil cek validasi (250000>0) AND (4>=1)|TRUE|4|250000|-|-|-|
|4|cek IF (is_member = TRUE) THEN presentase_diskon <- 0.10|TRUE|4|250000|-|-|-|
|5|hasil cek (is_member = TRUE)|TRUE|4|250000|0.10|250000  *0.10|-|
|6|cek nominal diskon IF (total_awal >= 200000) AND (jumlah_buku >=  3) THEN presentase_diskon <- 0.15|TRUE|4|250000|0.10|250000 * 0.10|-|
|7|hasil cek nominal diskon (250000>=200000) AND  (4>3) THEN presentase_diskon <- 0.15|TRUE|4|250000|0.10|250000 * 0.10|-|
|8|total_bayar = total_awal - nominal_diskon|TRUE|4|250000|0.15|250000 * 0.15|-|
|9|total_bayar = 250000 - nominal_diskon|TRUE|4|250000|0.15|37500|-|
|10|total_bayar  = 250000 - 37500|TRUE|4|250000|0.15|37500|-|
|11|total_bayar = 212500|TRUE|4|250000|0.15|37500|212500|

OUTPUT: (nominal_diskon=37500)
OUTPUT: (total_bayar=212500)

### Kasus B ###
INPUT: is_member =  False, total_awal = 350000, jumlah_buku = 2

|Urutan|Instruksi|is_member|jumlah_buku|total_awal|presentase_diskon|nominal_diskon|total_bayar|
| ---- | ------- | ------- | --------- |-------- | --------------- | ------------ | --------- |
|1|INPUT (is_member), INPUT (jumlah_buku), INPUT (total_awal)|FALSE|2|350000|-|-|-|
|2|cek validasi data (total_awal > 0) AND (jumlah_buku >= 1 )|FALSE|2|350000|-|-|-|
|3|hasil cek validasi (350000>0) AND (2>=1)|FALSE|2|350000|-|-|-|
|4|cek IF (is_member = TRUE) THEN presentase_diskon <- 0.10|FALSE|2|350000|-|-|-|
|5|hasil cek (is_member = FALSE)|FALSE|2|350000|-|-|-|
|6|cek nominal diskon  IF (total_awal >= 300000) THEN presentase_diskon <- 0.05|FALSE|2|350000|0.05|350000 * 0.05|-|
|7|hasil cek nominal diskon IF (350000 >= 300000) THEN presentase_diskon <- 0.05|FALSE|2|350000|0.05|350000 * 0.05|-|
|8|total_bayar = total_awal - nominal_diskon|FALSE|2|350000|0.05|350000 * 0.05|-|
|9|total_bayar = 350000 - nominal_diskon|FALSE|2|350000|0.05|17500|-|
|10|total_bayar = 350000 - 17500|FALSE|2|350000|0.05|17500|-|
|11|total_bayar = 332500|FALSE|2|350000|0.05|17500|332500|
  
OUTPUT: (nominal_diskon=17500)
OUTPUT: (total_bayar=332500)

### Kasus C ###
Input awal total_awal = -50000 (salah), lalu dikoreksi menjadi 100000, is_member = False, jumlah_buku = 1

|Urutan|Instruksi|is_member|jumlah_buku|total_awal|presentase_diskon|nominal_diskon|total_bayar|
| ---- | ------- | ------- | --------- |-------- | --------------- | ------------ | --------- |
|1|INPUT (is_member), INPUT (jumlah_buku), INPUT (total_awal)|FALSE|1|-50000 ("Data tidak valid! Silahkan masukkan data kembali")|-|-|-|
|2|cek validasi data (total_awal > 0) AND (jumlah_buku >= 1 )|FALSE|1|-50000 ("Data tidak valid! Silahkan masukkan data kembali")|-|-|-|
|3|INPUT (total_awal) diulang karena salah|FALSE|1|100000|-|-|-|
|4|cek validasi data (total_awal > 0) AND (jumlah_buku >= 1 )|FALSE|100000|-|-|-|
|5|hasil cek validasi (100000>0) AND (1>=1)|FALSE|1|10000|-|-|-|
|6|cek IF (is_member = TRUE) THEN presentase_diskon <- 0.10|FALSE|1|10000|-|-|-|
|7|hasil cek (is_member = FALSE)|FALSE|1|10000|-|-|-|
|8|cek nominal diskon  IF (total_awal >= 300000) THEN presentase_diskon <- 0.05|FALSE|1|10000|0|0|-|
|9|hasil cek nominal diskon IF (100000 >= 300000) THEN presentase_diskon <- 0|FALSE|1|10000|0|0|-|
|10|total_bayar = total_awal - nominal_diskon|FALSE|1|10000|0|0|-|
|11|total_bayar = 100000 - nominal_diskon|FALSE|1|10000|0|0|-|
|12|total_bayar = 100000 - 0|FALSE|1|10000|0|0|-|
|13|total_bayar = 100000|FALSE|1|10000|0|0|100000|
