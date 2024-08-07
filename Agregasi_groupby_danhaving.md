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

![[Asset/gambar1.JPG]]
- `desc pegawai`;` 
Kueri ini digunakan untuk menampilkan struktur tabel `pegawai`, termasuk nama kolom, tipe data, batasan null/bukan null, batasan kunci, nilai default, dan informasi tambahan. Output kueri ini memberikan gambaran umum yang jelas tentang skema tabel, yang berguna untuk memahami data yang tersimpan dalam tabel.

- `NIP (Nomor Induk Pegawai)`: Bidang ini adalah tipe data integer dan bertindak sebagai kunci utama untuk tabel. Bidang ini tidak boleh null, yang berarti bahwa setiap baris dalam tabel harus memiliki nilai NIP yang unik.
- `NDep (Nama Departemen)`: Ini adalah kolom varchar yang menyimpan nama departemen. Kolom ini tidak boleh null, yang berarti bahwa setiap karyawan harus dikaitkan dengan suatu departemen.
- `NBlk (Nama Blok)`: Ini adalah kolom varchar yang menyimpan nama blok. Kolom ini tidak boleh null, yang berarti bahwa setiap karyawan harus dikaitkan dengan blok.
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