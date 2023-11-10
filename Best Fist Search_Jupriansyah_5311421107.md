### Jupriansyah 5311421107

<center><h1>PRAKTIKUM 6 : PERMAINAN TIC TAC TOE</h1></center>

Praktikum ini dilakukan untuk meningkatkan pemahaman mahasiswa terhadap code permainan tic tac toe. Selain itu, modul 6
memberikan pengetahuan tentang Object Oriented Programming menggunakan bahasa pemrograman
Java terutama Java Swing dan Japplet.

##### Enumaration State (State.Java)

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Enumeration%20State.png)

Kode Java tersebut mendefinisikan sebuah enumerasi bernama `GameState` dalam paket `TicTacToe`. Enum ini memiliki empat nilai yang mungkin:

1. `PLAYING`: Permainan sedang berlangsung.
2. `DRAW`: Permainan berakhir dengan hasil seri.
3. `CROSS_WON`: Pemain dengan simbol "X" menang.
4. `NOUGHT_WON`: Pemain dengan simbol "O" menang.

Enumerasi ini digunakan untuk merepresentasikan berbagai keadaan atau kondisi yang mungkin terjadi dalam permainan Tic Tac Toe.

##### Enumaration Seed (Seed.Java)

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Enumeration%20Seed.png)

Kode Java di atas mendefinisikan sebuah kelas enumerasi bernama `Seed` dalam paket `TicTacToe`. Enumerasi ini digunakan untuk merepresentasikan tiga kemungkinan isi sel atau kotak dalam permainan Tic Tac Toe.

Enum `Seed` memiliki tiga nilai:
1. `EMPTY`: Mewakili sel atau kotak yang kosong atau belum diisi oleh pemain manapun.

2. `CROSS`: Mewakili sel atau kotak yang diisi oleh pemain dengan simbol "X".

3. `NOUGHT`: Mewakili sel atau kotak yang diisi oleh pemain dengan simbol "O".

Dengan menggunakan enumerasi `Seed`, kita dapat dengan jelas dan mudah membedakan antara sel yang kosong dan sel yang diisi oleh pemain dengan simbol tertentu. Ini memudahkan pengembangan dan pemeliharaan logika permainan Tic Tac Toe.

Sebagai contoh, jika kita ingin menentukan isi suatu sel dalam papan permainan, kita bisa menggunakan `Seed.EMPTY`, `Seed.CROSS`, atau `Seed.NOUGHT` untuk merepresentasikan keadaan sel tersebut.

##### Enumaration Game State (GameState.Java)

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Enumeration%20GameState.png)

Kode Java tersebut mendefinisikan sebuah kelas enumerasi bernama `State` dalam paket `TicTacToe`. Enumerasi ini digunakan untuk merepresentasikan berbagai keadaan atau kondisi yang mungkin terjadi dalam permainan Tic Tac Toe.

Enum `State` memiliki empat nilai:

1. `PLAYING`: Menunjukkan bahwa permainan masih berlangsung, belum ada pemenang, dan masih ada langkah yang dapat dilakukan.

2. `DRAW`: Menunjukkan bahwa permainan berakhir dengan hasil seri, artinya semua sel atau kotak dalam papan telah terisi, tetapi tidak ada pemain yang menang.

3. `CROSS_WON`: Menunjukkan bahwa pemain yang menggunakan simbol "X" telah menang.

4. `NOUGHT_WON`: Menunjukkan bahwa pemain yang menggunakan simbol "O" telah menang.

Enumerasi ini menyediakan representasi jelas dan terstruktur untuk keadaan permainan dalam permainan Tic Tac Toe. Ini memudahkan dalam pengembangan dan pemeliharaan logika permainan.

##### Class Cell.Java

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Kodingan%20Class%20Cell.png)

Kode Java di atas mendefinisikan kelas `Cell` yang merepresentasikan sel atau kotak dalam papan permainan Tic-Tac-Toe. Berikut adalah penjelasan lebih detailnya:

1. **Package and Imports**:
   - `package TicTacToe;`: Mendefinisikan paket untuk kelas `Cell`.
   - `import java.awt.Graphics;`, `import java.awt.*;`, `import java.awt.Graphics2D;`: Mengimpor kelas-kelas dari pustaka Java Abstract Window Toolkit (AWT) untuk penanganan grafis.

2. **Class Definition**:
   - `public class Cell`: Mendefinisikan kelas `Cell`.

