# Salary Prediction Model


**Disusun oleh: Nicholas**

Proyek ini dilakukan sebagai penyelesaian tugas proyek pertama Dicoding - Applied Machine Learning. Proyek ini bertujuan untuk menciptakan sebuah model untuk memprediksi gaji dari pegawai dengan atribut tertentu.

# Domain Proyek

**Latar Belakang**

Penghidupan yang layak merupakan salah satu syarat untuk hidup yang makmur dengan tingginya persentase masyarakat Indonesia yang menganggap bahwa status finansial yang mumpuni merupakan hal yang kurang dalam hidup mereka. Namun, banyak orang yang merasa kesulitan untuk melakukan negosiasi gaji yang cocok dengan rekruiter yang sesuai dengan skillset, experience dan kontribusi mereka ke perusahaan.
<br><br>
Ukuran gaji seseorang biasanya bergantung pada beberapa faktor antara lain skillset, posisi dan experience yang dimiliki. Namun, sulit untuk ditentukan secara pasti gaji yang sesuai dengan kriteria tersebut secara manual. Hal ini berdampak pada tidak sesuainya gaji yang diterima oleh pekerja yang dapat merugikan perusahaan dan pegawai baik karena kurangnya motivasi dan retensi/loyalty pegawai untuk bekerja dalam perusahaan maupun dana yang terlalu banyak dikeluarkan untuk biaya sumber daya manusia. Oleh karena itu, diperlukanlah suatu sistem terstruktur untuk memprediksi kompensasi yang sesuai untuk seorang pekerja dengan atribut tertentu.
<br><br>
Model prediksi gaji memiliki dampak penting dalam konteks ekonomi dan manajemen sumber daya manusia. Secara ekonomi, model ini dapat membantu perusahaan dalam pengambilan keputusan strategis terkait alokasi sumber daya, termasuk anggaran tenaga kerja dan struktur kompensasi. Dengan memiliki perkiraan yang akurat tentang gaji, perusahaan dapat mengoptimalkan pengeluaran mereka dan memastikan kompetitivitas di pasar tenaga kerja.
<br><br>
Dari segi manajemen sumber daya manusia, model prediksi gaji dapat membantu dalam proses rekrutmen, penempatan, dan retensi karyawan. Perusahaan dapat menggunakan model ini untuk menentukan penawaran gaji yang sesuai dengan nilai pasar dan profil karyawan yang diinginkan. Selain itu, model ini juga dapat membantu dalam identifikasi risiko turnover dan pengembangan strategi retensi karyawan.
<br><br>
Penelitian ini dilakukan untuk menciptakan suatu model machine learning yang bertujuan untuk memprediksi gaji pegawai dengan data yang ada. Diharapkan model ini dapat memprediksi dengan sesuai dan memberikan acuan bagi professional hiring perusahaan maupun pencari pekerjaan untuk melakukan negosiasi gaji untuk meningkatkan retensi pegawai dan melakukan hiring sumber daya manusia dengan lebih efisien. Model ini juga diharapkan dapat memajukan ekonomi bangsa  dengan cara memberikan guideline bagi perusahaan untuk memanajemen sumber daya manusia mereka dan memberikan motivasi bagi masyarakat untuk terus belajar dan menggapai skillset baru.
<br><br>
Hasil proyek ini diharapkan dapat diterapkan secara aplikatif melalui integrasi model prediksi gaji ke dalam sistem HR perusahaan. Hal ini akan memungkinkan pengguna, seperti manajer sumber daya manusia atau profesional hiring, untuk dengan mudah mengakses dan menggunakan perkiraan gaji saat membuat keputusan terkait kompensasi karyawan. Selain itu, hasil proyek ini juga dpaat diaplikasikan ke dalam web platform misal website seperti Glassdoor yang memungkinkan pencari kerja untuk memiliki base pay dalam benak mereka sebelum melakukan interview.

# Business Understanding

Model ini dibuat untuk skenario sebagai berikut:<br>
1. Pegawai yang ingin apply ke perusahaan tertentu untuk mendapatkan gaji yang lebih tinggi daripada posisi lamanya<br>
2. Pegawai yang ingin meminta promosi atau kenaikan gaji.<br>
3. Perusahaan yang ingin mempekerjakan seorang pegawai tertentu dan ingin menghemat biaya operasional atau ingin mendapatkan karyawan yang kompeten.<br>
4. Evaluasi kesejahteraan karyawan oleh perusahaan untuk memastikan retensi karyawan yang tinggi. <br>

