[GAP SEMENTARA]

1. Huseljic et al. (2025)
   Systematic Evaluation of Uncertainty Calibration in Pretrained Object Detectors membahas evaluasi uncertainty calibration pada object detector, termasuk ketika menghadapi distribution shift dan out-of-distribution data. Penelitian tersebut menggunakan Faster R-CNN dan DETR serta mengevaluasi pengaruh post-processing dan pilihan metrik terhadap calibration. Penelitian ini menjadi landasan untuk memahami bahwa performa deteksi dan reliabilitas probabilistik merupakan dua aspek yang perlu dievaluasi secara berbeda.

   Research Gap: menguji reliabilitas confidence pada YOLOv8 sebagai one-stage detector dengan eksperimen degradasi citra yang terkontrol.

2. Yoon dan Kim (2026)
   Non-linear Performance Degradation Mechanism and Quantitative Inflection Point Identification of AI-based Pedestrian and Vehicle Detection Reliability under Image Data Degradation: A Case Study on the COCO Dataset with YOLOv8 menggunakan YOLOv8 Nano dan COCO 2017 untuk menganalisis dampak penurunan resolusi dan kompresi JPEG terhadap reliability deteksi person dan car. Penelitian ini menemukan bahwa confidence tidak selalu menurun secara linear ketika kualitas citra mengalami degradasi. Penelitian baru tidak cukup hanya mengulang pengukuran penurunan confidence akibat resolusi atau JPEG compression.

   Research Gap: menganalisis hubungan antara confidence dan kebenaran setiap prediksi pada beberapa tingkat degradasi, dengan evaluasi yang secara eksplisit mempertimbangkan kecocokan kelas dan bounding box terhadap ground truth.
   
3. Zheng et al. (2026)
   Confidence-calibrated semantic resource allocation for multi-UAV low-altitude networks menggunakan YOLOv8-n dan mekanisme confidence calibration untuk mendukung pengambilan keputusan dalam komunikasi semantik multi-UAV. Penelitian tersebut menunjukkan bahwa confidence calibration pada YOLOv8 telah diteliti dalam konteks penerapan tertentu.

   Research Gap: memusatkan penelitian pada evaluasi perubahan reliabilitas confidence ketika kondisi citra berubah, bukan pada penggunaan confidence untuk alokasi sumber daya komunikasi.

Berdasarkan penelusuran awal, penelitian terdahulu telah membahas kalibrasi object detection, degradasi citra pada YOLOv8, maupun penggunaan confidence terkalibrasi dalam aplikasi tertentu. Peluang penelitian yang direncanakan adalah mengevaluasi secara terstruktur hubungan antara tingkat degradasi citra, performa deteksi, dan kesesuaian confidence dengan kebenaran prediksi pada YOLOv8.

Fokus eksperimen meliputi:
- Perbandingan citra asli dan empat kondisi degradasi.
- Evaluasi performa deteksi dan kalibrasi confidence pada kondisi yang sama.
- Analisis apakah perubahan performa deteksi sejalan dengan perubahan reliabilitas confidence.
