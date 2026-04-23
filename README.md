🌿 Sistem Klasifikasi & Deteksi Penyakit Daun
Proyek ini merupakan pipeline lengkap untuk mendeteksi dan mengklasifikasikan kondisi daun (seperti pada anggrek Coelogyne) menggunakan teknik Deep Learning. Proyek ini terbagi menjadi dua tahap utama: anotasi/persiapan data menggunakan format YOLO dan klasifikasi gambar menggunakan CNN (Convolutional Neural Networks).

📂 Struktur Notebook
Yolo.ipynb (Data Preparation & Labeling)

Fokus pada pembagian dataset (Split Data) dengan rasio 8:2.

Proses pelabelan data menggunakan standar format YOLO.

Pengaturan struktur folder:

images/train & images/val

labels/train & labels/val

Konfigurasi data.yaml.

Daun_Debug.ipynb (Model Training & Debugging)

Tahap pelatihan model klasifikasi menggunakan TensorFlow/Keras.

Implementasi ImageDataGenerator untuk augmentasi gambar guna mencegah overfitting.

Arsitektur model: Sequential CNN (Conv2D, MaxPooling, Dropout, Dense).

Fitur: Early Stopping untuk menghentikan training saat akurasi sudah optimal.

Output: Model disimpan dalam format .keras dan .h5 (coelogyne_model.h5).

🛠️ Teknologi yang Digunakan
Python 3 (Google Colab Environment)

TensorFlow & Keras: Untuk membangun dan melatih model CNN.

OpenCV: Untuk pemrosesan gambar.

Matplotlib & Numpy: Untuk analisis data dan visualisasi hasil training.

Ultralytics (YOLO): Untuk standarisasi label dan deteksi.

🚀 Alur Kerja
1. Persiapan Data (Yolo.ipynb)
Hubungkan ke Google Drive, kemudian jalankan script untuk merapikan dataset. Pastikan semua gambar telah dianotasi dan file data.yaml telah dikonfigurasi dengan benar untuk menentukan jalur (path) folder training dan validasi.

2. Pelatihan Model (Daun_Debug.ipynb)
Jalankan notebook ini untuk melatih model klasifikasi:

Augmentasi: Gambar akan di-rescale, shear, zoom, dan flip secara otomatis.

Training: Model akan mempelajari pola visual dari daun yang sehat maupun yang bergejala penyakit.

Inference: Terdapat blok kode khusus untuk mengunggah gambar baru dan melakukan prediksi langsung.

📊 Evaluasi & Prediksi
Model ini dilengkapi dengan visualisasi grafik akurasi dan loss. Setelah model disimpan, Anda dapat memuatnya kembali menggunakan:

Python
from tensorflow.keras.models import load_model
model = load_model('coelogyne_model.h5')
🗂️ Output Model
Hasil akhir dari kedua notebook ini adalah:

Dataset yang terstruktur rapi di Google Drive.

File model coelogyne_model.h5 yang siap dideploy untuk aplikasi deteksi penyakit daun.