### Problem Statement

1. Atribut apa yang paling berpengaruh terhadap gaji seorang pegawai?
2. Berapa gaji yang sesuai untuk seorang pekerja dengan karakteristik tertentu? 
3. Bagaimana cara melakukan alokasi dana yang terstruktur untuk gaji pegawai secara mudah dan terotomatisir?

### Goals

1. Mengetahui atribut yang paling berpengaruh pada gaji seorang pegawai.
2. Melakukan analisa dan pengolahan data untuk mendapatkan insight dan memberikan data yang lebih mudah dicerna oleh machine learning.
3. Menciptakan model machine learning dengan akurasi minimal 87% untuk memprediksi gaji yang sesuai untuk seorang pekerja dengan skillset tertentu.

### Solution Statement

1. Menganalisis data dengan melakukan univariate analysis, multivariate analysis dan visualisasi.
2. Melakukan preprocessing data data agar bisa digunakan dalam membangun model.
3. Melakukan hyperparameter tuning menggunakan grid search dan membangun model regresi yang dapat memprediksi bilangan kontinu. ALgoritma yang dipakai dalam proyek ini adalah Linear Regression, K-Nearest Neighbour, Random Forest, dan AdaBoost.
4. Melakukan evaluasi model machine learning dengan Mean Squared Error

## Data Understanding 

Dataset yang digunakan dalam proyek ini merupakan data salary prediction data dari Kaggle. https://www.kaggle.com/datasets/mrsimple07/salary-prediction-data.

Berikut informasi pada dataset :

+ Dataset memiliki format CSV (Comma-Seperated Values).
+ Dataset memiliki 1000 sample dengan 7 fitur.
+ Dataset memiliki 1 fitur bertipe float64, 2 fitur bertipe int64 dan 4 fitur bertipe object.
+ Tidak ada missing value dalam dataset.

### Variable - variable pada dataset

+ Education: Tingkat pendidikan pegawai.
+ Experience: Jumlah tahun pengalaman bekerja dari pegawai
+ Location: Lokasi kantor dan tempat data diambil.
+ Job_title: Posisi dari karyawan dalam perusahaan
+ Age: Usia karyawan
+ Gender: Jenis Kelamin pegawai.
+ Salary: Gaji pegawai yang akan dijadikan target pada model ini

### Visualisasi Data Univariate Analysis

#### Visualisasi Data Kategorikal
<div><img src='https://github.com/Nicholas438/Salary-Prediction/assets/69570302/7a11a22a-4271-4c13-8137-fdc343f95e17'></div>
<div><img src = 'https://github.com/Nicholas438/Salary-Prediction/assets/69570302/076506fd-7fd1-4c56-a756-2f344bbe2f0f'/></div>
Gambar 1. Visualisasi Data Kategorikal <br><br>

Dapat terlihat bahwa Data Kategorikal memiliki sebaran data yang cukup merata. Setiap atribut pada kategori memiliki jumlah yang relatif seimbang tanpa memiliki perbedaan yang signifikan dan dapat diberi ke model machine learning secara langsung. Beberapa insight dalam data kategorikal:
 + Mayoritas data diambil dari lulusan SMA, dilanjutkan oleh S1, S3 dan S2.
 + Rural dan Suburban memiliki jumlah data yang lebih banyak daripada data yang diambil pada lokasi urban.
 + Director dan Analyst memiliki jumlah data terbanyak diikuti oleh manager dan engineer.
 + Data diambil lebih banyak dari laki-laki daripada perempuan.

#### Visualisasi Data Numerik
<div><img src='https://github.com/Nicholas438/Salary-Prediction/assets/69570302/f5f0bd89-2b5c-4c95-a376-9f1482a05925'/></div>
<div><img src='https://github.com/Nicholas438/Salary-Prediction/assets/69570302/4c3d0d8b-55a3-415c-9b43-a7ffecb88751'/></div><br>
Gambar 2. Visualisasi Data Numerik <br><br>
Data Numerik juga memiliki persebaran data yang cukup merata dan target data yang ingin diprediksi yaitu salary memiliki bentuk data yang berbentuk menyerupai bell curve sehingga dapat diberikan ke model machine learning.
Beberapa insight yang dapat diambil dalam visualisasi data numerik:<br>

 + Data diambil dari rentang usia 20-60 dan experience 0-30.
 + Data salary memiliki rentang antara 40000 - 180000 dengan data yang menyerupai sebuah bell curve.
 + Data didominasi oleh pekerja yang berusia 20-25.


