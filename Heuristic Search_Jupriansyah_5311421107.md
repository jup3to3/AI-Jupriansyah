### Jupriansyah 5311421107

<center><h1>PRAKTIKUM 5 : TEKNIK HEURISTIC SEARCH</h1></center>

1. Pelajari class EightPuzzleSearch, EightPuzzleSpace, dan Node.

- EightPuzzleSearch Class

Kelas EightPuzzleSearch adalah representasi dari algoritma pencarian yang digunakan dalam masalah 8-Puzzle. Masalah 8-Puzzle adalah permainan papan di mana kita harus menggeser ubin-ubin yang diacak di papan 3x3 untuk membentuk pola tertentu. Dalam situasi ini, simbol "0" digunakan untuk menandai ubin kosong yang dapat dipindahkan.

- EightPuzzleSpace Class

Kelas ini menentukan keadaan awal dan tujuan dalam permainan 8-puzzle, juga menghasilkan simpul-simpul penerus. Fungsi `getRoot()` memberikan kembali keadaan awal sebagai simpul. Fungsi `getGoal()` mengembalikan keadaan tujuan sebagai simpul. Fungsi `getSuccessors(Node parent)` menciptakan simpul-simpul penerus dengan mempertimbangkan perpindahan ubin kosong. Sedangkan fungsi `transformState()` digunakan untuk membentuk simpul baru dengan menukar posisi dua ubin dalam keadaan.

- Node Class

Kelas Node menggambarkan suatu simpul atau keadaan dalam domain pencarian, terutama dalam konteks menyelesaikan masalah 8-puzzle. Properti `state` berisi sebuah array yang memuat sembilan angka bulat yang mewakili keadaan atau posisi ubin dalam papan permainan. Sementara itu, properti `cost` mengindikasikan biaya terkait untuk mencapai simpul ini. `parent` adalah referensi ke simpul yang menjadi induk dalam struktur pencarian. Selanjutnya, properti `successors` adalah kumpulan dari simpul-simpul anak.

Kode dalam kelas ini menerapkan metode pencarian heuristik untuk menemukan solusi dalam masalah 8-puzzle. Pendekatan ini melibatkan eksplorasi berbagai keadaan, menilai biaya berdasarkan heuristik, dan memilih simpul-simpul yang menjanjikan untuk dieksplorasi lebih lanjut. Proses pencarian terus berlanjut hingga solusi ditemukan atau semua kemungkinan telah dijelajahi.

HASIL SIMULASI

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Hasil%20Simulasi%20Nomor%201.png)

a. Keadaan awal : Tata letak papan puzzle terdiri dari sembilan kotak yang disusun dalam format matriks 3x3. Nilai 0 mewakili kotak kosong yang dapat dipindahkan ke atas, bawah, kiri, atau kanan untuk mencapai tujuan akhir.

b. Langkah 1 : Pada tahap awal, kotak kosong dipindahkan dari koordinat (3,3) ke koordinat (2,3), menghasilkan konfigurasi baru.

c. Langkah 2 : Ubin digeser dari posisi (2,3) ke (2,2)

d. Langkah 3 : Ubin digeser dari posisi (2,2) ke (1,2)

e. Tujuan : Ubin kosong digeser dari posisi (1,2) ke (1,1), sehingga mencapai keadaan tujuan yang diinginkan.

2. Ubahlah initial dan goal state dari program di atas sehingga bentuk initial dan goal statenya Gambar 8. Kemudian tentukan langkah-langkah mana saja sehingga puzzlenya mencapai goal state. Analisa dan bedakan dengan solusi pada point 1.

HASIL SIMULASI

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Hasil%20Simulasi%20Nomor%202.png)

Langkah-langkah

a. Menggeser ubin kosong dari (3,3) ke (3,2)

b. Menggeser ubin kosong dari (3,2) ke (3,1)

c. Menggeser ubin kosong dari (3,1) ke (2,1)

d. Menggeser ubin kosong dari (2,1) ke (2,2)

e. Menggeser ubin kosong dari (2,2) ke (1,2)

f. Menggeser ubin kosong dari (1,2) ke (1,2)

g. Menggeser ubin kosong dari (1,3) ke (2,3)

h. Menggeser ubin kosong dari (2,3) ke (2,2)

i. Menggeser ubin kosong dari (2,2) ke (2,1)

j. Menggeser ubin kosong dari (2,1) ke (1,1)

k. Menggeser ubin kosong dari (1,1) ke (1,2)

l. Menggeser ubin kosong dari (1,2) ke (1,3)

m. Menggeser ubin kosong dari (1,3) ke (2,3)

n. Menggeser ubin kosong dari (2,3) ke (2,2)

