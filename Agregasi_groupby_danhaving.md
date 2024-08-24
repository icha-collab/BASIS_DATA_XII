# DEADLINE: 7 Agustus Pukul 20.00 WITA
PENGUMPULAN: via Google Form dengan mengirimkan link github

1. Buat database dengan nama company_namamu misal company_valen
2. Buatlah tabel dengan nama pegawai menggunakan perintah CREATE TABLE ...

Ketentuan tabel: tipe data dan constraintnya
- NIP: int & primary key
- NDep: varchar & NOT NULL
- NBlk: varchar
- JK: enum, NOT NULL
- Alamat: text, NOT NULL
- Telp: varchar, NOT NULL
- Jabatan: enum
- Gaji: BIGINT, NOT NULL
- NoCab: Varchar, NOT NULL

2. Masukkan data-data sesuai dengan yang ada di gambar dengan perintah INSERT INTO
3. Buat folder obsdian dengan nama BASIS DATA - XII dan buat file baru dengan nama Agregasi dengan GROUP BY & HAVING
4. Masukkan hasil struktur tabel pegawai tsb menggunakan perintah DESC di file obsidian kalian
5. Masukkan pula hasil data pada tabel pegawai menggunakan perintah SELECT di file obsidian kalian
6. Buat repositorty baru di github dengan nama BASIS DATA - XII
7. Hubungkan catatan lokal kalian ke github
8. Kirim linknya ke form pengumpulnaa tugas

# 1. Masukkan hasil struktur tabel pegawai tsb menggunakan perintah DESC di file obsidian kalian

Hasil struktur tabel pegawai

