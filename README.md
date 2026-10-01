# Co-Kriging
# Spatial Interpolation using Ordinary Co-Kriging (Python)

Repositori ini berisi implementasi algoritma **Ordinary Co-Kriging** dari awal (*scratch*) menggunakan Python untuk interpolasi spasial konsentrasi logam berat (*Zinc* dan *Copper*) dengan memanfaatkan transformasi **Box-Coxx** guna memenuhi asumsi normalitas data.

## Fitur Utama Proyek
1. **Eksplorasi Data Spasial (EDA):** Analisis statistik deskriptif, histogram, boxplot, dan matriks korelasi.
2. **Transformasi Box-Coxx:** Menemukan nilai parameter $\lambda$ optimal untuk mengatasi asimetri (*skewness*) pada data *Zinc* dan *Copper*.
3. **Pemodelan Variogram Empiris & Teoretis:** 
   * Perhitungan semivarians empiris (variogram utama, sekunder, dan *cross-variogram*).
   * Fitting model teoretis (**Spherical**, **Exponential**, dan **Gaussian**) menggunakan optimasi numerik dengan evaluasi nilai **SSE (Sum of Squared Errors)** otomatis untuk mencari model terbaik.
4. **Ordinary Co-Kriging & Validasi Silang:**
   * Pembentukan sistem matriks pembobot kriging spasial.
   * Validasi silang menggunakan metode *Leave-One-Out Cross-Validation* (LOOCV) untuk menghitung **RMSE** dan **R-Squared ($R^2$)**.
5. **Pemetaan Spasial:** Visualisasi peta estimasi konsentrasi dan peta ketidakpastian (*variance*) menggunakan grid spasial.

## Kebutuhan Pustaka (Libraries)
Pastikan pustaka berikut terinstal di lingkungan Python Anda (Google Colab / Jupyter Notebook):
- `numpy`
- `pandas`
- `matplotlib`
- `seaborn`
- `scipy`
- `scikit-learn`

## Cara Menjalankan
1. Unggah file skrip Python atau buka file di Google Colab.
2. Siapkan dataset spasial (misalnya `meuse.csv` yang mencakup koordinat `x`, `y`, `zinc`, dan `copper`).
3. Jalankan sel kode secara berurutan mulai dari input data hingga visualisasi peta akhir.

## Hasil Evaluasi Model
* **Model Variogram Terbaik:** Terpilih secara otomatis berdasarkan SSE terkecil (Spherikal / Eksponensial / Gaussian).
* **Metrik Akurasi (LOOCV):** Menampilkan nilai RMSE dan $R^2$ pada skala transformasi maupun skala asli setelah proses *inverse*.