o. Menggeser ubin kosong dari (2,2) ke (2,1)

p. Menggeser ubin kosong dari (2,1) ke (1,1)

q. Menggeser ubin kosong dari (1,1) ke (1,2)

r. Tujuan : Menggeser ubin kosong dari (1,2) ke (1,3)

Perbandingan Cara Penyelesaian dengan Jawaban Nomor 1

Kedua penyelesaian berhasil mencapai tujuan akhir, tetapi mereka berbeda dalam kompleksitas dan jumlah langkah yang dibutuhkan. Penyelesaian pertama lebih sederhana dan efisien, sementara penyelesaian kedua memerlukan lebih banyak langkah karena kondisi awal yang berbeda. Kedua penyelesaian ini menunjukkan bagaimana perbedaan dalam kondisi awal dapat mempengaruhi jalur pencarian dalam masalah 8-puzzle.

3. Ubahlah initial dan goal state dari program di atas sehingga bentuk initial dan goal statenya Gambar 5.9. Kemudian tentukan langkah-langkah mana saja sehingga puzzlenya mencapai goal state. Analisa dan bedakan dengan solusi pada point 1 dan 2.

HASIL SIMULASI

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Hasil%20Simulasi%20Nomor%203.png)

Solusi pertama dan kedua adalah solusi yang efektif dan cenderung lebih mudah. Baik solusi pertama maupun kedua memerlukan jumlah langkah yang sama dan dapat mencapai tujuan dengan cepat. Di sisi lain, solusi ketiga, meskipun berhasil mencapai tujuan, memerlukan jumlah langkah yang lebih banyak dan memakan waktu lebih lama untuk diselesaikan. Perbedaan dalam keadaan awal dan tujuan dapat mempengaruhi kompleksitas dari teka-teki ini.

4. Ubahlah initial dan goal state dari program di atas sehingga bentuk initial dan goal statenya Gambar 5.10. Kemudian tentukan langkah-langkah mana saja sehingga puzzlenya mencapai goal state. Analisa dan bedakan dengan solusi pada point 1, 2, dan 3.

HASIL SIMULASI

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Hasil%20Simulasi%20Nomor%204.png)

Hasil analisis menunjukkan bahwa Solusi 1 dan Solusi 4 adalah yang paling optimal, sementara Solusi 3 adalah yang paling lambat dan membutuhkan waktu yang sangat lama. Solusi 2 berada di posisi tengah dalam hal jumlah langkah, namun masih memakan waktu yang signifikan dibandingkan dengan Solusi 1 dan Solusi 4.

5. Ubahlah initial dan goal state dari program dan class-class di atas sehingga bentuk initial dan goal statenya Gambar 5.11. Kemudian tentukan langkah-langkah mana saja sehingga puzzlenya mencapai goal state.

Langkah-langkah

a. Geser ubin C ke atas, sehingga keadaannya menjadi "DBEAF0HCCG".

b. Geser ubin G ke kiri, sehingga keadaannya menjadi "DBEAFGH0CC".

c. Geser ubin H ke kiri, sehingga keadaannya menjadi "DBEAFH0GCC".

d. Geser ubin C ke atas, sehingga keadaannya menjadi "DBEAF0HCFC".

e. Geser ubin F ke kanan, sehingga keadaannya menjadi "DBEAFHF0CC".

f. Geser ubin E ke kanan, sehingga keadaannya menjadi "DBEAF0EFCH".

g. Geser ubin C ke atas, sehingga keadaannya menjadi "DBEAFCE0FH".

h. Geser ubin D ke kiri, sehingga keadaannya menjadi "DBEAF0CDEF".

i. Geser ubin E ke atas, sehingga keadaannya menjadi "DBE0FCEAHF".

j. Geser ubin F ke kanan, sehingga keadaannya menjadi "DBEFCE0AHF".

k. Geser ubin A ke kanan, sehingga keadaannya menjadi "DBEF0CEAHF".

l. Geser ubin H ke kanan, sehingga keadaannya menjadi "DBEFCEAH0F".

m. Geser ubin H ke kanan, sehingga keadaannya menjadi "DBEFCEA0HF".

n. Geser ubin F ke kanan, sehingga keadaannya menjadi "DBEFCE0AHF".

o. Geser ubin C ke atas, sehingga keadaannya menjadi "DBE0CEFAHF".

p. Geser ubin E ke atas, sehingga keadaannya menjadi "DBECE0FAHF".

q. Geser ubin F ke kanan, sehingga keadaannya menjadi "DBECEF0AHF".

r. Geser ubin A ke kanan, sehingga mencapai keadaan tujuan "AHGB0FCDE".
