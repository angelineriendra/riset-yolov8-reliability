1. Judul

   Analisis Reliabilitas Confidence YOLOV8 sebagai One-Stage Object Detector pada Berbagai Tingkat Degradasi CItra
   
2. Latar Belakang

   Object detection merupakan salah satu bidang computer vision yang digunakan untuk mendeteksi dan menentukan lokasi objek dalam citra. Salah satu model yang digunakan untuk tugas tersebut adalah YOLOv8, yang menghasilkan prediksi berupa kelas objek, bounding box, dan confidence score.
   Confidence score menunjukkan tingkat keyakinan model terhadap hasil prediksinya. Namun, nilai confidence yang tinggi tidak selalu menjamin bahwa prediksi tersebut benar. Hal ini menimbulkan pertanyaan mengenai sejauh mana confidence yang dihasilkan model dapat dipercaya.
   Dalam penerapan nyata, kualitas citra dapat mengalami penurunan akibat blur dan kompresi JPEG. Perubahan kualitas citra tersebut dapat memengaruhi hasil deteksi dan hubungan antara confidence dengan kebenaran prediksi.
   Oleh karena itu, penelitian ini bertujuan menganalisis reliabilitas confidence YOLOv8 pada citra asli dan citra dengan berbagai tingkat degradasi. Analisis dilakukan dengan membandingkan performa deteksi, distribusi confidence, serta metrik kalibrasi pada setiap kondisi pengujian.
   
3. Rumusan Masalah
   - Bagaimana perubahan performa deteksi YOLOv8 pada berbagai tingkat degradasi citra?
   - Bagaimana perubahan confidence score YOLOv8 ketika citra mengalami blur dan kompresi JPEG?
   - Apakah confidence score tetap mencerminkan kebenaran prediksi pada citra terdegradasi?
   - Bagaimana perubahan reliabilitas atau kalibrasi confidence YOLOv8 antara citra asli dan citra terdegradasi?
   - Apakah perubahan performa deteksi sejalan dengan perubahan reliabilitas confidence?
     
4. Tujuan Penelitian
   - Menganalisis perubahan performa deteksi YOLOv8 pada berbagai tingkat degradasi citra.
   - Menganalisis perubahan distribusi confidence score pada setiap kondisi pengujian.
   - Mengevaluasi kesesuaian confidence dengan kebenaran prediksi.
   - Membandingkan hasil kalibrasi confidence antara citra asli dan citra terdegradasi.
   - Menganalisis hubungan antara perubahan performa deteksi dan perubahan reliabilitas confidence.
     
5. Batasan Penelitian
   - Model yang digunakan adalah YOLOv8 pretrained.
   - Dataset yang direncanakan adalah COCO 2017 validation.
   - Jumlah citra asli yang digunakan sebanyak 5.000 gambar.
   - Jenis degradasi yang diuji adalah Gaussian blur dan kompresi JPEG.
   - Setiap jenis degradasi memiliki dua tingkat keparahan.\
   - Citra asli digunakan sebagai baseline pembanding.
   - Penelitian berfokus pada evaluasi confidence bawaan model, bukan membangun metode kalibrasi baru.
   - Eksperimen menggunakan model dan konfigurasi inferensi yang sama pada semua kondisi.
   - Parameter degradasi, confidence threshold, dan prosedur evaluasi ditetapkan serta didokumentasikan sebelum eksperimen utama.
   
8. Metodologi Penelitian

Tahap 1 — Persiapan dataset
- Mengunduh citra COCO 2017 validation dan anotasi objeknya.
- Menggunakan 5.000 citra asli beserta anotasi ground truth.
- Mempertahankan ID gambar untuk menghubungkan citra, anotasi, dan hasil eksperimen.

Tahap 2 — Pembuatan citra terdegradasi
- Menggunakan citra asli sebagai baseline.
- Membuat dua tingkat Gaussian blur.
- Membuat dua tingkat kompresi JPEG.
- Mempertahankan dimensi dan geometri citra agar anotasi bounding box tetap relevan.

Tahap 3 — Inferensi YOLOv8
- Menjalankan model pada citra asli dan seluruh kondisi degradasi.
- Menyimpan kelas prediksi, bounding box, confidence score, dan waktu inferensi.
- Menggunakan konfigurasi inferensi yang konsisten pada setiap kondisi.

Tahap 4 — Pencocokan dengan ground truth
- Mencocokkan bounding box dan kelas prediksi dengan anotasi ground truth.
- Menentukan prediksi benar dan salah berdasarkan aturan pencocokan yang ditetapkan.
- Mengidentifikasi objek yang tidak terdeteksi dan prediksi duplikat.

Tahap 5 — Evaluasi
- Menghitung mAP, precision, dan recall untuk performa deteksi.
- Menganalisis distribusi confidence score.
- Menghitung Expected Calibration Error (ECE) menggunakan protokol kalibrasi object detection yang dijelaskan secara eksplisit.
- Membuat reliability diagram untuk melihat kesesuaian confidence dengan proporsi prediksi benar.

Tahap 6 — Analisis perbandingan
- Membandingkan performa dan reliabilitas confidence antara citra asli, blur tingkat 1, blur tingkat 2, JPEG tingkat 1, dan JPEG tingkat 2.
- Menganalisis apakah perubahan performa deteksi sejalan dengan perubahan kalibrasi.
- Menarik kesimpulan berdasarkan hasil eksperimen.
   
