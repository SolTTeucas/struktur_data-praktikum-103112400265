# <h1 align="center">Laporan Praktikum Modul 2 <br> Pengenalan C++</h1>
<p align="center">Reza Sahrul Nuramdani - 103112400265</p>

## Dasar Teori
	Dalam modul ini kita akan memahami penggunaan pointer, dan alamat memori. Serta mengimplementasikan fungsi dan procedure dalam program.

##### I. Array
Kumpulan data dengan setiap elemen yang bertipe data sama.
###### I.II. Array Satu Dimensi 
Array yang terdiri dari satu larik.

	tipe_data nama_var[ukuran]
	
	(di sini ukuran menandakan jumlah maksimal ukuran array-nya.)

```cpp
int nilai[10]; //deklarasi array dengan tipe integer yang memiliki ukuran 10 elemen.

nilai[4] = 90; //assign value 90 pada elemen ke 4 array.

cin >> nilai[4]; //userInput untuk diassign ke array elemen ke 4.
```

###### I.II. Array Dua Dimensi
Mirip seperti table. Secara prinsip mirip seperti array satu dimensi, hanya saja indeks yang digunakan ada dua.

```cpp
int data_nilai[4][3]; //deklarasi pembuatan array dua dimensi, dengan banyak row 4, dan column 3.
nilai [2][0]=10; //assign value 10 pada elemen array yang berada di row ke-dua, column 0.
```


|     |   0  | 1 | 2 | 3 
| --- | --- |---|---|---|
| 0     |     | |   
| 1     |     | |   
| 2     | 10    | |   
| 3     |     | |   
Di atas adalah visualisasi posisi data pada array dua dimensi.
###### I.III. Array Dimensi Banyak
 Indeks banyak, lebih dari dua. Dan lebih susah untuk digambarkan. Cara Deklarasi
 ```
 tipe_data nama_var[ukuran1][ukuran2]...[ukuran-N];
 ```
 ```
 int data_nama[4][6][6];
 ```
###### II. Pointer
###### II.I Data dan Memori
Setiap cell memory memiliki “indeks” atau “alamat” unik yang berguna untuk identitas yang biasa kita sebut sebagai “address”.
Pada saat komputer pertama kali berjalan keadaan memori adalah kosong. Saat variabel dideklarasikan, OS akan mencarikan cell kosong untuk dialokasikan sebagai memori variabel tersebut.

```cpp
char a;
int j;
charr arr[6]; //array dengan tipe data characters
arr[3] = 'b'; //assing value character 'b' pada elemen array ke 3.
a = 'u'; //assign value character 'u' pada variable a.
```

|   C++  |   Output  | Keterangan  
| --- | --- |---|
| cout << a << endl; | 'u' |Nilai variabel a  |   
| cout  << &a | x6 | Alamat variabe a |   
| cout << j << endl; | 0 | Nilai variable j (default untuk empty int)|   
| cout << &j << end; | x21 | Alamat variable arr[4] |


##### II.II Pointer dan Alamat
Merupakan dasar tipe variabel yang berisi integer dalam format heksadesimal. Pointer digunakan untuk menyimpan alamat memori variabel lain sehingga pointer dapat mengakses nilai.
```
type *nama_variable;
```
contoh : 
```cpp
int *p_int;
/*p_int merupakan variable pointer yang menunjuk ke data bertipe int*/
```
Agar pointer menujuk suatu variable, mula-mula pointer harus diisi dengan alamat memori yang ditunjuk.
```cpp
p_int = &j;
//dapat dikatakan bahwa p_int menunjuk ke variabel j.
//Untuk mendapatkan nilai dari variabel yang ditunjuk pointer, gunakan tanda * di depan nama variable pointer.
```
|   C++  |   Output  | Keterangan  
| --- | --- |---|
| int j, k; |  |  |   
| j = 10;  | | Alamat variabe a |   
| int *p_int; | | Nilai variable j (default untuk empty int)|   
| p_int = &j; | | |
| cout << j << endl; | 10 | Nilai variable j |
| cout << &j << endl; | x6 | Alamat variable j |
| cout << p_int << endl; | x6 | Nilai variable p_int |
| cout << &p_int << endl; | x1 |  Alamat variable p_int |
| cout << *p_int << endl; | 10 | Nilai variable yang ditunjuk p_int|
| k = *p_int << endl; | | |
| cout << k << endl; | 10 |  Nilai variable k|

