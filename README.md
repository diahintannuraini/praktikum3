# <h1 align="center">Laporan Praktikum Modul Sorting</h1>
<p align="center">Diah Intan Nuraini</p>

## Dasar Teori

Pengurutan  data (sorting)  (ada  juga  yang  menyebutnya sebagai pemilahan data) secara umum bisa didefinisikan sebagai suatu   proses   untuk   menyusun   kembali   himpunan   obyek menggunakan  aturan  tertentu.  Secara  umum  ada  dua  jenis pengurutan data, yaitu pengurutan secara urut naik (ascending),yaitu  dari  data  yang  nilainya  paling  kecil  sampai  data  yang nilainya  paling  besar;  atau  pengurutan  data  secara  urut  turun (descending), yaitu dari data yang mempunyai nilai paling besar sampai  paling  kecil. Tujuan pengurutan data adalah   untuk   lebih   mempermudah   pencarian   data   dikelak kemudian  hari.  Pengurutan  data  menjadi  satu  bagian  yang penting  dalam  ilmu  komputer  karena  waktu  yang  diperlukan untuk  melakukan  proses  pengurutan  perlu  dipertimbangkan.[1]

#### Jenis-jenis Algoritma Sorting
1. Bubble Sort : Bubble    sort adalah    algoritma pengurutan tertua    dan    paling    sederhana    untuk di implementasikan. Algoritma ini juga cukup mudah dipahami. Algoritma ini bekerja dengan cara membandingkan  nilai setiap elemen pada tabel dengan elemen setelahnya, dan menukar nilainya jika sesuai dengan kondisi yang dibutuhkan. Proses ini akan terus berulang sampai semua elemen pada  tabel  sudah  diproses  dan  elemen  pada  tabel  sudah  terurut. Bubble  sortharus  melakukan banyak perbandingan ketika lebih banyak elemen data perlu disortir.[3]

2. Quick Sort : Algoritma ini mudah
diimplementasikan, mampu diterapkan untuk hampir berbagai jenis tipe data, dan relatif bekerja lebih ringan jika dibandingkan dengan
metode yang Iain. Quicksort adalah jenis algoritma divide-andconquer. Untuk mengurutkan sekelompok elemen pada array A[4]

3. Shell Sort : merupakanAlgoritma yang paling  efisien diantara algoritma dengan kompleksitas algoritma yang sama adalah algoritma dengan kompleksitas O(n2).

4. Selection Sort : selection  sort  adalah  metode  penyortiran  data, pemilihan    data    dalam    urutan    tertentu,    dan    kemudian membandingkannya  dengan  data  lain  dari  posisi  [Posisi  +  1] posisi untukmenemukan data terkecil dari rentang posisi ini[6]

5. Insert Sort: e insertion sort adalah teknik sederhana untuk menyortir daftar yang 
hampir berurutan yang relatif efisien. Algoritma ini juga dapat digunakan sebagai 
komponen yang lebih kompleks. [5]

6. Merge Sort :Algoritma Merge Sort adalah salah satu algoritma pengurutan yang efisien dan populer dalam ilmu komputer. Dalam pengembangan perangkat lunak, sering kali kita dihadapkan pada tugas pengurutan data, di mana urutan elemen-elemen data harus diatur secara teratur.[2]


## Guided 

### 1. Mengurutkan secara ascending untuk data numerik bertipe double menggunakan Algoritma Bubble Sort


```C++
#include <iostream>
using namespace std;

void bubble_sort(double arr[], int length) {
    bool not_sorted = true;
    int j=0;
    double tmp;

    while (not_sorted) {
        not_sorted = false;
        j++;
        for (int i = 0; i < length - j; i++){
            if (arr[i] > arr[i + 1]) {
                tmp = arr[i];
                arr[i] = arr[i+1];
                arr[i + 1] = tmp;
                not_sorted = true;
            }// end of if
        }// end of for loop
    }//end of while loop
}// end of bubble_sort

void print_array(double a[], int length) {
    for(int i=0; i<length; i++) {
        cout << a[i] << "\t";
    }
    cout << endl;
}

int main() {
    int length = 5;
    double a[] = {22.1, 15.3, 8.2, 33.21, 99,99};

    cout << "Urutkan bilangan sebelum sorting: " << endl;
    print_array(a, length);

    bubble_sort(a, length);

    cout << "\nUrutkan bilangan setelah sorting: " << endl;
    print_array(a, length);
}
```

