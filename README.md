# ML-UAS2025

# PREDIKSI PENYAKIT DIABETES MENGUNAKAN MODEL LOGISTIC REGRESSION

   Diabetes adalah penyakit yang banyak dialami masyarakat dan bisa menyebabkan komplikasi serius jika tidak ditangani sejak awal. Sayangnya, proses diagnosa sering butuh waktu dan bisa saja kurang akurat jika hanya mengandalkan pemeriksaan manual.
Project ini bertujuan membuat model machine learning untuk memprediksi apakah seseorang berisiko diabetes atau tidak. Model ini menggunakan beberapa faktor seperti jumlah kehamilan, kadar glukosa, tekanan darah, ketebalan kulit, insulin, BMI, riwayat keluarga (silsilah), dan usia. Diharapkan model ini bisa membantu proses deteksi lebih cepat dan akurat.

TUJUANNYA :
1. Membangun model machine learning yang dapat memprediksi kemungkinan seseorang terkena penyakit diabetes berdasarkan data medis.
2. Mengevaluasi kinerja model menggunakan metrik evaluasI.
3. Membuat rekomendasi perbaikan

# MODEL PENYELESAIAN

![image](https://github.com/user-attachments/assets/e0894434-2919-4055-a053-1e2650199c64)

# PENJELASAN DATASET
- Pregnancies: Jumlah kehamilan yang pernah dialami oleh pasien.
- Glucose: Kadar glukosa plasma dalam darah setelah melakukan tes toleransi glukosa 2 jam. Semakin tinggi nilai ini, semakin besar kemungkinan pasien mengalami diabetes.
- BloodPressure: Tekanan darah diastolik pasien saat istirahat (dalam mm Hg).
- SkinThickness: Ketebalan lipatan kulit triceps yang diukur dalam milimeter, digunakan sebagai indikator lemak tubuh.
- Insulin: Kadar insulin dalam serum dua jam setelah makan (μU/ml). Nilai ini dapat mencerminkan seberapa baik tubuh mengatur gula darah.
- BMI (Body Mass Index): Indeks massa tubuh pasien, dihitung dari berat badan (kg) dibagi tinggi badan kuadrat (m²). Nilai tinggi biasanya berkaitan dengan risiko diabetes.
- DiabetesPedigreeFunction: Nilai ini merepresentasikan riwayat genetik terhadap diabetes berdasarkan silsilah keluarga. Semakin tinggi nilainya, semakin besar kemungkinan faktor keturunan berpengaruh.
- Age: Umur pasien dalam tahun. Risiko diabetes cenderung meningkat seiring bertambahnya usia.
- Outcome: Merupakan label (target) dari dataset ini. Nilai 1 berarti pasien terdiagnosis diabetes, sedangkan 0 berarti tidak.

  Variabel-variabel ini digunakan sebagai fitur dalam model regresi logistik untuk memprediksi kemungkinan seseorang mengidap diabetes. Selain itu, dataset ini juga mencakup label (Outcome), yang menentukan apakah pasien terdiagnosis diabetes (1) atau tidak (0).

  # PROSES DATASET DIOLAH

1. Import Library
 Library yang diperlukan seperti numpy, pandas, train_test_split, LogisticRegression, dan classification_report dari scikit-learn diimpor untuk kebutuhan pengolahan data dan pelatihan model klasifikasi.

2. Membaca Data
Data mengenai penyakit diabetes dibaca dari file CSV bernama diabetes.csv menggunakan pandas, dan disimpan ke dalam variabel diabetes_data.

3. Memisahkan Fitur dan Label
Data dipisahkan menjadi fitur (X) dan label (Y), di mana X berisi semua kolom kecuali kolom Outcome, sedangkan Y berisi kolom Outcome sebagai target prediksi, dengan nilai 1 untuk pasien yang terkena diabetes dan 0 untuk yang tidak.

4. Mencetak Label
Label Y dicetak untuk melihat distribusi jumlah pasien yang terkena dan tidak terkena diabetes.

5. Membagi Data
Data dibagi menjadi data pelatihan dan pengujian menggunakan fungsi train_test_split dengan proporsi 80:20. Parameter stratify=Y digunakan untuk menjaga distribusi kelas antara data latih dan data uji, dan random_state digunakan agar pembagian data selalu konsisten saat dijalankan ulang.

6. Mencetak Bentuk Data
Ukuran data lengkap, data pelatihan (X_train), dan data pengujian (X_test) dicetak untuk memverifikasi bahwa pembagian data telah dilakukan dengan benar.

7. Membuat dan Melatih Model
Model klasifikasi Logistic Regression dibuat dan dilatih menggunakan data pelatihan (X_train dan Y_train).

8. Evaluasi Model pada Data Pengujian
Model digunakan untuk memprediksi hasil pada data pengujian (X_test). Hasil prediksi kemudian dievaluasi menggunakan classification_report, yang menampilkan nilai precision, recall, dan F1-score untuk kedua kelas: pasien yang tidak terkena diabetes dan yang terkena diabetes.

9. Prediksi Data Baru
Sebuah data pasien baru diberikan sebagai input (misalnya: (6,148,72,35,0,33.6,0.627,50)), lalu data tersebut diubah menjadi array numpy dan di-reshape agar sesuai dengan format input model. Model kemudian memprediksi apakah pasien tersebut terkena diabetes atau tidak.

10. Mencetak Hasil Prediksi
Hasil dari prediksi ditampilkan. Jika model memprediksi 0, maka pasien tidak terkena diabetes; jika 1, maka pasien terkena diabetes.

KESIMPULAN : Secara keseluruhan, kode ini menjalankan rangkaian proses mulai dari membaca dataset, memisahkan fitur dan label, melatih model klasifikasi, hingga mengevaluasi kinerjanya menggunakan data uji. Dengan memanfaatkan algoritma Logistic Regression, model mampu melakukan prediksi terhadap kemungkinan seseorang terkena penyakit jantung, serta menghasilkan laporan klasifikasi yang mencerminkan tingkat akurasi dan efektivitas model tersebut.

# Evaluasi Performa Model Logistic Regression Berdasarkan Classification Report

![image](https://github.com/user-attachments/assets/4fe58840-9686-4994-8e5f-c4b8007eccd3)

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

# Evaluasi Performa Model XGBClassifier Berdasarkan Classification Report 

![image](https://github.com/user-attachments/assets/d1d30769-b9b4-4220-b58f-9fb89fe6c443)

- Precision:
1. Tidak Terkena Diabetes: 0.78 (78% dari prediksi tidak terkena diabetes adalah benar)
2. Terkena Diabetes: 0.65 (65% dari prediksi terkena diabetes adalah benar)

- Recall:
1. Tidak Terkena Diabetes: 0.84 (84% dari pasien yang benar-benar tidak terkena diabetes berhasil dikenali oleh model)
2. Terkena Diabetes: 0.56 (56% dari pasien yang benar-benar terkena diabetes berhasil dikenali)

- F1-Score:
1. Tidak Terkena Diabetes: 0.81 (Rata-rata harmonis dari precision dan recall)
2. Terkena Diabetes: 0.60

- Akurasi:
74% (74% dari keseluruhan prediksi model adalah benar)

- Macro avg:
Rata-rata tidak berbobot dari precision, recall, dan F1-score untuk kedua kelas.

- Weighted avg:
Rata-rata berbobot dari precision, recall, dan F1-score, memperhitungkan jumlah sampel di setiap kelas.

# Evaluasi Performa Model RandomForestClassifier Berdasarkan Classification Report 

![image](https://github.com/user-attachments/assets/42ffc65b-6b6f-4744-9b34-5af029ff8982)

- Precision:
1. Tidak Terkena Diabetes: 0.77 (77% dari prediksi tidak terkena diabetes adalah benar)
2. Terkena Diabetes: 0.58 (58% dari prediksi terkena diabetes adalah benar)

- Recall:
1. Tidak Terkena Diabetes: 0.78 (78% dari pasien yang benar-benar tidak terkena diabetes berhasil dikenali oleh model)
2. Terkena Diabetes: 0.57 (57% dari pasien yang benar-benar terkena diabetes berhasil dikenali)

- F1-Score:
1. Tidak Terkena Diabetes: 0.78 (Rata-rata harmonis dari precision dan recall)
2. Terkena Diabetes: 0.58

- Akurasi:
71% (71% dari keseluruhan prediksi model adalah benar)

- Macro avg:
Rata-rata tidak berbobot dari precision, recall, dan F1-score untuk kedua kelas.

- Weighted avg:
Rata-rata berbobot dari precision, recall, dan F1-score, memperhitungkan jumlah sampel di setiap kelas.

# KESIMPULAN PERFOMA DARI 3 MODEL
 Rekomendasi:
1. Validasi Model Lanjutan: Uji model dengan data yang berbeda dari data latih untuk memastikan model tidak hanya bekerja baik pada data yang sudah dikenalnya, tetapi juga mampu menggeneralisasi ke data baru.

2. Tuning Hyperparameter: Lakukan pengaturan nilai hyperparameter secara optimal (misalnya menggunakan GridSearchCV) untuk meningkatkan performa model secara keseluruhan.

3. Pengembangan Fitur (Feature Engineering): Analisis lebih lanjut terhadap fitur yang ada sangat disarankan. Ada kemungkinan fitur tertentu kurang relevan, atau bahkan ada fitur baru yang bisa ditambahkan untuk memperkuat prediksi.

4. Cross-Validation: Gunakan teknik validasi silang untuk memastikan performa model konsisten dan tidak hanya bergantung pada satu pembagian data saja.

Kesimpulan:
Secara Keselruhan Model LogisticRegression memiliki performa yang paling baik dalam mengidentifikasi potensi penyakit diabetes. Berdasarkan hasil prediksi pada data baru, model mampu mendeteksi individu yang berisiko terkena diabetes dengan tingkat akurasi yang memadai. Hal ini menunjukkan bahwa model dapat digunakan sebagai alat bantu dalam proses skrining awal penyakit diabetes.

# LANGKAH PROSES PREDIKSI MENGUNAKAN LOGISTIC REGRESSION

1. Input Data Pasien
Data pasien dimasukkan dalam bentuk tuple seperti berikut:
![image](https://github.com/user-attachments/assets/a229b2e0-0a58-411a-b7ae-3cd8350b2743)

Nilai-nilai tersebut menggambarkan fitur yaitu : 
Pregnancies: 6
Glucose: 148
BloodPressure: 72
SkinThickness: 35
Insulin: 0
BMI: 33.6
Diabetes Pedigree Function: 0.627
Age: 50

2. Mengubah Format ke Array Numpy
Data input dikonversi ke bentuk array menggunakan numpy agar bisa dibaca oleh model:
![image](https://github.com/user-attachments/assets/91a176a5-3330-4ec5-84a1-60ac12faadf7)


3. Merapikan Bentuk Data
Karena model membutuhkan data dalam format dua dimensi, dilakukan reshape:
![image](https://github.com/user-attachments/assets/80f52c8c-cd4c-4ecb-ad65-e0a56b5127ff)


4. Melakukan Prediksi
Model kemudian digunakan untuk memprediksi apakah pasien menderita diabetes atau tidak:
![image](https://github.com/user-attachments/assets/2429bd08-f72b-448d-90a0-23e4436210e2)


5. Menampilkan Hasil
Hasil prediksi ditampilkan dengan kondisi sebagai berikut:
![image](https://github.com/user-attachments/assets/b6d0b971-82da-4b97-889e-67f32ed49d51)

Hasil setelah diprediksi
![image](https://github.com/user-attachments/assets/6ed5e076-7b30-43d6-9357-4dd58f887d20)

KESIMPULANNYA : Model berhasil memproses data input pasien dan memberikan hasil prediksi. Jika output dari model adalah 1, maka pasien diperkirakan mengidap diabetes. Sebaliknya, jika hasilnya 0, maka pasien tidak terindikasi diabetes. Hasil ini dapat digunakan sebagai bahan pertimbangan awal dalam proses diagnosis, namun tidak menggantikan pemeriksaan medis yang sebenarnya. Evaluasi lebih lanjut tetap perlu dilakukan oleh tenaga kesehatan profesional.

