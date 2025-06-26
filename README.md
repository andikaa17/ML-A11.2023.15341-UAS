# ML-UAS2025

# PREDIKSI PENYAKIT DIABETES MENGUNAKAN MODEL LOGIC REGRESSION

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

  # PROSESNYA DATASET DIOLAH

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

# HASIL EVALUASI MODEL MENGUNAKAN LOGIC REGRESSION

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

# HASIL EVALUASI MODEL MENGUNAKAN XGBClassifier

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