### Outlier Identification
Akan dilakukan visualisasi dengan boxplot untuk mengidentifikasi outlier pada data pada data numerik sebagai berikut <br>
<div><img src='https://github.com/Nicholas438/Salary-Prediction/assets/69570302/2f1d3d20-afd9-4d02-9d9c-e0236ed2caef'/></div>
<div><img src='https://github.com/Nicholas438/Salary-Prediction/assets/69570302/a270db52-b5f7-45de-a7cc-dd07f00d5ab4'/></div>
<div><img src='https://github.com/Nicholas438/Salary-Prediction/assets/69570302/d9d9320a-449b-4c4d-bd64-2e4a2a87d6f0'/></div><br>
Gambar 3. Visualisasi Data Outlier <br><br>
Boxplot menunjukkan data dan ambang batas data untuk memasuki kategori data non-outlier. Segitiga yang ada di tengah boxplot berfungsi sebagai penanda mean dari data dan bulatan di luar kotak boxplot menunjukkan outlier yang ada pada data.<br>
Pada data dapat dilihat bahwa salary memiliki tepat satu outlier yang akan dikeluarkan untuk memberikan data yang lebih mudah dicerna oleh sistem model machine learning.<br>
Outlier ini akan disingkirkan dengan metode IQR yang menyisakan 999 data pada dataset.<br>


### Multivariate Analysis

#### Visualisasi data salary terhadap data kategorikal
<div><img src ='https://github.com/Nicholas438/Salary-Prediction/assets/69570302/a3c82088-c5ad-4432-a5be-93e4db78f593'/></div>
<div><img src ='https://github.com/Nicholas438/Salary-Prediction/assets/69570302/53cc0148-e0f1-4cb1-88c2-923e956ed3e8'/></div>
Gambar 4. Visualisasi Data Salary terhadap data kategorikal <br><br>

Dapat terlihat bahwa lokasi, tingkat pendidikan dan posisi pekerjaan menentukan besarnya gaji yang didapatkan dengan posisi atau pendidikan yang lebih tinggi dan lokasi yang lebih ramai (urban) cenderung emmberikan penghasilan yang lebih tinggi juga kepada pegawainya.
<br> Jenis Kelamin juga sedikit mempengaruhi dengan pegawai laki-laki yang berpenghasilan sedikit lebih banyak daripada perempuan.<br>
Beberapa insight lain yang dapat ditemukan:

 + Tingkat pendidikan memiliki pengaru yang paling besar pada salary yang didapatkan.
 + Director memiliki rata-rata salary tertinggi dilanjutkan dengan manager, engineer dan terakhir analyst.
 + Gender memiliki pengaruh paling sedikit terhadap salary yang didapatkan dengan perbedaan yang cukup negligible


#### Visualisasi Salary terhadap data numerik
<div><img src='https://github.com/Nicholas438/Salary-Prediction/assets/69570302/cebcab9d-e7df-423f-887c-627f18b0c913'/></div>
Gambar 5. Visualisasi Salary terhadap data numerik <br><br>



#### Korelasi Salary terhadap Data Numerik
<div><img src = 'https://github.com/Nicholas438/Salary-Prediction/assets/69570302/1ed5ba32-964d-4659-8a83-76f8cad7d2e3'/></div>
Gambar 6. Visualisasi Korelasi data numerik <br><br>


Data numerik memiliki grafik yang tidak menunjukkan garis yang dapat terlihat secara langsung pada visualisasi sehingga tidak dapat disimpulkan secara langsung korelasi yang jelas. <br>
Data Numerik memiliki korelasi yang cukup rendah dengan Salary, terutama pada data usia, namun jika digabungkan dengan atribut data lain, maka bisa saja kedua data ini berpengaruh terutama jika digabungkan dengan data posisi pekerjaan dan tingkat pendidikan.

