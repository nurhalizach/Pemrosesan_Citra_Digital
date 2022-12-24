
# TUGAS KELOMPOK 5

- Egyn Terescova Nadia
- Nurhaliza
- Risma Wulandari

## FILTER




## Low Pass Filtering

<p align = "justify">Low-pass filtering adalah proses filter yang melewatkan komponen citra dengan nilai intensitas yang rendah dan meredam komponen citra dengan nilai intensitas yang tinggi.<br>
LPF (Low Pass Filter) atau disebut juga smoothing filter merupakan salah satu metode untuk menghilangkan noise acak, noise berkala, dan menampilkan pola latar belakang. <br>
Fungsi dasar dari low-pass filter yang ideal adalah untuk memperkirakan rata-rata sebuah piksel dan semua piksel tetangga dan akhirnya mengganti nilai asli dari piksel tersebut. <br>
Low pass filter diterapkan untuk menghasilkan citra yang lebih halus dan lebih blur. </p>

<p align = "justify">Aturan kernel untuk low-pass filter adalah:<br>
1. Semua koefisien kernel harus positif.<br>
2. Jumlah semua koefisien kernel harus sama dengan 1.<br>

Contoh kernel yang dapat digunakan pada <b>low-pass filtering</b> adalah</p>

![low-pass](gambar/low-pass.png)


<h3>Dibawah ini merupakan code untuk Low Pass Filtering menggunakan fungsi conv2 yang ada pada Octave:</h3>

``` Octave
pkg load image;

% membaca citra awal
image = imread('smurf.jpg');
img = rgb2gray(image);

% membuat beberapa matriks kernel
LPF1 = [1/16 1/8 1/16: 1/8 1/4 1/8: 1/16 1/8 1/16];
LPF2 = [1/10 1/10 1/ 10: 1/10 1/5 1/10];
LPF3 = [1 1 1: 1 1 1: 1 1 1]/9;

% konvolusi dengan fungsi conv2
result1 = uint8(conv2(double(img), LPF1, 'same'));
result2 = uint8(conv2(double(img), LPF2, 'same'));
result3 = uint8(conv2(double(img), LPF3, 'same'));

% menampilkan citra
figure(1);
subplot(2,2,1); imshow(img); title("Citra Asli");
subplot(2,2,2); imshow(result1); title("Hasil Low Pass Filtering 1");
subplot(2,2,3); imshow(result2); title("Hasil Low Pass Filtering 2");
subplot(2,2,4); imshow(result3); title("Hasil Low Pass Filtering");
```

<h3>Berikut hasil citra yang diperoleh:</h3>

![output-1](gambar/LPF.PNG)

<h3>Dibawah ini merupakan code untuk Low Pass Filtering menggunakan metode manual:</h3>

``` Octave
% membaca citra awal
asli = imread('smurf.jpg');
img = rgb2gray(asli);

% membuat matriks kernel
LPF = [1 1 1; 1 1 1; 1 1 1]/9;

% mengcopy citra image ke img
imgxLPF = img;

% melakukan konvolusi dan mendapatkan ukuran matriks citra
[bf, kf] = size(img);
[bg, kg] = size(LPF);

m2 = floor(bg/2);
n2 = floor(kg/2);

% penambahan elemen nol
pad = zeros(bf+2, kf+2);
pad (2:bf+1, 2:kf+1) = img;
[b_pad, k_pad] = size(pad);

for i = m2+1 : b_pad-m2;
  for j = n2+1 : k_pad-n2;
    temp = 0;
    for k = -m2 : m2;
      for l = -n2 : n2;
        temp = temp + LPF(k+m2+1, l+n2+1) * pad(i-k, j-l);
      end
    end
      imgxLPF(i,j) = temp;
  end
end

imgxLPF = uint8(imgxLPF(2:bf-1, 2:kf-1));

% menampilkan citra
figure(1);
subplot(1,2,1); imshow(img); title("Citra Asli");
subplot(1,2,2); imshow(imgxLPF); title("Hasil Low Pass Filtering");
```

<h3>Berikut hasil citra yang diperoleh:</h3>

![output-2](gambar/LPF-2.PNG)


## High Pass Filtering

<p align = "justify">High Pass Filter (HPF) adalah proses filter yang mengambil citra dengan gradiasi intensitas yang tinggi dan perbedaan intensitas yang rendah akan dikurangi atau dibuang. High Pass Filtering adalah salah satu dari metode penajaman (sharpening).<br>
Tujuan utama dari proses penajaman ini adalah untuk menyoroti detail-detail halus dalam gambar atau untuk meningkatkan detail yang telah dikaburkan baik dalam kesalahan atau efek alami dari proses akuisisi citra tertentu.</p>

<p align = "justify">Aturan kernel untuk high-pass filter adalah:<br>
1. Koefisien penapis boleh negatif, nol, ataupun bernillai positif.<br>
2. Total keseluruhan koefisiennya ialah bernilai 0 ataupun 1.<br>
3. Apabila jumlah koefisiennya berjumlah = 0, maka setiap elemen yang rendah frekuensinya nilainya akan menurun. <br>
4. Namun, apabila total dari koefisien adalah = 1, maka elemen yang memiliki frekuensi rendah nilainya tetap sama dengan nilai semula.</p>