![[gambar1.jpg|550]]
- `desc pegawai`;` 
Kueri ini digunakan untuk menampilkan struktur tabel `pegawai`, termasuk nama kolom, tipe data, batasan null/bukan null, batasan kunci, nilai default, dan informasi tambahan. Output kueri ini memberikan gambaran umum yang jelas tentang skema tabel, yang berguna untuk memahami data yang tersimpan dalam tabel.

- `NIP (Nomor Induk Pegawai)`: Bidang ini adalah tipe data integer dan bertindak sebagai kunci utama untuk tabel. Bidang ini tidak boleh null, yang berarti bahwa setiap baris dalam tabel harus memiliki nilai NIP yang unik.
- `NDep (Nama Departemen)`: Ini adalah kolom varchar yang menyimpan nama departemen. Kolom ini tidak boleh null, yang berarti bahwa setiap karyawan harus dikaitkan dengan suatu departemen.
- `NBlk (Nama belakang)`: Ini adalah kolom varchar yang menyimpan nama belakang Kolom ini tidak boleh null, yang berarti bahwa setiap karyawan harus dikaitkan dengan nama belakang.
- `JK (Jenis Kelamin)`: Ini adalah kolom enum yang menyimpan jenis kelamin karyawan, dengan kemungkinan nilai 'L' (Laki-laki) atau 'P' (Perempuan). Kolom ini tidak boleh null, yang berarti bahwa setiap karyawan harus memiliki jenis kelamin yang ditentukan.
- `Alamat`: Ini adalah kolom teks yang menyimpan alamat karyawan. Kolom ini tidak boleh kosong, yang berarti setiap karyawan harus memiliki alamat.
- `Telp (Telepon)`: Ini adalah kolom varchar yang menyimpan nomor telepon karyawan. Kolom ini tidak boleh kosong dan harus unik, yang berarti setiap karyawan harus memiliki nomor telepon yang unik.
- `Jabatan`: Ini adalah kolom enum yang menyimpan posisi pekerjaan karyawan, dengan kemungkinan nilai 'Manajer', 'Penjualan', atau 'Staf'. Kolom ini tidak boleh kosong, yang berarti bahwa setiap karyawan harus memiliki posisi pekerjaan yang ditentukan.
- `Gaji (Gaji)`: Ini adalah kolom bigint yang menyimpan gaji karyawan. Kolom ini tidak boleh null, yang berarti setiap karyawan harus memiliki gaji yang ditentukan.
- `NoCab (Nomor Cabang)`: Ini adalah kolom varchar yang menyimpan nomor cabang. Kolom ini tidak boleh null dan merupakan bagian dari indeks multikolom, yang berarti bahwa kombinasi NoCab dan satu atau beberapa kolom lainnya harus unik.

Jadi Constraint dalam tabel database digunakan untuk menjaga integritas dan konsistensi data, seperti memastikan keunikan, kewajiban isian, validasi nilai, serta hubungan antartabel.


# 2. Masukkan pula hasil data pada tabel pegawai menggunakan perintah SELECT di file obsidian kalian

Hasil data tabel Pegawai

![[Asset/gambar2.JPG]]

- `SELECT * FROM pegawai;` Ini adalah query untuk menampilkan semua kolom dan baris dari tabel `pegawai`.
- Hasil keluaran menunjukkan 9 baris data yang berisi informasi lengkap mengenai para pegawai, termasuk NIP, NDep, NBlk, JK, Alamat, Telp, Jabatan, Gaji, dan NoCab.

 Jadi dapat disimpulkan bahwa:

1. Tabel `pegawai`memiliki 9 baris data yang menampilkan informasi tentang para pegawai.
2. Tabel ini memiliki 9 kolom, yaitu `NIP`, `NDep`, `NBlk`, `JK`, `Alamat`, `Telp`, `Jabatan`, `Gaji`, dan `NoCab`.
3. Setiap pegawai memiliki data yang lengkap, termasuk nomor induk pegawai (NIP), departemen (NDep), nama blok (NBlk), jenis kelamin (JK), alamat, nomor telepon (Telp), jabatan, gaji, dan nomor cabang (NoCab) .
4. Terdapat 4 pegawai dengan jabatan Manajer, 3 pegawai dengan jabatan Sales, 2 pegawai dengan jabatan Staf, dan 1 pegawai yang tidak memiliki jabatan yang terdata.
5. Rentang gaji pegawai berada di antara Rp1.725.000,- hingga Rp6.250.000,-.

Secara keseluruhan, tabel `pegawai`ini menyediakan informasi yang cukup lengkap mengenai para pegawai beserta detail-detail terkait.


# PENJELASAN LAINNYA :

```SQL
SELECT COUNT(NIP) AS JumlahPegawai, COUNT(Jabatan) AS JumlahJabatan FROM pegawai;
```

 ![[Asset/gambar_hilang.jpg|550]]

1. **SELECT COUNT(NIP) AS JumlahPegawai**:
    
    - **`SELECT`**: Klausa ini digunakan untuk memilih kolom atau hasil perhitungan yang ingin ditampilkan dalam output query.
    - **`COUNT(NIP)`**: Fungsi agregasi `COUNT` menghitung jumlah baris di mana kolom `NIP` tidak bernilai `NULL`. Ini berarti fungsi ini menghitung jumlah pegawai yang terdaftar dalam tabel `pegawai`.
    - **`AS JumlahPegawai`**: Alias `JumlahPegawai` digunakan untuk memberi nama pada hasil perhitungan `COUNT(NIP)`. Nama ini akan muncul sebagai judul kolom dalam hasil query.
    
2. **COUNT(Jabatan) AS JumlahJabatan**:
    
    - **`COUNT(Jabatan)`**: Sama seperti `COUNT(NIP)`, fungsi `COUNT(Jabatan)` menghitung jumlah baris di mana kolom `Jabatan` tidak bernilai `NULL`. Ini berarti fungsi ini menghitung berapa kali data di kolom `Jabatan` memiliki nilai, yang bisa merepresentasikan jumlah jabatan yang diisi di tabel `pegawai`.
    - **`AS JumlahJabatan`**: Alias `JumlahJabatan` digunakan untuk memberi nama pada hasil perhitungan `COUNT(Jabatan)`. Nama ini akan muncul sebagai judul kolom dalam hasil query.

3.  **FROM pegawai**:
    
    - **`FROM`**: Klausa ini menentukan tabel yang akan digunakan untuk mengambil data, yaitu tabel `pegawai`.
    - Dalam konteks ini, tabel `pegawai` berisi data pegawai, termasuk informasi tentang `NIP` dan `Jabatan`.

### Kesimpulan

- **Tujuan Query**: Query ini dirancang untuk menghitung dan menampilkan dua hal:
    
    1. Jumlah total pegawai (`JumlahPegawai`) berdasarkan perhitungan kolom `NIP`.
    2. Jumlah total jabatan (`JumlahJabatan`) yang terdaftar dalam tabel `pegawai` berdasarkan kolom `Jabatan`.
    
- **Fungsi `COUNT`**: `COUNT(NIP)` menghitung jumlah pegawai yang memiliki `NIP`, sedangkan `COUNT(Jabatan)` menghitung jumlah entri jabatan yang terdaftar dalam tabel, dengan masing-masing hasil diberi alias untuk memudahkan interpretasi.
    
- **Hasil Akhir**: Hasil query ini akan menampilkan satu baris dengan dua kolom: `JumlahPegawai` dan `JumlahJabatan`, yang masing-masing menunjukkan total pegawai dan total jabatan yang ada di tabel `pegawai`.


---


```SQL 
SELECT COUNT(NIP) AS JumlahPegawai
FROM pegawai 
WHERE NoCab = 'C102';
	```

![[gambar_hilang2.PNG]]

1. **SELECT COUNT(NIP) AS JumlahPegawai**:
    - **`SELECT`**: Ini adalah klausa yang digunakan untuk menentukan kolom apa saja yang ingin ditampilkan dalam hasil query.
    - **`COUNT(NIP)`**: Fungsi `COUNT` digunakan untuk menghitung jumlah baris yang memenuhi kriteria tertentu. Dalam hal ini, fungsi `COUNT(NIP)` menghitung jumlah baris di mana kolom `NIP` (Nomor Induk Pegawai) memiliki nilai yang tidak `NULL`.
    - **`AS JumlahPegawai`**: Kata kunci `AS` digunakan untuk memberikan alias pada hasil fungsi `COUNT`. Alias `JumlahPegawai` ini digunakan untuk memberi nama kolom hasil perhitungan, sehingga dalam hasil query, kolom ini akan diberi label "JumlahPegawai".
    
2. **FROM pegawai**:
    - **`FROM`**: Klausa ini digunakan untuk menentukan tabel mana yang akan digunakan dalam query.
    - **`pegawai`**: Ini adalah nama tabel yang menjadi sumber data untuk query ini. Dalam konteks ini, tabel `pegawai` berisi data pegawai, termasuk informasi seperti `NIP` dan `NoCab`.
    
3. **WHERE NoCab = 'C102'**
    - **`WHERE`**: Klausa ini digunakan untuk menetapkan kondisi atau kriteria yang harus dipenuhi oleh data yang akan dipilih.
    - **`NoCab = 'C102'`**: Kondisi ini berarti query hanya akan menghitung jumlah pegawai yang memiliki nilai `NoCab` (Nomor Cabang) sama dengan 'C102'. Jadi, hanya pegawai yang terdaftar di cabang dengan kode 'C102' yang akan dihitung.

### Kesimpulan:
- Query ini akan menghitung jumlah pegawai yang terdaftar di cabang dengan kode 'C102'. Hasil dari query ini adalah satu nilai yang menunjukkan jumlah pegawai yang berada di cabang tersebut, dan hasilnya akan ditampilkan dengan label `JumlahPegawai`.


---

```SQL
SELECT NoCab, COUNT(NIP) AS Jumlah_Pegawai
FROM pegawai
GROUP BY NoCab
HAVING COUNT(NIP) >= 3;