## Data preparation

Data diubah agar mudah diproses oleh model machine learning dengan teknik-teknik sebagai berikut:
+ Outlier Handling
  Outlier yang diidentifikasikan pada visualisasi data dengan boxplot akan diubah pada data dengan metode IQR. IQR bekerja dengan cara mengidentifikasi setiap kuartil dan mendefinisikan IQR yaitu kuartil ketiga dikurangi dengan kuartil pertama.Lalu outlier yang bertempat pada Q1 - 1.5 IQR dan Q3 + 1.5 IQR akan dibuang dari data. Oulier handling akan memberikan model machine learning data yang tidak terpengaruh oleh noise yang berlebihan.
  
+ One Hot Encoding

  One hot encoding adalah teknik mengubah data kategorik menjadi data numerik dimana setiap kategori menjadi kolom baru dengan nilai 0 atau 1. Hal ini memudahkan machine learning untuk memproses data karena berbentuk binary/integer dan tidak bersifat deskriptif yang sulit untuk diproses model machine learning. One Hot Encoding akan dilakukan pada semua data kategorikal yaitu Job_Title, Education, Location dan Gender dengan setiap atribut yang hanya memiliki maksimal 4 kelompok data. 
  
+ Train Test Split

  Train test split aja proses membagi data menjadi data latih dan data uji. Data latih akan digunakan untuk membangun model, sedangkan data uji akan digunakan untuk menguji performa model. Pada proyek ini dataset sebesar 1000 dibagi menjadi 899 untuk data latih dan 100 untuk data uji. Pemilihan angka ini dilakukan untuk memberikan training data yang masih cukup banyak dan testing data yang cukup untuk melakukan pengujian model.
  
+ Normalization

  Algoritma machine learning akan memiliki performa lebih baik dan bekerja lebih cepat jika dimodelkan dengan data seragam yang memiliki skala relatif sama. Teknik normalisasi yang digunakan pada proyek ini adalah Standarisasi dengan sklearn.preprocessing.StandardScaler. Normalisasi dilakukan untuk menempatkan data numerik ke dalam lingkup range data yang mudah diproses oleh machine learning yang awalnya mungkin bisa bersifat puluhan sampai jutaan.

## Modeling

+ Algoritma
  Penelitian ini melakukan pemodelan dengan 4 algoritma, yaitu Linear Regression, K-Nearest Neighbour, Random Forest, dan Adaboost

  + Linear Regression
     Linear Regression adalah teknik regresi yang menggunakan teknik regresi linear pada matematika. Regresi ini memodelkan grafik yang terdiri atas berbagai titik menjadi satu garis lurus dengan melakukan training data ke dalam model tersebut. Teknik ini tidak menggunakan parameter apapun.<br>
    Kelebihan:
    + Mudah diimplementasi
    + Efisien
    <br>
    Kekurangan:
    + Sensitif terhadap outlier
    + Kompleksitas terbatas
    
  + K-Nearest Neighbour
    K-Nearest Neighbour bekerja dengan membandingkan jarak satu sampel ke sampel pelatihan lain dengan memilih sejumlah k tetangga terdekat. Parameter yang digunakan pada teknik ini adalah :
    + `n_neighbors` = Jumlah k tetangga tedekat.
    Kelebihan:
    + Mudah diimplementasi
    + Adaptibilitas dengan data
    + Tidak sensitif terhadap outlier
    <br>
    Kekurangan:
    + Kompleks secara komputasional
    + Memerlukan memori tinggi

  + Random Forest
    Algoritma random forest adalah teknik dalam machine learning dengan metode ensemble. Teknik Random Forest merupakan kumpulan decision tree untuk melakukan prediksi. Parameter yang digunakan pada teknik ini adalah :
    + `n_estimators` = Jumlah maksimum estimator di mana boosting dihentikan.
    + `max_depth` = Kedalaman maksimum setiap tree.
    + `random_state` = Mengontrol seed acak yang diberikan pada setiap base_estimator pada setiap iterasi boosting.
    Kelebihan:
    + Memiliki akurasi yang secara konsisten tinggi
    + Memiliki handling noise
    <br>
    Kekurangan:
    + Kompleks secara komputasional dan secara pemahaman
    + Memiliki hyperparameter tuning yang memakan waktu

  + Adaboost
    AdaBoost juga disebut Adaptive Boosting adalah teknik dalam machine learning dengan metode ensemble.  Algoritma ini bertujuan untuk meningkatkan performa atau akurasi prediksi dengan cara menggabungkan beberapa model sederhana dan dianggap lemah (weak learners) secara berurutan sehingga membentuk suatu model yang kuat (strong ensemble learner). Parameter yang digunakan pada teknik ini adalah :
    + `n_estimators` = Jumlah maksimum estimator di mana boosting dihentikan.
    + `learning_rate` = Learning rate memperkuat kontribusi setiap regressor.
    + `random_state` = Mengontrol seed acak yang diberikan pada setiap base_estimator pada setiap iterasi boosting.
    Kelebihan:
    + Versatile
    + Tidak sensitif terhadap data imbalance
    <br>
    Kekurangan:
    + Sensitif terhadap noise
    + Computationally intensive

