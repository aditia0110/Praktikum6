# Praktikum6

Repository ini dibuat untuk memenuhi tugas Module Praktikum 5, Pertemuan 10, Mata Kuliah Bahasa Pemrograman

Nama    : Aditia Seftiawan

NIM     : 312210094

Kelas   : TI.22.B1

Tugas Module Praktikum 5-Pertemuan 10 Dosen memberi tugas latihan sebagai berikut :

* Soal Latihan yang ada pada Module Praktikum 5 sebagai berikut :

![image](https://user-images.githubusercontent.com/115475348/204063706-b90db95a-71e2-4886-9073-d08109008899.png)

* Berikut adalah program syntax, input program seperti berikut ini :

    print("===================================================================")
print("Nama         :   Aditia Seftiawan")
print("NIM          :   312210094")
print("Kelas        :   TI.22.B1")
print("Mata Kuliah  :   Bahasa Pemrograman")
print("===================================================================")

# Buat dictionary daftar kontak
print("Buat dictionary nama sebagai key, dan nomor sebagai value")

isi = {'Ari': '081267888', 'Dina': '087677776'}
print("Nama | Nomor kontak")
print(isi)

print("Tampilkan Kontaknya Ari")
print(isi['Ari'])

print("Tambah kontak baru dengan nama Riko, nomor 087654544")
isi['Riko']= '087654544'
print(isi)

print("Ubah kontak Dina dengan nomor baru 088999776")
isi['Dina']= '088999777'
print(isi)

print("Tampilkan semua Nama")
print(isi.keys())

print("Tampilkan semua Nomor")
print(isi.values())

print("Tampilkan daftar Nama dan nomornya")
print(isi.items())

print("Hapus kontak Dina")
del isi['Dina']
print(isi)

print("===================================================================")


















