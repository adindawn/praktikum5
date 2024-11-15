## NAMA  : ADINDA AULIA NABILA PUTRI 

## NIM   : 312410309

## KELAS : TI.24.A.4 

# Tugas Praktikum 5 

```PYTHON
def hitung_nilai_akhir(tugas, uts, uas):
    return (tugas * 0.30) + (uts * 0.35) + (uas * 0.35)

def tampilkan_daftar(daftar_mahasiswa):
    print("=" * 70)
    print("| No |     Nama      |    NIM    | Tugas | UTS | UAS | Akhir |")
    print("=" * 70)
    for idx, mhs in enumerate(daftar_mahasiswa, 1):
        print("| {:<2} | {:<12} | {:<8} | {:<5} | {:<3} | {:<3} | {:<5.2f} |".format(
            idx, 
            mhs['nama'], 
            mhs['nim'],
            mhs['tugas'],
            mhs['uts'],
            mhs['uas'],
            mhs['nilai_akhir']
        ))
    print("=" * 70)

def main():
    daftar_mahasiswa = []
    
    while True:
        print("\nMasukkan data mahasiswa")
        nama = input("Nama : ")
        nim = input("NIM : ")
        
        while True:
            try:
                tugas = float(input("Nilai Tugas : "))
                if 0 <= tugas <= 100:
                    break
                print("Nilai harus antara 0-100!")
            except ValueError:
                print("Masukkan nilai yang valid!")
        
        while True:
            try:
                uts = float(input("Nilai UTS : "))
                if 0 <= uts <= 100:
                    break
                    print("Nilai harus antara 0-100!")
            except ValueError:
                print("Masukkan nilai yang valid!")
        
        while True:
            try:
                uas = float(input("Nilai UAS : "))
                if 0 <= uas <= 100:
                    break
                print("Nilai harus antara 0-100!")
            except ValueError:
                print("Masukkan nilai yang valid!")
        
        # Hitung nilai akhir
        nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
        
        # Tambahkan ke daftar
        mahasiswa = {
            'nama': nama,
            'nim': nim,
            'tugas': tugas,
            'uts': uts,
            'uas': uas,
            'nilai_akhir': nilai_akhir
        }
        daftar_mahasiswa.append(mahasiswa)
        
# Tanya apakah ingin menambah data lagi
        tambah = input("\nTambah data (y/t)? ")
        if tambah.lower() != 'y':
            break
    
# Tampilkan daftar akhir
    print("\nDaftar Nilai Mahasiswa:")
    tampilkan_daftar(daftar_mahasiswa)

if __name__ == "__main__":
     main()
````

# Berikut hasil code dari Visual Studio Code 

   ![Screenshot (71)](https://github.com/user-attachments/assets/80f176fb-e1fb-4fd7-8c10-6943af9ef13e)


```PYTHON
def hitung_nilai_akhir(tugas, uts, uas):
    return (tugas * 0.30) + (uts * 0.35) + (uas * 0.35)
````

Fungsi ini menerima 3 parameter : nilai tugas, UTS, dan UAS 
Menghitung nilai akhir dengan bobot 
   - Tugas : 30% (0.30)
   - UTS : 35% (0.35)
   - UAS : 35% (0.35)

Mengembalikan hasil perhitungan nilai akhir.

```PYTHON
def tampilkan_daftar(daftar_mahasiswa):
    print("=" * 70)
    print("| No |     Nama      |    NIM    | Tugas | UTS | UAS | Akhir |")
    print("=" * 70)
````
- Menerima Parameter berikut list yang berisi data mahasiswa
- Membuat tampilan tabel dengan header
- Menggunakan perulangan untuk menampilkan setiap data mahasiswa
- format output menggunakan string formatting untuk merapikan tampilan
- enumerate(daftar_mahasiswa, 1) digunakan untuk membuat penomoran mulai dari 1

```PYTHON
def main():
    daftar_mahasiswa = []
````

- Fungsi utama program
- Membuat list kosong untuk menyimpan data mahasiswa

```PYTHON
while True:
        print("\nMasukkan data mahasiswa")
        nama = input("Nama : ")
        nim = input("NIM : ")
        
        while True:
            try:
                tugas = float(input("Nilai Tugas : "))
                if 0 <= tugas <= 100:
                    break
                print("Nilai harus antara 0-100!")
            except ValueError:
                print("Masukkan nilai yang valid!")
````

- Menggunakan nested while loop untuk input dan validasi
- Tyr-except untuk menangani input nilai yang tidak valid
- validasi rentang nilai (0-100)
- Proses yang sama dilakukan untuk nilai UTS dan UAS

```PYTHON
# Hitung nilai akhir
        nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
        
        # Tambahkan ke daftar
        mahasiswa = {
            'nama': nama,
            'nim': nim,
            'tugas': tugas,
            'uts': uts,
            'uas': uas,
            'nilai_akhir': nilai_akhir
        }
        daftar_mahasiswa.append(mahasiswa)
````

- Memanggil fungsi hitung_nilai_akhir
- Membuat dictionary untuk menyimpan data satu mahasiswa
- Menambah dictionary kedalam list daftar_mahasiswa

```PYTHON
tambah = input("\nTambah data (y/t)? ")
        if tambah.lower() != 'y':
            break
````

- Meminta konfirmasi untuk menambah data lagi
- jika input bukan 'y', keluar dari loop

```PYTHON
print("\nDaftar Nilai Mahasiswa:")
    tampilkan_daftar(daftar_mahasiswa)
````

- Memanggil fungsi tampil_daftar untuk menampilkan semua data

```PYTHON
if __name__ == "__main__":
     main()
````

- Memastikan fungsi main() hanya dijalankan jika file dijalankan langsung
- Tidak akan menjalankan jika file di-import sebagai modul

# Berikut Flowchart nya 

   ![flowchartprak5](https://github.com/user-attachments/assets/441d9db2-3812-41bb-a93b-3422bc8008e6)

