
# Explainable AI for Rice Leaf Disease Classification

### MobileNetV2 + Grad-CAM | EECCIS 2026 — Final Revision

Repositori ini berisi implementasi resmi untuk riset klasifikasi penyakit daun padi menggunakan pendekatan **Explainable AI (XAI)**. Riset ini menggabungkan arsitektur ringan **MobileNetV2** dengan **Grad-CAM** untuk memberikan transparansi pada keputusan model deep learning.

## 🚀 Key Improvements (Revision Phase)

* **[R1] Reproducibility:** Global SEED (42) dikunci untuk memastikan hasil yang konsisten.
* **[R1] Image Quality:** Seluruh visualisasi (Learning Curves, Confusion Matrix, Grad-CAM) dihasilkan dengan resolusi **300 DPI**.
* **[R2] XAI Validation Protocol:** Penambahan protokol validasi semi-kuantitatif menggunakan metrik **Focus Score** dan **Active Region Analysis**.

## 📊 Dataset

Dataset terdiri dari citra daun padi yang seimbang (Balanced Dataset) dengan kategori:

* **Bacterial Leaf Blight** (40 images)
* **Brown Spot** (40 images)
* **Leaf Smut** (40 images)

*Dataset split: 80% Training (96 images) / 20% Validation (24 images).*

## 🧠 Methodology

Arsitektur model menggunakan strategi **Transfer Learning** (MobileNetV2 pretrained ImageNet):

* **Input Size:** 224 × 224 × 3
* **Base Model:** Frozen (Non-trainable) untuk menjaga stabilitas pada dataset kecil.
* **Classifier Head:** Dense (128 units, ReLU), Dropout (0.5), Dense (3 units, Softmax).
* **XAI Engine:** Grad-CAM pada layer `out_relu` (konvolusi terakhir dari base model).

## 📈 Performance Results

Model menunjukkan performa yang kompetitif dan stabil melalui mekanisme *Early Stopping* untuk mencegah overfitting:

* **Training Accuracy:** 94.79%
* **Validation Accuracy (Best):** 91.67%
* **Weighted Avg F1-Score:** 0.88

## 🔍 Explainability Analysis (Reviewer 2 Response)

Kami mengukur transparansi model secara kuantitatif melalui protokol validasi Grad-CAM:

* **Mean Confidence:** ~89% (Model menunjukkan keyakinan tinggi pada prediksi kelas yang benar).
* **Active Region:** ~26% (Model fokus pada area spesifik daun, meminimalisir pengaruh noise latar belakang).
* **Mean Focus Score:** ~11.8 (Memberikan dasar kuantitatif untuk evaluasi spasial interpretibilitas).

## 🛠️ Installation & Usage

1. **Clone Repository:**
```bash
git clone https://github.com/valen3005/rice-disease-xai-mobilenetv2.git

```


2. **Setup Environment:**
Gunakan Google Colab atau install library lokal:
```bash
pip install tensorflow matplotlib seaborn scikit-learn opencv-python-headless

```


3. **Run Notebook:**
Jalankan file `Paper_ValentinoJulioMemah.ipynb` secara berurutan.

## 📂 Repository Structure

* `Paper_ValentinoJulioMemah.ipynb`: Notebook utama eksperimen (versi revisi).
* `outputs/`: Grafik resolusi tinggi untuk kebutuhan publikasi (DPI=300).
* `xai_validation_summary.txt`: Laporan otomatis metrik interpretibilitas per kelas.

## 🎓 Citation

Jika Anda menggunakan kode atau metodologi ini, silakan kutip:

> Memah, V. J., Gunawan, A. A. S., & Tedjasulaksana, J. J. (2026). Explainable AI for Rice Leaf Disease Classification. *Proceedings of the 13th Electrical Power, Electronics, Communications, Controls and Informatics Seminar (EECCIS 2026)*.
