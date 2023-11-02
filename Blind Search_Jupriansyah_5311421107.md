### Jupriansyah 5311421107

<center><h1>PRAKTIKUM 4 : TEKNIK PENCARIAN BLIND SEARCH</h1></center>

1. Tentukan bagaimana algoritma BFS di atas dapat menentukan node ke 8, 6, dan 7!

Breadth-First Search (BFS) adalah sebuah algoritma pencarian dalam ilmu komputer yang digunakan untuk melakukan penjelajahan atau pencarian informasi pada graf atau struktur data berdasarkan tingkat jarak atau kedalaman dari simpul awal. Algoritma ini memungkinkan kita untuk menemukan jalur terpendek dari satu simpul (node) ke simpul lain dalam graf. Pada algoritma ini, simpul-simpul yang terhubung secara langsung dengan simpul awal akan dieksplorasi terlebih dahulu sebelum simpul-simpul yang berada lebih dalam atau lebih jauh dari simpul awal.
   
    
Berikut adalah proses pencarian dari algoritma BFS:
    
a. Langkah pertama adalah menginisialisasi simpul awal, yaitu simpul 3, dan kemudian memasukkannya ke dalam antrian.
    
b. Selanjutnya, simpul 3 akan mengeksplorasi simpul-simpul yang terhubung langsung dengannya, yaitu simpul 2 dan simpul 4, karena keduanya memiliki jarak 1 dari simpul 3. Kemudian, simpul 4 akan melanjutkan dengan mengeksplorasi simpul 1, simpul 6, dan simpul 5 yang terhubung dengan itu.
    
c. Setelah itu, simpul 5 akan mengeksplorasi simpul 8 dan simpul 7.
    
d. Proses ini akan terus berlanjut sampai semua simpul yang terhubung dengan simpul awal telah diperiksa. Oleh karena itu, simpul-simpul 8, 6, dan 7 akan ditemukan dan diproses sesuai dengan aturan BFS.

HASIL PROGRAM

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Hasil%20Tugas%20No%201.png)

Berdasarkan hasil di atas, proses BFS dimulai dari simpul (node) ke-3 (n3). Berikut adalah langkah-langkah untuk mencapai node ke-8, 6, dan 7:
- Node 3 (d=0): BFS dimulai dari simpul n3 dengan jarak 0.
- Node 4 (d=1): n3 memiliki tetangga n4, sehingga BFS melanjutkan ke n4 dengan jarak 1.
- Node 2 (d=1): n4 memiliki tetangga n2, namun n2 sudah diwarnai GRAY (dalam proses BFS), jadi BFS tidak melanjutkan ke n2.
- Node 5 (d=2): n4 juga memiliki tetangga n5, yang belum diwarnai, jadi BFS melanjutkan ke n5 dengan jarak 2.
- Node 6 (d=2): n5 memiliki tetangga n6, yang belum diwarnai, jadi BFS melanjutkan ke n6 dengan jarak 2.
- Node 1 (d=2): n5 juga memiliki tetangga n1, yang belum diwarnai, jadi BFS melanjutkan ke n1 dengan jarak 2.
- Node 7 (d=3): n6 memiliki tetangga n7, yang belum diwarnai, jadi BFS melanjutkan ke n7 dengan jarak 3.
- Node 8 (d=3): n6 juga memiliki tetangga n8, yang belum diwarnai, jadi BFS melanjutkan ke n8 dengan jarak 3.

2. Ubahlah method static void main sehingga bentuk tree seperti Gambar 4.4 dapat dibentuk! Kemudian tentukan bagaimana algoritma BFS dapat menemukan node 5!

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Kodingan%20Tugas%202%20(Node).png)

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Kodingan%20Tugas%202%20(Graph).png)

HASIL PROGRAM

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Hasil%20Tugas%20No%202.png)

