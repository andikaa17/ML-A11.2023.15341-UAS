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
