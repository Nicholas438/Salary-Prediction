# Salary Prediction Model

**Disusun oleh: Nicholas**

Proyek ini dilakukan sebagai penyelesaian tugas proyek pertama Dicoding - Applied Machine Learning. Proyek ini bertujuan untuk menciptakan sebuah model untuk memprediksi gaji dari pegawai dengan atribut tertentu.

# Domain Proyek

**Latar Belakang**

Penghidupan yang layak merupakan salah satu syarat untuk hidup yang makmur dengan tingginya persentase masyarakat Indonesia yang menganggap bahwa status finansial yang mumpuni merupakan hal yang kurang dalam hidup mereka. Namun, banyak orang yang merasa kesulitan untuk melakukan negosiasi gaji yang cocok dengan rekruiter yang sesuai dengan skillset, experience dan kontribusi mereka ke perusahaan.
<br><br>
Ukuran gaji seseorang biasanya bergantung pada beberapa faktor antara lain skillset, posisi dan experience yang dimiliki. Namun, sulit untuk ditentukan secara pasti gaji yang sesuai dengan kriteria tersebut secara manual. Hal ini berdampak pada tidak sesuainya gaji yang diterima oleh pekerja yang dapat merugikan perusahaan dan pegawai baik karena kurangnya motivasi maupun dana yang terlalu banyak dikeluarkan untuk biaya sumber daya manusia. Oleh karena itu, diperlukanlah suatu sistem terstruktur untuk memprediksi kompensasi yang sesuai untuk seorang pekerja dengan atribut tertentu.
<br><br>
Penelitian ini dilakukan untuk menciptakan suatu model machine learning yang bertujuan untuk memprediksi gaji pegawai dengan data yang ada. Diharapkan model ini dapat memprediksi dengan sesuai dan memberikan acuan bagi perusahaan maupun pekerja untuk melakukan negosiasi gaji untuk meningkatkan retensi pegawai dan melakukan hiring sumber daya manusia dengan lebih efisien.

# Business Understanding

Model ini dibuat untuk skenario sebagai berikut:<br>
1. Pegawai yang ingin apply ke perusahaan tertentu<br>
2. Pegawai yang ingin meminta promosi atau kenaikan gaji.<br>
3. Perusahaan yang ingin mempekerjakan seorang pegawai tertentu.<br>

### Problem Statement

1. Atribut apa yang paling berpengaruh terhadap gaji seorang pegawai?
2. Bagaimana cara melakukan preprocessing data yang dapat dicerna lebih baik oleh model?
3. Berapa gaji yang sesuai untuk seorang pekerja dengan karakteristik tertentu?

### Goals

1. Mengetahui atribut yang paling berpengaruh pada gaji seorang pegawai.
2. Melakukan persiapan data untuk dapat dilatih oleh model.
3. Membuat model machine learning yang dapat memprediksi gaji seorang pegawai dengan akurasi yang tinggi.

### Solution Statement

