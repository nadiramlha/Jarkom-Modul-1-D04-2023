# Jarkom-Modul-1-D04-2023


## Praktikum Jarkom 1 

### Kelompok D04
### Anggota Kelompok :
Muhammad Rafi Sutrisno - 5025211167
Nadira Milha Nailul Fath - 5025211253

## No 1
**Jawaban :** 
a. 258040667
b. 1044861039
c. 1044861039
d. 258040696

**Langkah Penyelesaian :**
a. Menggunakan filter STOR untuk khusus perintah pengunggahan dalam FTP. lalu klik 2 kali maka akan didapat sequence number raw.
![Alt text](url)
b. Menggunakan filter STOR untuk khusus perintah pengunggahan dalam FTP. lalu klik 2 kali maka akan didapat acknowledge number raw.
![Alt text](url)
c. Selanjutnya pada paket tersebut mengandung zip maka untuk mencari respon dari paket tersebut dapat menggunakan filter :
![Alt text](url)
d. maka didapat  sequence number raw dan acknowledge number raw dari paket response.
![Alt text](url)

## No 3
**Jawaban :** 
a. 21
b. UDP

**Langkah Penyelesaian :**
- Lakukan filtering agar ip IP source maupun destination address adalah 239.255.255.250 dengan port 3702 menggunakan : (ip.addr == 239.255.255.250 or ip.src == 239.255.255.250) and udp.port == 3702.
- Setelah itu bisa dilihat di displayed bagian bawah bahwa ada 21 paket 
dan terlihat protocol nya menggunakan UDP.
![Alt text](url)

## No 4
**Jawaban :** 
0x18e5

**Langkah Penyelesaian :**
- Pertama cari paket dengan nomor 130 menggunakan filter : frame.number == .
- Selanjutnya klik 2 kali lau di user diagram control akan ada checksum.
dan terlihat protocol nya menggunakan UDP
![Alt text](url)

## No 5
**Jawaban :** 
a. 60
b. 25
c. 74.53.140.153


**Langkah Penyelesaian :**
a. Jumlah semua paket dapat dilihat dari displayed dibagian bawah yaitu 60.
![Alt text](url)
b. filter untuk mencari yang menggunakan service smtp lalu port dapat dilihat di Transmission Control Protocol.
![Alt text](url)
c. Yang merupakan public maka filter paket yang memiliki ip tidak mengandung 10. karena ip private biasanya berawalan 10.
![Alt text](url)

**Untuk mencari password zip :**
- Filter paket smtp
![Alt text](url)
- lalu buka salah satu paket
- lalu klik kanan paket follow tcp
![Alt text](url)
- didalam file itu akan ada password yang dtulis
![Alt text](url)
- lalu decode password tersebut menggunakan base64 
![Alt text](url)