# Tugas Mandiri 5 — Membandingkan SQL Mentah dan ORM

## Operasi yang Dipilih

Operasi yang dipilih adalah **mengubah data jadwal berdasarkan ID** pada tabel `jadwal`.
Contoh yang digunakan adalah mengubah status jadwal dengan `id = 2` menjadi `nonaktif`.

## A. SQL Mentah

```sql
UPDATE jadwal
SET status = 'nonaktif'
WHERE id = 2;
```
Query tersebut digunakan untuk mengubah nilai `status` pada data jadwal yang memiliki ID `2`.


## B. ORM
Contoh menggunakan Prisma:

```js
const jadwal = await prisma.jadwal.update({
  where: {
    id: 2
  },
  data: {
    status: "nonaktif"
  }
});
```

Kode tersebut melakukan operasi yang sama, yaitu mengubah status jadwal dengan ID `2` menggunakan ORM Prisma.

## Perbandingan SQL Mentah dan ORM

| **Pendekatan** | **Cara Kerja** | **Kelebihan** |
| :------------- | :------------- | :------------ |
| SQL Mentah | Menggunakan perintah SQL secara langsung untuk mengubah data pada database. | Memberikan kontrol langsung terhadap query dan cocok untuk kebutuhan query tertentu. |
| ORM | Menggunakan method `update()` untuk mengubah data melalui object dan parameter. | Kode lebih sederhana, terstruktur, dan mudah dibaca. |


## Jawaban Pertanyaan

### 1. Apa perbedaan SQL mentah dan ORM?
SQL mentah menggunakan perintah SQL secara langsung untuk berinteraksi dengan database. ORM menggunakan object, method, dan model dari library untuk melakukan operasi database melalui bahasa pemrograman.

### 2. Apa kelebihan SQL mentah?
SQL mentah memberikan kontrol yang lebih langsung terhadap query database dan dapat digunakan untuk kebutuhan query yang kompleks.

### 3. Apa kelebihan ORM?
ORM membuat kode lebih sederhana dan terstruktur serta memudahkan programmer melakukan operasi database tanpa menulis SQL secara langsung untuk setiap operasi.

### 4. Apa risiko SQL injection?
SQL injection adalah serangan ketika input pengguna yang tidak aman masuk ke dalam query SQL sehingga dapat memanipulasi perintah atau data pada database.

### 5. Mengapa penggunaan parameter query dapat mengurangi risiko SQL injection?
Parameter query memisahkan data input dari struktur perintah SQL sehingga nilai yang diberikan pengguna tidak diperlakukan sebagai bagian dari sintaks SQL.

### 6. Bagaimana ORM membantu programmer dalam mengakses database?
ORM menyediakan model dan method untuk operasi seperti mengambil, menambahkan, mengubah, dan menghapus data. Dengan demikian, programmer dapat berinteraksi dengan database menggunakan kode yang lebih sederhana dan terstruktur.


## Kesimpulan
SQL mentah dan ORM dapat digunakan untuk melakukan operasi database yang sama dengan pendekatan yang berbeda. SQL mentah memberikan kontrol langsung terhadap query, sedangkan ORM menyediakan cara yang lebih sederhana dan terstruktur untuk mengakses database. Pemilihan pendekatan dapat disesuaikan dengan kebutuhan aplikasi dan kompleksitas operasi database.