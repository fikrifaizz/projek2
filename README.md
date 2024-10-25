# Laporan Proyek Machine Learning - Fikri Faiz Zulfadhli
## Project Overview
Dalam beberapa tahun terakhir, pertumbuhan data digital yang sangat pesat telah membuat pengguna semakin sulit menemukan item yang relevan dari berbagai pilihan yang tersedia. Hal ini sangat terlihat dalam industri seperti e-commerce, layanan streaming, dan platform media sosial, di mana pengguna sering merasa kewalahan oleh banyaknya konten atau produk yang ditawarkan. Misalnya, platform seperti Netflix, Amazon, dan YouTube menawarkan ribuan hingga jutaan item, mulai dari film, serial TV, hingga produk yang tersedia untuk dibeli. Oleh karena itu, sistem rekomendasi telah menjadi alat penting dalam membantu pengguna menemukan konten yang relevan secara efisien dan personal [[1]](https://doi.org/10.1145/2843948 'Sistem Rekomendasi Netflix').

Sistem rekomendasi adalah algoritma yang dirancang untuk memberikan saran yang dipersonalisasi kepada pengguna berdasarkan data yang ada. Ada dua pendekatan utama dalam sistem rekomendasi yaitu Content-Based Filtering, yang menggunakan informasi fitur dari item (seperti genre film) untuk memberikan rekomendasi [[2]](https://doi.org/10.1007/978-0-387-85820-3_3 'Content-Based Filtering') dan Collaborative Filtering, yang menggunakan data interaksi pengguna lain untuk memberikan saran [[3]](https://doi.org/10.1007/978-3-540-72079-9_9 'Collaborative Filtering').

Proyek ini penting diselesaikan karena dapat memberikan pengalaman pengguna yang lebih baik dengan menyajikan rekomendasi yang dipersonalisasi, membantu mengurangi kebingungan dalam memilih dari banyaknya pilihan yang tersedia. Menurut Netflix, lebih dari 80% konten yang ditonton penggunanya didasarkan pada rekomendasi yang diberikan oleh sistem mereka, menunjukkan pentingnya rekomendasi yang tepat dalam meningkatkan keterlibatan pengguna [[1]](https://doi.org/10.1145/2843948 'The Netflix Recommender System'). Selain itu, penelitian menunjukkan bahwa sistem rekomendasi berperan penting dalam peningkatan konversi dan penjualan, seperti yang dilaporkan Amazon, di mana sistem rekomendasi mereka berkontribusi hingga 35% terhadap peningkatan penjualan [[4]](https://www.mckinsey.com 'How Retailers Can Keep Up With Consumers'). Dalam era big data, sistem rekomendasi juga memungkinkan perusahaan untuk memanfaatkan data pengguna dan item secara lebih efektif, mengubahnya menjadi wawasan yang dapat mendorong keputusan pengguna dengan lebih efisien [[5]](https://doi.org/10.1145/3285029 'Deep Learning Based Recommender System'). Proyek ini juga bertujuan mengatasi masalah seperti cold start problem, yang sering terjadi ketika menangani pengguna atau item baru yang belum memiliki cukup data historis [[3]](https://doi.org/10.1007/978-3-540-72079-9_9 'Collaborative Filtering Recommender Systems'). Dengan menggabungkan pendekatan content-based filtering dan collaborative filtering, diharapkan proyek ini dapat memberikan rekomendasi yang lebih akurat, bahkan untuk pengguna atau film baru dengan sedikit interaksi.

Recommendation system telah diterapkan pada beberapa permasalahan diantaranya *TF-IDF combined rank factor Naive Bayesian algorithm for intelligent language classification recommendation systems* [[6]](https://www.sciencedirect.com/science/article/pii/S2772941924000656 'TF-IDF combined rank factor Naive Bayesian algorithm for intelligent language classification recommendation systems'), *A decision-support productive resource recommendation system for enhanced construction project management* [[7]](https://www.sciencedirect.com/science/article/abs/pii/S1474034624004415 'A decision-support productive resource recommendation system for enhanced construction project management') dan *Link Prediction based on bipartite graph for recommendation system using optimized SVD++* [[8]](https://www.sciencedirect.com/science/article/pii/S187705092300114X 'Link Prediction based on bipartite graph for recommendation system using optimized SVD++').

Dari permasalahan dan latar belakang di atas, proyek ini akan membuat sebuah model machine learning berupa sistem rekomendasi untuk menentukan rekomendasi film yang terbaik kepada pengguna. Model ini nantinya dapat digunakan dan di-deploy untuk berbagai keperluan, misalnya diterapkan dalam katalog film pada platform streaming, daftar rekomendasi film di perpustakaan digital, media sosial berbasis konten video, ataupun pada e-commerce yang menjual konten film baik dalam format digital maupun fisik. Proyek ini menggabungkan pendekatan content-based filtering dan collaborative filtering untuk memberikan rekomendasi yang lebih akurat dan personal kepada pengguna berdasarkan preferensi dan interaksi mereka.

## Business Understanding

### Problem Statements



## Referensi
[1] Gomez-Uribe, C. A., & Hunt, N. (2015). The Netflix Recommender System: Algorithms, Business Value, and Innovation. ACM Transactions on Management Information Systems (TMIS), 6(4), 1-19. DOI: https://doi.org/10.1145/2843948

[2] Lops, P., De Gemmis, M., & Semeraro, G. (2011). Content-based Recommender Systems: State of the Art and Trends. Recommender Systems Handbook, 73-105. DOI: https://doi.org/10.1007/978-0-387-85820-3_3

[3] Schafer, J. B., Frankowski, D., Herlocker, J., & Sen, S. (2007). Collaborative Filtering Recommender Systems. Lecture Notes in Computer Science, 291-324. DOI: https://doi.org/10.1007/978-3-540-72079-9_9

[4] McKinsey & Company. (2020). How Retailers Can Keep Up With Consumers. [Online]. Available: https://www.mckinsey.com

[5] Zhang, S., Yao, L., Sun, A., & Tay, Y. (2019). Deep Learning Based Recommender System: A Survey and New Perspectives. ACM Computing Surveys (CSUR), 52(1), 1-38. DOI: https://doi.org/10.1145/3285029

[6] TF-IDF combined rank factor Naive Bayesian algorithm for intelligent language classification recommendation systems. Systems and Soft Computing, 2024. DOI: https://doi.org/10.1016/j.sasc.2024.200136

[7] A decision-support productive resource recommendation system for enhanced construction project management. Advanced Engineering Informatics, 2024. DOI: https://doi.org/10.1016/j.aei.2024.102793

[8] Link Prediction based on bipartite graph for recommendation system using optimized SVD++. Procedia Computer Science, 2023. DOI: https://doi.org/10.1016/j.procs.2023.01.114
