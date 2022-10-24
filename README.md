# Analisis-Diskriminan

    Analisis diskriminan adalah salah satu teknik statistik yang bisa digunakan pada hubungan dependensi (hubungan antarvariabel dimana sudah bisa dibedakan mana variabel respon dan mana variabel penjelas). 
   
   Contoh kasus yang digunakan dalam latihan ini diadaptasi dari Santoso dan Tjiptono (2002), dimana pengelola Minimarket X menduga bahwa ada dua kelompok pembeli, yaitu mereka yang sering berbelanja di Minimarket X dan mereka yang dapat dikategorikan jarang berbelanja di minimarket tersebut. Kategori konsumen sering belanja, jika konsumen berbelanja di Minimarket X minimal 7 kali dalam sebulan, selain dari itu dikategorikan jarang berbelanja. 
  
  Pihak pengelola minimarket ingin mengetahui faktor-faktor apa saja yang mendorong seorang konsumen untuk sering berbelanja atau jarang berbelanja di minimarket tersebut. Untuk mencapai tujuan tersebut, setiap responden diberikan kuesioner yang memuat pertanyaan tentang pendapatnya terhadap 10 atribut minimarket, serta frekuensi berbelanja di minimarket tersebut. Atribut-atribut tersebut adalah:
  
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


#1. Menentukan objek dan variabel yang akan dianalisis

Objek dalam kasus ini adalah “belanja” dengan 2 kategori, yaitu sedikit (0) dan banyak (1). Sementara variabel bebasnya ada 10, yaitu Layout, Bersih, Harga, Kasir, Lengkap, AC, Diskon, Parkir, Staf, dan Citra. Data dan cara mengimpor datanya dalam R dilakukan, sebagai berikut:

