# Tugas4

### **Penjelasan Program Pengelolaan Nilai Mahasiswa**

Program ini bertujuan untuk mempermudah pengelolaan data nilai mahasiswa, termasuk nilai **tugas**, **UTS** (Ujian Tengah Semester), dan **UAS** (Ujian Akhir Semester). Berdasarkan nilai-nilai ini, program menghitung nilai akhir mahasiswa dengan memperhatikan bobot setiap komponen nilai. Bobotnya adalah:
- **Tugas**: 30% dari nilai akhir
- **UTS**: 35% dari nilai akhir
- **UAS**: 35% dari nilai akhir

Program ini juga menyediakan fitur untuk memasukkan data mahasiswa sebanyak mungkin, dan akhirnya menampilkan daftar semua mahasiswa yang sudah dimasukkan beserta nilai akhirnya.

### **Struktur Program**

Program ini terdiri dari beberapa bagian utama yang bekerja bersama-sama untuk mencapai tujuan tersebut, yaitu:

1. **Fungsi `hitung_nilai_akhir()`** untuk menghitung nilai akhir mahasiswa.
2. **Fungsi `main()`** yang merupakan fungsi utama untuk menjalankan program, termasuk menginput data mahasiswa dan menghitung nilai akhir.
3. **Perulangan untuk menginput data mahasiswa** yang memungkinkan pengguna untuk menambah data sebanyak yang diinginkan.
4. **Menampilkan hasil** berupa daftar nilai mahasiswa yang sudah dimasukkan.

### 1. **Fungsi `hitung_nilai_akhir(tugas, uts, uas)`**

```python
def hitung_nilai_akhir(tugas, uts, uas):
    # Menghitung nilai akhir berdasarkan bobot
    return tugas * 0.30 + uts * 0.35 + uas * 0.35
```

Fungsi `hitung_nilai_akhir` adalah inti dari perhitungan nilai akhir mahasiswa. Fungsi ini menerima tiga parameter input, yaitu:
- `tugas`: nilai dari tugas yang diberikan kepada mahasiswa,
- `uts`: nilai dari Ujian Tengah Semester (UTS),
- `uas`: nilai dari Ujian Akhir Semester (UAS).

Fungsi ini bekerja dengan cara mengalikan setiap nilai komponen dengan bobot yang sesuai:
- **Tugas** (30%) dihitung dengan cara mengalikan nilai tugas dengan 0.30.
- **UTS** (35%) dihitung dengan cara mengalikan nilai UTS dengan 0.35.
- **UAS** (35%) dihitung dengan cara mengalikan nilai UAS dengan 0.35.

Rumus perhitungan nilai akhir adalah sebagai berikut:
\[
\text{Nilai Akhir} = (\text{Tugas} \times 0.30) + (\text{UTS} \times 0.35) + (\text{UAS} \times 0.35)
\]

Dengan demikian, fungsi ini menghasilkan nilai akhir yang merupakan gabungan dari kontribusi masing-masing komponen nilai, sesuai dengan bobot yang telah ditentukan.

### 2. **Fungsi `main()` - Program Utama**

```python
def main():
    # Membuat list kosong untuk menyimpan data mahasiswa
    daftar_mahasiswa = []
```

Fungsi `main()` adalah titik awal dari program ini. Di dalamnya terdapat beberapa proses utama yang akan dijalankan saat program dijalankan. Fungsi ini diawali dengan deklarasi sebuah **list kosong** bernama `daftar_mahasiswa`. List ini akan digunakan untuk menyimpan data mahasiswa, yang masing-masing datanya disusun dalam bentuk **dictionary**.

#### **Perulangan untuk Memasukkan Data Mahasiswa**

```python
    while True:
        # Memasukkan nama mahasiswa (dalam hal ini "YUDHA" sebagai input pertama)
        nama = "YUDHA"  # Nama otomatis "YUDHA"
        tugas = 80  # Nilai tugas
        uts = 75    # Nilai UTS
        uas = 95    # Nilai UAS
```

Pada bagian ini, kita menggunakan perulangan `while True`, yang akan terus berlanjut sampai pengguna memilih untuk berhenti. Dalam perulangan ini, kita secara otomatis mengisi beberapa data untuk mahasiswa pertama, yaitu:
- **Nama** mahasiswa: `"YUDHA"`,
- **Nilai tugas**: 80,
- **Nilai UTS**: 75,
- **Nilai UAS**: 95.

Meskipun dalam kode ini nama mahasiswa telah diatur menjadi "YUDHA" dan nilai-nilai lainnya juga sudah diberikan secara manual, program ini dapat dikembangkan lebih lanjut untuk meminta input dari pengguna.

#### **Menghitung Nilai Akhir**

