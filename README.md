# Belbar IT PATP

# Percabangan
Percabangan memungkinkan kita untuk menentukan kode manakah yang akan kita eksekusi berdasarkan suatu kondisi. Percabangan di bahasa C ada 4, yaitu `if`, `if-else`, `if-else if`, dan `switch`.

## Percabangan If

Sintaks yang digunakan dalam percabangan menggunakan `if` adalah sebagai berikut.

```c
if (<Ekspresi/Kondisi>) {

    // Kode yang akan dieksekusi jika kondisi tersebut benar

}
```

Cara kerja percabangan `if` yaitu memeriksa dan mengevaluasi suatu kondisi untuk menentukan apakah instruksi selanjutnya dalam _bracket_ akan dijalankan atau tidak oleh program.
- Jika kondisi tersebut bernilai **TRUE (1)**, kode yang di dalam bracket akan **dieksekusi**. 
- Sebaliknya jika kondisi tersebut bernilai **FALSE (0)**, kode yang di dalam bracket **tidak akan dieksekusi**.

```c
#include <stdio.h>
int main()
{
    int gasoline = 3;
    if (gasoline < 10) //jika bahan bakar kurang dari 10 liter
    {
        // Apa yang perlu dilakukan ketika kondisi terpenuhi?
        printf("Lampu Indikator menyala!\n");
    }
}
```

Output

```
Lampu Indikator menyala!
```

## Percabangan If-Else

Sintaks yang digunakan dalam percabangan menggunakan `if-else` adalah sebagai berikut.

```c
if (<Ekspresi/Kondisi>) {

    // Kode yang akan dieksekusi jika kondisi tersebut benar

} else {

    // Kode yang akan dieksekusi jika kondisi tersebut salah

}
```

Cara kerja percabangan `if-else` yaitu memeriksa kondisi dalam `if`.
- Jika kondisi tersebut bernilai **TRUE (1)**, Program akan **menjalankan kode di dalam bracket `if`**.
- Sebaliknya jika kondisi tersebut bernilai **FALSE (0)**, kode di bawah **`else`** lah **yang akan dijalankan**.

```c
#include <stdio.h>

int main()
{
    int hadir = 1;
    if (hadir) // Jika orang tersebut hadir
    {
        printf("V\n");
    } else {
        printf("X\n");
    }
}
```

Output

```
V

```

## Percabangan If-Else if

Sintaks yang digunakan dalam percabangan menggunakan `if-else if` adalah sebagai berikut.

```c
if (<Ekspresi/Kondisi>) {

    // Kode yang akan dieksekusi jika kondisi tersebut benar

}else if (<Ekspresi/Kondisi>) {

    // Kode yang akan dieksekusi jika kondisi tersebut salah

}
// Boleh menambahkan else{} apabila perlu
```

Cara kerja percabangan `if-else` yaitu memeriksa kondisi dalam `if`.
- Jika kondisi tersebut bernilai **TRUE (1)**, Program akan **menjalankan kode di dalam bracket `if`**.
- Apabila kondisi pertama tidak memenuhi, maka ia akan memerika kondisi didalam `else-if`, apabila bernilai **TRUE (1)**, maka ia akan **menjalankan perintah dalam bracket tersebut**, apabila tidak maka ia akan menjalankan sequence selanjutnya.
- Apabila kita menyediakan statement else diakhir, maka ketika **seluruh kondisi** `if` dan `else-if` tidak memenuhi atau **FALSE (0)**, maka secara otomatis ia akan **menjalankan perintah di dalam `else`** tersebut.

```c
#include <stdio.h>

int main()
{
    int alpa = 3;
    if (alpa >= 3)
    {
        printf("Tidak lulus\n");
    } else if (alpa >= 0) {
        printf("Lulus\n");
    } else {
        printf("Error : Tidak Valid\n");
    }
}
```

## Percabangan Switch-Case

Selain penggunaan statement `if` untuk memilih diantara banyak alternatif, terdapat pula statement `switch` yang memiliki fungsi yang sama, untuk memilih diantara banyak alternatif berdasarkan sebuah kondisi. Kondisi pada statemen `switch` berisi ekspresi yang dapat menggunakan sebuah variable tunggal bertipe int atau char yang akan diperiksa nilainya di setiap blok case.

Sintaks untuk Switch-Case:

```c
switch(ekspresi) {

    case ekspresi-konstan:
        statement;
        break;

    case ekspresi-konstan:
        statement;
        break;
  
    /* Anda bisa memiliki jumlah case sebanyak mungkin */

    /* Anda harus mengakhiri blok kode Switch-Case dengan "default",
       yaitu bagian kode yang akan dieksekusi jika tidak ada case yang memenuhi */

    default: 
        statement;
}
```