1. Menganalisis data dengan melakukan univariate analysis, multivariate analysis dan visualisasi.
2. Melakukan preprocessing data data agar bisa digunakan dalam membangun model.
3. Melakukan hyperparameter tuning menggunakan grid search dan membangun model regresi yang dapat memprediksi bilangan kontinu. ALgoritma yang dipakai dalam proyek ini adalah K-Nearest Neighbour, Random Forest, dan AdaBoost.

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
![image](https://github.com/Nicholas438/Salary-Prediction/assets/69570302/7a11a22a-4271-4c13-8137-fdc343f95e17)
![image](https://github.com/Nicholas438/Salary-Prediction/assets/69570302/076506fd-7fd1-4c56-a756-2f344bbe2f0f)

Dapat terlihat bahwa Data Kategorikal memiliki sebaran data yang cukup merata. Setiap atribut pada kategori memiliki jumlah yang relatif seimbang tanpa memiliki perbedaan yang signifikan.

#### Visualisasi Data Numerik
![image](https://github.com/Nicholas438/Salary-Prediction/assets/69570302/f5f0bd89-2b5c-4c95-a376-9f1482a05925)
![image](https://github.com/Nicholas438/Salary-Prediction/assets/69570302/4c3d0d8b-55a3-415c-9b43-a7ffecb88751)<br>
Data Numerik juga memiliki kasus yang serupa dengan data kategorikal

### Outlier Identification
Akan dilakukan visualisasi dengan boxplot untuk mengidentifikasi outlier pada data pada data numerik sebagai berikut <br>
![image](https://github.com/Nicholas438/Salary-Prediction/assets/69570302/2f1d3d20-afd9-4d02-9d9c-e0236ed2caef)
![image](https://github.com/Nicholas438/Salary-Prediction/assets/69570302/a270db52-b5f7-45de-a7cc-dd07f00d5ab4)
![image](https://github.com/Nicholas438/Salary-Prediction/assets/69570302/d9d9320a-449b-4c4d-bd64-2e4a2a87d6f0)<br>
Boxplot menunjukkan data dan ambang batas data untuk memasuki kategori data non-outlier. Segitiga yang ada di tengah boxplot berfungsi sebagai penanda mean dari data dan bulatan di luar kotak boxplot menunjukkan outlier yang ada pada data.<br>
Pada data dapat dilihat bahwa salary memiliki tepat satu outlier yang akan dikeluarkan untuk memberikan data yang lebih mudah dicerna oleh sistem model machine learning


### Multivariate Analysis

#### Visualisasi data salary terhadap data kategorikal
![image](https://github.com/Nicholas438/Salary-Prediction/assets/69570302/a3c82088-c5ad-4432-a5be-93e4db78f593)
![image](https://github.com/Nicholas438/Salary-Prediction/assets/69570302/53cc0148-e0f1-4cb1-88c2-923e956ed3e8)

#### Visualisasi Salary terhadap data numerik
![image](https://github.com/Nicholas438/Salary-Prediction/assets/69570302/cebcab9d-e7df-423f-887c-627f18b0c913)

#### Korelasi Salary terhadap Data Numerik
![image](https://github.com/Nicholas438/Salary-Prediction/assets/69570302/1ed5ba32-964d-4659-8a83-76f8cad7d2e3)



## Data preparation

+ One Hot Encoding

  One hot encoding adalah teknik mengubah data kategorik menjadi data numerik dimana setiap kategori menjadi kolom baru dengan nilai 0 atau 1. 
  
+ Train Test Split

  Train test split aja proses membagi data menjadi data latih dan data uji. Data latih akan digunakan untuk membangun model, sedangkan data uji akan digunakan untuk menguji performa model. Pada proyek ini dataset sebesar 1000 dibagi menjadi 899 untuk data latih dan 100 untuk data uji.
  
+ Normalization

  Algoritma machine learning akan memiliki performa lebih baik dan bekerja lebih cepat jika dimodelkan dengan data seragam yang memiliki skala relatif sama. Teknik normalisasi yang digunakan pada proyek ini adalah Standarisasi dengan sklearn.preprocessing.StandardScaler.

## Modeling

+ Algoritma
  Penelitian ini melakukan pemodelan dengan 4 algoritma, yaitu Linear Regression, K-Nearest Neighbour, Random Forest, dan Adaboost

  + Linear Regression
     Linear Regression adalah teknik regresi yang menggunakan teknik regresi linear pada matematika. Regresi ini memodelkan grafik yang terdiri atas berbagai titik menjadi satu garis lurus dengan melakukan training data ke dalam model tersebut. Teknik ini tidak menggunakan parameter apapun.
    
  + K-Nearest Neighbour
    K-Nearest Neighbour bekerja dengan membandingkan jarak satu sampel ke sampel pelatihan lain dengan memilih sejumlah k tetangga terdekat. Parameter yang digunakan pada teknik ini adalah :
    + `n_neighbors` = Jumlah k tetangga tedekat.

  + Random Forest
    Algoritma random forest adalah teknik dalam machine learning dengan metode ensemble. Teknik Random Forest merupakan kumpulan decision tree untuk melakukan prediksi. Parameter yang digunakan pada teknik ini adalah :
    + `n_estimators` = Jumlah maksimum estimator di mana boosting dihentikan.
    + `max_depth` = Kedalaman maksimum setiap tree.
    + `random_state` = Mengontrol seed acak yang diberikan pada setiap base_estimator pada setiap iterasi boosting.

  + Adaboost
    AdaBoost juga disebut Adaptive Boosting adalah teknik dalam machine learning dengan metode ensemble.  Algoritma ini bertujuan untuk meningkatkan performa atau akurasi prediksi dengan cara menggabungkan beberapa model sederhana dan dianggap lemah (weak learners) secara berurutan sehingga membentuk suatu model yang kuat (strong ensemble learner). Parameter yang digunakan pada teknik ini adalah :
    + `n_estimators` = Jumlah maksimum estimator di mana boosting dihentikan.
    + `learning_rate` = Learning rate memperkuat kontribusi setiap regressor.
    + `random_state` = Mengontrol seed acak yang diberikan pada setiap base_estimator pada setiap iterasi boosting.

+ Hyperparameter Tuning (Grid Search)
  Hyperparameter tuning adalah cara untuk mendapatkan parameter terbaik dari algoritma dalam membangun model. Salah satu teknik dalam hyperparameter tuning yang digunakan dalam proyek ini adalah grid search. Berikut adalah hasil dari Grid Search pada proyek ini :
  | model    | best_params                                                     |
  |----------|-----------------------------------------------------------------|
  | Linear   | {}                                                              |
  | knn      | {'n_neighbors': 4}                                              |
  | boosting | {'learning_rate': 0.1, 'n_estimators': 100, 'random_state': 88} |
  | rf       | {'max_depth': 8, 'n_estimators': 100, 'random_stste': 88}        |

## Evaluation

Metrik evaluasi yang digunakan pada proyek ini adalah akurasi dan mean squared error (MSE). Akurasi menentukan tingkat kemiripan antara hasil prediksi dengan nilai yang sebenarnya (y_test). Mean squared error (MSE) mengukur error dalam model statistik dengan cara menghitung rata-rata error dari kuadrat hasil aktual dikurang hasil prediksi. Berikut formulan MSE :
<div><img src="https://user-images.githubusercontent.com/107544829/188412654-f5dc0ae1-901b-470e-aae5-1f6b5fb68b4d.png" width="300"/></div>

Berikut hasil evaluasi pada proyek ini :

+ Akurasi
  | model    | accuracy |
  |----------|----------|
  | linear   | 0.89110  |         
  | knn      | 0.84907  |
  | boosting | 0.83218  |
  | rf       | 0.87927  |

+ Mean Squared Error (MSE)<br>
  ![image](https://github.com/Nicholas438/Salary-Prediction/assets/69570302/d849db19-505c-44c3-8f7d-3d51ed627dac)

Dari hasil evaluasi dapat dilihat bahwa model dengan algoritma Linear Regression memiliki akurasi lebih tinggi tinggi dan tingkat error lebih kecil pada testing dari model lainnya pada proyek ini.
