
# Explainable AI for Rice Leaf Disease Classification

### MobileNetV2 + Grad-CAM | EECCIS 2026 — Final Revision

Repositori ini berisi implementasi resmi untuk riset klasifikasi penyakit daun padi menggunakan pendekatan **Explainable AI (XAI)**. Riset ini menggabungkan arsitektur ringan **MobileNetV2** dengan **Grad-CAM** untuk memberikan transparansi pada keputusan model deep learning.

## 🚀 Key Improvements (Revision Phase)

* **[R1] Reproducibility:** Global SEED kaku dan dokumentasi parameter lengkap.
* **[R1] Image Quality:** Seluruh visualisasi dihasilkan dengan resolusi **300 DPI**.
* **[R2] XAI Validation Protocol:** Penambahan protokol validasi semi-kuantitatif menggunakan **Focus Score** dan **Active Region Analysis**.

## 📊 Dataset

Dataset terdiri dari citra daun padi yang seimbang (Balanced Dataset) dengan kategori:

* **Bacterial Leaf Blight**
* **Brown Spot**
* **Leaf Smut**

*Dataset split: 80% Training (96 images) / 20% Validation (24 images).*

## 🧠 Methodology

Arsitektur model menggunakan strategi **Transfer Learning** (MobileNetV2 pretrained ImageNet) dengan spesifikasi:

* **Input Size:** 224 × 224 × 3
* **Base Model:** Frozen (Non-trainable) untuk menjaga stabilitas pada dataset kecil.
* **Classifier Head:** Dense (128 units, ReLU), Dropout (0.5), Dense (3 units, Softmax).
* **XAI Engine:** Grad-CAM pada layer `out_relu` (konvolusi terakhir).

## 📈 Performance Results

Model mencapai performa tinggi yang stabil tanpa indikasi overfitting:

* **Training Accuracy:** 97.79%
* **Validation Accuracy:** 95.83%
* **Mean F1-Score:** > 0.95 (Sangat Kuat)

## 🔍 Explainability Analysis (Reviewer 2 Response)

Kami memperkenalkan metrik baru untuk memvalidasi kejujuran model secara kuantitatif:

* **Focus Score:** Rata-rata > 75/100 (Menunjukkan model sangat terfokus pada lesi penyakit).
* **Active Region:** Rata-rata < 15% (Membuktikan model tidak melihat background atau noise).

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

* `Paper_ValentinoJulioMemah.ipynb`: Notebook utama eksperimen.
* `outputs/`: Folder berisi grafik resolusi tinggi (Loss, Accuracy, Confusion Matrix, Grad-CAM).
* `xai_validation_summary.txt`: Laporan detail metrik interpretabilitas.

## 🎓 Citation

Jika Anda menggunakan kode atau metodologi ini, silakan kutip:

> Memah, V. J., Gunawan, A. A. S., & Tedjasulaksana, J. J. (2026). Explainable AI for Rice Leaf Disease Classification. *Proceedings of the 13th Electrical Power, Electronics, Communications, Controls and Informatics Seminar (EECCIS 2026)*.