### Output:
![Guided 1](https://github.com/suxeno/Struktur-Data-Assignment/assets/162097079/0d678fe6-11e1-41c7-8cf3-376d5cf3ca83)
 ### Interpretasi : 
 Kodingan di atas menggunakan algoritma Bubble Sort untuk mengurutkan array bilangan double secara meningkat. Algoritma ini membandingkan pasangan elemen dalam array dan menukar posisi jika diperlukan. Iterasi terus dilakukan hingga tidak ada lagi pertukaran posisi yang dibutuhkan, menandakan bahwa array sudah terurut. Fungsi 'print_array' digunakan untuk mencetak array sebelum dan sesudah pengurutan. Dalam 'main', array diinisialisasi dan dicetak sebelum dan sesudah pengurutan dilakukan.

### 2.Mengurutkan karakter secara descending (dari terbesar hingga terkecil) menggunakan Algoritma Insertion Sort
```C++
#include <iostream>
using namespace std;

void insertion_sort(char arr[], int length) {
    int i, j;
    char tmp;

    for (i = 1; 1 < length; i++) {
        j = i;

        while (j > 0 && arr[j - i] < arr[j]) {
            tmp = arr[j];
            arr[j] = arr[j - 1];
            arr[j - 1] = tmp;
        }//end of while loop
    }//end of for loop
}

void print_array(char a[], int length) {

    for(int i=0; i<length; i++) {
        cout << a[i] << "\t";
    }
    cout << endl;
}

int main() {
    int length = 6;
    char a[length] = {'c', 'f', 'a', 'z', 'd', 'p'};

    cout << "Urutan karakter sebelum sorting:" << endl;
    print_array(a, length);

    cout << "\nUrutan karakter setelah sorting:" << endl;
    print_array(a, length);
}
```
### Output: 

![Guided 2](https://github.com/suxeno/Struktur-Data-Assignment/assets/162097079/eeb27b23-dd77-4613-addb-288bd5d44860)

### Interpretasi:

Kodingan di atas menggunakan algoritma Insertion Sort untuk mengurutkan array karakter. Algoritma ini membandingkan setiap elemen dengan elemen-elemen sebelumnya dalam array, kemudian memasukkannya ke posisi yang sesuai dengan urutan yang diinginkan. Loop 'for' berjalan melalui array dimulai dari indeks kedua, dengan loop 'while' di dalamnya untuk memeriksa dan menukar posisi elemen-elemen jika diperlukan. Fungsi 'print_array' mencetak array sebelum dan sesudah pengurutan. Dalam 'main', array karakter diinisialisasi dan dicetak sebelum dan sesudah pengurutan


## Unguided 

### 1. Kelas S1 IF 2016 G memiliki 5 mahasiswa. Pada akhir semester mereka menerima lembar Indeks Prestasi Semester (IPS), masing-masing mahasiswa tersebut memiliki IPS sebagai berikut: {3.8, 2.9, 3.3, 4.0, 2.4}. Buatlah program untuk mengurutkan IPS mahasiswa tersebut dari yang terbesar hingga terkecil dengan menggunakan algoritma Selection Sort!

```C++
#include<iostream>
using namespace std;
void selection_sort(float arr[], int n) {
    for (int i = 0; i < n-1; i++) {
        int min = i;
        for (int j = i+1; j < n; j++) {
            if (arr[j] < arr[min]) {
                min = j;
} }
        if (min != i) {
            float temp = arr[i];
            arr[i] = arr[min];
            arr[min] = temp;
} }
}
void print_array205(float arr[], int n) {
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
}
int main() {
    const int length = 5;
    float a[length] = {3.8, 2.9, 3.3, 4.0, 2.4};
    cout << "IPS sebelum sorting: " << endl;
    print_array205(a, length);
    selection_sort(a, length);
    cout << "IPS setelah sorting: " << endl;
    print_array205(a, length);
return 0; 
}
```
### Output:
![Unguided 1](https://github.com/suxeno/Struktur-Data-Assignment/assets/162097079/fb29776e-e211-4225-b1c6-c80c38253d60)

### Interpretasi: 
Program di atas menggunakan algoritma selection sort dalam C++ untuk mengurutkan angka dalam array. Algoritma ini bekerja dengan membandingkan setiap angka satu per satu, lalu menukar posisi jika ditemukan angka yang lebih kecil. Proses ini terus berulang hingga seluruh angka dalam array terurut dari yang terkecil ke yang terbesar.

Program memiliki dua fungsi utama: selection_sort untuk melakukan pengurutan, dan print_array205 untuk mencetak isi array. Fungsi utama (main) membuat array angka awal, mencetaknya, mengurutkannya dengan selection sort, dan mencetak hasilnya.

Output program adalah angka dalam array sebelum dan setelah diurutkan. Sebelum diurutkan, angka dalam array adalah 3.8 2.9 3.3 4.0 2.4, dan setelah diurutkan menjadi 2.4 2.9 3.3 3.8 4.0.

### Analisis Kompleksitas:
Waktu Kompleksitas:

Iterasi luar dalam fungsi selection_sort berjalan sebanyak (n - 1) kali, karena elemen terakhir sudah pasti terurut setelah iterasi sebelumnya.
Di dalam iterasi luar, terdapat iterasi dalam yang berjalan sebanyak (n - i) kali, di mana i adalah indeks dari iterasi luar. Hal ini karena setiap iterasi luar akan memastikan elemen terkecil diposisikan pada indeks yang tepat.
Setiap iterasi dalam memiliki kompleksitas waktu O(n) karena melakukan perbandingan pada setiap elemen.
Sehingga, waktu kompleksitas untuk algoritma Selection Sort adalah O(n^2), di mana n adalah jumlah elemen dalam array.

Ruang Kompleksitas:

Algoritma ini menggunakan penyimpanan sementara dalam bentuk variabel 'min' dan 'temp'.
Karena tidak ada alokasi memori tambahan yang bergantung pada ukuran masukan (array), ruang kompleksitasnya adalah O(1), yaitu konstan.

### 2. Pak RT memiliki 10 warga dengan nama: siti, situ, sana, ana, ani, caca, cici, dida, dodo, dan dadi. Supaya mudah dalam melakukan pencarian, Pak RT akan mengurutkan namanama tersebut sesuai dengan alfabet. Buatlah program untuk membantu Pak RT dengan menggunakan algoritma Bubble Sort!
```C++
#include<iostream>
using namespace std;
void bubbleSort(string arr[], int n) {
    for (int i = 0; i < n-1; i++) {
        for (int j = 0; j < n-i-1; j++) {
            if (arr[j] > arr[j+1]) {
                string temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
} }
} }
void printArray(string arr[], int n) {
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
}
int main() {
const int jumlah205 = 10;
string nama[jumlah205] = {"siti", "situ", "sana", "ana",
"ani", "caca", "cici", "dida", "dodo", "dadi"};
cout << "Nama-nama warga sebelum diurutkan: " << endl; printArray(nama, jumlah205);
bubbleSort(nama, jumlah205);
cout << "Nama-nama warga setelah diurutkan: " << endl; printArray(nama, jumlah205);
return 0; 
}
```
### Output:
![Unguided 2](https://github.com/suxeno/Struktur-Data-Assignment/assets/162097079/4d4d0eb4-db9f-474e-8e3e-e81ee2626083)

### Interpretasi:
Fungsi utama bubbleSort digunakan untuk melakukan pengurutan dengan dua loop bersarang untuk membandingkan dan menukar elemen-elemen array. Setelah pengurutan, array akan terurut.

Selain itu, ada fungsi printArray yang mencetak isi array ke layar. Di dalam fungsi main, array nama diisi dengan nama-nama warga dan dicetak sebelum dan setelah diurutkan menggunakan bubble sort.

Hasil output program menampilkan nama-nama warga sebelum dan sesudah pengurutan. Sebelum diurutkan, nama-nama warga adalah "siti situ sana ana ani caca cici dida dodo dadi", dan setelah diurutkan menjadi "ana ani caca cici dadi dida dodo sana siti situ".

### Analisis Kompleksitas:
Waktu Kompleksitas:

Iterasi luar dalam fungsi bubbleSort berjalan sebanyak (n - 1) kali, karena setiap iterasi luar memastikan bahwa setidaknya satu elemen sudah berada pada posisi yang tepat.
Di dalam iterasi luar, terdapat iterasi dalam yang berjalan sebanyak (n - i - 1) kali, di mana i adalah indeks dari iterasi luar. Hal ini karena setiap iterasi luar akan menempatkan elemen terbesar di posisi yang tepat di bagian belakang array.
Setiap iterasi dalam memiliki kompleksitas waktu O(n) karena melakukan perbandingan pada setiap elemen.
Sehingga, waktu kompleksitas untuk algoritma Bubble Sort adalah O(n^2), di mana n adalah jumlah elemen dalam array.

Ruang Kompleksitas:

Algoritma ini menggunakan penyimpanan sementara dalam bentuk variabel 'temp'.
Karena tidak ada alokasi memori tambahan yang bergantung pada ukuran masukan (array), ruang kompleksitasnya adalah O(1), yaitu konstan.

### 3. Buatlah program yang meminta user menginputkan suatu bilangan n dan meminta user untuk menginputkan sejumlah n karakter. Kemudian program akan melakukan sorting secara menaik (ascending) dan menurun (descending)! 
```C++
#include<iostream>
using namespace std;
void bubbleSortAscending(char arr[], int n) {
    for (int i = 0; i < n-1; i++) {
        for (int j = 0; j < n-i-1; j++) {
            if (arr[j] > arr[j+1]) {
                char temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
} }
} }
void bubbleSortDescending(char arr[], int n) {
    for (int i = 0; i < n-1; i++) {
        for (int j = 0; j < n-i-1; j++) {
            if (arr[j] < arr[j+1]) {
                char temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
} }
} }
int main() {
    int n;
    cout << "input (n): "; cin >> n;
    char karakter205[n];
    for (int i = 0; i < n; i++) {
        cout << "Karakter ke-" << i+1 << ": ";
        cin >> karakter205[i];
    }
cout << "\nUrutan karakter sebelum sorting: " << endl; for (int i = 0; i < n; i++) {
        cout << karakter205[i] << " ";
    }
    cout << endl;
    bubbleSortAscending(karakter205, n);
 
    cout << "\nUrutan karakter setelah ascending sort: " << endl;
    for (int i = 0; i < n; i++) {
        cout << karakter205[i] << " ";
    }
    cout << endl;
    bubbleSortDescending(karakter205, n);
cout << "\nUrutan karakter setelah descending sort: " << endl;
    for (int i = 0; i < n; i++) {
        cout << karakter205[i] << " ";
    }
    cout << endl;
return 0; 
}
```
#### Output:
![Unguided 3](https://github.com/suxeno/Struktur-Data-Assignment/assets/162097079/20c93e8c-d948-4de3-8f0c-d61a44505d4f)

### Interpretasi:

Pada fungsi bubbleSortAscending dan bubbleSortDescending, terdapat dua loop bersarang untuk membandingkan dan menukar karakter-karakter dalam array. Fungsi bubbleSortAscending digunakan untuk mengurutkan karakter-karakter dari terkecil ke terbesar, sementara bubbleSortDescending untuk mengurutkan dari terbesar ke terkecil.

Di dalam fungsi main, program meminta input jumlah karakter yang akan diurutkan, kemudian karakter-karakter tersebut dimasukkan ke dalam array. Setelah itu, program mencetak urutan karakter sebelum pengurutan, melakukan pengurutan secara ascending, mencetak urutan setelah pengurutan secara ascending, melakukan pengurutan secara descending, dan terakhir mencetak urutan setelah pengurutan secara descending.

Hasil output program menampilkan urutan karakter sebelum pengurutan, urutan setelah pengurutan secara ascending, dan urutan setelah pengurutan secara descending.

### Analisis Kompleksitas:
Waktu Kompleksitas:

Algoritma Bubble Sort Ascending dan Bubble Sort Descending keduanya memiliki struktur yang sama dengan Bubble Sort pada umumnya.
Iterasi luar dalam kedua fungsi berjalan sebanyak (n - 1) kali, karena setiap iterasi luar memastikan bahwa setidaknya satu elemen sudah berada pada posisi yang tepat.
Di dalam iterasi luar, terdapat iterasi dalam yang berjalan sebanyak (n - i - 1) kali, di mana i adalah indeks dari iterasi luar. Hal ini karena setiap iterasi luar akan menempatkan elemen terbesar (pada Bubble Sort Ascending) atau terkecil (pada Bubble Sort Descending) di posisi yang tepat di bagian belakang array.
Setiap iterasi dalam memiliki kompleksitas waktu O(n) karena melakukan perbandingan pada setiap elemen.
Sehingga, waktu kompleksitas untuk kedua algoritma Bubble Sort Ascending dan Bubble Sort Descending adalah O(n^2), di mana n adalah jumlah elemen dalam array.

Ruang Kompleksitas:

Karena tidak ada alokasi memori tambahan yang bergantung pada ukuran masukan (array), ruang kompleksitas kedua algoritma adalah O(1), yaitu konstan.

## Kesimpulan
Algoritma Selection Sort digunakan untuk mengurutkan array bilangan float dengan cara membandingkan setiap elemen dan menukar mereka jika diperlukan. Waktu eksekusi algoritma ini tergantung pada jumlah elemen dalam array. Sebagai contoh, array float berhasil diurutkan dari yang terkecil hingga terbesar menggunakan Selection Sort. Di sisi lain, Bubble Sort merupakan algoritma sorting sederhana yang membandingkan dan menukar pasangan elemen yang berdekatan secara berulang. Meskipun efektif untuk mengurutkan array string secara alfabetis, Bubble Sort kurang efisien terutama pada data yang besar. Dalam kasus ketiga, Bubble Sort digunakan untuk mengurutkan karakter baik dalam urutan naik maupun turun, menunjukkan fleksibilitas algoritma ini dalam mengatasi berbagai jenis data dengan sedikit modifikasi pada implementasinya.

## Referensi
[1] Tarigan, Wanra. Algoritma Pemrograman dan Struktur Data. Eureka Media Aksara, 2022.

[2] Maulana, M. R. (2018). Komparasi Algoritma Sorting pada Bahasa Pemrograman Java. IC-Tech, 12(2). https://doi.org/10.47775/ictech.v12i2.9

[3] Astuti, Y. (2023). Analisis Pengujian Data Algoritma Bubble Sort. REMIK: Riset Dan E-Jurnal Manajemen Informatika Komputer, 7(3), 1413-1420. https://doi.org/10.33395/remik.v7i3.12594

[4] Audy, A. (2015). Komparasi Algoritma Quicksort dan Bucket Sort pada Pengurutan Data Integer. Ultimatics: Jurnal Teknik Informatika, 7(1).

[5] Harahap, Z. ANALISIS PERBANDINGAN KOMPLEKSITAS DALAM ALGORITMA PEMROGRAMAN.

[6] DE, F. A., & Otik, D. (2023). PENGGUNAAN ALGORITMA SELECTION SORT UNTUK MENENTUKAN NILAI TERTINGGI SISWA. JuSiTik: Jurnal Sistem dan Teknologi Informasi Komunikasi, 6(2), 23-26.
