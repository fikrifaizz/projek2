# Laporan Proyek Machine Learning - Fikri Faiz Zulfadhli
## Project Overview
Dalam beberapa tahun terakhir, pertumbuhan data digital yang sangat pesat telah membuat pengguna semakin sulit menemukan item yang relevan dari berbagai pilihan yang tersedia. Hal ini sangat terlihat dalam industri seperti e-commerce, layanan streaming, dan platform media sosial, di mana pengguna sering merasa kewalahan oleh banyaknya konten atau produk yang ditawarkan. Misalnya, platform seperti Netflix, Amazon, dan YouTube menawarkan ribuan hingga jutaan item, mulai dari film, serial TV, hingga produk yang tersedia untuk dibeli. Oleh karena itu, sistem rekomendasi telah menjadi alat penting dalam membantu pengguna menemukan konten yang relevan secara efisien dan personal [[1]](https://doi.org/10.1145/2843948 'Sistem Rekomendasi Netflix').

Sistem rekomendasi adalah algoritma yang dirancang untuk memberikan saran yang dipersonalisasi kepada pengguna berdasarkan data yang ada. Ada dua pendekatan utama dalam sistem rekomendasi yaitu Content-Based Filtering, yang menggunakan informasi fitur dari item (seperti genre film) untuk memberikan rekomendasi [[2]](https://doi.org/10.1007/978-0-387-85820-3_3 'Content-Based Filtering') dan Collaborative Filtering, yang menggunakan data interaksi pengguna lain untuk memberikan saran [[3]](https://doi.org/10.1007/978-3-540-72079-9_9 'Collaborative Filtering').

Proyek ini penting diselesaikan karena dapat memberikan pengalaman pengguna yang lebih baik dengan menyajikan rekomendasi yang dipersonalisasi, membantu mengurangi kebingungan dalam memilih dari banyaknya pilihan yang tersedia. Menurut Netflix, lebih dari 80% konten yang ditonton penggunanya didasarkan pada rekomendasi yang diberikan oleh sistem mereka, menunjukkan pentingnya rekomendasi yang tepat dalam meningkatkan keterlibatan pengguna [[1]](https://doi.org/10.1145/2843948 'The Netflix Recommender System'). Selain itu, penelitian menunjukkan bahwa sistem rekomendasi berperan penting dalam peningkatan konversi dan penjualan, seperti yang dilaporkan Amazon, di mana sistem rekomendasi mereka berkontribusi hingga 35% terhadap peningkatan penjualan [[4]](https://www.mckinsey.com 'How Retailers Can Keep Up With Consumers'). Dalam era big data, sistem rekomendasi juga memungkinkan perusahaan untuk memanfaatkan data pengguna dan item secara lebih efektif, mengubahnya menjadi wawasan yang dapat mendorong keputusan pengguna dengan lebih efisien [[5]](https://doi.org/10.1145/3285029 'Deep Learning Based Recommender System'). Proyek ini juga bertujuan mengatasi masalah seperti cold start problem, yang sering terjadi ketika menangani pengguna atau item baru yang belum memiliki cukup data historis [[3]](https://doi.org/10.1007/978-3-540-72079-9_9 'Collaborative Filtering Recommender Systems'). Dengan menggabungkan pendekatan content-based filtering dan collaborative filtering, diharapkan proyek ini dapat memberikan rekomendasi yang lebih akurat, bahkan untuk pengguna atau film baru dengan sedikit interaksi.

Recommendation system telah diterapkan pada beberapa permasalahan diantaranya *TF-IDF combined rank factor Naive Bayesian algorithm for intelligent language classification recommendation systems* [[6]](https://www.sciencedirect.com/science/article/pii/S2772941924000656 'TF-IDF combined rank factor Naive Bayesian algorithm for intelligent language classification recommendation systems'), *A decision-support productive resource recommendation system for enhanced construction project management* [[7]](https://www.sciencedirect.com/science/article/abs/pii/S1474034624004415 'A decision-support productive resource recommendation system for enhanced construction project management') dan *Link Prediction based on bipartite graph for recommendation system using optimized SVD++* [[8]](https://www.sciencedirect.com/science/article/pii/S187705092300114X 'Link Prediction based on bipartite graph for recommendation system using optimized SVD++').

Dari permasalahan dan latar belakang di atas, proyek ini akan membuat sebuah model machine learning berupa sistem rekomendasi untuk menentukan rekomendasi film yang terbaik kepada pengguna. Model ini nantinya dapat digunakan dan di-deploy untuk berbagai keperluan, misalnya diterapkan dalam katalog film pada platform streaming, daftar rekomendasi film di perpustakaan digital, media sosial berbasis konten video, ataupun pada e-commerce yang menjual konten film baik dalam format digital maupun fisik. Proyek ini menggabungkan pendekatan content-based filtering dan collaborative filtering untuk memberikan rekomendasi yang lebih akurat dan personal kepada pengguna berdasarkan preferensi dan interaksi mereka.

## Business Understanding

### Problem Statements

Berdasarkan latar belakang yang telah dijelaskan di atas, maka diperoleh rumusan masalah yang akan diselesaikan pada proyek ini, yaitu:
1. Bagaimana cara melakukan tahap persiapan data film, pengguna, dan rating atau penilaian agar dapat digunakan sebagai informasi untuk membuat model machine learning sistem rekomendasi?
2. Bagaimana cara membuat model machine learning untuk sistem rekomendasi film yang akurat dan relevan bagi pengguna?

### Goals

Berdasarkan rumusan masalah yang telah dipaparkan di atas, maka didapatkan tujuan dari proyek ini, yaitu:
1. Melakukan tahap persiapan data sehingga data siap digunakan pada model *machine learning* untuk sistem rekomendasi.
2. Membuat model *machine learning* untuk sistem rekomendasi film terbaik kepada pengguna.

### Solution Statements

Dalam proyek ini, dua pendekatan utama akan digunakan untuk mencapai tujuan dalam membangun sistem rekomendasi yang efektif: Content-Based Filtering dan Collaborative Filtering. Kedua pendekatan ini memiliki kelebihan masing-masing dan dapat saling melengkapi dalam menghasilkan rekomendasi yang relevan dan akurat bagi pengguna.

1. Content-Based Filtering

  - Content-Based Filtering adalah pendekatan yang memanfaatkan karakteristik atau fitur dari item itu sendiri untuk memberikan rekomendasi kepada pengguna. Dalam konteks rekomendasi film, fitur yang relevan bisa berupa genre, sinopsis, atau aktor yang terlibat dalam film. Sistem ini akan menganalisis preferensi pengguna berdasarkan film yang sudah mereka tonton dan memberikan rekomendasi film lain dengan fitur serupa.

 - Cara Kerja:

    - Ekstraksi Fitur: Sistem menganalisis deskripsi atau fitur yang dimiliki oleh setiap film (misalnya, genre atau sinopsis).
    - Kemiripan Item: Menggunakan teknik seperti TF-IDF (Term Frequency-Inverse Document Frequency) atau cosine similarity untuk menghitung kesamaan antara film yang sudah ditonton pengguna dengan film lain yang tersedia.
    - Rekomendasi: Berdasarkan hasil perhitungan kesamaan, sistem akan merekomendasikan film yang memiliki karakteristik serupa dengan film yang disukai pengguna.
    - Rumus yang Digunakan: Cosine Similarity
      - Untuk mengukur kemiripan antar item (film), sering digunakan cosine similarity, yang diukur berdasarkan vektor fitur dari dua item:

        $$S_c(A,B)=cos(\theta)= \frac{A \times B}{|A| |B|} = \frac{\sum^{n}{i=1} A_iB_i}{\sqrt{\sum^{n}{i=1} A^{2}{i} } \sqrt{\sum^{n}{i=1} B^{2}_{i}} }$$
2. Collaborative Filtering
  - Collaborative Filtering adalah pendekatan yang menggunakan data interaksi pengguna lain untuk memberikan rekomendasi. Sistem ini tidak hanya bergantung pada fitur item, tetapi juga mempelajari pola interaksi pengguna (misalnya, rating yang diberikan) dan menemukan pengguna lain yang memiliki pola serupa. Ada dua jenis collaborative filtering yang sering digunakan: User-Based Collaborative Filtering dan Item-Based Collaborative Filtering.
  - Cara Kerja:
      - User-Based Collaborative Filtering: Sistem mencari pengguna lain yang memiliki preferensi atau pola rating yang mirip dengan pengguna target. Jika dua pengguna memberikan rating serupa pada sejumlah film, maka film yang disukai oleh satu pengguna akan direkomendasikan kepada pengguna lainnya.
      - Item-Based Collaborative Filtering: Sistem mencari kemiripan antar item berdasarkan rating yang diberikan oleh berbagai pengguna. Jika dua film sering mendapat rating serupa dari pengguna yang berbeda, maka film yang mirip dengan film yang sudah disukai pengguna akan direkomendasikan.
  - Teknologi yang Digunakan: Singular Value Decomposition (SVD) : Singular Value Decomposition (SVD) adalah algoritma yang digunakan untuk memfaktorkan matriks pengguna-item dan menemukan pola laten di balik interaksi pengguna dan film. SVD digunakan untuk memprediksi rating yang belum ada (misalnya, pengguna belum menonton film tertentu).
  - Rumus yang Digunakan: SVD
    SVD memecah matriks rating 𝑅 menjadi tiga matriks 𝑈, $$Σ$$, dan $$𝑉^𝑇$$ :

    $$R \approx U \Sigma V^T$$

## Data Understanding

[<img src="https://github.com/user-attachments/assets/b7f9ca5b-0aac-45ec-8935-7272ec39f1c2" alt="Movielens Kaggle Dataset" title="Movielens Kaggle Dataset" width="100%">](https://www.kaggle.com/datasets/ayushimishra2809/movielens-dataset/data)

Data yang digunakan dalam proyek ini adalah *dataset* yang diambil dari Kaggle Dataset. Di bawah ini adalah informasi detail tentang *dataset* yang digunakan.

|                         | Keterangan                                                                                                                                                                         |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Sumber                  | [Kaggle Dataset: Movielens Dataset](https://www.kaggle.com/datasets/ayushimishra2809/movielens-dataset/data 'Movielens dataset') |
| *Usability*             | 6.47                                                                                                                                                                              |
| Lisensi                 | Unknown                                                                      |
| Jenis dan Ukuran Berkas | zip (2.99 MB)                                                                                                                                                                        |
| Kategori                | Arts and Entertainment, Earth and Nature, Computer Science, Recommender Systems                                                      |

Dalam dataset tersebut berisi dua (2) berkas CSV ([Comma-separated Values](https://en.wikipedia.org/wiki/Comma-separated_values 'Wikipedia - Comma-separated values')), yaitu `movies.csv`, `ratings.csv`.

- **movies.csv**, memiliki atribut atau fitur sebagai berikut,

  <img src="https://github.com/user-attachments/assets/849757b9-25d0-4c12-9894-cc33c79502d5" alt="Deskripsi Variabel Movies" title="Deskripsi Variabel Movies">

  - `movieID` : ID unik untuk setiap film dalam dataset
  - `title` : Nama atau judul film yang bersangkutan
  - `genres` : Kategori film

  Untuk data movies total ada 3 kolom dan 10329 baris.
  
- **ratings.csv**, memiliki atribut atau fitur sebagai berikut,

  <img src="https://github.com/user-attachments/assets/cc65a168-b900-4d02-bdad-2d07d4ffa460" alt="Deskripsi Variabel Ratings" title="Deskripsi Variabel Ratings">

  - `userID` :  ID unik untuk setiap pengguna yang memberikan rating terhadap film
  - `rating` : Nilai yang diberikan oleh pengguna terhadap film
  - `timestamp` : Menunjukkan kapan pengguna memberikan rating terhadap film
  - `movieID` : ID unik untuk setiap film dalam dataset

Deskripsi statistik untuk *dataset* `ratings` pada fitur `rating` dapat dilihat pada gambar di bawah ini.

<img src="https://github.com/user-attachments/assets/ae094fea-8777-48ee-b004-85c96483118a" alt="Deskripsi Statistik Ratings" title="Deskripsi Statistik Ratings">

Dari gambar di atas dapat dilihat bahwa terdapat,
- Total jumlah data (`count`) sebanyak 7.000;
- Rata-rata *rating* (`mean`) 3;
- Simpangan baku/standar deviasi *rating* (`std`) 1;
- *Rating* Minimal (`min`) 0 ;kuartil bawah/Q1 *rating* (`25%`), kuartil tengah/Q2/median *rating* (`50%`) 0;
- Kuartil bawah/Q1 *rating* (`25%`) 3;
- Kuartil tengah/Q2/median dan Kuartil atas/Q3 *rating* (`75%`) 4;
- *Rating* maksimum (`max`) 5

Berikut adalah Visualisasi grafik frekuensi sebaran data rating pengguna terhadap movies yang sudah pernah ditonton, mulai dari rating 1 hingga rating 5.

<img src="https://github.com/user-attachments/assets/911b8d1e-3af3-4103-9cdc-18bdca32caf4" alt="Grafik Histogram Frekuensi Sebaran Data Rating" title="Grafik Histogram Frekuensi Sebaran Data Rating" width="100%">

Secara keseluruhan, distribusi rating ini menunjukkan kecenderungan positif dari pengguna, di mana film-film yang ditonton umumnya dinilai baik (rating 3 dan ke atas), dengan sebagian besar pengguna memberikan rating 4. Pengguna cenderung memberikan rating rendah hanya pada sedikit film.

## Data Preprocessing dan Data Preparation

Tahap pra-pemrosesan data atau data preprocessing merupakan tahap yang perlu diterapkan sebelum melakukan proses pemodelan. Tahap ini adalah teknik yang digunakan untuk mengubah data mentah (raw data) menjadi data yang bersih (clean data) yang siap untuk digunakan pada proses selanjutnya. Dalam kasus ini, tahap data preprocessing dilakukan penggabungkan data movies dan ratings berdasarkan kolom movieID.

  - **Penggabungan Data**  
  Penggabungan dataset movies dan ratings berdasarkan kolom movieId, menggunakan fungsi merge() di Pandas. Penggabungan ini akan menggabungkan kedua dataset berdasarkan movieId.
  <img src="https://github.com/user-attachments/assets/f95393b9-5ae7-45a7-b2cb-89dd77a4004b" alt="Penggabungan Data" title="Penggabungan Data">

  - **Pengecekan *Missing Value***
  
    Proses pengecekan missing value pada dataframe dapat dilakukan dengan menggunakan fungsi .isnull().sum(), sehingga diperoleh total jumlah data yang kosong atau hilang (missing).

    <img src="https://github.com/user-attachments/assets/fd203d48-5d40-4d76-b00f-fc528805a9fe" alt="Missing Value" title="Missing Value">  

    Pada dataframe gather ternyata tidak ditemukan adanya nilai null/kosong di setiap atribut/kolom.

  - **Pengecekan Data Duplikat**

    <img src="https://github.com/user-attachments/assets/b02ad4ae-bb92-4800-9d36-8391a0037959" alt="Missing Value" title="Duplikat">
  
    Melakukan pengecekan data yang duplikat atau data yang sama pada dataframe dapat dilakukan dengan menggunakan fungsi .duplicated().sum() dan hasilnya tidak ada duplikat.

  - **Penerapan TF-IDF**

    Proses TF-IDF Vectorizer diterapkan pada kolom genres dari dataset movies.csv untuk menghasilkan representasi numerik dari genre film. Ini digunakan sebagai langkah penting dalam content-based filtering.

  - ***Splitting Data***

    Data rating dibagi menjadi train dan test set dengan rasio 75% untuk training dan 25% untuk testing. Ini penting untuk evaluasi model collaborative filtering.

    ```python
    trainset, testset = train_test_split(data, test_size=0.25) 
    ```

## Modeling

Tahap selanjutnya adalah proses modeling atau membuat model machine learning yang dapat digunakan sebagai sistem rekomendasi untuk menentukan rekomendasi buku yang terbaik kepada pengguna dengan beberapa algoritma sistem rekomendasi tertentu.

Dalam kasus ini data yang akan digunakan untuk proses pemodelan machine learning data akan dibatasi hanya 10.000 baris data movies dan 7000 baris data rating.

```python
books   = books[:10000]
ratings = ratings[:7000]
```

1. **Content-based Recommendation**
    - TF-IDF Vectorizer

      TF-IDF Vectorizer akan mentransformasikan teks menjadi representasi angka yang memiliki makna tertentu dalam bentuk matriks. Ukuran matriks yang diperoleh adalah sebesar 10 data genres dan 21 data genres yang sudah dipisah.

      <img src="https://github.com/user-attachments/assets/4f7f7b62-d09d-4855-ac23-329f51733c6b" alt="Tabel Hasil TF-IDF Vectorizer" title="Tabel Hasil TF-IDF Vectorizer">

    - *Cosine Similarity*

      Cosine Similarity akan melakukan perhitungan derajat kesamaan (similarity degree) antar judul buku. Ukuran matriks yang diperoleh adalah sebesar 10.000 data film dan 10.000 data film juga.

     <img src="https://github.com/user-attachments/assets/d97e55d7-3d83-4227-b7af-b6053956f5fe" alt="Tabel Hasil Cosine Similirity" title="Tabel Hasil Cosine Similirity">

    - Hasil *Top-N Recommendation*

     Hasil pengujian sistem rekomendasi dengan pendekatan *content-based recommendation* adalah sebagai berikut.
     
     <img src="https://github.com/user-attachments/assets/d4763eb4-74cd-4374-8ff7-04f54d559427" alt="Content Based Pilih Film" title="Content Based Pilih Film">

     Dapat dilihat bahwa sistem yang telah dibangun berhasil memberikan rekomendasi beberapa judul film berdasarkan input atau masukan sebuah judul film, yaitu "Toy Story (1995)", dan diperoleh beberapa judul film yang berdasarkan perhitungan sistem.

2. **Collaborative Filtering Recommendation**
   - Data Preparation

     Mengatur rentang skala rating dengan skala 0.5 hingga 5 yang akan digunakan untuk mengonfigurasi rentang skala rating dari dataset yang akan digunakan untuk melatih model rekomendasi. Ini diperlukan untuk memastikan bahwa model mengenali batas atas dan bawah dari rating yang diberikan oleh pengguna pada item (misalnya, film).

     ```python
     reader = Reader(rating_scale=(0.5, 5))
     # Membuat dataset Surprise dari dataframe ratings
     data = Dataset.load_from_df(ratings[['userId', 'movieId', 'rating']], reader)
     ```

  - ***Model Development and Training***

    Singular Value Decomposition (SVD): Digunakan untuk memfaktorkan matriks pengguna-item menjadi matriks laten.

    Parameter SVD:
    - Latent Factors: 50 (default).
    - Learning Rate: 0.005.
    - Regularization: 0.02.

    ```python
    svd_model = SVD()
    svd_model.fit(trainset)
    # Membuat prediksi pada testset
    predictions = svd_model.test(testset)
    # Menghitung akurasi model menggunakan RMSE
    accuracy.rmse(predictions)
    ```

    Dan didapatkan RMSE nya sebesar 1.0351.

    <img src="https://github.com/user-attachments/assets/9de4a545-8ed3-4ae4-90cd-540a6d537448" alt="Collaborative Filtering Recommendation" title="Collaborative Filtering Recommendation">

    Berdasarkan hasil di atas, dapat dilihat bahwa sistem akan mengambil pengguna secara acak, yaitu pengguna dengan userID 1. Dapat dilihat terdapat 10 daftar buku yang direkomendasikan oleh sistem.

## Evaluation

1. **Content-based Recommendation**

   - Precision: Menghitung seberapa banyak film yang direkomendasikan sesuai dengan preferensi pengguna. Evaluasi ini dapat dilakukan dengan memeriksa persentase rekomendasi yang cocok dengan film yang sudah disukai pengguna.
   - Hasil: Precision untuk model content-based filtering adalah 0.80 (80%)

2. **Collaborative Filtering**

   - RMSE (Root Mean Square Error): Digunakan untuk mengukur seberapa jauh prediksi model terhadap rating asli pengguna. Hasil RMSE pada collaborative filtering adalah 1.0351.
    
## Kesimpulan

Dalam content-based filtering, kita membuat representasi fitur dari setiap item menggunakan teknik seperti TF-IDF atau CountVectorizer. Kemudian, kita menghitung kesamaan antara item yang disukai pengguna dengan item lain menggunakan cosine similarity. Item yang paling mirip dengan yang sudah disukai pengguna akan direkomendasikan. Dalam collaborative filtering, kita menggunakan algoritma seperti SVD (Singular Value Decomposition) untuk memfaktorkan matriks pengguna-item dan menemukan pola laten di balik preferensi pengguna. Ini memungkinkan kita untuk memprediksi rating yang belum diketahui dan memberikan rekomendasi film yang mungkin disukai pengguna.
      
## Referensi
[1] Gomez-Uribe, C. A., & Hunt, N. (2015). The Netflix Recommender System: Algorithms, Business Value, and Innovation. ACM Transactions on Management Information Systems (TMIS), 6(4), 1-19. DOI: https://doi.org/10.1145/2843948

[2] Lops, P., De Gemmis, M., & Semeraro, G. (2011). Content-based Recommender Systems: State of the Art and Trends. Recommender Systems Handbook, 73-105. DOI: https://doi.org/10.1007/978-0-387-85820-3_3

[3] Schafer, J. B., Frankowski, D., Herlocker, J., & Sen, S. (2007). Collaborative Filtering Recommender Systems. Lecture Notes in Computer Science, 291-324. DOI: https://doi.org/10.1007/978-3-540-72079-9_9

[4] McKinsey & Company. (2020). How Retailers Can Keep Up With Consumers. [Online]. Available: https://www.mckinsey.com

[5] Zhang, S., Yao, L., Sun, A., & Tay, Y. (2019). Deep Learning Based Recommender System: A Survey and New Perspectives. ACM Computing Surveys (CSUR), 52(1), 1-38. DOI: https://doi.org/10.1145/3285029

[6] TF-IDF combined rank factor Naive Bayesian algorithm for intelligent language classification recommendation systems. Systems and Soft Computing, 2024. DOI: https://doi.org/10.1016/j.sasc.2024.200136

[7] A decision-support productive resource recommendation system for enhanced construction project management. Advanced Engineering Informatics, 2024. DOI: https://doi.org/10.1016/j.aei.2024.102793

[8] Link Prediction based on bipartite graph for recommendation system using optimized SVD++. Procedia Computer Science, 2023. DOI: https://doi.org/10.1016/j.procs.2023.01.114