![high-pass](gambar/high-pass.png)

### Implementasi High Pass Filtering menggunakan Octave
<p align = "justify">

   1. Kode Program Manual <br>
       ![hpf](gambar/hpf.png)<br>
       ![hpf](gambar/hpf2.png)<br>
       ![hpf](gambar/hpf3.png)<br>

       <h3>Output Kode Program</h3>
       
       ![manual1](gambar/manual1.png)<br>
       ![manual2](gambar/manual2.png)<br>
       ![manual3](gambar/manual3.png)

<br>

   2. Kode Program yang Tersedia di Octave<br>
       ![hpf_kode](gambar/hpf_kode.png)<br>

       <h3>Output Kode Program</h3>

      - Kernel 1<br>
       ![kernel1](gambar/kernel1.png)<br>

      - Kernel 2<br>
       ![kernel2](gambar/kernel2.png)<br>

      - Kernel 3<br>
       ![kernel3](gambar/kernel3.png)<br>

      - Kernel 4<br>
       ![kernel4](gambar/kernel4.png)<br>

      - Kernel 5<br>
       ![kernel5](gambar/kernel5.png)<br>

      - Kernel 6<br>
       ![kernel1](gambar/kernel6.png)


## High Boost Filtering

<p align = "justify">High-Boost Filtering merupakan salah satu bagian dari operasi yang dapat dilakukan untuk melakukan perbaikan citra.<br>
High-Boost Filtering bertujuan untuk menekankan komponen frekuensi tinggi yang mewakili detail gambar tanpa menghilangkan komponen frekuensi rendah (seperti sharpening). Filter high boost dapat digunakan untuk mengubah komponen frekuensi tinggi.<br>
High boost filter disusun oleh semua pass filter dan edge detection filter (Laplacian filter). Dengan demikian,  High boost filtering menekankan  edge dan menghasilkan image sharpener.</p>

<p align = "justify">cara menghitung:<br>
Highboost = a Original – Lowpass

       = (a – 1) Original + Original – Lowpass

       = (a – 1) Original + Highpass

Jika a = 1, kita mendapatkan unsharp masking.<br>
Jika a >1, bagian citra original ditambahkan kembali ke citra hasil high pass filter. Highboost = (a – 1) Original + Highpass<br>

ilustrasi dari High Boost Filtering<br>

![high-boost](gambar/high-boost.png)

</p>


## Median Filtering

<p align = "justify">Median Filtering adalah salah satu teknik filter yang mengurutkan nilai intensitas sekelompok pixel, kemudian mengganti nilai pixel yang diproses dengan nilai mediannya (nilai tengahnya).<br>
Metode ini digunakan dalam penghalusan citra (image smoothing) atau menghilangkan derau noise. Filter ini merupakan suatu filter non linear yang dikembangkan oleh Tukey.
</p>

<p align = "justify">Algoritma dari Median Filtering<br>

- Memasukkan dan membaca image / gambar untuk dapat diproses
- Penentuan mask filter tersebut. Bisa 3x3 atau 5x5
- Mengurutkan nilai pixel dari nilai pixel terkecil ke terbesar
- Tentukan mediannya
- Mengubah nilai tengah pixel dengan nilai median yang telah ditemukan
- Proses diatas berulang hingga ke piksel terakhir citra
- Menampilkan gambar berupa perbandingan sebelum dan sesudah di filter</p>

<h3>Dibawah ini merupakan code untuk Median Filtering menggunakan fungsi yang ada pada Octave:</h3>

``` Octave
pkg load image;
clear;
clc;

# Membaca Citra Awal
image = imread('smurf.jpg');
img = rgb2gray(image);

% Memberi noise (derau) pada citra
noisy = imnoise(img, 'salt & pepper', 0.2);

% Mengaplikasikan median fillter
output = medfilt2(noisy);
output2 = medfilt2(img);

% Menampilkan citra
subplot(2,3,1); imshow(img), title("Citra Awal");
subplot(2,3,2); imshow(noisy), title("Citra yang Diberi Noise");
subplot(2,3,3); imshow(output), title("Citra noise yang diberi Media Filter");
subplot(2,3,4); imshow(img), title("Citra Awal");
subplot(2,3,5); imshow(output2), title("Citra awal yang diberi Media filter");
```

<h3>Berikut hasil citra yang diperoleh:</h3>

![output-1](gambar/median-2.PNG)

<h3>Dibawah ini merupakan code untuk Median Filtering menggunakan metode manual:</h3>

