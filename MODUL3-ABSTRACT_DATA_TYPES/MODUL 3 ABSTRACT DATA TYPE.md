# <h1 align="center">Laporan Praktikum Modul 3 <br> Abstract Data Types</h1>
<p align="center">Reza Sahrul Nuramdani - 103112400265</p>

## Dasar Teori
	Dalam modul ini kita akan Memahami konsep Abstract Data Type (ADT) dan penggunaannya dalam pemrograman.

### I. Abstract Data Type
ADT adalah TYPE dan sekumpulan PRIMITIF (operasi dasar) terhadap TYPE tersebut. ADT merupakan definisi STATIK, yang berarti definisi dari ADT tidak akan berubah pada saat runtime.

PRIMITIF (operasi dasar) adalah operasi paling dasar yang dapat dieksekusi oleh komputer dan dihitung sebagai "satu-step"

PRIMITIF dikelompokkan menjadi : 
1. **Konstruktor/kreator.**
   Semua objek (variabel) bertype tersebut harus
   melalui konstruktor. Biasanya namanya diawali Make.
2. **Selector**
   mengakses tipe komponen(biasanya namanya diawali Get).
3. **Procedure**
   Pengubah nilai komponen (biasanya namanya diawali Get).
4. **Validator Komponen**
   Apakah dapat membentuk tipe sesuai dengan batasan.
5. **Destruktor**
   Digunakan untuk “menghancurkan” nilai objek/variabel (sekaligus memori penyimpanannya).
6. **Baca/Tulis**
   Untuk interface dengan input/output device.
7. **Operator Operasional**
   Relasional, terhadap tipe tersebut untuk mendefinisikan lebih besar, lebih kecil, sama dengan dan sebagainya.
8. **Aritmatika Terhadap Tipe Tersebut**
   Biasanya aritmatika dalam bahasa C hanya terdefinisi untuk bilangan numerik.
9. **Konversi**
   Tipe data tersebut ke tipe dasar dan sebaliknya.

### II. Teknik ADT
Biasanya diimplementasikan menjadi dua buah modul, Utama dan satu buah modul *interface program utama (driver)*. Antara lain : 
- **Definisi Types dan Primitives (Header Fungsi / .h)**
  Fungsi : nama, domain, range, dan prekondisi jika ada.
  Prosedur : initial state, final state, dan proses yang dilakukan.
- **Realisasi/body dari primitives (.c)**
  Realisasi fungsi dan prosedur harus sedapat mungkin memanfaatkan selector dan konstruktor.

> Untuk menerapkan konsep ADT, kita harus memisah deklarasi tipe, variabel, dan fungsi dari program ke dalam sebuah file.h

```cpp
//CONTOH STRUKTUR PROGRAM TANPA IMPELEMTASI ADT
#include <iostream>
#include <string>
using namespace std;


/*Definisi PRIMITIF, HEADER FUNGSI (.h)*/
struct mahasiswa {
    char nim[10];
    int nilai1, nilai2;
};

void inputMhs(mahasiswa &m);
float rata2(mahasiswa m);
/*Definisi PRIMITIF, HEADER FUNGSI (.h)*/

int main() {
    mahasiswa mhs;
    inputMhs(mhs);
    cout << "rata-rata nilai: " << rata2(mhs);
    return 0;
}


/*Body atau Realisasi dari PRIMITF header (.cpp)*/
void inputMhs(mahasiswa &m) {
    cout << "Input NIM : ";
    cin >> m.nim;
    cout << "Input Nilai 1 : ";
    cin >> m.nilai1;
    cout << "Input Nilai 2 : ";
    cin >> m.nilai2;
}
float rata2(mahasiswa m) {
    return float(m.nilai1 + m.nilai2) / 2; //"m.nilai" berarti mengakses struct mahasiswa -> type nilai1, dan nilai2
}
/*Body atau Realisasi dari PRIMITF header (.cpp)*/
```
Bisa dilihat program diatas bisa dibuat lebih efisien dengan membagi beberapa block of code menjadi file header dan .cpp lainnya.