Setiap blok, case harus ditambahkan statement **``break``**, karena apabila tidak maka ia akan tetap menjalankan blok case di bawahnya hingga bertemu `break` lain atau pada akhir blok switch.

Contoh

```c
#include <stdio.h>

int main()
{
    char platNomor;
    printf("Masukkan huruf awal plat nomor anda: ");
    scanf("%c", &platNomor);

    switch(platNomor)
    {
        case 'L':
            printf("Surabaya");
            break;

        case 'B':
            printf("Jakarta");
            break;

        case 'D':
            printf("Bandung");
            break;

        case 'N':
            printf("Malang/Lumajang");
            break;

        default:
            printf("Karakter plat nomor tidak diketahui");
    } 
    return 0;
}
```

Dalam contoh di atas, **ekspresi** yang digunakan adalah **PlatNomor**, di mana **case-case** nya adalah, huruf plat nomor tersebut, L, B, D, N, dan sebagainya.

## Operator Kondisional (` ? : `)

Operator kondisional mempunyai bentuk sintaks sebagai berikut:

```
(ekspresi/kondisi) ? (ekspresi jika TRUE) : (ekspresi jika FALSE);
```

Operator kondisional adalah satu-satunya operator ternary dalam bahasa C. Operator kondisional bertingkah seperti layaknya percabangan `if - else`. Ekspresi/kondisi yang akan dievaluasi diletakkan sebelum tanda tanya (`?`). Apabila menghasilkan **TRUE**, maka program akan mengeksekusi bagian di **kiri** tanda titik dua. Jika **FALSE**, akan mengeksekusi bagian di **kanan** tanda titik dua.

Contoh:

```c
#include <stdio.h>

int main()
{
    int mark;
    
    scanf("%d", &mark);
    printf(mark >= 75 ? "Lulus\n" : "Tidak Lulus\n");
    return 0;
}
```

Program di atas ekuivalen dengan:

```c
#include <stdio.h>

int main()
{
    int mark;
    
    scanf("%d", &mark);
    if (mark >= 75) {
        printf("Lulus\n");
    } else {
        printf("Tidak Lulus\n");
    }
    return 0;
}
```


# Perulangan

Perulangan atau _looping_ memungkinkan kita untuk mengeksekusi potongan kode berulang-ulang hingga mencapai suatu kondisi. Ada 3 jenis perulangan dalam bahasa C, yaitu `while`, `do - while`, dan `for`.

## Perulangan While

Perulangan `while` adalah bentuk perulangan yang paling sederhana. Sintaksnya adalah sebagai berikut.

```c
//initial value misal, i = 0
while (<Ekspresi/Kondisi>) {
    // Potongan kode yang ingin dieksekusi
    .
    .
    .
    // increment/decrement misalnya, i++
}
```
Cara kerja perulangan `while` mirip dengan `if`. Jika pada **if** potongan kode akan dieksekusi **sekali saja** apabila ekspresi/kondisi bernilai **TRUE**, pada **while** potongan kode akan **terus dieksekusi** hingga ekspresi/kondisi menghasilkan **FALSE**.

Contoh

```c
#include <stdio.h>

int main()
{
    int i = 0;
    while (i < 10)
    {
        printf("Hello World! ke-%d \n",i);
        i++;
    }
    return 0;
}
```

Sehingga pada contoh di atas:

- Pada awalnya, **variabel `i`** bernilai 0. 
- Sequence selanjutnya adalah `while`, dan i bernilai kurang dari 10 (**TRUE**), maka kode didalam `while` akan dijalankan, yakni print Hello world ke-i. 
- Setelah melakukan print hello world, **variabel `i`** akan di increment, dan kembali ke statement `while` untuk memeriksa apakah **`i`** masih kurang dari 10 setelah di-increment
- Karena setelah **`i`** di-increment nilainya masih 1 dan kurang dari 10, maka `while` akan dijalankan lagi hingga **`i`** bernilai 10 yang berarti tidak memenuhi kondisi `while`.

## Perulangan Do-While

Sintaks dari perulangan `do – while` adalah sebagai berikut.
```c
do {
    // Potongan kode yang dieksekusi.
    .
    .
    // increment/decrement
} while (<Ekspresi/Kondisi>)
```

Cara kerja dari perulangan `do – while` mirip dengan perulangan `while`. Hanya saja, pada perulangan `do – while`, potongan kode dijamin akan dieksekusi tepat satu kali sebelum mengevaluasi ekspresi/kondisi.

Contoh

```c
#include <stdio.h>
int main()
{
    int num = 0;
    do
    {
        printf("Num sekarang adalah %d\n",num);
        printf("Masukkan bilangan integer positif (-1 untuk keluar ): ");
        scanf("%d", &num);
    } while (num != -1);
    return 0;
}
```