3. **Instance Variables**:
   - `Seed content;`: Merepresentasikan isi dari sel ini (berupa `Seed.EMPTY`, `Seed.CROSS`, atau `Seed.NOUGHT`).
   - `int row, col;`: Merepresentasikan baris dan kolom dari sel ini dalam papan permainan.

4. **Constructor**:
   - `public Cell(int row, int col)`: Konstruktor untuk menginisialisasi sel dengan baris dan kolom tertentu. Ketika sel dibuat, konstruktor ini akan dijalankan. Sel akan diatur ke keadaan awal kosong (`Seed.EMPTY`) dengan memanggil metode `clear()`.

5. **Clear Method**:
   - `public void clear()`: Metode untuk mengosongkan isi sel. Ini mengatur konten sel ke `Seed.EMPTY`.

6. **Paint Method**:
   - `public void paint(Graphics g)`: Metode untuk menggambar sel pada kanvas grafis yang diberikan.

      - `Graphics2D g2d = (Graphics2D)g;`: Mengonversi objek `Graphics` ke `Graphics2D` yang memungkinkan pengaturan ketebalan garis.
      - `g2d.setStroke(new BasicStroke(GameMain.SYMBOL_STROKE_WIDTH, ...));`: Mengatur ketebalan garis untuk gambar simbol.
      - `int x1 = col * GameMain.CELL_SIZE + GameMain.CELL_PADDING;`: Menghitung koordinat x untuk gambar simbol.
      - `int y1 = row * GameMain.CELL_SIZE + GameMain.CELL_PADDING;`: Menghitung koordinat y untuk gambar simbol.

      Jika konten sel adalah `Seed.CROSS`, maka:
      - Garis-garis diagonal berwarna merah akan digambar.

      Jika konten sel adalah `Seed.NOUGHT`, maka:
      - Sebuah lingkaran biru akan digambar.

Kelas `Cell` ini bertanggung jawab untuk merepresentasikan dan menggambar setiap sel atau kotak dalam papan permainan Tic-Tac-Toe.

##### Class Board.Java

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Kodingan%20Class%20Board%201.png)

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Kodingan%20Class%20Board%202.png)

Kode Java yang diberikan mendefinisikan kelas `Board` yang digunakan untuk mengelola papan permainan Tic-Tac-Toe. Berikut adalah penjelasan lebih detailnya:

1. `Cell[][] cells`: Ini adalah atribut yang merupakan sebuah array 2D dari objek `Cell`. `Cell` merepresentasikan setiap kotak atau sel dalam papan permainan. `cells` menyimpan semua sel dalam papan permainan.


2. `public Board()`: Ini adalah konstruktor kelas `Board`. Saat objek `Board` dibuat, konstruktor ini akan dijalankan. Dalam konstruktor ini, papan permainan akan diinisialisasi.

   - `cells = new Cell[GameMain.ROWS][GameMain.COLS];`: Membuat array 2D dari objek `Cell` dengan ukuran yang sesuai dengan konstanta `ROWS` dan `COLS` dari kelas `GameMain`.

   - `for (int row = 0; row < GameMain.ROWS; ++row) { ... }`: Looping untuk mengisi setiap elemen array dengan objek `Cell`.
   

3. `public void init()`: Metode ini digunakan untuk menginisialisasi ulang papan permainan. Ini berarti mengosongkan isi dari setiap sel di papan.

   - `cells[row][col].clear();`: Memanggil metode `clear()` dari objek `Cell` untuk mengosongkan isi sel.
   

4. `public boolean isDraw()`: Metode ini memeriksa apakah permainan berakhir dengan hasil seri (draw), artinya tidak ada sel kosong yang tersisa.

   - Pertama-tama, metode melakukan dua kali loop untuk mengakses setiap sel di papan.

   - Jika ditemukan sel yang masih kosong (`cells[row][col].content == Seed.EMPTY`), maka permainan belum berakhir dengan hasil seri.

   - Jika tidak ada sel yang kosong ditemukan, maka permainan dianggap berakhir dengan hasil seri.
   

5. `public boolean hasWon(Seed seed, int seedRow, int seedCol)`: Metode ini memeriksa apakah pemain dengan simbol `seed` telah memenangkan permainan setelah menempatkan biji di posisi `(seedRow, seedCol)`.

   - Metode ini menggunakan serangkaian kondisi logis untuk memeriksa apakah ada baris, kolom, atau diagonal yang terdiri dari tiga simbol `seed`.
   