```

![[Asset/gambar 4.png]]

1. **SELECT NoCab, COUNT(NIP) AS Jumlah_Pegawai**:
    - **`SELECT`**: Klausa ini digunakan untuk memilih kolom-kolom yang ingin ditampilkan dalam hasil query.
    - **`NoCab`**: Kolom `NoCab` (Nomor Cabang) dipilih untuk ditampilkan. Ini menunjukkan cabang mana yang sedang dihitung.
    - **`COUNT(NIP) AS Jumlah_Pegawai`**: Fungsi `COUNT(NIP)` menghitung jumlah pegawai (`NIP` tidak `NULL`) di setiap cabang. Alias `Jumlah_Pegawai` digunakan untuk memberi nama kolom hasil perhitungan tersebut, sehingga hasil query akan menampilkan jumlah pegawai per cabang.
    
2.  **FROM pegawai**:
    - **`FROM`**: Klausa ini menentukan tabel `pegawai` sebagai sumber data untuk query ini.
    - Tabel `pegawai` berisi data pegawai, termasuk informasi tentang `NIP` dan `NoCab`.
    
3. **GROUP BY NoCab**:
    - **`GROUP BY`**: Klausa ini mengelompokkan hasil query berdasarkan nilai yang unik di kolom `NoCab`. Dengan kata lain, semua baris dengan nilai `NoCab` yang sama akan dikelompokkan bersama.
    - Setelah dikelompokkan, fungsi agregasi `COUNT(NIP)` akan diterapkan pada setiap kelompok, menghitung jumlah pegawai di setiap cabang (`NoCab`).
    
4.  **HAVING COUNT(NIP) >= 3**:
    - **`HAVING`**: Klausa ini digunakan untuk menyaring hasil yang sudah dikelompokkan oleh `GROUP BY`.
    - **`COUNT(NIP) >= 3`**: Kondisi ini berarti hanya kelompok (`NoCab`) yang memiliki 3 atau lebih pegawai (berdasarkan perhitungan `COUNT(NIP)`) yang akan ditampilkan dalam hasil akhir. Cabang dengan kurang dari 3 pegawai akan diabaikan.

### Kesimpulan

- **Tujuan Query**: Query ini bertujuan untuk menampilkan daftar cabang (`NoCab`) yang memiliki tiga atau lebih pegawai (`Jumlah_Pegawai`).
    
- **Fungsi `GROUP BY` dan `HAVING`**: `GROUP BY` digunakan untuk mengelompokkan data berdasarkan cabang (`NoCab`), dan `HAVING` menyaring hanya kelompok-kelompok yang memenuhi syarat, yaitu yang memiliki 3 atau lebih pegawai.
    
- **Hasil Akhir**: Hasil query akan menampilkan dua kolom: `NoCab` dan `Jumlah_Pegawai`. Setiap baris dalam hasil tersebut akan menunjukkan sebuah cabang yang memiliki 3 atau lebih pegawai, beserta jumlah pegawai di cabang tersebut.


---

```SQL

```