+ Hyperparameter Tuning (Grid Search)
  Hyperparameter tuning denagn Grid Search adalah cara untuk mendapatkan parameter terbaik dari algoritma dalam membangun model. Salah satu teknik dalam hyperparameter tuning yang digunakan dalam proyek ini adalah grid search. Grid search berfungsi untuk mencocokan setiap hyperparameter yang disediakan dan memilih parameter yang memberikan hasil terbaik. Berikut adalah hasil dari Grid Search pada proyek ini :
  | model    | best_params                                                     |
  |----------|-----------------------------------------------------------------|
  | Linear   | {}                                                              |
  | knn      | {'n_neighbors': 4}                                              |
  | boosting | {'learning_rate': 0.1, 'n_estimators': 100, 'random_state': 88} |
  | rf       | {'max_depth': 8, 'n_estimators': 100, 'random_stste': 88}       |
  
Tabel 1. Best parameters setiap model

## Evaluation

Metrik evaluasi yang digunakan pada proyek ini adalah akurasi dan mean squared error (MSE). Akurasi menentukan tingkat kemiripan antara hasil prediksi dengan nilai yang sebenarnya (y_test). MSE merupakan ukuran dari rata-rata kuadrat perbedaan antara nilai aktual dan nilai prediksi. Dalam konteks prediksi gaji, MSE mengukur seberapa dekat perkiraan gaji model dengan gaji sebenarnya dalam dataset. MSE yang rendah menunjukkan bahwa model memiliki presisi yang tinggi dalam memperkirakan gaji, yang dapat diinterpretasikan sebagai tingkat ketepatan prediksi. Berikut formulan MSE :
$$MSE = {1 \over n} * \sum_{i=1}^n (y_i - ŷ_i)^2 $$


Berikut hasil evaluasi pada proyek ini :

+ Akurasi
  | model    | accuracy |
  |----------|----------|
  | linear   | 0.89110  |         
  | knn      | 0.84907  |
  | boosting | 0.83218  |
  | rf       | 0.87927  |
Tabel 2. Akurasi setiap model

+ Mean Squared Error (MSE)<br>
<div><img src = 'https://github.com/Nicholas438/Salary-Prediction/assets/69570302/d849db19-505c-44c3-8f7d-3d51ed627dac'/></div>
Gambar 7. Visualisasi MSE setiap algoritma <br><br>

Dari hasil evaluasi dan goals yang sudah ditentukan di awal yaitu 87%, dapat dilihat bahwa model dengan algoritma Linear Regression dan Random Forest memiliki akurasi lebih tinggi dan Mean Squared Error lebih kecil pada testing dari model lainnya pada proyek ini, dilanjutkan dengan KNN dan terakhir Adaboost dengan MSE terbesar. Sehingga dapat dipilih Linear Regression ataupun Random Forest untuk membantu perusahaan atau pegawai untuk memprediksi gaji yang pantas berdasarkan skillset atau atribut yang mereka miliki.

+ Prediksi
  <br>
  Berikut beberapa prediksi dari keempat model yang telah dibuat
  <div><img src = 'https://github.com/Nicholas438/Salary-Prediction/assets/69570302/eb6d3881-8692-4cc5-ad36-bff7943f746f'></div>
  Gambar 8. Prediksi setiap algoritma terhadap beberapa data <br><br>

