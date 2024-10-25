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

## Referensi
[1] Gomez-Uribe, C. A., & Hunt, N. (2015). The Netflix Recommender System: Algorithms, Business Value, and Innovation. ACM Transactions on Management Information Systems (TMIS), 6(4), 1-19. DOI: https://doi.org/10.1145/2843948

[2] Lops, P., De Gemmis, M., & Semeraro, G. (2011). Content-based Recommender Systems: State of the Art and Trends. Recommender Systems Handbook, 73-105. DOI: https://doi.org/10.1007/978-0-387-85820-3_3

[3] Schafer, J. B., Frankowski, D., Herlocker, J., & Sen, S. (2007). Collaborative Filtering Recommender Systems. Lecture Notes in Computer Science, 291-324. DOI: https://doi.org/10.1007/978-3-540-72079-9_9

[4] McKinsey & Company. (2020). How Retailers Can Keep Up With Consumers. [Online]. Available: https://www.mckinsey.com

[5] Zhang, S., Yao, L., Sun, A., & Tay, Y. (2019). Deep Learning Based Recommender System: A Survey and New Perspectives. ACM Computing Surveys (CSUR), 52(1), 1-38. DOI: https://doi.org/10.1145/3285029

[6] TF-IDF combined rank factor Naive Bayesian algorithm for intelligent language classification recommendation systems. Systems and Soft Computing, 2024. DOI: https://doi.org/10.1016/j.sasc.2024.200136

[7] A decision-support productive resource recommendation system for enhanced construction project management. Advanced Engineering Informatics, 2024. DOI: https://doi.org/10.1016/j.aei.2024.102793

[8] Link Prediction based on bipartite graph for recommendation system using optimized SVD++. Procedia Computer Science, 2023. DOI: https://doi.org/10.1016/j.procs.2023.01.114
