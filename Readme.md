# Jarkom-Modul-1-D04-2023


## Praktikum Jarkom 1 

### Kelompok D04
### Anggota Kelompok :
Muhammad Rafi Sutrisno - 5025211167 <br/>
Nadira Milha Nailul Fath - 5025211253

## No 1
**Soal**
User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.
a) Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 
b) Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 
c) Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
d) Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

**Jawaban :** <br/>
a. 258040667<br/>
b. 1044861039<br/>
c. 1044861039<br/>
d. 258040696

**Langkah Penyelesaian :**<br/>
a. Menggunakan filter STOR untuk khusus perintah pengunggahan dalam FTP. lalu klik 2 kali maka akan didapat sequence number raw.
![Alt text](/Gambar/no1-a.jpeg)<br/>
b. Menggunakan filter STOR untuk khusus perintah pengunggahan dalam FTP. lalu klik 2 kali maka akan didapat acknowledge number raw.
![Alt text](/Gambar/no1-b.jpeg)<br/>
c. Selanjutnya pada paket tersebut mengandung zip maka untuk mencari respon dari paket tersebut dapat menggunakan filter :
![Alt text](/Gambar/no1-c.png)<br/>
d. maka didapat sequence number raw dan acknowledge number raw dari paket response.
![Alt text](/Gambar/no1-c.png)<br/>

## No 2
**Soal**
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!
**Jawaban :** gunicorn <br/>
**Langkah penyelesaian :**
- Lakukan filtering dengan menggunakan ip.addr == 10.21.78.111 (karena ini adalah ip web server yang digunakan portal praktikum jaringan komputer), kemudian klik kanan dan lakukan Follow, lalu klik TCP Stream, kemudian akan muncul tampilan berikut

![Alt text](/Gambar/no2-filtering.png)<br/>
- Masukkan jawaban pada terminal, lalu akan muncul flag seperti gambar dibawah ini

![Alt text](/Gambar/no2-flag.png)<br/>

## No 3
**Soal**
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
a) Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?
b) Protokol layer transport apa yang digunakan?

**Jawaban :** <br/>
a. 21<br/>
b. UDP

**Langkah Penyelesaian :**
- Lakukan filtering agar ip IP source maupun destination address adalah 239.255.255.250 dengan port 3702 menggunakan : (ip.addr == 239.255.255.250 or ip.src == 239.255.255.250) and udp.port == 3702.<br/>
- Setelah itu bisa dilihat di displayed bagian bawah bahwa ada 21 paket 
dan terlihat protocol nya menggunakan UDP.
![Alt text](/Gambar/no3-a.png)

## No 4
**Soal**
Berapa nilai checksum yang didapat dari header pada paket nomor 130?

**Jawaban :** <br/>
0x18e5

**Langkah Penyelesaian :**
- Pertama cari paket dengan nomor 130 menggunakan filter : frame.number == .<br/>
- Selanjutnya klik 2 kali lau di user diagram control akan ada checksum dan terlihat protocol nya menggunakan UDP

![Alt text](/Gambar/no4.png)
![Alt text](/Gambar/no4-b.png)

## No 5
**Soal**
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
a) Berapa banyak packet yang berhasil di capture dari file pcap tersebut?
b) Port berapakah pada server yang digunakan untuk service SMTP?
c) Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?


**Jawaban :** <br/>
a. 60<br/>
b. 25<br/>
c. 74.53.140.153


**Langkah Penyelesaian :** <br/>
a. Jumlah semua paket dapat dilihat dari displayed dibagian bawah yaitu 60.
![Alt text](/Gambar/no5-a.png)<br/>
b. filter untuk mencari yang menggunakan service smtp lalu port dapat dilihat di Transmission Control Protocol.
![Alt text](/Gambar/no5-b.png)<br/>
c. Yang merupakan public maka filter paket yang memiliki ip tidak mengandung 10. karena ip private biasanya berawalan 10.
![Alt text](/Gambar/no5-c.png)

**Untuk mencari password zip :**
- Filter paket smtp
![Alt text](/Gambar/no5-zip-1.jpeg)<br/>
- lalu buka salah satu paket<br/>
- lalu klik kanan paket follow tcp
![Alt text](/Gambar/no5-zip-2.jpeg)<br/>
- didalam file itu akan ada password yang dtulis
![Alt text](/Gambar/no5-zip-3.png)<br/>

- lalu decode password tersebut menggunakan base64

![Alt text](/Gambar/no5-zip-4.jpeg)<br/>

## No 6
**Soal**
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

**Jawaban :** JDRNJA <br/>
- Pada soal terdapat "server SOURCE ADDRESS 7812 is invalid", lakukan filtering pada packet no 7812. Ditemukan source berikut
![Alt text](/Gambar/no6-filtering.png)<br/>
- Kemudian sesuai hint "Jenis cipher merupakan substitusi a1z26 Cipher", artinya source yang ditemukan harus di-decrypt sesuai aturan a1z26 Cipher. Kemudian sesuai hint "Clue 1: Sepertinya ada yang salah dengan penulisan tersebut secara KBBI. Ada sesuatu yang Besar di depan mata" diketahui semua huruf yang diinginkan adalah huruf kapital. Dan dilakukan decrypt seperti gambar berikut
![Alt text](/Gambar/no6-decrypt.png)<br/>
- Masukkan jawaban pada terminal, kemudian akan muncul flag seperti gambar berikut
![Alt text](/Gambar/no6-flag.png)<br/>

## No 7
**Soal**
Berapa jumlah packet yang menuju IP 184.87.193.88?

**Jawaban :** 6 <br/>
- Lakukan filtering dengan menggunakan ip.dst == 184.87.193.88, lalu akan muncul 6 packet pada wireshark, seperti gambar berikut
![Alt text](/Gambar/no7-filtering.png)<br/>
- Kemudian masukkan jawaban pada terminal dan akan muncul flag seperti gambar dibawah ini
![Alt text](/Gambar/no7-flag.png)<br/>

## No 8
**Soal**
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)

**Jawaban :** tcp.dstport == 80 || udp.dstport == 80 <br/>
- Proses filtering pada soal ini tidak menghasilkan petunjuk apapun karena yang diminta adalah kueri filter
![Alt text](/Gambar/no8-filtering.png)<br/>
- Kemudian masukkan jawaban tcp.dstport == 80 || udp.dstport == 80 pada terminal dan akan muncul flag seperti gambar dibawah ini
![Alt text](/Gambar/no8-flag.png)<br/>

## No 9
**Soal**
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!

**Jawaban :** ip.src == 10.51.40.1 && ip.dst != 10.39.55.34
- Proses filtering pada soal ini tidak menghasilkan petunjuk apapun karena yang diminta adalah kueri filter
![Alt text](/Gambar/no9-filtering.png)<br/>
- Kemudian masukkan jawaban ip.src == 10.51.40.1 && ip.dst != 10.39.55.34 pada terminal dan akan muncul flag seperti gambar dibawah ini
![Alt text](/Gambar/no9-flag.png)<br/>

## No 10
**Soal**
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet

**Jawaban :** dhafin:kesayangannyak0k0
- Lakukan filtering TELNET protocol, kemudian klik kanan dan lakukan follow kemudian akan terdapat user dan password (kredensial), pada proses ini tidak semua packet memiliki kredensial (saya melakukan pencarian manual)
![Alt text](/Gambar/no10-filtering.png)<br/>
- Kemudian masukkan jawaban dhafin:kesayangannyak0k0 pada terminal dan akan muncul flag seperti gambar dibawah ini
![Alt text](/Gambar/no10-flag.png)<br/>