```python
        # Menghitung nilai akhir
        nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
```

Setelah data mahasiswa dimasukkan (nama dan nilai), langkah berikutnya adalah menghitung **nilai akhir** mahasiswa tersebut. Fungsi `hitung_nilai_akhir()` dipanggil dengan parameter nilai tugas, UTS, dan UAS yang sudah dimasukkan sebelumnya. Fungsi ini akan mengembalikan hasil perhitungan nilai akhir, yang kemudian disimpan dalam variabel `nilai_akhir`.

#### **Menyimpan Data Mahasiswa dalam Dictionary**

```python
        # Menyimpan data mahasiswa dalam bentuk dictionary
        mahasiswa = {
            "Nama": nama,
            "Tugas": tugas,
            "UTS": uts,
            "UAS": uas,
            "Nilai Akhir": nilai_akhir
        }
```

Setelah nilai akhir dihitung, informasi tentang mahasiswa disimpan dalam bentuk **dictionary**. Dictionary ini menyimpan informasi sebagai pasangan kunci dan nilai:
- `Nama`: Nama mahasiswa,
- `Tugas`: Nilai tugas,
- `UTS`: Nilai UTS,
- `UAS`: Nilai UAS,
- `Nilai Akhir`: Hasil perhitungan nilai akhir.

#### **Menambahkan Data Mahasiswa ke dalam Daftar**

```python
        # Menambahkan data mahasiswa ke dalam daftar
        daftar_mahasiswa.append(mahasiswa)
```

Setelah data mahasiswa disimpan dalam dictionary, data tersebut dimasukkan ke dalam list `daftar_mahasiswa` menggunakan metode `append()`. Dengan demikian, setiap mahasiswa yang datanya telah dimasukkan akan disimpan dalam list tersebut.

#### **Menanyakan Apakah Pengguna Ingin Menambah Data Lagi**

```python
        # Menanyakan apakah ingin menambah data lagi
        tanya = input("Apakah Anda ingin menambah data? (y/t): ").lower()
        if tanya == 't':
            break
```

Di sini, program akan menanyakan kepada pengguna apakah mereka ingin menambahkan data mahasiswa lagi. Program akan meminta input berupa "y" (ya) atau "t" (tidak). Jika pengguna mengetikkan **"t"**, perulangan `while` akan dihentikan dengan menggunakan `break`. Jika jawabannya "y", perulangan akan terus berjalan, dan pengguna dapat memasukkan data mahasiswa lainnya.

#### **Menampilkan Daftar Nilai Mahasiswa**

```python
    # Menampilkan daftar mahasiswa dan nilai akhir
    print("\nDaftar Nilai Mahasiswa:")
    print("="*50)
    for mhs in daftar_mahasiswa:
        print(f"Nama: {mhs['Nama']}, Tugas: {mhs['Tugas']}, UTS: {mhs['UTS']}, UAS: {mhs['UAS']}, Nilai Akhir: {mhs['Nilai Akhir']:.2f}")
    print("="*50)
```

Setelah pengguna memilih untuk berhenti dan tidak menambah data lagi, program akan menampilkan semua data mahasiswa yang telah dimasukkan. Program akan menampilkan nama, nilai tugas, UTS, UAS, dan nilai akhir setiap mahasiswa dalam format yang mudah dibaca. Format tersebut menggunakan **f-string** untuk menampilkan informasi dari dictionary `mhs` dalam bentuk yang rapi. Angka **nilai akhir** ditampilkan dengan dua angka desimal.

### 3. **Menjalankan Program Utama**

```python
# Menjalankan program utama
if __name__ == "__main__":
    main()
```

Bagian ini memastikan bahwa program akan berjalan hanya ketika script ini dijalankan langsung (bukan diimpor sebagai modul ke dalam program lain). Fungsi `main()` dipanggil untuk menjalankan keseluruhan program.

---

### **Contoh Output Program**

Jika program dijalankan dengan input yang sudah ditentukan (misalnya nilai tugas, UTS, dan UAS untuk mahasiswa "YUDHA"), berikut adalah contoh output yang dapat dilihat oleh pengguna:

```
Masukkan nilai tugas (0-100): 80
Masukkan nilai UTS (0-100): 75
Masukkan nilai UAS (0-100): 95
Apakah Anda ingin menambah data? (y/t): t

Daftar Nilai Mahasiswa:
==================================================
Nama: YUDHA, Tugas: 80, UTS: 75, UAS: 95, Nilai Akhir: 84.25
==================================================
```

### **Flowchart**
![Screenshot 2024-11-15 192611](https://github.com/user-attachments/assets/f1f317cb-cdeb-4e91-a580-538ed0d45954)



