# SIG_Basic-Raster-Styling-and-Analysis-

*Tutorial Basic Raster Styling and Analysis 

1. Download file gpw-v4-population-count-rev11_2000_2pt5_min_tif.zip dan gpw-v4-population-count-rev11_2010_2pt5_min_tif.zip terlebih dahulu

2. Buka QGIS dan cari file yang di download pada panel browser. Seret atau klik dua kali file gpw-v4-population-count-rev11_2000_2pt5_min.tif ke kanvas (*Gambar 1*)

3. Pada layer baru gpw-v4-population-count-rev11_2000_2pt5_min akan ditambahkan ke panel layers. Selanjutnya cari file gpw-v4-population-count-rev11_2010_2pt5_min_tif.zip dan seret ke kanvas file gpw-v4-population-count-rev11_2010_2pt5_min.tif (*Gambar 2*)

4. Selanjutnya klik tombol Identify Features pada toolbar. Setelah itu klik titik mana pun pada kanvas (*Gambar 3*)

5. Nilai yang terkait dengan pixel akan ditampilkan di Identify Results. Pada Identify Results ubah mode menjadi Top Down. Ini akan menampilkan nilai semua pixel dari semua raster, bukan hany layer paling atas. Bandingkan nilai dari kedua layer. Karena resolusi raster kira-kira 5km x 5km, nilai pixel mewakili total populasi di area (25km persegi) yang diwakili oleh pixel (*Gambar 4*)

6. Tutup panel Identfy Results. Selanjutnya kita buat visualisasi layer yang lebih baik. Klik tombol Open the layer styling panel di panel Layers (*Gambar 5*)

7. Pada panel Layer Styling, klik dropdown Render type dan pilih Singleband pseudocolor renderer (*Gambar 6*)

8. Renderer ini akan memberi style pada layer menggunakan color ramp. Jalan warna default adalah putih merah dimana nilai minimum akan diberi warna putih dan nilai maksimum di lapisan akan diberi warna merah. Perluas pengaturan nilai min/max dan pilih opsi pemotongan jumlah kumulatif. Kita akan melihat bahwa visualisai peta jauh lebih baik sekarang. Rentang data standar diatur dari 2% hingga 98% dan nilai data yang berarti bahwa outlier tidak akan digunakan untuk menetapkan nilai minimum dan maksimum, sehingga menghasilkan visualisasi yang jauh lebih representatif (*Gambar 7*)

9. Tutup panel Layer Styling. Kita dapat menerapkan gaya yangs erupa pada layer lainnya. Klik kanan layer gpw-v4-population-count-rev11_2010_2pt5_min layer dan pilih Styles lalu Copy Style (*Gambar 8*)

10. Sekarang klik kanan layer gpw-v4-population-count-rev11_2000_2pt5_min yang tidak ditata dan pilih Styles lalu Paste Style (*Gambar 9*)

11. Parameter gaya yang sama akan diterapkan ke later lainnya. Fitur ini sangat berguna ketika kita ingin membandingkan lapisan yang berbeda menggunakan kategorisasi yang sama. Saat kita mengaktifkan visibilitas laer atas, kita dapat melihat perubahan populasi secara visual (*Gambar 10* *Gambar 11*)

12. Selanjutnya kita akan membuat peta tematik perubahan populasi. Kita hitung perbedaan antara 2 lapisan dan buat raster lain dimana setiap pixel mewakili perubahan populasi. Klik raster lalu pilih Raster Calculator... (*Gambar 12*)

13. Pada bagian Raster bands, kita bisa memilih layer dengan mengklik dua kali pada layer tersebut. Kalkulator rester dapat menerapkan operasi matematika pada pixel raster. Dalam hal ini kita ingin memasukkan rumus sederhana untuk mengurangkan populasi 2010 dari 2000. Masukkan ekspresi berikut "gpw-v4-population-count-rev11_2010_2pt5_min@1" - "gpw-v4-population-count-rev11_2000_2pt5_min@1", selanjutnya klik tombol disebelah Output layer. Masukkan population_change_2010_2000.tif sebagai file output. Klik OK untuk memulai perhitungan (*Gambar 13*)

14. Setelah selesai layer baru population_change_2010_2000 akan ditambahkan ke panel layers. Kita akan mengubah gayanya agar perubahan populasi negatif dan positif dapat divisualisasikan dengan lebih baik. Klik tombol Open the layer styling panel di panel layers (*Gambar 14*)

15. Kita menggunakan teknik penataan yang sama seperti sebelumnya dan memilih jalur warna yang berbeda. Klik drop-down Color ramp dan pilih spectral ramp. KLik drop-down lagi dan pilih Invert Color Ramp untuk menetapkan warna biru ke nilai rendah dan merah ke nilai tinggi (*Gambar 15*)

16. Visualisasinya bagus tetapi tidak mudah untuk ditafsirkan. Kita kan membuat peta yang lebih baik dengan 4 kategori Decline, Neutral, Growth, and High Growth. Scroll le bawah ke tabel dengan kelas. Tahan tombol Shift dan pilih semua baris, lalu klik tombol hapus baris yang dipilih (*Gambar 16*)

17. Ubah mode interpolasi ke Discrete. Kita akan membuat peta warna secara manual. klik tombol tambah nilai secara manual. Masukkan -100 sebagi nilai dan Decline sebagai label. Tetapkan warna biru untuk kategori ini. Cara kerja peta warna adalah semua nilai yang dimsukkan akan diberi warna entri tersebut. Kita akan melihat kanvas hanya akan menampilkan area dengan perubahan populasi negatif (*Gambar 17*)

18. Lengkapi peta warna dengan nilai yang sesuai. Disini kita bisa memilih 100, 1000, 100000 sebagai batas atas untuk kategori Neutral, Growth, dan High Growth. Tetapkan warna untuk setiap kategori yang dibuat (*Gambar 18*)

19. Setelah selesai mengatur warna, tutup panel layer styling. Kita sekarang memiliki peta tematik global tentang perubahan populasi (*Gambar 19*)



