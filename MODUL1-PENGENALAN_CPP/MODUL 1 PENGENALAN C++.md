# <h1 align="center">Laporan Praktikum Modul 1 <br> Pengenalan C++</h1>
<p align="center">Reza Sahrul Nuramdani - 103112400265</p>

## Dasar Teori

#### Overview
	Bahasa C++ diciptakan oleh Bjarne Stroustrup di AT&T Bell Laboratories pada awal tahun 1980-an. Prototype C++ muncul sebagai C yang dipercanggih dengan fasilitas kelas, operator, dan fungsi yang kemudian melahirkan apa yang disebut C++.

	Simbol ++ merupakan operator C untuk operasi penaikan, penggunaanya dalam nama C++ menginsinuasikan bahwa bahasa baru ini adalah versi yang lebih canggih dari C.

	Ada banyak perusahaan yang membuat compiler C++ untuk mengkompilasi sourcecode-nya  menjadi executables, antara lain : 
	1. Borland C++
	2. Turbo C++
	3. Topspeed C++
	4. Zortech C++
	5. Code Blocks
	Dan lain-lainnya.

##### I. Struktur Program C++
```cpp
int var1;
float var2[2];

/* PENDEKLARASIAN VARIABLE */
```

```cpp
int function_A(){
	//
}
void procedure_B(){
	//
}

/* PENDEKLARASIAN FUNGSI DAN PROSEDUR */
```

```cpp
struct new_record_type {
	int element1;
	float element2;
}

/* PENDEKLARASIAN STRUCT */
```
##### II. Tipe Data Dasar
Tipe Data Dasar berdasarkan jenisnya dibagi dalam 5 kelompok : 

	1. Bilangan bulat (integer) i.e. int
	2. Bilangan real presisi - tunggal i.e. float
	3. Bilangan real presisi - ganda i.e. double
	4. Karakter i.e. char
	5. Tak-bertipe
##### III. Output
```cpp
int main(){
	cout << "Saya lagi makan permen dan melakukan sulap berbahaya!"
	return 0;
}

/* PEMAKAIAN COUT */
```

	Penentu Format

|    Tipe Data  |Penentu Format     |
| --- | --- |
|Integer     |%d     |
| Floating Point Desimal| %f|
| Floating Point Berpangkat | %e
| Floating Point lebih pendek antara Desimal dan berpangkat | %g
| Double Precision  | %lf
| Character | %c
| String | %s
| Unsigned Integer | %u
| Long Integer | %ld
| Long Unsigned Integer | %lu
| Unsigned hexadecimal integer |%x
| Unsigned octal integer | %0

	Escape Sequence

|Escape Sequence     | Pengertian     |
| ---  | --- |
|     \b| Backspace     |
| \f | Formfeed
| \n | New Line
| \r | Carriage return
| \t | Tabulasi
| \\' | Tanda kutip tunggal
| \\" | Tanda kutip ganda
| \\\ | Backslash
| \xaa | Kode ASCII dalam hexadecimal (aa : menunjukan angka ASCII)

##### IV. Input
```cpp
int main(){
	int jumlahGajah;
	cin >> jumlahGajah;
	cout << "Kamu punya Gajah sebanyak : " << jumlahGajah;
	return 0;
}

/* INPUT PADA C++ MENGGUNAKAN "cin" */
```
	Fungsi getchar() -- Digunakan untuk membaca satu karakter input, berbeda dengan cin yang membaca satu line.
```cpp
int main(){
	char ch;
	cout << "Masukkan sebuah karakter:";
	ch = getchar();
	//digunakan untuk membaca satu karakter input
	
	cout  << "Karakter yang Anda masukkan adalah : " << ch << endl;
	return 0;
}
```
##### V. Operator Increment & Decrement
	Increment ++
	menambah nilai 1 dari variable
	
	Decrement --
	akan mengurangi variable dengan nilai 1

|Operator     |Function     |
| --- | --- |
|     ++i|Ekuivalen dengan i=i+1     |
|--j  | Ekuivalen dengan j=j-1
| ++i | Variable akan diincrement dulu
| i++ | Maka nilai i akan digunakan terlebih dahulu, baru diincrement  