###### II.II Pointer dan Array

Mendefinisikan array sebesar 10, kemudian blok dari objek array tersebut diberi nama a[0],a[1],a[2],…………a[9].

Notasi a[i] akan merujuk elemen ke-i dari array
```cpp
int *pa
```
Maka pernyataan :
```cpp
pa = &a[0];
```
Membuat pa menunjuk ke alamat dari elemen ke-0 dari variabel a. Sehingga, pa akan mengandung alamat dari a[0].
Sekarang, pernyataan : 
```cpp
x = *pa;// akan menyalinkan isi dari a[0] ke variable x
```
- Pendefinisian 𝑝𝑎 + 1 akan menunjuk elemen berikutnya.
- 𝑝𝑎 + 𝑖 akan menunjuk elemen ke-𝑖 setelah 𝑝a 
- 𝑝𝑎 − 𝑖 akan menunjuk elemen ke-𝑖 sebelum 𝑝𝑎 sehingga jika 𝑝𝑎 menunjuk ke 𝑎[0]
- ∗ (𝑝𝑎 + 1) akan mengandung isi elemen ke 𝑎[1] 

𝑝𝑎 + 𝑖 merupakan alamat dari 𝑎[𝑖] , dan ∗ (𝑝𝑎 + 𝑖) akan mengandung isi dari elemen 𝑎[𝑖]

###### III. String
Data type untuk mengolah data teks atau kalimat. Pada dasarnya string merupakan kumpulan dari karakter
atau array dari karakter.
```cpp
//deklarasi variable string
char nama[50];//50 menyatakan jumlah maksimal karakter dalam string.

//untuk memasukan data string 
cin >> nama;

//inisialisasi string
char nama[] = "strukdat";
```
> catatan: cin hanya membaca hingga spasi pertama.Jika anda ingin membaca seluruh baris,gunakan getline().
> seperti "getline(cin, nama);"


Untuk mengakses data string seperti halnya mengakses data pada array
```cpp
cout << nama[3]; //mengambil karakter ke-3 dari string
```

###### IV. Pointer dan String
Array diakhiri dengan karakter ‘\0’ sehingga program dapat menemukan akhir dari program. 

Ketika karakter string tampil dalam sebuah program maka untuk mengaksesnya digunakan pointer karakter.
```cpp
char *pmessage;

pmessage = "now is the time"
//Akan membuat pmessage sebagai pointer pada karakter array.

//PERHATIKAN PERBEDAAN
char message[] = "now is the time"; //array
char *pmessage = "now is the time";//pointer
```

###### IV. Fungsi
Fungsi merupakan blok dari kode yang dirancang untuk melaksanakan tugas khusus.

Fungsi memerlukan masukan yang dinamakan sebagai parameter.
```cpp
tipe_keluaran nama_fungsi(daftar_parameter){
	blok pernyataan fungsi;
}
```

###### V. Procedure
Prosedur adalah istilah yang sering digunakan untuk merujuk pada fungsi yang tidak mengembalikan nilai.
Prosedur ini dikenal sebagai fungsi void, melakukan tugas tertentu tetapi tidak memberikan nilai balik (return value) kepada pemanggilnya.

Berbeda dengan fungsi yang mengembalikan nilai, seperti int atau double, memberikan hasil yang dapat digunakan lebih lanjut dalam program.

```cpp
//bentuk umum suatu procedure sebagai berikut
void nama_procedure (daftar_parameter){
	blok pernyataan procedure;
}
```

###### VI. Parameter Format dan Aktual
Parameter formal adalah variabel yang ada pada daftar paramerter ketika mendefinisikan fungsi.
```
float perkalian (float x, float y){
	return(x*y);
}
```
Sedangkan untuk parameter aktual adalah 
```cpp
x = perkalian(a, b); //parameters ini adalah parameter aktual
y = perkalian(10, 30);
```
###### VI. Call By Value
Pada pemanggilan dengan nilai, nilai dari parameter aktual akan disalin kedalam parameter formal, jadi parameter aktual tidak akan berubah meskipun parameter formalnya berubah.

