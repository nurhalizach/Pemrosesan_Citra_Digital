<style>
    p{
        text-align: justify;
</style>

Nama : Nurhaliza

NIM: 2110131120007

Mata Kuliah : Pemrosesan Citra Digital

---

### ALGORITMA UNTUK PATTERNING, DITHERING, HISTOGRAM EQUALIZATION DAN BIT PLANE SLICING

#### 1. Algoritma Patterning
<p>
Algortima:
1. Buat matriks kosong dengan panjang kolom dan baris dari matriks citra asli yaitu (baris x 3) x (kolom x 3) 
2. Menentukan pola matriks untuk setiap gray level, untuk hitam bernilai 0 dan putih bernilai 255

        gray_level_0 = [0,0,0;0,0,0;0,0,0];
        gray_level_1 = [0,0,0;0,0,0;0,0,255];
        gray_level_2= [255,0,0;0,0,0;0,0,255];
        gray_level_3 = [255,0,255;0,0,0;0,0,255];
        gray_level_4 = [255,0,255;0,0,0;255,0,255];
        gray_level_5= [255,0,255;0,0,0;255,255,255];
        gray_level_6 = [255,0,255;255,0,0;255,255,255];
        gray_level_7 = [255,255,255;255,0,0;255,255,255];
        gray_level_8 = [255,255,255;255,0,255;255,255,255];
        gray_level_9 = [255,255,255;255,255,255;255,255,255];

3. buat perbandingan untuk setiap gray level

untuk setiap nilai matriks indeks [i]:

- jika nilai matriks >=0 dan <=25, maka matriks kosong dari indeks baris [i,i] sampai [i+2,i+2] dan kolom [i,i] sampai [i+2,i+2] untuk matriks 3x3 di isi dengan matriks gray_level_0
- jika nilai matriks >=26 dan <=51, maka matriks kosong dari indeks baris [i,i] sampai [i+2,i+2] dan kolom [i,i] sampai [i+2,i+2] untuk matriks 3x3 di isi dengan matriks gray_level_1
- jika nilai matriks >=52 dan <=77, maka matriks kosong dari indeks baris [i,i] sampai [i+2,i+2] dan kolom [i,i] sampai [i+2,i+2] untuk matriks 3x3 di isi dengan matriks gray_level_2
- jika nilai matriks >=78 dan <=103, maka matriks kosong dari indeks baris [i,i] sampai [i+2,i+2] dan kolom [i,i] sampai [i+2,i+2] untuk matriks 3x3 di isi dengan matriks gray_level_3
- jika nilai matriks >=104 dan <=129, maka matriks kosong dari indeks baris [i,i] sampai [i+2,i+2] dan kolom [i,i] sampai [i+2,i+2] untuk matriks 3x3 di isi dengan matriks gray_level_4
- jika nilai matriks >=130 dan <=155, maka matriks kosong dari indeks baris [i,i] sampai [i+2,i+2] dan kolom [i,i] sampai [i+2,i+2] untuk matriks 3x3 di isi dengan matriks gray_level_5
- jika nilai matriks >=156 dan <=181, maka matriks kosong dari indeks baris [i,i] sampai [i+2,i+2] dan kolom [i,i] sampai [i+2,i+2] untuk matriks 3x3 di isi dengan matriks gray_level_6
- jika nilai matriks >=182 dan <=207, maka matriks kosong dari indeks baris [i,i] sampai [i+2,i+2] dan kolom [i,i] sampai [i+2,i+2] untuk matriks 3x3 di isi dengan matriks gray_level_7
- jika nilai matriks >=208 dan <=233, maka matriks kosong dari indeks baris [i,i] sampai [i+2,i+2] dan kolom [i,i] sampai [i+2,i+2] untuk matriks 3x3 di isi dengan matriks gray_level_8
- jika nilai matriks >=234 dan <=256, maka matriks kosong dari indeks baris [i,i] sampai [i+2,i+2] dan kolom [i,i] sampai [i+2,i+2] untuk matriks 3x3 di isi dengan matriks gray_level_9

#### 2. Algoritma Dithering

1. Simpan nilai matriks Dithering
2. Buat matriks kosong dengan ukuran yang sama dengan matriks citra asli
3. Membandingkan nilai matriks Dithering. Misal, ukuran dithering 2x2 dan ukuran matriks citra 4x4

untuk setiap bagian matriks 2x2 atau pada matriks [i,i],[i,i+1],[i+1,i],[i+1,i+!]:

- Jika nilai matriks < matriks dithering, maka matriks bernilai 0 atau hitam
- Jika nilai matriks > matriks dithering, maka matriks bernilai 255 atau putih

#### 3. Algortima Histogram Equalization

1. hitung seluruh nilai histogram; dengan masing masing jumlah histogram dari nilai histogram di jumlahkan dengan nilai histogram sebelumnya
2. normalisasi jumlah histogram dengan membagikannya dengan jumlah seluruh nilai histogram(jumlah pixel)
3. kalikan hasil normalisasi histogram dengan banyaknya maximum gray level
4. untuk setiap hasil, tentukan jumlah masing masing gray level dengan menjumlahkan number of pixel dengan gray level yang sama

#### 4. Algoritma Bit Plane Slicing

1. Ubah setiap angka dalam matriks sebagai bilangan biner
2. Simpan masing masing nilai angka biner
3. untuk 1 angka di masing masing urutan, masukkan ke dalam bentuk matriks sehingga akan terdapat 8 buah matriks
4. matriks di kanal pertama adalah least significant bit
5. matrisk di kanal terakhir adalah most significant bit

</p>