# Praktikum Partitioning Database MySQL

## Deskripsi
Repository ini berisi praktikum penggunaan fitur **Partitioning** pada MariaDB/MySQL menggunakan database **toko**. Partitioning digunakan untuk membagi data ke dalam beberapa partisi berdasarkan kategori barang sehingga data lebih terorganisir dan mudah dikelola.

## Teknologi yang Digunakan
- MariaDB 10.4
- MySQL
- XAMPP
- Command Prompt (CMD)

## Struktur Tabel

Tabel `barang` menggunakan metode **LIST Partition** berdasarkan kolom `kategori`.

```sql
CREATE TABLE barang (
    id_barang INT,
    nama_barang VARCHAR(50),
    kategori INT,
    stok INT,
    PRIMARY KEY (id_barang, kategori)
)
PARTITION BY LIST (kategori) (
    PARTITION elektronik VALUES IN (1),
    PARTITION aksesoris VALUES IN (2),
    PARTITION lainnya VALUES IN (3)
);
```

## Data Sample

```sql
INSERT INTO barang VALUES
(1,'Laptop',1,10),
(2,'Mouse',2,20),
(3,'Keyboard',2,15),
(4,'Meja Komputer',3,5);
```

## Screenshot Praktikum

- Membuat Tabel Partitioning
- Menampilkan Data Partisi Tabel
- Melihat Struktur Tabel
- Melihat Jumlah Data di Partisi

## Tujuan Praktikum

- Memahami konsep partitioning pada database.
- Membuat tabel menggunakan fitur partitioning.
- Menampilkan data berdasarkan partisi tertentu.
- Melihat struktur tabel partitioning.
- Mengetahui jumlah data pada setiap partisi.

## Hasil

Praktikum berhasil membuat tabel partitioning menggunakan metode LIST Partition. Data tersimpan pada partisi yang sesuai dengan kategori barang dan dapat ditampilkan berdasarkan partisi tertentu.

## Author

Nama : Asroful Awlya  
Mata Kuliah : Sistem Basis Data  
Universitas : [Nama Kampus]