###### VII. Call By Pointer
Cara untuk melewatkan alamat suatu variabel ke dalam suatu fungsi. Dengan cara ini dapat mengubah nilai dari variabel aktual yang dilewatkan ke dalam fungsi.
```cpp
//cara penulisannya adalah
tukar(int *px, int *py){
	int temp;
	temp = *px;
	*px = *py; //penukaran
	*py = temp;
}

//lalu untuk pemanggilannya seperti ini : 
tukar(&a, &b);
```
- *px merupakan suatu variabel pointer yang menunjuk ke suatu variabel integer.
- Yang diubah dalam fungsi tukar() adalah variabel yang dilewatkan dalam fungsi itu juga, karena yang dilewatkan dalam fungsi adalah alamat dari variabel tersebut, jadi bukan sekedar disalin.
###### VIII. Call By Reference
- Cara untuk melewatkan alamat suatu variabel kedalam suatu fungsi.
- Dapat mengubah nilai dari variabel aktual yang dilewatkan ke dalam  fungsi.
- Dapat mengubah variabel yang ada diluar fungsi.

```cpp
tukar(int &px, int &py){
	int temp;
	temp = px;
	px = py;
	py = temp;
}

//Cara memanggilnya bisa menggunakan : 
tukar(a, b); //di sini terletak perbedaan dengan cara pemanggilan parameter call-by-pointer.
```
Harus mendeklarasikan di parameter awal, serta untuk pemanggilan tidak perlu menggunakan paramter tambahan seperti pada call by pointer.

## Guided
### Soal 1 - Pointer
```cpp
#include <iostream>
#include <string>
using namespace std;

int main(){
    int x, y; // x dan y bertipe int
    int *px; // variable pointer px yang menunjuk ke tipe data int

    x = 87;
    px = &x; // px menyimpan alamat dari variable x
    y = *px; // nilai dari alamat yang disimpan di px (nilai x) disalin ke y

    cout << "Alamat x: " << &x << endl; //mengambil nilai alamat x
    cout << "Isi px = " << px << endl; //menampilkan isi dari pointer px (alamat x)
    cout << "Nilai yang ditunjuk px = " << *px << endl; //menampilkan nilai yang ditunjuk oleh pointer px (nilai x)
    cout << "Nilai y = " << y << endl; //menampilkan nilai y

    return 0;
}
```
> Output
> ![[guided1-MODUL2-pointer.png]] 
### Soal 2 - Pointer Array
```cpp
#include <iostream>
#define MAX 5  //tidak ada titik koma karena ini adalah macro 
using namespace std;

int main(){
    int i, j; float nilai_total, rata_rata; float nilai[MAX];
    /*INISIALISASI ARRAY 2 DIMENSI*/ 
    static int nilai_tahun[MAX] [MAX] = {
        {0, 2, 2, 0, 0},
        {0, 1, 1, 1, 0},
        {0, 3, 3, 3, 0},
        {4, 4, 0, 0, 4},
        {5, 0, 0, 0, 5}
    };

    /*INPUT NILAI TERINTEGRASI DENGAN FOR LOOP, MENGAKOMODASI SIZE MAX ARRAY*/
    for (i=0; i<MAX; i++){
        cout << "masukkan nilai ke- " << i+1 << "=" << nilai[i] << endl; //nilai[i] adalah elemen array ke-i, dan karena dia kosong awalnya, dia akan menampilkan nilai sampah (garbage value).
        cin >> nilai[i];
    }
    cout << "\n data nilai siswa : \n";

    /*MENAMPILKAN DATA NILAI ARRAY SATU DIMENSI YANG SUDAH DIINPUTKAN OLEH USER*/
    for (i=0; i<MAX; i++){
        cout << "nilai ke - " << i+1 << "=" << nilai[i] << endl; //pada looping in nilai[i] adalah elemen array ke-i yang sudah diisi oleh user pada for-loop sebelumnya, jadi niai yang ditampilkan adalah nilai yang sudah diinput user, bukan random values lagi.
        cout << "\n Nilai tahunan : \n"; 
    }
    /*MENAMPILKAN DATA NILAI ARRAY DUA DIMENSI YANG SUDAH DIINPUTKAN OLEH USER*/
    for (i=0; i<MAX; i++){
        for (j=0; j<MAX; j++){
            cout << nilai_tahun[i][j] << " ";
        }
        cout << endl;
    }
    return 0;
}
```
> Output
> ![[guided2-MODUL2-pointerArray.png]] 

