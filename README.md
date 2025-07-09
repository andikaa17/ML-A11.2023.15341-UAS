Nama      : Andika Apriyanto

Nim       : A11.2023.15341

Kelompok  : 4406


# ML-UAS-2025

# PREDIKSI PENYAKIT DIABETES MENGUNAKAN MODEL LOGISTIC REGRESSION

   Diabetes adalah penyakit yang banyak dialami masyarakat dan bisa menyebabkan komplikasi serius jika tidak ditangani sejak awal. Sayangnya, proses diagnosa sering butuh waktu dan bisa saja kurang akurat jika hanya mengandalkan pemeriksaan manual.
Proyek ini bertujuan membuat model machine learning untuk memprediksi apakah seseorang berisiko diabetes atau tidak. Model ini menggunakan beberapa faktor seperti jumlah kehamilan, kadar glukosa, tekanan darah, ketebalan kulit, insulin, BMI, riwayat keluarga (silsilah), dan usia. Diharapkan model ini bisa membantu proses deteksi lebih cepat dan akurat.

# Tujuan yang akan dicapai :
1. Membangun model machine learning yang dapat memprediksi kemungkinan seseorang terkena penyakit diabetes berdasarkan data medis.
2. Mengevaluasi kinerja model menggunakan metrik evaluasi.
3. Membuat rekomendasi perbaikan

# Model Penyelesaian