##### VI. Kondisional
	"if" statement
	
	if(kondisi)
	pernyataan;
```cpp
int main(){
	double tot_pembelian, diskon;
	
	if (tot_pembelian >= 10000)
		diskon = 0.05 * tot_pembelian;
	
	cout <<"besar diskon = Rp" << diskon;
}
```

	"If -- else" statement
	
	if(kondisi)
		pernyataan1;
	else
		pernyataan2;
```cpp
int main(){
	//variable declaration and stuff...
	
	if (tot_pembelian >= 10000)
		diskon = 0.05*tot_pembelian;
	else
		diskon = 0;
	
	cout << "besar diskon = Rp" << diskon;
}
```

	"switch case"
	
	switch(Variable) {
		case kondisi1: pernyataan1; break;
			case kondisi2 : pernyataan2;
		break;
			default: pernyataan_n;
			break;
	}

## Guided

### Soal 1 - Input

```cpp
#include <iostream>
using namespace std;
int main(){
    int inp;
    cin >> inp;
    cout << "nilai = " << inp;
    return 0;
}
```
> Output
> ![[guided-soal1-input.png]]

### Soal 2 - Getchar
```cpp
#include <iostream>
using namespace std;

//getchar ada di dalam header <cstdio>
main(){
    char ch;
    cout << "Masukkan sebuah karakter: ";
    ch = getchar(); //membaca satu karakter

    cout << "Karakter yang Anda masukan adalah: " << ch << endl;
    return 0;
}
```
> Output
> ![[guided-getchar.png]]

### Soal 3 - OperatorAritmatika
```cpp
#include <stdio.h>
#include <iostream>
using namespace std;
//Contoh penggunaan operator matematika dasar.
int main(){
    int W, X, Y;
    float Z;

    X = 7; Y = 3; W = 1;
    Z = (X + Y) / (Y + W);

    cout << "Nilai z = " << Z << endl;
    return 0;
}
```
> Output
> ![[guided-aritmatika.png]]

### Soal 4 - Size Of 
```cpp
#include <iostream>
using namespace std;

//size-of mengambil ukuran bytes suatu type
int main(){
    char x;
    float z;

    cout << "ukuran variable char adalah : " << sizeof(x) << endl;
    cout << "ukuran variable float adalah : " << sizeof(z) << endl;
    return 0;
}

```
> Output
> ![[guided-sizeof.png]]

### Soal 5 - Increment
```cpp
#include <iostream>
using namespace std;
/* ALGORITMA INCREMENT BELAKANG */
//disebut juga "pre-increment"
int main(){
    int r = 10;
    int s;

    s = 10 + ++r; //nilai r ditambah 1 dulu baru dipakai dalam ekspresi
    
    //karena ditambah dulu, nilai r yang diolah berganti in accordance with the increment.
    cout << "Nilai r = " << r << endl;
    //makannya  di sini r = 11 not 10
    cout << "Nilai s = " << s << endl;
    return 0;
}

```
> Output
> ![[guided-incrementBelakang.png]]

```cpp
#include <iostream>
using namespace std;
/* INCREMENT DEPAN */
/* disebut juga post-increment */ 
int main(){
    int r = 10;
    int s;

    s = 10 + r++;
    //nilai r dipakai dulu dalam ekspresi baru ditambah 1
    cout << "Nilai r = " << r << endl;
    //karena r dipake dulu, makanya hasil s adalah 20, and not 21
    cout << "Nilai s = " << s << endl;
    return 0;
}
```

 Output
> ![[guided-incrementDepan.png]]

### Soal 6 - Conditionals
```cpp
#include <iostream>
using namespace std;
/* BENTUK PERTAMA */
int main(){
    double totPembelian, diskon;

    cout << "total pembelian: Rp. ";
    cin >> totPembelian;
    diskon = 0;
    //base-case
    
    if (totPembelian >= 100000)//kondisi
        diskon = 0.05 * totPembelian;//pernyataan
    cout << "besar diskon = Rp. " << diskon << endl;
}
```
Block of code diatas mengaplikasikan bentuk percabangan/kondisional pertama. 