## Guided
### Soal 1 - Implementasi ADT
```cpp
//FILE mahasiswa.h

#ifndef MAHASISWA_H_INCLUDED
#define MAHASISWA_H_INCLUDED

struct mahasiswa {
    char nim[10];
    int nilai1, nilai2;
};

void inputMhs(mahasiswa &m);
float rata2(mahasiswa m);

#endif // MAHASISWA_H_INCLUDED
```

```cpp
//FILE mahasiswa.cpp

#include "mahasiswa.h"
#include <iostream>
using namespace std;

void inputMhs(mahasiswa &m) {
    cout << "Input NIM : ";
    cin >> m.nim;
    cout << "Input nilai 1 : ";
    cin >> m.nilai1;
    cout << "Input nilai 2 : ";
    cin >> m.nilai2;
}

float rata2(mahasiswa m) {
    return float(m.nilai1 + m.nilai2) /2;
}
```

```cpp
//FILE main.cpp

#include <iostream>
#include "mahasiswa.h"
using namespace std;

int main(){
    mahasiswa mhs; //definisi variable mhs dengan struct type mahasiswa yang didefinisikan di header mahasiswa.h
    inputMhs(mhs);
    cout << "rata-rata = " << rata2(mhs);
    return 0;
}
```
> Output
> ![[guided1-MODUL3-implementasiADT.png]]
 
## UNGUIDED
### Soal 1 - Program Mahasiswa
Buat program yang dapat menyimpan data mahasiswa (max. 10) ke dalam sebuah array dengan field nama, nim, uts, uas, tugas, dan nilai akhir. Nilai akhir diperoleh dari FUNGSI dengan rumus 0.3*uts+0.4*uas+0.3*tugas.
```cpp
/*mahasiswa.h*/


#ifndef MAHASISWA_H_INCLUDED
#define MAHASISWA_H_INCLUDED
#define MAX 10
#include <string>
using namespace std;

struct mahasiswa {
    string nama;
    char nim[10];
    int nilaiUTS, nilaiUAS, nilaiTugas;
};

extern mahasiswa mhsList[MAX];

void inputMhs(mahasiswa &m);
float nilaiAkhir(mahasiswa m);

#endif // MAHASISWA_H_INCLUDED
```

```cpp
/*mahasiswa.cpp*/

#include <iostream>
#include <string>
#include "mahasiswa.h"
using namespace std;

void inputMhs(mahasiswa &m) {
    cout << "Input Nama : ";
    getline(cin, m.nama);
    cout << "Input NIM : ";
    cin >> m.nim;
    cout << "Input Nilai UTS : ";
    cin >> m.nilaiUTS;
    cout << "Input Nilai UAS : ";
    cin >> m.nilaiUAS;
    cout << "Input Nilai Tugas : ";
    cin >> m.nilaiTugas;
    cin.ignore();
}


float nilaiAkhir(mahasiswa m) {
    return (0.3 * m.nilaiUTS) + (0.4 * m.nilaiUAS) + (0.3 * m.nilaiTugas);
} 
```

```cpp
/*main.cpp*/

#include <iostream>
#include "mahasiswa.h"
#include <string>
#define MAX 10
using namespace std;

int main(){
    mahasiswa daftarMhs[MAX];
    //local variable dengan bentuk array dengan struct mahasiswa, untuk menampung data mahasiswa sebanyak MAX (10)

    for (int i=0; i < MAX; i++) { //looping input data mahasiswa sebanyak MAX (10)
        cout << "Masukkan data Mahasiswa ke- " << i+1 << ":\n";
        inputMhs(daftarMhs[i]);//manggil function inputMhs yang isinya function untuk input data mahasiswa, nama, nim, dll.
    }

    //algoritma untuk menampilkan data array of struct mahasiswa yang di looping sebelumnya sudah di input.
    cout << "\n DATA MAHASISWA \n" << endl;
    for (int i=0; i<MAX; i++) {
        cout << "Mahasiswa ke- " << i+1 << " = \n"
        << "Nama : " << daftarMhs[i].nama << endl
        << "NIM : " << daftarMhs[i].nim << endl
        << "Nilai UTS : " << daftarMhs[i].nilaiUTS << endl
        << "Nilai UAS : " << daftarMhs[i].nilaiUAS << endl
        << "Nilai Tugas : " << daftarMhs[i].nilaiTugas << endl
        << "Nilai Akhir : " << nilaiAkhir(daftarMhs[i]) << endl
        << "------------------------" << endl;

    }
    return 0;
}
```