![image](https://user-images.githubusercontent.com/116244436/197431725-dec21193-4417-447b-a2f5-e5bb1a7b1bb4.png)

![image](https://user-images.githubusercontent.com/116244436/197431323-431a740e-ba1e-47bf-897f-25729d08c6e8.png)

![image](https://user-images.githubusercontent.com/116244436/197431765-6c207a3a-5e7e-4b84-8a95-d567a3ee5323.png)

#2. Pengujian asumsi multikolinearitas 

![image](https://user-images.githubusercontent.com/116244436/197432601-47a5e9b7-961b-4624-ba9d-0e95a6355d7f.png)

Berdasarkan hasil uji multikolinearitas diperoleh bahwa semua variabel bebas mempunyai nilai P > 0.05. Hal ini menunjukkan bahwa tidak terjadi kasus multikolinearitas pada data.

#3. Pengujian asumsi distribusi normal multivariate

Berikut diberikan syntax untuk membuat plot Chi-Kuadrat untuk melihat secara visual, apakah data mengikuti distribusi normal multivariat. Jika plot tersebut membentuk pola garis lurus, maka dapat diduga data mengikuti distribusi normal multivariat.

![image](https://user-images.githubusercontent.com/116244436/197432752-078c442c-b26d-4da8-a989-40cb70980e3d.png)

![image](https://user-images.githubusercontent.com/116244436/197432804-c0516c21-7318-4455-a4e6-3cc2a4d30039.png)

Berdasarkan Gambar, terlihat bahwa pola data sepertinya membentuk sebuah garis lurus. Untuk lebih meyakinkan bahwa data mengikuti distribusi normal multivariat, dilakukan pengujian, sebagai berikut:

![image](https://user-images.githubusercontent.com/116244436/197432925-08922f23-b4b4-4cdc-a193-1cdf77eea531.png)

![image](https://user-images.githubusercontent.com/116244436/197432964-d7f3400c-8c21-41f6-860b-8f100f9748b6.png)

Hasil yang diperoleh adalah nilai-p<0.05. Ini berarti bahwa data tidak mengikuti distribusi normal multivariat.

#4. Pengujian asumsi kesamaan matriks varians kovarian

![image](https://user-images.githubusercontent.com/116244436/197433092-cfe8c51b-0d95-40d4-b6f8-71e43154d8a9.png)

![image](https://user-images.githubusercontent.com/116244436/197433137-3725f3bf-5945-4a4b-9345-7e4e8fa22d02.png)

Hasil yang diperoleh adalah nilai-p>0.05. Ini berarti bahwa data pada kelompok “berbelanja jarang” dan data pada kelompok “berbelanja sering” adalah homogen.

#5. Pengujian asumsi kesamaan vektor mean

![image](https://user-images.githubusercontent.com/116244436/197433276-f42770b7-0b85-4ab1-9f87-6ac531d322de.png)

![image](https://user-images.githubusercontent.com/116244436/197433322-f02dc074-a826-46fc-a3c9-0f8cb70df54b.png)

Karena nilai-p<0.05, maka diperoleh bahwa terdapat perbedaan vektor mean dari data. Ini menunjukkan bahwa pemisahan kelompok “berbelanja jarang” dan kelompok “berbelanja sering” signifikan.

#6. Mengestimasi fungsi diskriminan

![image](https://user-images.githubusercontent.com/116244436/197433483-07735474-2811-4ead-bc73-5f430667e291.png)

![image](https://user-images.githubusercontent.com/116244436/197433625-ae95cff0-ac84-4a50-b421-1a8f2466cbeb.png)

Berdasarkan hasil pemodelan tersebut diperoleh fungsi diskriminan

Y = 1.045 Layout – 0.547 Bersih – 0.740 Harga – 0.749 Kasir – 0.476 Lengkap – 1.018 AC – 0.419 Diskon + 1.100 Parkir – 0.094 Staf – 0.258 Citra

Berdasarkan nilai Groups means bahwa variabel “Parkir” dan “AC” untuk kelompok “Berbelanja Jarang” dan “Berbelanja Sering” mempunyai nilai yang hampir sama, sehingga dapat dikatakan bahwa dua variabel tersebut tidak mempengaruhi perilaku seseorang dalam berbelanja. Sementara variabel Layout, Bersih, Harga, Kasir, Lengkap, Diskon, Staf dan Citra mempunyai masing-masing nilai mean yang berbeda antara kelompok “Berbelanja Jarang” dan “Berbelanja Sering”, sehingga dapat dikatakan bahwa kedua variabel tersebut dapat mempengaruhi perilaku sesorang dalam berbelanja.

![image](https://user-images.githubusercontent.com/116244436/197433994-1f1ebe52-e5b2-4c46-9eea-78d18c56047f.png)

#7. Mengecek hasil pengklasifikasian 

![image](https://user-images.githubusercontent.com/116244436/197435352-07596f82-8161-4475-a982-792a8ed247e9.png)

![image](https://user-images.githubusercontent.com/116244436/197437242-aacb80ae-ee23-4ce1-bb70-798e1122b882.png)

Berdasarkan hasil pengklasifikasian diperoleh tingkat keakuratan ((0.960+0.667))/2 = 0.81 (81%) di mana terdapat 6 pengamatan yang salah klasifikasi.

#8. Memprediksi objek baru 

![image](https://user-images.githubusercontent.com/116244436/197437491-8e5175a7-fe9e-49dd-983d-ee87e6180c69.png)

![image](https://user-images.githubusercontent.com/116244436/197437529-4e53395d-9f4d-4638-a4e1-365a375dc998.png)

Berdasarkan hasil diperoleh bahwa analisis diskriminan dapat digunakan untuk memisahkan kelompok “berbelanja jarang” dan “berbelanja sering”, berdasarkan variabel layout, bersih, harga, kasir, lengkap, AC, diskon, parkir, staf, dan citra dengan tingkat akurasi 81%. Delapan variabel, yaitu layout, bersih, harga, kasir, lengkap, diskon, staf, dan citra yang paling berpengaruh terhadap pemisahan tersebut.