```
if (kondisi)
	pernyataan
```
> Output
> ![[guided-conditionals-bentuk1.png]]
>  - Jika **TIDAK** memenuhi kondisi, besar diskon = 0
> - Jika **MEMENUHI** kondisi, besar diskon akan dikalkulasi berdasarkan pernyataan yang ditulis pada bagian pernyataan.

```cpp
#include <iostream>
using namespace std;
/* BENTUK KEDUA */ 
int main(){
    double totPembelian, diskon;
    cout << "total pembelian: Rp. ";
    cin >> totPembelian;
    diskon = 0; //initialize

    if(totPembelian >= 100000){
        diskon = 0.05 * totPembelian;
    } else { //disini pake else
        diskon = 0;
    }
    cout << "besar diskon = Rp. " << diskon << endl;
}
```
Block of code diatas mengaplikasikan bentuk percabangan/kondisional kedua.
```
if (kondisi)
	pernyataan1;
else
	pernyataan2;
```
Output
> ![[guided-conditionals-bentuk2.png]]
>  - Jika **TIDAK** memenuhi kondisi, akan mengeksekusi else
> - Jika **MEMENUHI** kondisi, besar diskon akan dikalkulasi berdasarkan pernyataan yang ditulis pada bagian pernyataan.
> - Beda karena lebih fleksible kalo ada else.

```cpp
#include <iostream>
using namespace std;
/* BENTUK KETIGA */
int main(){
     int kodehari;
     puts("Menentukan hari kerja/libur\n");
     puts("1 = Senin  3 = Rabu  5 = Jumat 7 = Minggu ");
     puts("2 = Selasa 4 = Kamis 6 = Sabtu");
     cin >> kodehari;

     switch(kodehari){
        case 1 : //fallthrogh, jika 1,2,3,4,5 akan menjalankan perintah yang muncul pertama
        case 2 : //past case 5, akan menjalankan perintah dari pernyataan case selanjutnya terdekat.
        case 3 : //fallthrough bisa terjadi karena ada break di setiap akhir case.
        case 4 : 
        case 5 : 
            cout << "Hari Kerja" << endl;
            break;
        case 6 :
        case 7 :
            cout << "Hari Libur" << endl;
            break;
        default : 
        cout << "Kode Masukan Salah" << endl;
     }
     return 0;
}
```
Block of code diatas mengaplikasikan bentuk percabangan/kondisional ketiga.
```
switch (variable) {
case kondisi1; pernyataan1; break;
	case kondisi2; pernyataan2;
break:
	
}
```
Output
> ![[guided-conditionals-bentuk3.png]]
> - Dipake kalo ada banyak case.
> - You can take advantage of a something called "fallthrough" by using breaks.

### Soal 7 - Perulangan
```cpp
#include <iostream>
using namespace std;
/*FOR-LOOP*/
int main(){
    int jum;
    cout << "Jumlah perulangan: ";
    cin >> jum;

    for(int i=0; i<jum; i++){ //executed 5 times because the initialization of i was from 0 not i
        cout << "Saya pintar\n";
    }
    return 0;
}
```
> Output
> ![[guided-perulangan-forLoop.png]]

```cpp
#include <iostream>
using namespace std;
/*WHILE-LOOP*/
int main(){
    int i = 1;
    int jum;

    cout << "Masukkan banyak baris: ";
    cin >> jum;

    while (i <= jum){
        cout << "Baris ke- " << i << endl;
        i++; //sama dengan i=i+1
    }
    return 0;
}

```
Di atas adalah block of code algoritma while-loop
- increment berada setelah pernyataan loopnya
- selama nilai increment i sesuai kondisi, pernyataan akan terus dieksekusi.
Output
> ![[guided-perulangan-whileLoop.png]]

```cpp
#include <iostream>
using namespace std;
/*DO-WHILE*/
int main(){
    int i = 1;
    int jum;
    cin >> jum;

    do {
        cout << "baris ke- " << (i+1) << endl;
        i++;
    } while (i < jum); //kondisi-nya di akhir
    return 0;
}
```
Di atas adalah block of code algoritma do-while, yang memiliki karakteristik penempatan kondisi perulangan setelah pernyataan loop-nya.

Output
> ![[guided-perulangan-doWhile.png]]

