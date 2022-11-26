# Praktikum6

## Latihan Dictionary pada python membuat program crud sederhana

Repository ini dibuat untuk memenuhi tugas `Module Praktikum 5`, `Pertemuan 10`, Mata Kuliah Bahasa Pemrograman

Nama    : Aditia Seftiawan

NIM     : 312210094

Kelas   : TI.22.B1

Tugas `Module Praktikum 5-Pertemuan 10` Dosen memberi tugas latihan sebagai berikut :

**Soal Latihan yang ada pada `Module Praktikum 5` sebagai berikut :**

![image](https://user-images.githubusercontent.com/115475348/204063706-b90db95a-71e2-4886-9073-d08109008899.png)

1. Berikut adalah program syntax, input program seperti berikut ini :

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

2. Langkah selanjutnya run, dan akan keluar hasil seperti berikut ini :

<img width="602" alt="image" src="https://user-images.githubusercontent.com/115475348/204064251-12da3275-f94c-4586-b78c-eb2c296633c4.png">

3. Selanjutnya kita akan membuat program crud sederhana dan berikut `flowchart` program yang dibuat :


![image](https://user-images.githubusercontent.com/115475348/204071198-68802385-f9fc-4768-8ebe-3b19f180eab6.png)


**Berikut ini adalah soal tugas Praktikum pada `Module Praktikum 5` :**

![image](https://user-images.githubusercontent.com/115475348/204064467-96f5d7ea-01cb-4a0b-b1bc-ee415239b7ab.png)

Berikut ini adalah hasil yang diinginkan pada Tugas `Praktikum 5`

![image](https://user-images.githubusercontent.com/115475348/204065010-7ce62636-fda8-48b0-8ad8-6bab53209b09.png)



![image](https://user-images.githubusercontent.com/115475348/204065023-1547d128-d634-4d85-8a6c-c4aa36ddd349.png)

1. Setelah memahami materi tersebut, input program seperti berikut ini :

        from prettytable import PrettyTable

        print("===================================================================")
        print("Nama         :   Aditia Seftiawan")
        print("NIM          :   312210094")
        print("Kelas        :   TI.22.B1")
        print("Mata Kuliah  :   Bahasa Pemrograman")
        print("===================================================================")

        baris = []
        x = PrettyTable()

        while True:
            print("[ (L)ihat , (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar ]")
            tanya = input("Masukkan Pilihan : ")
            if tanya == "L":
                print("==== Daftar Nilai ====")
                no = 0
                no += 1
                x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
                if not baris:
                    x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
                    print("Not Data")
                else:
                    for data in baris:
                        x.add_row([no, data["nim"], data["nama"], data["tugas"], data["uts"], data["uas"], data["akhir"]])
                    print(x)
            elif tanya == "T":
                print("Tambah Data ")
                nim_v = input("NIM : ")
                nama_v = input("Nama Lengkap : ")
                uts_v = input("Nilai UTS : ")
                uas_v = input("Nilai UAS : ")
                tugas_v = input("Nilai Tugas : ")
                akhir_v = 0.3 * float(tugas_v) + 0.35 * float(uts_v) + 0.35 * float(uas_v)
                baris.append({"nim": nim_v, "nama": nama_v, "tugas": tugas_v, "uts": uts_v, "uas": uas_v, "akhir": akhir_v})
                print()
                print("==== Daftar Nilai ====")
                i = 0
                for data in baris:
                    i += 1
                    x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
                    x.add_row([i, data["nim"], data["nama"], data["tugas"], data["uts"], data["uas"], data["akhir"]])
                print(x)
            elif tanya == "U":
                print("Edit File")
                print("Data siapa yang akan diubah ?")
                siapa = input("Masukkan NIM Mahasiswa yang akan diubah : ")

                print("Data apa yang akan diubah ? : ")
                mhs = input(" 1. Nama \n 2. Nilai Tugas \n 3. Nilai UTS \n 4. Nilai UAS\n Pilih dengan angka (1/2/3/4) : ")
                if mhs == "1":
                    ubahnama = input("Silahkan masukan nama yang benar : ")
                    i = 0
                    d = next(item for item in baris if item['nim'] == siapa)
                    d['nama'] = ubahnama
                    x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
                    i += 1
                    x.add_row([i, d["nim"], d["nama"], d["tugas"], d["uts"], d["uas"], d["akhir"]])
                    print(x)
                elif mhs == "2":
                    ubahtugas = input("Masukkan Nilai Tugas yang benar : ")
                    i = 0
                    d = next(item for item in baris if item['nim'] == siapa)
                    d['tugas'] = ubahtugas
                    lihatuts = d['uts']
                    lihatuas = d['uas']
                    lihatakhir = 0.3 * float(ubahtugas) + 0.35 * float(lihatuts) + 0.35 * float(lihatuas)
                    d['akhir'] = lihatakhir
                    x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
                    for data in baris:
                        i += 1
                    x.add_row([i, data["nim"], data["nama"], data["tugas"], data["uts"], data["uas"], data["akhir"]])
                    print(x)
                elif mhs == "3":
                    ubahuts = input("Masukkan Nilai UTS yang benar : ")
                    i = 0
                    d = next(item for item in baris if item['nim'] == siapa)
                    d['uts'] = ubahuts
                    lihattugas = d['tugas']
                    lihatuas = d['uas']
                    lihatakhir = 0.3 * float(lihattugas) + 0.35 * float(ubahuts) + 0.35 * float(lihatuas)
                    d['akhir'] = lihatakhir
                    x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
                    for data in baris:
                        i += 1
                        x.add_row([i, data["nim"], data["nama"], data["tugas"], data["uts"], data["uas"], data["akhir"]])
                    print(x)
                elif mhs == "4":
                    ubahuas = input("Masukkan Nilai UAS yang benar : ")
                    i = 0
                    d = next(item for item in baris if item['nim'] == siapa)
                    d['uas'] = ubahuas
                    lihattugas = d['tugas']
                    lihatuts = d['uts']
                    lihatakhir = 0.3 * float(lihattugas) + 0.35 * float(lihatuts) + 0.35 * float(ubahuas)
                    d['akhir'] = lihatakhir
                    x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
                    for data in baris:
                        i += 1
                        x.add_row([i, data["nim"], data["nama"], data["tugas"], data["uts"], data["uas"], data["akhir"]])
                    print(x)
                else:
                    print("Pilihan Salah")

            elif tanya == "C":
                print(" ========== Pencarian Data ==========")
                print(" Pencarian berdasarkan NIM ")
                carinim = input("Masukkan NIM yang akan dicari : ")
                xdata = next(item for item in baris if item['nim'] == carinim)
                print("NIM : ", carinim)
                print("Nama : ", xdata['nama'])
                print("Nilai Tugas : ", xdata['tugas'])
                print("Nilai UTS : ", xdata['uts'])
                print("Nilai UAS : ", xdata['uas'])
                print("Nilai Akhir : ", xdata['akhir'])
            elif tanya == "H":
                print("Hapus Data Berdasarkan NIM")
                datahapus = input("Masukkan NIM data yang akan dihapus : ")
                xhapus = next(item for item in baris if item['nim'] == datahapus)
                del xhapus['nim']
                del xhapus['nama']
                del xhapus['tugas']
                del xhapus['uts']
                del xhapus['uas']
                del xhapus['akhir']
                print("Data Berhasil Dihapus")
                no = 0
                no += 1
                x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
                if not baris:
                    x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
                    print("Not Data")
                else:
                    for data in baris:
                        x.add_row([no, data["NIM"], data["NAMA"], data["TUGAS"], data["UTS"], data["UAS"], data["AKHIR"]])
                    print(x)

            elif tanya == "K":
                print("Anda Keluar Dari Aplikasi")
                break
            else:
                print("Anda Memilih Pilihan Yang Salah")

2. Langkah selanjutnya run program tersebut dan uraikan satu persatu dan berikut ini adalah hasilnya :


* `Pilih (T)` untuk menambahkan data, dan hasilnya seperti berikut ini :

<img width="603" alt="image" src="https://user-images.githubusercontent.com/115475348/204065539-78716a37-c213-4c8a-9ce1-7cfb3741605c.png">

* `Pilih (L)` untuk melihat data, dan hasilnya seperti berikut ini :

<img width="460" alt="image" src="https://user-images.githubusercontent.com/115475348/204065592-d5598be3-27e0-413a-9906-420041739204.png">

* `Pilih (U)` untuk merubah data, dan hasilnya seperti berikut ini :

<img width="507" alt="image" src="https://user-images.githubusercontent.com/115475348/204065841-684ef341-4c63-4e8c-8744-f78cc9793929.png">

* `Pilih (C)` untuk mencari data yang telah diinput, dan hasilnya seperti berikut ini :

<img width="413" alt="image" src="https://user-images.githubusercontent.com/115475348/204065912-dd4e3bee-d2d3-4cf4-80cc-839656bc4e74.png">

* `Pilih (H)` untuk menghapus data yang ingin di hapus, hasilnya seperti berikut ini :

<img width="413" alt="image" src="https://user-images.githubusercontent.com/115475348/204065989-20571b22-17ed-4b8a-b2a5-c979ef37009a.png">

* `Pilih (K)` untuk keluar dari program aplikasi, dan hasil nya seperti berikut ini :

<img width="369" alt="image" src="https://user-images.githubusercontent.com/115475348/204066441-8dd04821-31e6-4cc0-965f-29b3a80afdfc.png">

Demikianlah sedikit penjelasan dari saya, kurang lebihnya mohon maaf

Terimakasih