``` Octave
pkg load image;
clear;
clc;

# Membaca Citra Awal
image = imread('smurf.jpg');
img = rgb2gray(image);

% Memberi noise (derau) pada citra
noisy = imnoise(img, 'salt & pepper', 0.2);

% Mendapatkan ukuran matriks citra
[img_height, img_width] = size(noisy);

# buat sebuah wadah baru untuk citra
new_img = zeros(img_height, img_width);

% Mengonversikan ukuran matriks tadi kedalam 8 bitand
new_img = uint8(new_img);

for i = 1:img_height
  for j = 1:img_width
    % Memberikan batasan agar mask filter tidak melebihi dimensi citra
    xmin = max(1, i-1);
    xmax = min(img_height, i+1);
    ymin = max(1, j-1);
    ymax = min(img_width, j+1);

    % Mask filter akan menjadi
    temp = noisy(xmin:xmax, ymin:ymax);
    new_img(i,j) = median(temp(:));
  end
end

% Menampilkan citra
subplot(1,3,1); imshow(img), title("Citra Awal");
subplot(1,3,2); imshow(noisy), title("Citra yang Diberi Noise");
subplot(1,3,3); imshow(new_img), title("Citra noise yang diberi Media Filter");
```

<h3>Berikut hasil citra yang diperoleh:</h3>

![output-2](gambar/median.PNG)

## Edge Detection

1. Edge Detection Sobel

<p align = "justify"> Metode atau operator Sobel merupakan operator yang menghindari adanya perhitungan gradient di titik interpolasi. Operator Sobel menggunakan kernel ukuran 3x3 piksel untuk perhitungan gradientnya, dengan pembobotan yang lebih besar pada piksel-piksel yang dekat dengan titik pusat. Kelebihan dari metode sobel ini adalah kemampuan untuk mengurangi noise sebelum melakukan perhitungan deteksi tepi.<br>

Kernel filter yang digunakan dalam metode Sobel ini adalah:<br>

![kernel sobel](gambar/kernelSobel.PNG)<br>
</p>

<p align = "justify">Algoritma Edge Detection Sobel<br>

- Memasukkan dan membaca image / gambar untuk dapat diproses
- Mengkonversikan image RGB warna asli ke citra skala kelabu
- Mengubah citra menjadi dua kali lipat
- Pra-alokasikan matriks baru seukuran citra asli dengan nol
- Masukkan matriks kernel sobel
- Proses Deteksi Tepi dengan memperkirakan gradien komputasi dan besarnya vektor
- Mendefinisikan treshold gambar yang di filter
- Menampilkan citra hasil deteksi tepi

</p>

#### Implementasi Edge Detection Sobel menggunakan Octave
<p align = "justify">

   1. Kode Program Manual <br>
       ![Sobel](gambar/sobelManual1.PNG)<br>
       ![Sobel](gambar/sobelManual2.PNG)<br>

       <h3>Output Kode Program</h3>
       
       ![Output](gambar/sobelManual3.PNG)<br>
       ![Output](gambar/sobelManual4.PNG)<br>
       ![Output](gambar/sobelManual5.PNG)<br>

<br>

   2. Kode Program yang Tersedia di Octave<br>
       ![Sobel](gambar/sobelFungsi1.PNG)<br>

       <h3>Output Kode Program</h3>

       ![Sobel](gambar/sobelFungsi2.PNG)<br>

</p>

2. Edge Detection Prewitt

<p align = "justify"> Metode Prewitt merupakan pengembangan metode robert dengan menggunakan filter HPF yang diberi satu angka nol penyangga. Metode ini mengambil prinsip dari fungsi laplacian yang dikenal sebagai fungsi untuk membangkitkan HPF. Persamaan gradien pada operator prewitt sama dengan gradien pada operator sobel perbedaannya adalah pada prewitt menggunakan konstanta c = 1.<br>

Kernel filter yang digunakan dalam metode Prewitt ini adalah:<br>

![kernel Prewitt](gambar/kernelPrewitt.PNG)<br>
</p>

<p align = "justify">Algoritma Edge Detection Prewitt<br>

- Memasukkan dan membaca image / gambar untuk dapat diproses
- Mengkonversikan image RGB warna asli ke citra skala kelabu
- Mengubah citra menjadi dua kali lipat
- Pra-alokasikan matriks baru seukuran citra asli dengan nol
- Masukkan matriks kernel Prewitt
- Proses Deteksi Tepi dengan memperkirakan gradien komputasi dan besarnya vektor
- Mendefinisikan treshold gambar yang di filter
- Menampilkan citra hasil deteksi tepi

</p>

#### Implementasi Edge Detection Prewitt menggunakan Octave
<p align = "justify">

   1. Kode Program Manual <br>
       ![Prewitt](gambar/prewittManual1.PNG)<br>
       ![Prewitt](gambar/prewittManual2.PNG)<br>

       <h3>Output Kode Program</h3>
       
       ![Output](gambar/prewittManual3.PNG)<br>
       ![Output](gambar/prewittManual4.PNG)<br>
       ![Output](gambar/prewittManual5.PNG)<br>

<br>

   2. Kode Program yang Tersedia di Octave<br>
       ![Prewitt](gambar/prewittFungsi1.PNG)<br>

       <h3>Output Kode Program</h3>

       ![Prewitt](gambar/prewittFungsi2.PNG)<br>

</p>