![image](https://github.com/user-attachments/assets/9b42d13b-df7a-4d2c-8488-e5c9b525282d)



# Penjelasan Dataset, EDA dan Proses Features Dataset
   Dataset yang digunakan dalam penelitian ini berasal dari situs web Kaggle, sebuah platform populer yang menyediakan berbagai dataset publik untuk keperluan pembelajaran mesin (machine learning) dan analisis data. Dataset ini bersifat terbuka, sehingga dapat diakses dan digunakan oleh siapa saja untuk keperluan penelitian dan pengembangan model prediktif. Dataset ini berisi data historis pasien yang terdiagnosis diabetes maupun yang tidak, dengan total 8 atribut medis dan 1 label (kelas). Atribut-atribut tersebut berkaitan dengan faktor risiko diabetes, seperti kadar glukosa, tekanan darah, indeks massa tubuh, serta riwayat keluarga.
Berikut adalah penjelasan setiap atribut yang digunakan dalam dataset ini:

1. Pregnancies: Jumlah kehamilan yang pernah dialami oleh pasien.

2. Glucose: Kadar glukosa dalam plasma darah setelah tes toleransi glukosa. Nilai yang tinggi menunjukkan risiko diabetes lebih besar.

3. BloodPressure: Tekanan darah diastolik pasien saat istirahat (dalam mm Hg).

4. SkinThickness: Ketebalan lipatan kulit triceps (dalam mm) yang digunakan untuk mengukur lemak tubuh.

5. Insulin: Kadar insulin dalam darah 2 jam setelah makan (μU/ml), mencerminkan fungsi pankreas.

6. BMI (Body Mass Index): Indeks massa tubuh pasien, dihitung dari berat dan tinggi badan.

7. DiabetesPedigreeFunction: Skor yang menunjukkan kemungkinan diabetes berdasarkan riwayat keluarga.

8. Age: Usia pasien (dalam tahun). Risiko diabetes biasanya meningkat seiring bertambahnya usia.

9. Outcome: Merupakan label target. Nilai 1 berarti pasien terdiagnosis diabetes, sedangkan 0 berarti tidak.

Variabel-variabel ini digunakan sebagai fitur dalam model regresi logistik untuk memprediksi kemungkinan seseorang mengidap diabetes. Selain itu, dataset ini juga mencakup label (Outcome), yang menentukan apakah pasien terdiagnosis diabetes (1) atau tidak (0). 

Visualisasi Distribusi Fitur:
Berdasarkan hasil visualisasi distribusi, fitur `Glucose` menunjukkan sebaran nilai yang cukup bervariasi, dengan dominasi nilai sedang hingga tinggi. Hal ini mendukung temuan bahwa kadar glukosa tinggi merupakan indikator kuat risiko diabetes.


![download (1)](https://github.com/user-attachments/assets/d708ca08-a0b4-45d9-b470-15129d8b14c8)

Selain itu, fitur seperti SkinThickness dan BloodPressure menunjukkan distribusi tidak merata, dengan nilai-nilai tertentu yang mendominasi. Pola-pola ini penting untuk dianalisis karena dapat memengaruhi performa model dalam membedakan antara pasien yang terkena dan tidak terkena diabetes.

![download (3)](https://github.com/user-attachments/assets/b294f091-a146-45b6-aef2-770f72b49f10) ![download (2)](https://github.com/user-attachments/assets/ebefd3b9-251d-4dde-ab13-c85c1b8f3283)





  # Proses Learning Dan Modeling
  Pada proyek ini, dilakukan proses pembangunan model machine learning menggunakan algoritma Logistic Regression untuk memprediksi kemungkinan seseorang mengidap penyakit diabetes berdasarkan data medis yang tersedia. Dataset yang digunakan adalah diabetes.csv, yang memuat informasi pasien seperti jumlah kehamilan, kadar glukosa, tekanan darah, ketebalan kulit, kadar insulin, BMI, riwayat keluarga diabetes, serta usia.

1. Import Library : 
 Library yang diperlukan seperti numpy, pandas, train_test_split, LogisticRegression, classification_report, dan accuracy_score dari scikit-learn diimpor untuk kebutuhan pengolahan data serta pelatihan dan evaluasi model klasifikasi.

2. Membaca Data : 
Data mengenai penyakit diabetes dibaca dari file CSV bernama diabetes.csv menggunakan pandas dan disimpan ke dalam variabel data.

3. Memisahkan Fitur dan Label :
Data dipisahkan menjadi fitur (X) dan label (Y), X berisi 768 data pasien dengan 8 kolom fitur medis, seperti jumlah kehamilan, kadar glukosa, tekanan darah, ketebalan kulit, insulin, BMI, riwayat keluarga diabetes, dan usia. Y berisi 768 data yang merupakan label Outcome, dengan nilai 1 untuk pasien yang terkena diabetes dan 0 untuk yang tidak.

4. Mencetak Label :
Label Y dicetak untuk melihat distribusi jumlah pasien yang terkena dan tidak terkena diabetes.

5. Membagi Data : 
Data dibagi menjadi data pelatihan dan pengujian menggunakan fungsi train_test_split dengan proporsi 80:20. Parameter stratify=Y digunakan untuk menjaga distribusi kelas antara data latih dan data uji, dan random_state digunakan agar pembagian data selalu konsisten saat dijalankan ulang.

6. Mencetak Bentuk Data : 
Ukuran data lengkap, data pelatihan (X_train), dan data pengujian (X_test) dicetak untuk memverifikasi bahwa pembagian data telah dilakukan dengan benar.

7. Membuat dan Melatih Model :
Model klasifikasi Logistic Regression dibuat dan dilatih menggunakan data pelatihan (X_train dan Y_train).

8. Evaluasi Model pada Data Pengujian :
Model digunakan untuk memprediksi hasil pada data pengujian (X_test). Hasil prediksi kemudian dievaluasi menggunakan
- classification_report, yang menampilkan nilai precision, recall, dan F1-score untuk kedua kelas: pasien yang tidak terkena diabetes dan yang terkena diabetes.
- accuracy_score yang menunjukkan tingkat akurasi keseluruhan model dalam memprediksi.

10. Prediksi Data Baru :
Sebuah data pasien baru diberikan sebagai input (misalnya: (6,148,72,35,0,33.6,0.627,50)), lalu data tersebut diubah menjadi array numpy dan di-reshape agar sesuai dengan format input model. Model kemudian memprediksi apakah pasien tersebut terkena diabetes atau tidak.

11. Mencetak Hasil Prediksi :
Hasil dari prediksi ditampilkan. Jika model memprediksi 0, maka pasien tidak terkena diabetes; jika 1, maka pasien terkena diabetes.

KESIMPULAN : Secara keseluruhan, kode ini menjalankan rangkaian proses mulai dari membaca dataset, memisahkan fitur dan label, melatih model klasifikasi, hingga mengevaluasi kinerjanya menggunakan data uji. Dengan memanfaatkan algoritma Logistic Regression, model mampu melakukan prediksi terhadap kemungkinan seseorang terkena Diabetes, serta menghasilkan laporan klasifikasi yang mencerminkan tingkat akurasi dan efektivitas model tersebut.

# Evaluasi Performa Model Logistic Regression Berdasarkan Classification Report, Accuracy_score

![image](https://github.com/user-attachments/assets/babba4f7-45de-4692-bb5a-d2031ded4f8a)

- **Classification Report**
- Precision:
1. Tidak Terkena Diabetes: 0.77 (77% dari prediksi tidak terkena diabetes adalah benar)

2. Terkena Diabetes: 0.70 (70% dari prediksi terkena diabetes adalah benar)

- Recall:
1. Tidak Terkena Diabetes: 0.88 (88% dari pasien yang benar-benar tidak terkena diabetes berhasil dikenali)
2. Terkena Diabetes: 0.52 (52% dari pasien yang benar-benar terkena diabetes berhasil dikenali oleh model)

- F1-Score:
1. Tidak Terkena Diabetes: 0.82 (Rata-rata harmonis dari precision dan recall)
2. Terkena Diabetes: 0.60

- Akurasi:
75% (75% dari keseluruhan prediksi model adalah benar)

- Macro avg:
Rata-rata tidak berbobot dari precision, recall, dan F1-score untuk kedua kelas.

- Weighted avg:
Rata-rata berbobot dari precision, recall, dan F1-score, memperhitungkan jumlah sampel di setiap kelas.

**Accuracy_score**
- Nilai accuracy_score sebesar 75.32% menunjukkan bahwa dari seluruh data uji, model berhasil memprediksi dengan benar sekitar 75 pasien dari setiap 100 pasien, baik untuk pasien yang terkena diabetes maupun yang tidak. Nilai ini menunjukkan performa global model yang cukup baik untuk digunakan sebagai alat bantu dalam skrining awal risiko diabetes.

Kesimpulan:
Secara keseluruhan, model Logistic Regression memiliki performa yang cukup baik dalam mengidentifikasi potensi penyakit diabetes. Berdasarkan hasil evaluasi pada data uji, model ini mampu mendeteksi individu yang berisiko terkena diabetes dengan tingkat akurasi sebesar 75%, serta nilai precision dan recall yang relatif baik. Namun, terlihat bahwa recall untuk kelas pasien yang benar-benar terkena diabetes masih sekitar 52%, yang mengindikasikan adanya tantangan dalam mendeteksi kasus positif secara optimal. Hal ini kemungkinan disebabkan oleh distribusi data yang kurang seimbang, di mana jumlah pasien yang tidak terkena diabetes lebih dominan. Oleh karena itu, model ini dapat digunakan sebagai alat bantu dalam proses skrining awal penyakit diabetes, tetapi pemeriksaan dan diagnosis lebih lanjut tetap harus dilakukan oleh tenaga medis profesional. Untuk meningkatkan performa, terutama dalam mendeteksi pasien yang benar-benar terkena diabetes, disarankan melakukan penanganan terhadap ketidakseimbangan data atau mencoba algoritma lain.

Rekomendasi Perbaikan :
1. Bandingkan dengan Model Lain:
Coba gunakan dan evaluasi model lain seperti Random Forest, Support Vector Machine, atau KNN untuk mengetahui apakah ada model yang mampu memberikan akurasi, recall, atau F1-score yang lebih baik dibanding Logistic Regression.

2. Gunakan Teknik Penyeimbangan Data:
Karena data target (Outcome) tidak seimbang (lebih banyak pasien tidak terkena diabetes), pertimbangkan penggunaan teknik seperti SMOTE (Synthetic Minority Over-sampling Technique) atau undersampling agar model tidak bias terhadap kelas mayoritas.

3. Terapkan Validasi Silang (Cross-Validation):
Gunakan teknik k-fold cross-validation untuk mengevaluasi model secara lebih konsisten, karena hanya memisahkan satu kali (train_test_split) bisa membuat evaluasi terlalu tergantung pada cara data dibagi.

# Langkah-langkah prediksi

1. Input Data Pasien : 
Data pasien dimasukkan dalam bentuk tuple seperti berikut:

![image](https://github.com/user-attachments/assets/a229b2e0-0a58-411a-b7ae-3cd8350b2743)

Nilai-nilai tersebut menggambarkan fitur yaitu : 
Pregnancies: 6,
Glucose: 148,
BloodPressure: 72,
SkinThickness: 35,
Insulin: 0,
BMI: 33.6,
Diabetes Pedigree Function: 0.627,
Age: 50

2. Mengubah Format ke Array Numpy : 
Data input dikonversi ke bentuk array menggunakan numpy agar bisa dibaca oleh model:

![image](https://github.com/user-attachments/assets/91a176a5-3330-4ec5-84a1-60ac12faadf7)


3. Merapikan Bentuk Data : 
Karena model membutuhkan data dalam format dua dimensi, dilakukan reshape sebagai berikut:

![image](https://github.com/user-attachments/assets/80f52c8c-cd4c-4ecb-ad65-e0a56b5127ff)

Langkah ini memastikan data memiliki 1 baris dengan banyak kolom, sesuai format yang diharapkan oleh model sklearn.


4. Melakukan Prediksi : 
Model kemudian digunakan untuk memprediksi apakah pasien menderita diabetes atau tidak:

![image](https://github.com/user-attachments/assets/2429bd08-f72b-448d-90a0-23e4436210e2)

Output akan menampilkan nilai 0 jika pasien tidak terkena diabetes, atau 1 jika pasien terkena diabetes.


5. Menampilkan Hasil Prediksi :
Hasil prediksi ditampilkan dengan kondisi sebagai berikut:

![image](https://github.com/user-attachments/assets/b6d0b971-82da-4b97-889e-67f32ed49d51)

Jika hasilnya 0, tampilkan pesan pasien tidak terkena diabetes.

Jika hasilnya 1, tampilkan pesan pasien terkena diabetes.

6. Hasil setelah diprediksi

![image](https://github.com/user-attachments/assets/6ed5e076-7b30-43d6-9357-4dd58f887d20)


KESIMPULANNYA : Model berhasil memproses data input pasien dan memberikan hasil prediksi. Jika output dari model adalah 1, maka pasien diperkirakan mengidap diabetes. Sebaliknya, jika hasilnya 0, maka pasien tidak terindikasi diabetes. Hasil ini dapat digunakan sebagai bahan pertimbangan awal dalam proses diagnosis, namun tidak menggantikan pemeriksaan medis yang sebenarnya. Evaluasi lebih lanjut tetap perlu dilakukan oleh tenaga kesehatan profesional.