### Soal 8 - Struct
Cara deklarasi struct, pengaksesan struct, dan pembuatan array yang mengakses suatu struct untuk menyimpan data mahasiswa dengan attribute nama dan nilai yang akan direturn pada akhir program.
```cpp
#include <iostream>
#define MAX 5 //maksimum elemen array
//MAX adalah konstanta, bukan variable
using namespace std;

int main(){
    int i;

    struct data{
        char nama[40];
        int nilai;
    };

    data mahasiswa[MAX]; //deklarasi array of struct

    for(i=0; i<MAX; i++){ //that means selama value i kurang dari MAX, lakukan perulangan
        cout << "masukkan data ke- " << i+1 << endl;
        cout << "nama = ";
        
        cin >> mahasiswa[i].nama;
            cout << "nilai = ";
            cin >> mahasiswa[i].nilai;
    }
    cout << "\ndata mahasiswa\n";
    cout << "=========";

    for (i = 0; i < MAX; i++)
    {
        cout << "\ndata ke- " << i+1;
        cout << "\n\nnama= " << mahasiswa[i].nama;
        cout << "\n\nnilai= " << mahasiswa[i].nilai;
    }
    return 0;
    
}
```
> Output
> ![[guided-struct.png]]

### Soal 9 - Blok Program
Menjelaskan struktur sourcecode yang lazim digunakan pada cpp.
```cpp
#include <iostream>
using namespace std;

/*Deklarasi Fungsi ctof*/
/*In an abstraction technique, this part would be inside the .h file */
float ctof(float celcius);

int main(){
    float celcius, fahrenheit;

    cout << "nilai celcius ? ";
    cin >> celcius;

    /*Menghitung konversi*/
    fahrenheit = ctof(celcius);
    cout << celcius << " celcius adalah " << fahrenheit << " Fahrenheit " << endl;
    return 0;
}

/*Pendefinisian Fungsi ctof*/
/*In an abstraction this block would be inside the function .cpp file */
float ctof(float celcius){
    return celcius * 1.8 + 32;
}
```
> Output
> ![[guided-blok-program.png]]
## Unguided

### Soal 1 Program input float - hasil aritmatika

Buatlah program yang menerima input-an dua buah bilangan betipe float, kemudian
memberikan output-an hasil penjumlahan, pengurangan, perkalian, dan pembagian dari dua
bilangan tersebut.

```go
#include <iostream>
using namespace std;

// Prosedur: hanya menampilkan hasil, tidak mengembalikan nilai
/* Cuma buat display ajah, sekalian sama penghitungannya bisa, nanti yang ditampilin value
hasilnya. */
//format display-nya.
//buat luas dan keliling itu diitung ulang 

// Fungsi: mengembalikan nilai luas
//double itu kek float cuma decimal numbers yang bisa ditampilin lebih banyak.
float hitungPenjumlahan(float x, float y) /*ini adalah function, paramsnya double p, sama double l*/
{
    return x + y; //algoritma untuk menghitung luas persegi panjang
}

// Fungsi: mengembalikan nilai keliling
float hitungPengurangan(float x, float y)
{
    return x - y; /* jadi yang diolah itu dataType int tapi dihitung dalam function yang keluarannya double*/
}

float hitungPerkalian(float x, float y)
{
    return x*y;
}

float hitungPembagian(float x, float y)
{
    return x/y;
}


void tampilkanHasil(double x, double y)
{
    cout << "\n=== Hasil Perhitungan ===" << endl;
    cout << "Float Pertama : " << x << endl;
    cout << "Float Kedua   : " << y << endl;
    cout << "Penjumlahan   : " << hitungPenjumlahan(x, y) << endl;
    cout << "Pengurangan   : " << hitungPengurangan(x, y) << endl;
    cout << "Perkalian     : " << hitungPerkalian(x, y) << endl;
    cout << "Pembagian     : " << hitungPembagian(x, y) << endl;
}


int main() //function juga bukan procedure
{
    float n1, n2;

    /*input yang akan diolah oleh function hitungLuas dan hitungKeliling*/
    cout << "Masukkan float pertama : ";
    cin >> n1; //jadi datatypes yang diinput itu berdasarkan datatype variablenya yang di extract.
    cout << "Masukkan float kedua : "; // "<< adalah operator extractor"
    cin >> n2;


    // // Panggil fungsi yang sudah dideklarasi di luar function main
    // float penjumlahan = hitungPenjumlahan(n1, n2); //pemanggilan function dimasukin ke variable luas
    // float pengurangan = hitungPengurangan(n1, n2);
    // float perkalian   = hitungPerkalian(n1, n2); 
    // float pembagian   = hitungPembagian(n1, n2);

    // /* format output sebelum ditampilkannya format akhir yang ada di procedure lain */
    // cout << "\nDihitung dengan fungsi:" << endl;
    // cout << "Penjumlahan      = " << penjumlahan << endl; //pemanggilan variable yang isinya function dan params, jadi yang di cout itu adalah hasil akhir
    // cout << "Pengurangan  = " << pengurangan << endl;

    // Panggil prosedur
    tampilkanHasil(n1, n2);

    return 0;
}


```

