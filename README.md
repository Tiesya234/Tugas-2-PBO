# Tugas-2-PBO
# 1. Mengimplementasikan kelas Mahasiswa, Jurusan, dan Universitas
class Mahasiswa: 
    #pendefinisian kelas 'Mahasiswa'
    def __init__(self, nama, nim, jurusan): 
        #method yang digunakan untuk menginisialisasi objek Mahasiswa dengan atribut nama, nim dan jurusan
        self.nama = nama
        self.nim = nim
        self.jurusan = jurusan
    
    def tampilkan_info(self): 
        #method ini digunakan untuk mencetak informasi tentang Mahasiswa berupa nama, nim dan jurusan
        print("Nama:", self.nama)
        print("NIM:", self.nim)
        print("Jurusan:", self.jurusan.NamaJurusan)


class Jurusan:
    #pendefinisian kelas 'Jurusan'
    def __init__(self, nama_jurusan):
        #method yang digunakan untuk menginisialisasi objek Jurusan dengan atribun nama_jurusan dan Daftar_Mahasiswa
        self.NamaJurusan = nama_jurusan
        self.Daftar_Mahasiswa = []
    
    def tambah_mahasiswa(self, mahasiswa):
        #method yang digunakan untuk menambahkan objek Mahasiswa ke dalam Daftar_Mahasiswa
        self.Daftar_Mahasiswa.append(mahasiswa) #menggunakan append untuk menambahkannya
    
    def tampilkan_daftar_mahasiswa(self):
        # method yang digunakan untuk mencetak daftar mahasiswa yang terdaftar dalam jurusan
        if len(self.Daftar_Mahasiswa) == 0:
            #jika Daftar_Mahasiswa kosong maka akan mencetak pesan tidak ada mahasiswa yang terdaftar dalam jurusan ini
            print("Tidak ada mahasiswa terdaftar dalam jurusan", self.NamaJurusan)
        else:
            print("Daftar mahasiswa dalam jurusan", self.NamaJurusan + ":")
            for mahasiswa in self.Daftar_Mahasiswa:
                #jika Daftar_Mahasiswa tidak kosong maka akan mencetak daftar mahasiswa dengan nama dan nim dari setiap mahasiswa
                print(mahasiswa.nama, "-", mahasiswa.nim)


class Universitas:
    #pendefinisian kelas 'Universitas'
    def __init__(self, namaUniversitas):
        #method yang digunakan untuk menginisialisasi objek Universitas dengan atribut namaUNiversitas dan Daftar_Jurusan
        self.NamaUniversitas = namaUniversitas
        self.Daftar_Jurusan = []
    
    def tambah_jurusan(self, jurusan):
        # method yang digunakan untuk menambahkan objek Jurusan ke dalam Daftar_Jurusan univeristas
        self.Daftar_Jurusan.append(jurusan) #menggunakan append untuk menambahkannya
    
    def tampilkan_daftar_jurusan(self):
        #method yang digunakan untuk mecetak daftar jurusan yang ada dalam universitas
        if len(self.Daftar_Jurusan) == 0:
            #jika Daftar_Jurusan kosong, maka akan mencetak pesan bahwa tidak ada jurusan yang terdafatar dalam universitas ini
            print("Tidak ada jurusan terdaftar dalam universitas", self.NamaUniversitas)
        else:
            print("Daftar jurusan dalam universitas", self.NamaUniversitas + ":")
            for jurusan in self.Daftar_Jurusan:
                #jika Daftar_Jurusan tidak kosong, maka akan mencetak nama jurusan dari setiap objek jurusan
                print(jurusan.NamaJurusan)

# 2. membuat objek Universitas dengan nama "XYZ University"
universitas_xyz = Universitas("XYZ University")

# 3. membuat objek Jurusan dengan nama "Teknik Informatika" dan tambahkan ke dalam Universitas XYZ
jurusan_ti = Jurusan("Teknik Informatika")
universitas_xyz.tambah_jurusan(jurusan_ti)

# 4. membuat objek Mahasiswa dan masukkan ke dalam Jurusan Teknik Informatika di Universitas XYZ
mahasiswa_Tiesya = Mahasiswa("Tiesya Andriani Ramadhanti", "G1A022014", jurusan_ti)
jurusan_ti.tambah_mahasiswa(mahasiswa_Tiesya)

# 5. menampilkan daftar jurusan di Universitas XYZ
universitas_xyz.tampilkan_daftar_jurusan()

# 6. menampilkan daftar mahasiswa yang terdaftar dalam Jurusan Teknik Informatika di Universitas XYZ
jurusan_ti.tampilkan_daftar_mahasiswa()