Hasil tersebut memvalidasi kesesuaian antara struktur pohon yang dihasilkan oleh program dengan gambar 4.5.
- Dalam pencarian node 5, algoritma BFS pertama-tama memasukkan node 1 ke dalam antrian.
- Setelah itu, node 1 akan mengeksplorasi node 2 dan node 3, yang langsung terhubung dengan node 1 atau memiliki kedalaman level 1.
- Selanjutnya, node 3 akan melanjutkan dengan mengeksplorasi node yang memiliki jarak atau kedalaman level 2, dimulai dengan memeriksa node 4, node 5, node 6, dan node 7.
- Setelah node 5 ditemukan, proses akan terus berlanjut hingga semua node yang terhubung dengan node awal telah diperiksa.
Oleh karena itu, node 5 akan ditemukan dan diproses sesuai dengan aturan algoritma BFS.

3. Ubahlah method static void main sehingga bentuk tree seperti Gambar 4.5 dapat dibentuk! Kemudian tentukan bagaimana algoritma BFS dapat menemukan node 9!

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Kodingan%20Tugas%203%20(Node).png)

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Kodingan%20Tugas%203%20(Graph).png)

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Kodingan%20Tugas%203%20(Graph)%202.png)

HASIL PRAKTIKUM

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Hasil%20Tugas%20No%203.png)

Hasil tersebut memverifikasi bahwa struktur pohon yang dihasilkan oleh program cocok dengan gambar 4.6.
- Dalam pencarian node 9, algoritma BFS memulainya dengan memasukkan node 1 ke dalam antrian.
- Kemudian, node 1 akan mengecek node 2, node 3, dan node 4 yang terhubung langsung dengan node 1 atau memiliki kedalaman level 1.
- Selanjutnya, node 4 akan mengecek node yang memiliki kedalaman level 2, dimulai dari memeriksa node 5, node 6, node 7, dan node 8.
- Setelah itu, node 8 akan mengecek node 9. Setelah node 9 ditemukan, proses akan terus berlanjut untuk memeriksa node 10, node 11, dan node 12 hingga semua node yang terhubung dengan node awal telah diperiksa.
Dengan demikian, pada akhir proses BFS, node 9 akan ditemukan dan diproses sesuai dengan aturan algoritma BFS.

4. Ubahlah kode program di atas sehingga bentuk tree seperti Gambar 6 dapat dibentuk! Kemudian tentukan bagaimana algoritma BFS dapat menemukan node C!

a. Dalam kelas Node, untuk dapat menerima huruf, perlu dilakukan perubahan pada tipe data variabel 'data' dari int menjadi String.

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Kodingan%20Tugas%204%20(String).png)

b. Setelah itu, dalam metode main, memasukkan nilai node dengan menggunakan tipe data string seperti yang tertera di bawah ini.

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Kodingan%20Tugas%204%20(Node).png)

c. Kemudian, di dalam metode addEdge dan bfs, disertakan logika pemrosesan data untuk tipe data String seperti berikut.

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Kodingan%20Tugas%204%20(Graph).png)

HASIL PROGRAM

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Hasil%20Tugas%20No%204.png)

Hasil tersebut memvalidasi bahwa struktur pohon yang dihasilkan oleh program sesuai dengan gambar 4.7.
- Dalam pencarian node 3 (C), algoritma BFS memulainya dengan memasukkan node 6 (F) ke dalam antrian.
- Selanjutnya, node 6 (F) akan memeriksa node 2 (B) dan node 7 (G) yang terhubung langsung dengan node 6 atau node yang memiliki kedalaman level 1.
- Selanjutnya, node 7 akan mengecek node yang memiliki kedalaman level 2, dimulai dari memeriksa node 1 (A), node 4 (D), dan node 9 (I).
- Setelah itu, node 9 akan mengecek node 3 (C). Setelah berhasil menemukan node 3 (C), proses akan terus berlanjut untuk mengecek node 5 (E) dan node 8 (H) hingga semua node yang terhubung dengan node awal telah diperiksa.
Akhirnya, pada akhir proses BFS, node 3 (C) akan ditemukan dan diproses sesuai dengan aturan algoritma BFS.