> Output
> ![[unguided1-MODUL3-adtProgramMahasiswa.png]]

### Soal 2 - Code Completion
Buatlah ADT pelajaran sebagai berikut di dalam file “pelajaran.h”
```cpp
/*pelajaran.h*/


#ifndef PELAJARAN_H_INCLUDED
#define PELAJARAN_H_INCLUDED
#include <string>

using namespace std;

struct pelajaran{
    string namaMatkul;
    string kodeMatkul;
};

pelajaran createPelajaran(string nama, string kode);

void displayPelajaran(pelajaran p);

#endif // PELAJARAN_H_INCLUDED
```

```cpp
/*pelajaran.cpp*/

#include <iostream>
#include "pelajaran.h"
using namespace std;

pelajaran createPelajaran(string nama, string kode) {
    pelajaran p; // membuat instance dengan struct pelajaran
    p.namaMatkul = nama;
    p.kodeMatkul = kode;
    return p;
}

void displayPelajaran(pelajaran p) { //function untuk menampilkan data pelajaran
    cout << "Nama Mata Kuliah: " << p.namaMatkul << endl;
    cout << "Kode Mata Kuliah: " << p.kodeMatkul << endl;
}
```

```cpp
/*main.cpp*/

#include <iostream>
#include "pelajaran.h"
using namespace std;

int main() {
    string namaMatkul = "Struktur Data";
    string kodeMatkul = "SD123";

    pelajaran matkul = createPelajaran(namaMatkul, kodeMatkul);
    displayPelajaran(matkul);
    return 0;
}
```

> Output
> ![[unguided2-MODUL3.png]]

### Soal 3 - 2D Array
Buatlah ADT pelajaran sebagai berikut di dalam file “pelajaran.h”
```cpp
/*array.h*/


#ifndef ARRAY_H
#define ARRAY_H
#define ROWS 3
#define COLS 3

typedef int array2D[ROWS][COLS];

void displayArray(array2D arr);

void tukarElemen(
    array2D A, array2D B,
    int rows, int cols
);

void tukarPointer(
    int *a,
    int *b
);
#endif // ARRAY_H
```

```cpp
/*array.cpp*/

#include <iostream>
#include "array.h"
using namespace std;

void displayArray(array2D arr) {
    for (int i = 0; i < ROWS; i++) {
        for (int j = 0; j < COLS; j++) {
            cout << arr[i][j] << " ";
        }
        cout << endl;
    }
}

void tukarElemen(
    array2D A, array2D B,
    int rows, int cols
) {
    int temp = A[rows][cols];
    A[rows][cols] = B[rows][cols];
    B[rows][cols] = temp; 
}

void tukarPointer(
    int *a, int *b
) {
    int temp = *a;
    *a = *b;
    *b = temp;
}
```

```cpp
/*main.cpp*/

#include <iostream>
#include "array.h"
using namespace std;


int main(){
    array2D A = {
        {1,2,3},
        {4,5,6},
        {7,8,9}
    };

    array2D B = {
        {9,8,7},
        {6,5,4},
        {3,2,1}
    };

    int x = 10, y = 20;
    int *px = &x;
    int *py = &y;

    cout << "Array A: \n";
    displayArray(A);

    cout << "\nArray B: \n";
    displayArray(B);

    cout << "\nTukar elemen A[1][1] ...\n";
    tukarElemen(A, B, 1, 1);

    cout << "\nArray A setelah tukar elemen: \n";
    displayArray(A);

    cout << "\nArray B setelah tukar elemen: \n";
    displayArray(B);

    cout << "\nSebelum tukar pointer: x = " << x << ", y = " << y << endl;
    tukarPointer(px, py);

    cout << "Nilai sesudah pointer swap:\n";
    cout << "x = " << x << ", y = " << y << endl;

    return 0;
}
```

> Output
> ![[unguided3-MODUL3.png]]

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