## Perulangan For

Perulangan `for` merupakan perulangan paling rumit diantara perulangan lainnya. Sintaksnya adalah sebagai berikut.

```c
for (init_statement; kondisi/ekspresi; end_statement) {
    //  Potongan kode yang dieksekusi
    .
    .
}
```

Cara kerjanya adalah sebagai berikut:
- Bagian `init_statement` digunakan untuk inisialisasi variabel yang akan digunakan dalam perulangan. Bagian ini hanya dijalankan sekali saka pada saat awal perulangan.
- Selanjutnya `kondisi/ekspresi` akan dievaluasi. Jika menghasilkan **TRUE**, maka akan mengeksekusi potongan kode. Jika menghasilkan **FALSE**, maka perulangan berhenti.
- Setelah potongan kode selesai dieksekusi, akan mengeksekusi bagian `end_statement`. Biasanya bagian ini digunakan sebagai **increment/decrement**.
- Lalu akan **mengevaluasi ekspresi/kondisi lagi**, dan begitu seterusnya.

Contoh

```c
#include <stdio.h>
int main()
{
    int i;
    //    init;condition; increment
    for (i = 0; i < 10  ; i++) {
        printf("Hello World!\n");
    }
}
```
1. Awalnya **`i`** bernilai 0
2. For statement akan memeriksa nilai **`i`** apakah kurang dari 10
3. Apabila **TRUE** maka jalankan kode dalam for block, yakni print hello world
4. Setelah command dalam block for selesai dijalankan, maka variabel **`i`** akan di-increment, dan diperiksa lagi.
5. Apabila **`i`** kurang dari 10, maka command dalam block dieksekusi, apabila tidak maka for loop akan berhenti

## Perulangan/Percabangan Bersarang (Nested)

Percabangan dan perulangan juga dapat dibuat secara bersarang (membuat percabangan/perulangan di dalam percabangan/perulangan), tentu saja menyesuaikan kebutuhan. Contoh berikut adalah perulangan `for` bersarang.
```c
int i, j;
for (i = 1; i <= 10; ++i) {
    // Statement yang ingin dijalankan pada level terluar

    for (j = 1; j <= 10; j++) {
        // Statement yang ingin dijalankan pada level terdalam

        // Percabangan di dalam perulangan
        if (i == 10) {
            // Lakukan sesuatu
        }
    }
    // Statement yang ingin dijalankan pada level terluar
}
```

# Break and Continue
Keyword `break` dan `continue` digunakan untuk mengendalikan (kontrol) alur pada perulangan. Berikut penjelasannya.

## Break
Perintah `break` digunakan untuk **menghentikan** perulangan (secara paksa). Apabila perintah `break` pada suatu perulangan dijalankan, maka perulangan tersebut akan **dihentikan (secara paksa) dari titik dimana perintah break muncul**.

Contoh

```c
#include <stdio.h>

int main()
{
	int i;
	for (i = 1; i <= 6; i++) {
		printf("%d\n", i);
		//   Jika i adalah 4, maka keluar dari perulangan
		if (i == 4) {
			break;
		}
	}
	return 0;
}
```

## Continue

Kebalikan dari perintah break, perintah `continue` digunakan untuk **melanjutkan perulangan**. Pada perulangan, apabila menemui perintah `continue`, maka perintah-perintah dibawah `continue` akan **diabaikan** dan **kembali akan mengevaluasi ekspresi/kondisi**. Sedangkan pada perulangan `for` akan langsung mengekekusi bagian end_statement kemudian mengevaluasi ekspresi/kondisi.

Contoh

```c
#include <stdio.h>

int main()
{
	int i;
    for (i = 1; i <= 6; i++) {
	    // Jika i adalah 4, maka abaikan perintah printf()
        if (i == 4) {
            continue;
        }
        printf("%d\n",i);
    }
    return 0;
}
```

# Infinite Loop

Infinite loop adalah kasus di mana perulangan tidak akan pernah berhenti. Hal ini terjadi karena perulangan tidak akan pernah menemui kondisi yang membuatnya berhenti. Contoh di bawah akan menghasilkan infinite loop.

```c
#include <stdio.h>

int main()
{
    int i;
    for (i = 1; i <= 100; i--) {
        // Perulangan tak akan pernah berhenti
    }
}
```

# Array

## Pengenalan Array

Array merupakan jenis struktur data yang menampung elemen betipe data sama secara sekuensial dengan ukuran (kapasitas) yang tetap (_fixed-size_). Bayangkanlah sebuah array sebagai sekumpulan elemen sejenis yang disusun secara berurutan pada satu _identifier_ (nama).

## Deklarasi Array

