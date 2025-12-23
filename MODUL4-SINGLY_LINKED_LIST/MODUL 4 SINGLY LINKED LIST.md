# <h1 align="center">Laporan Praktikum Modul 3 <br> Abstract Data Types</h1>
<p align="center">Reza Sahrul Nuramdani - 103112400265</p>

### Soal 1 - Program Buku
```cpp
//file buku.cpp

#include <iostream>
using namespace std;

struct Node {
    string ISBN;
    string title;
    string writer;
    Node* next;

};

Node* head = nullptr;

Node* createNode(
    string ISBN, string title, string writer
){
    Node* newNode = new Node();
    newNode-> ISBN = ISBN;
    newNode-> title = title;
    newNode-> writer = writer;
    newNode-> next = nullptr;
    return newNode;
}

void tambahBuku
(
    string title,
    string writer,
    string ISBN
)
{
    Node* newNode = new Node();
    if
    (
        head == nullptr
    )
    {
        head = newNode;
    }
    else
    {
        Node* temp = head;
        while(temp-> next != nullptr)
        {
            temp = temp-> next;
        }
        temp-> next = newNode;
    }
    cout << "Buku dengan judul " << title << "Dengan penulis" << writer << "memiliki ISBN " << ISBN << "berhasil ditambahkan.\n";
}
```

```cpp
//FILE main.cpp

#include <iostream>
#include <string>
using namespace std;

// Forward declarations (because your logic lives elsewhere)
struct Node {
    string ISBN;
    string title;
    string writer;
    Node* next;
};

extern Node* head;

// Function prototypes
void tambahBuku(string ISBN, string title, string writer);

// Utility function to display all books
void tampilkanBuku() {
    if (head == nullptr) {
        cout << "Daftar buku masih kosong.\n";
        return;
    }

    Node* temp = head;
    int index = 1;

    while (temp != nullptr) {
        cout << "\nBuku #" << index++ << endl;
        cout << "Judul   : " << temp->title << endl;
        cout << "Penulis : " << temp->writer << endl;
        cout << "ISBN    : " << temp->ISBN << endl;
        temp = temp->next;
    }
}

int main() {
    int pilihan;

    do {
        cout << "\n=== SISTEM DATA BUKU ===\n";
        cout << "1. Tambah Buku\n";
        cout << "2. Tampilkan Semua Buku\n";
        cout << "3. Keluar\n";
        cout << "Pilih menu: ";
        cin >> pilihan;
        cin.ignore(); // flush newline

        if (pilihan == 1) {
            string title, writer, ISBN;

            cout << "Judul Buku   : ";
            getline(cin, title);

            cout << "Penulis Buku : ";
            getline(cin, writer);

            cout << "ISBN         : ";
            getline(cin, ISBN);

            tambahBuku(ISBN, title, writer);
        }
        else if (pilihan == 2) {
            tampilkanBuku();
        }
        else if (pilihan == 3) {
            cout << "Program selesai. Sampai jumpa \n";
        }
        else {
            cout << "Pilihan tidak valid.\n";
        }

    } while (pilihan != 3);

    return 0;
}

```
> Output
> ![[guided1-MODUL4.png]]
 
## UNGUIDED
### Soal 1 - Program Antrian
```cpp
#include <iostream>
using namespace std;

struct Node
{
    string nama;
    string pesanan;
    Node* next;
};

Node* head = nullptr;

Node* createnode
(
    string nama, string pesanan
) 
{
    Node* newNode = new Node();
    newNode->nama = nama;
    newNode->pesanan = pesanan;
    newNode->next = nullptr;
    return newNode;
}

void tambahantrian
(
    string nama, string pesanan
) 
{
    Node* newNode = createnode(nama, pesanan);
    if (head == nullptr) {
        head = newNode;
    } else {
        Node* temp = head;
        while (temp->next != nullptr) {
            temp = temp->next;
        }
        temp->next = newNode;
    }
    cout << "pembeli " << nama << " pesanan nya \"" << pesanan << "\" berhasil ditambahkan ke antrian.\n";
}

void layaniantrian() 
{
    if (head == nullptr) {
        cout << "Antrian Kosong\n";
        return;
    }

    Node* temp = head;
    cout << "melayani pembeli: " << temp->nama << " (Pesanan: " << temp->pesanan << ")\n";
    head = head->next;
    delete temp;
}

void tampilkanantrian()
{
    if (head == nullptr) {
        cout << "tidak ada antrian!!\n";
        return;
    }

    Node* temp = head;
    cout << "\n=== DAFTAR ANTRIAN PEMBELI ===\n";
    while (temp != nullptr) {
        cout << "nama: " << temp->nama << " | pesanan: " << temp->pesanan << endl;
        temp = temp->next;
    }
    cout << "===============================\n";
}

int main()
{
    int pilihan;
    string nama, pesanan;

    do {
        cout << "\n=== MENU ANTRIAN PEMBELI ===\n";
        cout << "1. tambah antrian\n";
        cout << "2. layani antrian\n";
        cout << "3. tampilkan antrian\n";
        cout << "0. keluar\n";
        cout << "pilih: ";
        cin >> pilihan;

        switch (pilihan) {
            case 1:
                cout << "masukkan nama pembeli : ";
                cin >> nama;
                cout << "masukkan pesanan : ";
                cin >> pesanan;
                tambahantrian(nama, pesanan);
                break;
            case 2:
                layaniantrian();
                break;
            case 3:
                tampilkanantrian();
                break;
            case 0:
                cout << "program selesai.\n";
                break;
            default:
                cout << "pilihan tidak valid!\n";
        }
    } while (pilihan != 0);

    return 0;
}

```
> Output
> ![[unguided1-MODUL4.png]]

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