> Output
> ![[unguided1-programAritmatika.png]]
Penjelasan mengenai code ada didalam sourcecode yang tercantum di atas dalam bentuk comment.

### Soal 2 Data-Casting program

Buatlah sebuah program yang menerima masukan angka dan mengeluarkan output nilai
angka tersebut dalam bentuk tulisan. Angka yang akan di- input-kan user adalah bilangan bulat
positif mulai dari 0 s.d 100

```go
#include <iostream>
#include <string>
using namespace std;

/* BAGIAN FUNCTIONS LATIHAN 1 */
float hitungPenjumlahan(float x, float y) /*ini adalah function, paramsnya double p, sama double l*/
{
    return x + y; //algoritma untuk menghitung luas persegi panjang
}

// Fungsi: mengembalikan nilai keliling
float hitungPengurangan(float x, float y)
{
    return x - y; /* jadi yang diolah itu dataType int tapi dihitung dalam function yang keluarannya double*/
}

float hitungPerkalian(float x, float y)
{
    return x*y;
}

float hitungPembagian(float x, float y)
{
    return x/y;
}

/* END LINE FUNCTIONS LATIHAN 1*/


/* SECTION ARRAY LATIHAN 2*/
string satuan[] = {
    "", "satu", "dua", "tiga", "empat", "lima", "enam",
    "tujuh", "delapan", "sembilan"
};
string belasan[] = {
    "sepuluh", "sebelas", "dua belas", "tiga belas", "empat belas",
    "lima belas", "enam belas", "tujuh belas", "delapan belas",
    "sembilan belas"
};
string puluhan[] = {
    "","", "dua puluh", "tiga puluh", "empat puluh", "lima puluh",
    "enam puluh", "tujuh puluh", "delapan puluh", "sembilan puluh"
};
/* SECTION ARRAY LATIHAN 2*/


/* SECTION FUNCTION UNTUK CONDITION HANDLING LATIHAN2*/
string bilanganKeKata(int n){
    if (n==0)
    return "nol";

    if (n<10)
    return satuan[n];

    if (n<20)
    return belasan[n-10];

    if (n<100)
    return puluhan[n/10] + (n%10 ? " " + satuan[n%10] : "");

    if (n<200)
    return "seratus " + bilanganKeKata(n-100);

    if (n<1000)
    return satuan[n/100] + " ratus" + (n%100 ? " " + bilanganKeKata(n%100): "");

    if (n<1000000)
    return bilanganKeKata(n/1000) + " ribu" + (n%1000 ? " " + bilanganKeKata(n%1000): "");

    else
    return "terlalu besar";
};
/* END-LINE DARI SECTION FUNCTION HANDLING LATIHAN2 */



/* SECTION PROCEDURE UNTUK LATIHAN 1 */
void tampilkanHasil(double x, double y)
{
    cout << "\n=== Hasil Perhitungan ===" << endl;
    cout << "Float Pertama : " << x << endl;
    cout << "Float Kedua   : " << y << endl;
    cout << "Penjumlahan   : " << hitungPenjumlahan(x, y) << endl;
    cout << "Pengurangan   : " << hitungPengurangan(x, y) << endl;
    cout << "Perkalian     : " << hitungPerkalian(x, y) << endl;
    cout << "Pembagian     : " << hitungPembagian(x, y) << endl;
}
/* END-LINE SECTION PROCEDURE UNTUK LATIHAN1 */


/* SECTION PROCESURE UNTUK MAIN*/
void listModul(){
    cout <<
    "BERIKUT ADALAH LIST MODULES ANDA : \n"
    "1.) Modul 1\n"
    "2.) Modul 2\n"
    "3.) Modul 3\n"
    "4.) Modul 4\n";
}
/* END-LINE SECTION PROCESURE UNTUK MAIN*/


/* SECTION PROCEDURE PENAMPILAN LIST LATIHAN, MAIN.*/
void listLatihan(int x){
    switch(x)
    {
        case 1:
            cout <<
            "LIST LATIHAN DALAM MODUL "<< x << ":\n"
            "1- Latihan 1\n"
            "2- Latihan 2\n"
            "3- Latihan 3\n";
        break;
        
        case 2:
            cout <<
            "LIST LATIHAN DALAM MODUL " << x <<":\n"
            "1- (still empty)\n"
            "2- (still empty)\n"
            "3- (still empty)\n";
        break;
        
        default:
        break;
    }
}
/* END-LINE SECTION PROCEDURE PENAMPILAN LIST LATIHAN, MAIN.*/


int main()
{
    int bilangan;

    string cabut = "n";

    int modul;
    int latihan;

    while (cabut == "n")
    {
        listModul();//menampilkan listModul
        cout << 
        ">> Modul berapa yang ingin Anda akses : ";
        cin >> modul;
        cout << endl;

        switch (modul)
        {
        case 1:
            cout <<"------ANDA BERADA DALAM MODUL 1\n"<< endl;
            listLatihan(1);

            cout <<
            ">> Latihan berapa yang ingin Anda akses : ";
            cin >> latihan;

            switch(latihan)
            {
                //MAIN LATIHAN1
                //MAIN LATIHAN1
                //MAIN LATIHAN1
                case 1: 
                    float n1, n2;

                    /*input yang akan diolah oleh function hitungLuas dan hitungKeliling*/
                    cout << "Masukkan float pertama : ";
                    cin >> n1; //jadi datatypes yang diinput itu berdasarkan datatype variablenya yang di extract.
                    cout << "Masukkan float kedua : "; // "<< adalah operator extractor"
                    cin >> n2;

                    tampilkanHasil(n1, n2);
                break;

                case 2:
                    cout <<
                    "-------ANDA BERADA DALAM MODUL 1 - LATIHAN 2\n"
                    "-------INI ADALAH PROGRAM NUMBERS-TO-SENTENCE CONVERSION\n";

                    cout <<
                    "Masukkan bilangan-mu";
                    cin >> bilangan;

                    cout <<
                    "Bilangan Anda adalah : "
                    << bilanganKeKata(bilangan)
                    << endl;

                break;

                default:
                break;
            }
            break;
    
        case 2:
            cout <<
            "-------ANDA BERADA DALAM MODUL2\n";
            listLatihan(2);

            cout <<
            ">> Latihan berapa yang ingin Anda akses :";
            cin >> latihan;
        break;

        default:
        break;
        }
        cout <<
        ">> Mau cabut atau udah nyaman?(y/n)";
        cin >> cabut;
    }
    return 0;
}
```