Array juga sama seperti variabel, perlu dideklarasikan terlebih dahulu sebelum bisa digunakan. Deklarasi array sama seperti variabel, hanya saja saat pendeklarasiannya perlu dituliskan ukurannya.

```
tipe_data identifier_array[size];
```

## Inisialisasi Array

Kita juga bisa menginisialisasi elemen-elemen pada array setelah dideklarasikan. Sintaksnya adalah seperti berikut.

```
tipe_data identifier_array[size] = {elem1, elem2, elem3, ....}
```

## Mengakses Array

Seperti yang telah dijelaskan sebelumnya, array disimpan secara sekuensial (pada blok memori secara berurutan). Lalu bagaimana kita mengakses tiap elemennya? Pengaksesan elemen pada array dilakukan dengan menuliskan _identifier_ array-nya lalu digabung dengan menggunakan operator subscript `[]` dengan menyertakan indeks didalamnya.

![akses_array](https://github.com/AlproITS/DP_modul-2/blob/master/img/Array_access.png)

Indeks pada array menggunakan _zero-based index_, yang artinya elemen pertama pada array ditunjukkan oleh indeks ke 0 (bukan ke 1) dan elemen terakhir ditunjukkan oleh indeks ke N-1 (misal N adalah panjang array).
Elemen-elemen pada array dapat diperlakukan sama seperti halnya variabel. Kita dapat melakukan assignment, operasi aritmatika, dan lain-lain.

Contoh:

```c
int main () 
{

  int a[10]; //Deklarasi Array
  
  int b[5] = {1, 2, 3, 4, 5}; //Inisialisasi Array
  
  a[0] = 50;
  a[1] = 20;
  
  printf("%d %d\n", a[0], a[1]);
  
  return 0;

}
```

Mengapa kita perlu array? Andaikan kita membutuhkan 1000 inputan data, kita tidak perlu membuat deklarasi variabel berjumlah 1000, misalkan variabel a1 hinga a1000. Namun, kita cukup menuliskan 1 identifier array berkapasitas 1000.

Contoh program tanpa array:
```c
int main () {

  int a, b, c, d, e; //Deklarasi 5 variabel integer
  
  scanf("%d %d %d %d %d", &a, &b, &c, &d, &e);
  
  printf("Bilangan pertama adalah %d\n", a);
  printf("Bilangan kedua adalah %d\n", b);
  printf("Bilangan ketiga adalah %d\n", c);
  printf("Bilangan keempat adalah %d\n", d);
  printf("Bilangan kelima adalah %d\n", e);
  return 0;

}
```

Bayangkan kita tidak hanya memasukkan 5 data, melainkan 1000 data, bagaimana kita mendeklarasikan semuanya dalam variabel dan kemudian mencetaknya? Maka dari itulah array digunakan.

Contoh program menggunakan array:
```c
int main () 
{
	int a[5], i; 
	for(i = 0; i < 5; i++) {
		scanf("%d", &a[i]); //Input array
	}

	for(i = 0; i < 5; i++) {
		prinf("Bilangan ke-%d adalah %d\n", i+1, a[i]; // Output array
	}

	return 0;

}
```
## Dimensi Array

### Array Satu Dimensi

Sebuah array dikatan berdimensi satu apabila tiap elemennya hanya menyimpan satu data/objek. Contoh-contoh pada penjelasan sebelumnya merupakan array satu dimensi.

Contoh array satu dimensi:

```c
int main()
{
	int arr[5];
	arr[0] = 4;
	arr[1] = 2;
	arr[2] = 3;
	return 0;
}
```

Jika diilustrasikan, maka array tersebut akan tampak seperti di bawah.

![array-satu-dimens](https://github.com/AlproITS/DP_modul-2/blob/master/img/1D_Array.png)

### Array Multidimensi

Sebuah array dikatakan multidimensional apabila tiap elemen array  menampung array lainnya. Apabila array satu dimensi hanya memiliki sebuah index, array multidimensi memiliki dua atau lebih index untuk mengakses elemen dalam array tersebut. 

Cara deklarasinya pun berbeda dari array satu dimensi. Kita memerlukan N buah kurung siku untuk membuat array dengan N-dimensi.

Berikut adalah contoh program dengan array dua dimensi:
```c
int main () 
{
	int matriks[5][6];
	matriks[2][3] = 100;
	matriks[1][4] = 200;
	return 0;
}
```

Apabila diilustrasikan, bentuk array dua dimensi layaknya baris dan kolom, seperti gambar di bawah.

![array-dua-dimensi](https://github.com/AlproITS/DP_modul-2/blob/master/img/2D_Array.png)

Selain bentuk dua dimensi, kita dapat membuat array hingga N-dimensi, sesuai kebutuhan.