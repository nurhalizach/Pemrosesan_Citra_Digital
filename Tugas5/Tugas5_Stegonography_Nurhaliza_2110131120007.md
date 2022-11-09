<style>
    p{
        text-align: justify;
    }
    .image{
        text-align: center;
        padding-bottom: 100px;
    }
    .img{
        text-align:center;
    }
</style>

Nama : Nurhaliza

NIM: 2110131120007

Mata Kuliah : Pemrosesan Citra Digital

---

### STEGONOGRAPHY

1. PENGERTIAN

Steganografi atau Steganography adalah sebuah ilmu, teknik atau seni menyembunyikan sebuah pesan rahasia dengan suatu cara sehingga pesan tersebut hanya akan diketahui oleh si pengirim dan si penerima pesan rahasia tersebut. Steganografi berasal dari Bahasa Yunani yaitu Stegano yang berarti “tersembunyi atau menyembunyikan” dan graphy yang berarti “Tulisan, jadi Steganografi adalah tulisan atau pesan yang disembunyikan. Dalam steganografi beberapa istilah umum yang umum digunakan yaitu cover-image yang menggambarkan citra yang ditunjuk untuk membawa bit tertanam, stego-image mengacu pada gambar dengan data tertanam, steganalisi atau serangan mengacu pada pengolahan gambar dan pendekatan analisis statistic yang bertujuan untuk memecah atau menyerang algoritma steganografi (Cheddad, 2010).


Secara teknis teknik steganografi memanfaatkan kelemahan dari kesadaran manusia. Indra manusia yang terbatas tidak dilatih untuk mencari file yang tersembuyi didalam suatu wadah. Dalam metode ini diperlukan file sebagai penampung (cover) dan file lain yang akan ditampung (message). File penampung maupun file yang akan ditampung dapat berupa citra, audio, maupun text. Dibandingkan dengan media yang lainnya, media gambar paling banyak digunakan karena mudahnya mendapatkan media gambar dan keuntungan dari terbatasnya sistem pengelihatan manusia.

Steganografi kebalikannya kriptografi yang menyamarkan arti dari sebuah pesan rahasia saja, tetapi tidak menyembunyikan bahwa ada sebuah pesan. Kelebihan Steganografi dibandingkan dengan Kriptografi adalah pesan-pesannya akan dibuat tidak menarik perhatian dan tidak menimbulkan kecurigaan, berbeda dengan Kriptografi yang pesannya tidak disembunyikan, walaupun pesannya sulit untuk di pecahkan akan tetapi itu akan menimbulkan kecurigaan pesan tersebut.

2. CARA KERJA

Untuk menyisipkan data yang ingin disembunyikan membutuhkan dua unsur. Unsur pertama ialah media penampung seperti citra, suara, video dan sebagainya yang terlihat tidak mencurigakan untuk menyimpan pesan rahasia. Unsur kedua adalah pesan yang ingin disembunyikan yaitu media penampungnya berupa citra yang disebut cover-object dan citra yang telah disisipi pesan disebut stego-object.

Secara umum, terdapat dua proses didalam steganografi yaitu proses embedding untuk menyisipkan pesan kedalam cover-object dan proses decoding untuk ekstraksi pesan dari stego-object. Kedua proses ini mungkin memerlukan kunci rahasia yang dinamakan stego-key agar hanya pihak yang berhak saja yang dapat melakukan penyisipan dan ekstraksi pesan.

3. JENIS JENIS TEKNIK STEGANOGRAFI

- Injection,,merupakan suatu teknik menanamkan pesan rahasia secara langsung ke suatu media. Salah satu masalah dari teknik ini adalah ukuran media yang diinjeksi menjadi lebih besar dari ukuran normalnya sehingga mudah dideteksi. Teknik ini sering juga disebut embedding.

- Substitusi,, data normal digantikan dengan data rahasia. Biasanya hasil teknik ini tidak terlalu mengubah ukuran data asli, tetapi tergantung pada file media dan data yang akan disembunyikan. Teknik substitusi bisa menurunkan kualitas median yang ditumpangi.

- Tramsformasi Domain, teknik ini sangat efektif. Pada dasarnya, transformasi domain menyembunyikan data pada transformspace.

- SpreadSpectrum,,merupakan teknik pentransmisi menggunakan pseudo-noise code, yang independen terhadap data informasi sebagai modulator bentuk gelombang untuk menyebarkan energi sinyal dalam sebuah jalur komunikasi “bandwith” yang lebih besar dari pada sinyal jalur komunikasi informasi. Oleh penerima, sinyal dikumpulkan kembali menggunakan replika pseudo-noise code tersinkronisasi.

- Statistical Method,, teknik ini disebut juga skema steganographic 1 bit, skema tersebut menanamkan satu bit informasi pada media tumpangan dan mengubah statistik walaupun hanya 1 bity. Perubahan statistik ditunjukkan dengan indikasi 1 dan jika tidak ada perubahan, terlihat indikasi 0. Sistem ini bekerja berdasarkan kemampuan penerima dalam membedakan antara informasi yang dimodifikasi dan yang belum.

- Distortion. metode ini menciptakan perubahan atas benda yang ditumpangi oleh data rahasia.

- Cover Generation, metode ini lebih unik dari pada metode lainnya karena cover object dipilih untuk menyembunyikan pesan.

4. KRITERIA DAN ASPEK DALAM STEGANOGRAFI

Penyembunyian data rahasia ke dalam media digital mengubah kualitas media tersebut, kriteria yang harus diperhatikan dalam penyembunyian data diantaranya adalah:

- Fidelity, mutu citra penampung tidak jauh berubah, setelah penambahan data rahasia, citra hasil steganografi masih terlihat dengan baik. Pengamat tidak mengetahui kalau didalam citra tersebut terdapat data rahasia.

- Robustness, data yang disembunyikan harus tahan terhadap manipulasi yang dilakukan pada citra penampung “seperti” pengubahan kontras, penajaman, penempatan, penambahan noise, perbesaran gambar, pemotongan “cropping”, enkripsi dan sebagainya” bila pada citra dilakukan operasi pengolahan citra maka data yang disembunyikan tidak rusak.

- Recovery, data yang disembunyikan harus dapat diungkapkan kembali “recovery” karena tujuan steganografi adalah data hiding maka sewaktu-waktu data rahasia di dalam citra penampung harus dapat diambil kembali untuk digunakan lebih lanjut.