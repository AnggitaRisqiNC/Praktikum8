# Praktikum8
Nama : Anggita Risqi Nur Clarita

NIM : 312210450

Kelas : TI.22.A.4

## DAFTAR ISI <br>
| No | Description | Link |
|-----|------|-----|
|1|Tugas Praktikum 8|[Click Here](#tugas-praktikum-8)|
|2|Praktikum 8|[Click Here](#praktikum-8)|
|3|Flowchart Praktikum 8|[Click Here](#flowchart-praktikum-8)|
|4|Diagram Class Praktikum 8|[Click Here](#diagram-class-praktikum-8)

## Tugas Praktikum 8
Buat program sederhana dengan mengaplikasikan penggunaan class. Buatlah class untuk menampilkan daftar nilai mahasiswa, dengan ketentuan:
* Method **tambah()** untuk menambah data
* Method **tampilkan()** untuk menampilkan data
* Method **hapus(nama)** untuk menghapus data berdasarkan nama
* Method **ubah(nama)** untuk mengubah data berdasarkan nama
* Buat diagram class, flowchart dan penjelasan programnya pada README.md.
* Commit dan push repository ke github.

## Praktikum 8
### Program
![image](https://github.com/AnggitaRisqiNC/Praktikum8/blob/main/Gambar/1.png)
![image](https://github.com/AnggitaRisqiNC/Praktikum8/blob/main/Gambar/2.png)
![image](https://github.com/AnggitaRisqiNC/Praktikum8/blob/main/Gambar/3.png)
![image](https://github.com/AnggitaRisqiNC/Praktikum8/blob/main/Gambar/4.png)

### Hasil dari Program (RUN)
![image](https://github.com/AnggitaRisqiNC/Praktikum8/blob/main/Gambar/5.png)
![image](https://github.com/AnggitaRisqiNC/Praktikum8/blob/main/Gambar/6.png)
![image](https://github.com/AnggitaRisqiNC/Praktikum8/blob/main/Gambar/7.png)
![image](https://github.com/AnggitaRisqiNC/Praktikum8/blob/main/Gambar/8.png)
![image](https://github.com/AnggitaRisqiNC/Praktikum8/blob/main/Gambar/9.png)
![image](https://github.com/AnggitaRisqiNC/Praktikum8/blob/main/Gambar/10.png)

### Penjelasan
Pertama kita harus mendeklarasikan bahwa variabel data sebagai penyimpanan (dictionary) sebuah data inputan.
```python
data = {}
```

Selanjutnya adalah membuat Class :
```python
class Data():
```

**def _init_(self)** merupakan constructor (Method atau fungsi yang akan dieksekusi ketika instance class dibuat).
```python
def __init__(self, nama, nim, tugas, uts, uas, nilaiakhir):
```

Kemudian menambahkan definisi fungsi :

Menggunakan Perulangan `while True:` dapat diartikan perulangan akan terus mengulang jika inputan benar dan masuk kedalam proses jika tidak maka perulangan berhenti atau lanjut ke proses selanjutnya. Gunakan statement `if` untuk memproses perintah yang diinginkan sesuai inputan.
```python
while True:

    print("\33[34m")
    print("|1| Lihat Data")
    print("|2| Tambah Data")
    print("|3| Ubah Data")
    print("|4| Hapus Data")
    print("|5| Keluar")

    x = input(">> PILIH MENU : ")

    if x == '1':
        self.tampilkan()
    elif x == '2':
        self.tambah()
    elif x == '3':
        self.ubah()
    elif x == '4':
        self.hapus()
    else:
        exit()
```

1. Menambahkan Data

    Perintah dijalankan jika input yang dimasukan adalah '2', Kondisi berikut digunakan untuk melakukan input data seperti Nama, NIM, Nilai Tugas, UTS dan UAS :
    ```python
    def tambah(self):
            print()
            print("Tambah Data")
            self.nama  = input    ("Nama        : ")
            self.nim   = input    ("NIM         : ")
            self.tugas = int(input("Nilai Tugas : "))
            self.uts   = int(input("Nilai UTS   : "))
            self.uas   = int(input("Nilai UAS   : "))
            self.nilaiakhir = (self.tugas * 30 / 100) + (self.uts * 35 / 100) + (self.uas * 35 / 100)
            data[self.nama] = [self.nim, self.tugas, self.uts, self.uas, self.nilaiakhir]
            print("\33[32m\nDATA BERHASIL DITAMBAHKAN!")
    ```
    Untuk nilai akhir dibuat berdasarkan operasi dari variabel `self.tugas, self.uts, self.uas` yang mewakili Nilai Tugas, Nilai UTS, dan Nilai UAS.


Class Mahasiswa diturunkan dari Class data
```python
class mahasiswa(Data):
```

2. Menampilkan Data

    Perintah dijalankan jika input yang dimasukan adalah '1', Jika sebelumnya data sudah ditambahkan atau data tersedia, maka data tersebut akan ditampilkan sebanyak data yang ditambahkan. Jika data tersebut belum ditambahkan atau tidak tersedia, maka akan menampilkan bahwa tidak ada data : 
    ```python
    def tampilkan(self):
            if data.items():
                print()
                print("Daftar Nilai")
                print()
                print("=============================================================================================")
                print("|  No  |       NAMA       |      NIM      |   TUGAS   |    UTS    |    UAS    | Nilai Akhir |")
                print("=============================================================================================")
                i = 0
                for a in data.items():
                    i += 1
                    print("|  {no:2d}  |   {0:12s}   |  {1:11s}  |  {2:7d}  |  {3:7d}  |  {4:7d}  |   {5:6.2f}    |"
                        .format(a[0][: 14], a[1][0], a[1][1], a[1][2], a[1][3], a[1][4], no=i))
                print("=============================================================================================")

            else:
                print()
                print("Daftar Nilai")
                print()
                print("=============================================================================================")
                print("|  No  |       NAMA       |      NIM      |   TUGAS   |    UTS    |    UAS    | Nilai Akhir |")
                print("=============================================================================================")
                print("|                                       TIDAK ADA DATA                                      |")
                print("=============================================================================================")
    ```
    Data yang akan ditampilkan adalah Nama, NIM, Nilai Tugas, UTS, UAS, dan Nilai Akhir.

3. Mengubah Data

    Perintah dijalankan jika input yang dimasukan adalah '3', di dalam kondisi ini terdapat input dan kondisi, dimana jika ada di dalam variabel (data.keys) :
    ```python
    def ubah(self):
            print()
            print("Ubah Data Mahasiswa")
            self.nama = input("Nama        : ")
            if self.nama in data.keys():
                self.nim   = input    ("NIM         : ")
                self.tugas = int(input("Nilai Tugas : "))
                self.uts   = int(input("Nilai UTS   : "))
                self.uas   = int(input("Nilai UAS   : "))
                self.nilaiakhir = (self.tugas * 30 / 100) + (self.uts * 35 / 100) + (self.uas * 35 / 100)
                data[self.nama] = [self.nim, self.tugas, self.uts, self.uas, self.nilaiakhir]
                print("\33[33m\nDATA BERHASIL DIUBAH!")
            else:
                print("Data {0} tidak ada".format(self.nama))
                print("\33[31m\nDATA TIDAK DITEMUKAN!")
    ```
    Jika nama tersebut ada pada data, maka user akan diminta untuk menginputkan data apa saja yang ingin dirubah. Jika nama tersebut tidak ada, maka akan menampilkan bahwa data tidak ditemukan.

4. Menghapus Data

    Perintah dijalankan jika input yang digunakan adalah '4', sama seperti mengubah data, untuk menghapus data yang dipilih menggunakan variabel (data.keys):
    ```python
    def hapus(self):
            print()
            print("Hapus Data Mahasiswa")
            self.nama = input("Nama       : ")
            if self.nama in data.keys():
                del data[self.nama]
                print("\33[31m\nDATA BERHASIL DIHAPUS!")
            else:
                print("Data {0} tidak ada".format(self.nama))
                print("\33[31m\nDATA TIDAK DITEMUKAN!")
    ```
    Jika nama tersebut ada pada data, maka data tersebut akan di-delete pada dictionary sehingga data tidak tersedia lagi. Jika nama tersebut tidak ada pada data, maka akan menampilkan bahwa data tidak ditemukan.

## Diagram Class Praktikum 8
![image](https://github.com/AnggitaRisqiNC/Praktikum8/blob/main/Gambar/Diagram%20Class%20Praktikum%208.png)

## Flowchart Praktikum 8
![image](https://github.com/AnggitaRisqiNC/Praktikum8/blob/main/Gambar/Flowchart%20Praktikum%208.png)

## Finish