> Output
> ![[unguided2-numberToSequence.png]]

penjelasan kode terdapat di dalam sourcecode dalam bentuk comment.

### Soal 3 

```go
#include <iostream>
#include <string>
using namespace std;

/* BAGIAN FUNCTIONS LATIHAN 1 */
float hitungPenjumlahan(float x, float y) /*ini adalah function, paramsnya double p, sama double l*/
{
    return x + y; //algoritma untuk menghitung luas persegi panjang
}

// Fungsi: mengembalikan nilai keliling
float hitungPengurangan(float x, float y)
{
    return x - y; /* jadi yang diolah itu dataType int tapi dihitung dalam function yang keluarannya double*/
}

float hitungPerkalian(float x, float y)
{
    return x*y;
}

float hitungPembagian(float x, float y)
{
    return x/y;
}

/* END LINE FUNCTIONS LATIHAN 1*/


/* SECTION ARRAY LATIHAN 2*/
string satuan[] = {
    "", "satu", "dua", "tiga", "empat", "lima", "enam",
    "tujuh", "delapan", "sembilan"
};
string belasan[] = {
    "sepuluh", "sebelas", "dua belas", "tiga belas", "empat belas",
    "lima belas", "enam belas", "tujuh belas", "delapan belas",
    "sembilan belas"
};
string puluhan[] = {
    "","", "dua puluh", "tiga puluh", "empat puluh", "lima puluh",
    "enam puluh", "tujuh puluh", "delapan puluh", "sembilan puluh"
};
/* SECTION ARRAY LATIHAN 2*/


/* SECTION FUNCTION UNTUK CONDITION HANDLING LATIHAN2*/
string bilanganKeKata(int n){
    if (n==0)
    return "nol";

    if (n<10)
    return satuan[n];

    if (n<20)
    return belasan[n-10];

    if (n<100)
    return puluhan[n/10] + (n%10 ? " " + satuan[n%10] : "");

    if (n<200)
    return "seratus " + bilanganKeKata(n-100);

    if (n<1000)
    return satuan[n/100] + " ratus" + (n%100 ? " " + bilanganKeKata(n%100): "");

    if (n<1000000)
    return bilanganKeKata(n/1000) + " ribu" + (n%1000 ? " " + bilanganKeKata(n%1000): "");

    else
    return "terlalu besar";
};
/* END-LINE DARI SECTION FUNCTION HANDLING LATIHAN2 */



/* SECTION PROCEDURE UNTUK LATIHAN 1 */
void tampilkanHasil(double x, double y)
{
    cout << "\n=== Hasil Perhitungan ===" << endl;
    cout << "Float Pertama : " << x << endl;
    cout << "Float Kedua   : " << y << endl;
    cout << "Penjumlahan   : " << hitungPenjumlahan(x, y) << endl;
    cout << "Pengurangan   : " << hitungPengurangan(x, y) << endl;
    cout << "Perkalian     : " << hitungPerkalian(x, y) << endl;
    cout << "Pembagian     : " << hitungPembagian(x, y) << endl;
}
/* END-LINE SECTION PROCEDURE UNTUK LATIHAN1 */


/* SECTION DEKLARASI STRUCT MODUL 1 - LATIHAN 3*/
struct mirror
{
    int n;
};
/* END-LINE SECTION DEKLARASI STRUCT MODUL 1 - LATIHAN 3*/


/* SECTION PROCESURE UNTUK MAIN*/
void listModul(){
    cout <<
    "BERIKUT ADALAH LIST MODULES ANDA : \n"
    "1.) Modul 1\n"
    "2.) Modul 2\n"
    "3.) Modul 3\n"
    "4.) Modul 4\n";
}
/* END-LINE SECTION PROCESURE UNTUK MAIN*/


/* SECTION PROCEDURE PENAMPILAN LIST LATIHAN, MAIN.*/
void listLatihan(int x){
    switch(x)
    {
        case 1:
            cout <<
            "LIST LATIHAN DALAM MODUL "<< x << ":\n"
            "1- Latihan 1\n"
            "2- Latihan 2\n"
            "3- Latihan 3\n";
        break;
        
        case 2:
            cout <<
            "LIST LATIHAN DALAM MODUL " << x <<":\n"
            "1- (still empty)\n"
            "2- (still empty)\n"
            "3- (still empty)\n";
        break;
        
        default:
        break;
    }
}
/* END-LINE SECTION PROCEDURE PENAMPILAN LIST LATIHAN, MAIN.*/


int main()
{
    int bilangan;

    string cabut = "n";

    int modul;
    int latihan;

    /*SECTION VARIABLES MODUL 1 LATIHAN 3*/
    mirror pola;
    /*SECTION VARIABLES MODUL 1 LATIHAN 3*/
    
    while (cabut == "n")
    {
        listModul();//menampilkan listModul
        cout << 
        ">> Modul berapa yang ingin Anda akses : ";
        cin >> modul;
        cout << endl;

        switch (modul)
        {
        //MODUL1
        //MODUL1
        //MODUL1
        case 1:
            cout <<"------ANDA BERADA DALAM MODUL 1-------\n"<< endl;
            listLatihan(1);

            cout <<
            ">> Latihan berapa yang ingin Anda akses : ";
            cin >> latihan;
            cout << endl;

            switch(latihan)
            {
                //MAIN LATIHAN1
                //MAIN LATIHAN1
                //MAIN LATIHAN1
                case 1: 
                    float n1, n2;

                    cout <<
                    "-------ANDA BERADA DALAM MODUL " << modul << " - LATIHAN " << latihan << "-------" << endl;
                    "-------INI ADALAH PROGRAM ARITMATIKA-------\n";
                    cout << endl;
                    /*input yang akan diolah oleh function hitungLuas dan hitungKeliling*/
                    cout << "Masukkan float pertama : ";
                    cin >> n1; //jadi datatypes yang diinput itu berdasarkan datatype variablenya yang di extract.
                    cout << "Masukkan float kedua : "; // "<< adalah operator extractor"
                    cin >> n2;

                    tampilkanHasil(n1, n2);
                break;

                //MAIN LATIHAN2
                //MAIN LATIHAN2
                //MAIN LATIHAN2
                case 2:
                    cout <<
                    "-------ANDA BERADA DALAM MODUL " << modul << " - LATIHAN " << latihan << "-------" << endl;
                    cout << "-------INI ADALAH PROGRAM NUMBERS-TO-SENTENCE CONVERSION\n";
                    cout << endl;

                    cout <<
                    "Masukkan bilangan-mu : ";
                    cin >> bilangan;
                    cout << endl;

                    cout <<
                    "Bilangan Anda adalah : "
                    << bilanganKeKata(bilangan)
                    << endl;
                    cout << endl;

                break;

                //MAIN LATIHAN3
                //MAIN LATIHAN3
                //MAIN LATIHAN3
                case 3:
                    cout <<
                    "-------ANDA BERADA DALAM MODUL " << modul <<" - LATIHAN "<< latihan << "-------" << endl;
                    cout << "-------INI ADALAH PROGRAM LOOPING POLA SEGITIGA-------\n";
                    cout << endl;

                    cout <<
                    "Masukkan input : ";
                    cin >> pola.n; //nilai input
                    cout <<
                    "Output :" << endl;
                    cout << endl;

                    for (int i = pola.n; i>0; i--){ //loop utama untuk eksekusi setiap index
                        for(int s=pola.n; s>i; s--){
                            cout << " ";
                        }

                        //innerloop bagian kiri pola (descending)
                        for(int j = i; j>=1; j--){
                            cout << j;
                        }
                        cout << "*"; //bintang tengah (separator biar keliatan simetris)
                        //innerloop bagian kanan pola (ascending)
                        for(int j=1; j<=i; j++){
                            cout << j;
                        }
                        cout << endl;//bikin new-line setiap kelar iterasi loop kanan (ascending)

                        /*condition handling ketika i==1*/
                        if (i==1)
                        {   /*for-loop untuk menghitung jumlah printing space-character*/
                            //untuk keperluan printing "*" di row paling terakhir. (sebagai pucuk)
                            for (int k=pola.n; k>0;k--)//menghitung banyak space dengan banyak pola.n descendingly
                            {
                                cout << " ";
                            }
                            cout << "*";
                        }
                        
                    }
                    cout << endl;
                    cout << endl;
                break;

                default:
                break;
            }
            break;
        
        //MODUL2 
        //MODUL2 
        //MODUL2 
        case 2:
            cout <<
            "-------ANDA BERADA DALAM MODUL2-------\n";
            listLatihan(2);

            cout <<
            ">> Latihan berapa yang ingin Anda akses :";
            cin >> latihan;
            cout << endl;
        break;

        default:
        break;
        }

        //buat cabut.
        cout <<
        ">> Mau cabut atau udah nyaman?(y/n)\n";
        cin >> cabut;
    }
    return 0;
}
```

> Output
> ![[unguided3-pola-segitiga.png]]

Penjelasan terdapat pada dalam sourcecode dalam bentuk comment.

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
