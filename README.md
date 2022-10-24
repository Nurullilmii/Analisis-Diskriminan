# Analisis-Diskriminan

    Analisis diskriminan adalah salah satu teknik statistik yang bisa digunakan pada hubungan dependensi (hubungan antarvariabel dimana sudah bisa dibedakan mana variabel respon dan mana variabel penjelas). 
   
   Contoh kasus yang digunakan dalam latihan ini diadaptasi dari Santoso dan Tjiptono (2002), dimana pengelola Minimarket X menduga bahwa ada dua kelompok pembeli, yaitu mereka yang sering berbelanja di Minimarket X dan mereka yang dapat dikategorikan jarang berbelanja di minimarket tersebut. Kategori konsumen sering belanja, jika konsumen berbelanja di Minimarket X minimal 7 kali dalam sebulan, selain dari itu dikategorikan jarang berbelanja. 
  Pihak pengelola minimarket ingin mengetahui faktor-faktor apa saja yang mendorong seorang konsumen untuk sering berbelanja atau jarang berbelanja di minimarket tersebut. Untuk mencapai tujuan tersebut, setiap responden diberikan kuesioner yang memuat pertanyaan tentang pendapatnya terhadap 10 atribut minimarket, serta frekuensi berbelanja di minimarket tersebut. Atribut-atribut tersebut adalah
1. Penempatan produk yang dijual (Layout)
2. Kebersihan minimarket (Bersih)
3. Harga produk yang ditawarkan (Harga)
4. Pelayanan Kasir (Kasir)
5. Kelengkapan produk yang dijual (Lengkap)
6. Fasilitas AC yang dingin (AC)
7. Adanya diskon harga produk (Diskon)
8. Ketersedian Lahan Parkir yang aman dan luas (Parkir)
9. Pelayanan Karyawan (Staf)
10. Citra tentang minimarket tersebut (Citra)
Gunakan informasi data tersebut untuk mengetahui
a. apakah terdapat perbedaan seorang konsumen untuk sering berbelanja atau jarang berbelanja?
b. faktor-faktor apa saja yang mempengaruhi perbedaan perilaku tersebut?


##1. Menentukan objek dan variabel yang akan dianalisis
Objek dalam kasus ini adalah “belanja” dengan 2 kategori, yaitu sedikit (0) dan banyak (1). Sementara variabel bebasnya ada 10, yaitu Layout, Bersih, Harga, Kasir, Lengkap, AC, Diskon, Parkir, Staf, dan Citra. Data dan cara mengimpor datanya dalam R dilakukan, sebagai berikut:

setwd("D:/KMMI")
dt.disk <- read.csv("KMMI-Data Latihan An Diskriminan.csv")
dt.disk
dt.disk1 <- dt.disk[1:40,]
dt.disk2 <- dt.disk[41:50,]
dt.disk1

![image](https://user-images.githubusercontent.com/116244436/197431323-431a740e-ba1e-47bf-897f-25729d08c6e8.png)