### Soal 3 - Fungsi
```cpp
#include <iostream>
using namespace std;

//badan fungsi
int maks3(int a, int b, int c){
    //deklarasi variable lokal dalam fungsi
    int temp_max = a; //logika awal, anggap a adalah maximum
    if (b > temp_max)//bandingkan b dengan temp_max
        temp_max = b;
    if (c > temp_max)//bandingkan c dengan temp_max
        temp_max = c;
    return (temp_max);//kembalikan nilai temp_max sebagai output fungsi
}
int main(){
    int x, y, z;
    cout << "masukkan nilai bilangan ke-1 =  ";
    cin >> x;
    cout << "masukkan nilai bilangan ke-2 =  ";
    cin >> y;
    cout << "masukkan nilai bilangan ke-3 =  ";
    cin >> z;
    cout << "nilai maksimumnya adalah = " << maks3(x, y, z) << endl;
    return 0;
}
```
> Output
> ![[guided3-MODUL2-fungsi.png]] 

### Soal 4 - Procedure
```cpp
#include <iostream>
using namespace std;

//fungsi
void tulis(int x){
    for (int i=0; i<x; i++){
        cout << "baris ke- " << i+1 << endl;
    }
}

int main(){
    int jum;
    cout << "jumlah baris kata =";
    cin >> jum;
    tulis(jum);
    return 0;
}
```
> Output
> ![[guided4-MODUL2-procedure.png]] 

### Soal 5 - Call By Value
```cpp
#include <iostream>
using namespace std;

void tukar(int x, int y){
    int temp;
    temp = x;
    x = y;
    y = temp;
    cout << "nilai akhir pada fungsi tukar \n";
    cout << "x = " << x << " y = " << y << endl;
}

int main(){
    int a, b;
    a = 4;
    b = 6;

    cout << "kondisi sebelum ditukar \n";
    cout << "a = " << a << " b = " << b << endl;

    tukar(a, b);
    cout << "kondisi setelah ditukar \n";
    cout << "a = " << a << " b = " << b << endl;
    return 0;
}
```
> Output
> ![[guided5-MODUL-2-callByValue.png]]
> 
> Yang melewatkan variabel a dan b tidak mengubah nilai dari variabel tersebut. Hal ini dikarenakan ketika pemanggilan fungsi tersebut nilai dari a dan b disalin ke variabel formal yaitu x dan y.

### Soal 6 - Call By Reference
```cpp
#include <iostream>
using namespace std;

void tukar(int &x, int &y){
    int temp;
    temp = x;
    x = y; 
    y = temp;
    cout << "nilai akhir pada fungsi tukar \n";
    cout << "x = " << x << " y = " << y << endl;
}

int main(){
    int a, b;
    a = 4;
    b = 6;
    
    cout << "kondisi sebelum ditukar \n";
    cout << "a = " << a << " b = " << b << endl;
    tukar(a, b);// ini yang mengindikasi call by reference, parameter tanpa &.
    cout << "kondisi setelah ditukar \n";
    cout << "a = " << a << " b = " << b << endl;
    return 0;
}
```
> Output
> ![[guided6-MODUL2-callByReference.png]]

## Referensi

1. https://en.wikipedia.org/wiki/Data_structure 
2. https://www.w3schools.com/cpp/cpp_conditions.asp 
3. https://www.w3schools.com/cpp/cpp_conditions_else.asp
4. https://www.w3schools.com/cpp/cpp_conditions_elseif.asp
5. https://www.w3schools.com/cpp/cpp_structs.asp
6. https://www.programiz.com/cpp-programming/structure
7. https://www.w3schools.com/cpp/cpp_arrays.asp
8. https://www.w3schools.com/cpp/cpp_for_loop.asp
9. https://www.w3schools.com/cpp/cpp_while_loop.asp
10. https://www.w3schools.com/cpp/cpp_do_while_loop.asp
11. https://www.codewithharry.com/tutorial/cpp-for-loop
12. https://www.geeksforgeeks.org/cpp/cpp-increment-and-decrement-operators/
13. https://www.tutorialspoint.com/cplusplus/cpp_increment_decrement_operators.htm
14. https://www.geeksforgeeks.org/cpp/cpp-sizeof-operator/
15. https://en.cppreference.com/w/cpp/language/sizeof.html
16. https://www.geeksforgeeks.org/cpp/difference-between-cout-and-puts-in-c-with-examples/