6. `public void paint(Graphics g)`: Metode ini digunakan untuk menggambar papan permainan dan sel-selnya.

   - Pertama, metode menggambar garis-garis pembatas antar sel.

   - Kemudian, metode memanggil `paint(g)` untuk setiap sel di papan, sehingga setiap sel akan menggambar dirinya sendiri.

Kelas `Board` ini berfungsi sebagai representasi papan permainan dan menyediakan metode untuk mengelola, memeriksa status, dan menggambar papan tersebut.

##### Class GameMain.Java

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Kodingan%20Class%20GameMain%201.png)

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Kodingan%20Class%20GameMain%202.png)

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Kodingan%20Class%20GameMain%203.png)

![alt text](https://github.com/jup3to3/AI-Jupriansyah/blob/main/Kodingan%20Class%20GameMain%204.png)

Kode Java di atas adalah implementasi dari permainan Tic-Tac-Toe dengan antarmuka grafis. Ini terdiri dari beberapa kelas dan metode untuk mengelola logika permainan dan antarmuka pengguna.

Berikut adalah penjelasan rinci dari kelas `GameMain`:

1. **Package and Imports**:
   - `package TicTacToe;`: Mendefinisikan paket untuk kelas-kelas dalam permainan Tic-Tac-Toe.
   - `import java.awt.*;`, `import java.awt.event.*;`, `import javax.swing.*;`: Mengimpor kelas-kelas dari pustaka Java Abstract Window Toolkit (AWT) dan pustaka Java Swing untuk menangani antarmuka grafis.

2. **Class Definition**:
   - `public class GameMain extends JPanel`: Mendefinisikan kelas `GameMain` yang meng-extend kelas `JPanel`. Ini berarti `GameMain` adalah komponen GUI dan dapat digunakan dalam suatu jendela atau frame GUI.

3. **Named-Constants for the Game Board**:
   - `public static final int ROWS = 3;`, `public static final int COLS = 3;`: Mendefinisikan konstanta untuk ukuran papan permainan, yaitu 3 baris dan 3 kolom.
   - `public static final String TITLE = "Tic Tac Toe";`: Mendefinisikan judul untuk jendela permainan.

4. **Named-Constants for Graphics**:
   - Beberapa konstanta lain yang mendefinisikan ukuran dan properti grafis seperti ukuran sel, lebar garis grid, dll.

5. **Instance Variables**:
   - `private Board board;`: Merepresentasikan objek `Board` yang merupakan papan permainan.
   - `private GameState currentState;`: Merepresentasikan keadaan atau status saat ini dari permainan.
   - `private Seed currentPlayer;`: Merepresentasikan pemain saat ini (X atau O).
   - `private JLabel statusBar;`: Merepresentasikan label untuk menampilkan pesan status permainan.

6. **Constructor**:
   - `public GameMain()`: Konstruktor kelas `GameMain`. Di dalam konstruktor ini, berbagai inisialisasi dilakukan. Misalnya, mendefinisikan mouse-clicked handler, menginisialisasi status bar, membuat objek `Board`, dan memulai permainan dengan memanggil `initGame()`.

7. **Mouse Clicked Handler**:
   - Di dalam konstruktor, ada kode untuk menangani klik mouse. Jika permainan masih berlangsung (`currentState == GameState.PLAYING`), maka akan menentukan baris dan kolom yang diklik dan memperbarui permainan jika langkah tersebut sah.

8. **Initialize Game** (`initGame()`) :
   - Metode ini menginisialisasi ulang papan permainan dan keadaan permainan.

9. **Update Game** (`updateGame(Seed theSeed, int row, int col)`) :
   - Metode ini memperbarui keadaan permainan setelah pemain dengan simbol `theSeed` melakukan langkah di posisi `(row, col)`.

10. **Custom Painting Codes**:
   - `public void paintComponent(Graphics g)`: Metode ini menggambar komponen `GameMain`. Ini termasuk menggambar papan permainan dan sel-selnya, serta menampilkan pesan status di status bar.

11. **Main Method**:
    - `public static void main(String[] args)`: Metode utama yang menjalankan aplikasi. Itu memulai aplikasi dalam lingkungan GUI Swing.

Kode tersebut mengimplementasikan permainan Tic-Tac-Toe dengan antarmuka grafis dan menggunakan kelas `Board` untuk mengelola logika permainan.









