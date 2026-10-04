# Tugas Pendahuluan

## 1. Perbandingan Struktur Data `/posts/1` dan `/users/1`
Endpoint `/posts/1` digunakan untuk mengambil satu data postingan berdasarkan ID. Field yang terdapat di dalamnya yaitu `userId`, `id`, `title`, dan `body`. `userId` menunjukkan pengguna yang membuat postingan, `id` merupakan ID postingan, `title` adalah judul, dan `body` adalah isi postingan.

Sedangkan `/users/1` digunakan untuk mengambil data pengguna berdasarkan ID. Field yang tersedia antara lain `id`, `name`, `username`, `email`, `address`, `phone`, `website`, dan `company`. Jadi, `/posts/1` berfokus pada informasi postingan, sedangkan `/users/1` berfokus pada informasi pengguna.


## 2. Struktur Tabel dan Relasi `/posts` dan `/users`
Endpoint `/posts` dapat dianggap sebagai tabel `posts`, sedangkan `/users` sebagai tabel `users`. Pada tabel `posts` terdapat field `userId` yang menunjukkan user yang membuat suatu post. Field tersebut berhubungan dengan `id` pada tabel `users`, sehingga satu user dapat memiliki banyak post.

```text
users
----------------
id (PK)
name
username
email
   │
   │ 1 : N
   ▼
posts
----------------
id (PK)
userId (FK)
title
body
```


## 3. Hubungan URL, Method, dan Data yang Dikembalikan pada `/posts`
URL digunakan untuk menentukan resource yang ingin diakses, sedangkan HTTP method menentukan tindakan terhadap resource tersebut. Contohnya, `GET /posts` digunakan untuk mengambil seluruh data postingan, sedangkan `GET /posts/1` digunakan untuk mengambil satu postingan dengan ID `1`.

Setelah request dikirim, JSONPlaceholder mengembalikan response berupa data JSON yang sesuai dengan URL dan method yang digunakan. Jadi, URL menentukan data yang dituju, method menentukan operasinya, dan response berisi hasil dari request tersebut.


## 4. Perbedaan `/posts/1` dan `?userId=1`
`/posts/1` digunakan untuk mengambil satu postingan berdasarkan `id` postingan. Artinya, server mencari post yang memiliki `id = 1`.

Sedangkan `/posts?userId=1` menggunakan query parameter untuk memfilter postingan berdasarkan `userId`. Hasilnya dapat berupa beberapa postingan yang dibuat oleh user dengan `userId = 1`.

Jadi, `/posts/1` mencari berdasarkan **ID post**, sedangkan `/posts?userId=1` mencari berdasarkan **ID user**.



## 5. Perbandingan GET, POST, PUT, PATCH, dan DELETE pada JSONPlaceholder

| **Method** | **Endpoint** | **Status Code** | **Fungsi** | **Perubahan Data** |
| :--------- | :----------- | :------------: | :--------- | :----------------- |
| GET | `/posts/1` | 200 | Mengambil data postingan | Tidak mengubah data |
| POST | `/posts` | 201 | Menambahkan postingan baru | Data baru dibuat secara simulasi |
| PUT | `/posts/1` | 200 | Memperbarui seluruh data postingan | Perubahan disimulasikan |
| PATCH | `/posts/1` | 200 | Memperbarui sebagian data postingan | Perubahan disimulasikan |
| DELETE | `/posts/1` | 200 | Menghapus postingan | Penghapusan disimulasikan |

JSONPlaceholder mengembalikan status code sesuai hasil request. Namun, perubahan data dari POST, PUT, PATCH, dan DELETE hanya disimulasikan dan tidak disimpan secara permanen.