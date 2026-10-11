# riset-yolov8-reliability
Riset tentang reliabilitas confidence YOLOv8 pada berbagai tingkat degradasi citra dengan rencana judul "Analisis Reliabilitas Confidence YOLOv8 sebagai One-Stage Detector pada Berbagai Tingkat Degradasi Citra"

1. Formulasi Masalah
   - Bagaimana perubahan performa deteksi YOLOv8 pada berbagai tingkat degradasi citra?
   - Bagaimana perubahan confidence score YOLOv8 ketika tingkat degradasi citra meningkat?
   - Apakah confidence score yang tinggi tetap berkaitan dengan prediksi yang benar pada citra terdegradasi?
   - Bagaimana perubahan reliabilitas confidence YOLOv8 jika dievaluasi berdasarkan kebenaran prediksi dan calibration error?

2. Research Gap Penelitian Terdahulu
   - Huseljic et al. (2025)
     Penelitian Systematic Evaluation of Uncertainty Calibration in Pretrained Object Detectors membahas evaluasi uncertainty calibration pada object detector, termasuk ketika menghadapi distribution shift dan out-of-distribution data. Penelitian tersebut menggunakan Faster R-CNN dan DETR serta mengevaluasi pengaruh post-processing dan pilihan metrik terhadap calibration. Penelitian ini menjadi landasan untuk memahami bahwa performa deteksi dan reliabilitas probabilistik merupakan dua aspek yang perlu dievaluasi secara berbeda.
     Research Gap: menguji reliabilitas confidence pada YOLOv8 sebagai one-stage detector dengan eksperimen degradasi citra yang terkontrol.
   - Yoon dan Kim (2026)
     Penelitian Non-linear Performance Degradation Mechanism and Quantitative Inflection Point Identification of AI-based Pedestrian and Vehicle Detection Reliability under Image Data Degradation: A Case Study on the COCO Dataset with YOLOv8 menggunakan YOLOv8 Nano dan COCO 2017 untuk menganalisis dampak penurunan resolusi dan kompresi JPEG terhadap reliability deteksi person dan car. Penelitian ini menemukan bahwa confidence tidak selalu menurun secara linear ketika kualitas citra mengalami degradasi. Penelitian baru tidak cukup hanya mengulang pengukuran penurunan confidence akibat resolusi atau JPEG compression.
     Research Gap: menganalisis hubungan antara confidence dan kebenaran setiap prediksi pada beberapa tingkat degradasi, dengan evaluasi yang secara eksplisit mempertimbangkan kecocokan kelas dan bounding box terhadap ground truth.
   - Zheng et al. (2026)
     Penelitian Confidence-calibrated semantic resource allocation for multi-UAV low-altitude networks menggunakan YOLOv8-n dan mekanisme confidence calibration untuk mendukung pengambilan keputusan dalam komunikasi semantik multi-UAV. Penelitian tersebut menunjukkan bahwa confidence calibration pada YOLOv8 telah diteliti dalam konteks penerapan tertentu.
     Research Gap: memusatkan penelitian pada evaluasi perubahan reliabilitas confidence ketika kondisi citra berubah, bukan pada penggunaan confidence untuk alokasi sumber daya komunikasi.

3. Peluang Pengembangan
   - Analisis berbagai jenis degradasi citra
     Penelitian dapat menggunakan transformasi citra seperti Gaussian blur untuk mensimulasikan citra tidak fokus ataupun JPEG compression untuk mensimulasikan penurunan kualitas akibat kompresi. Jenis degradasi tambahan, seperti noise atau perubahan pencahayaan, dapat dipertimbangkan jika diperlukan. Namun, penelitian awal akan dibatasi agar eksperimen tetap realistis.
    - Analisis berbagai tingkat degradasi
      Setiap jenis degradasi dapat diberikan beberapa tingkat keparahan, mulai dari ringan hingga berat. Tujuannya untuk mengamati apakah perubahan confidence berlangsung sejalan dengan perubahan kebenaran prediksi atau terdapat kondisi ketika confidence menjadi kurang reliable.
    - Evaluasi berdasarkan kebenaran prediksi
      Prediksi model akan dicocokkan dengan ground truth menggunakan kesesuaian kelas dan Intersection over Union (IoU). Hasil pencocokan digunakan untuk menentukan prediksi yang benar dan salah sesuai aturan evaluasi yang ditetapkan. Dengan demikian, penelitian tidak hanya melihat apakah confidence menurun, tetapi juga apakah confidence tersebut tetap mencerminkan kebenaran prediksi.
    - Pengembangan Lanjutan
      Jika penelitian awal menunjukkan hasil yang memadai, penelitian selanjutnya dapat mengevaluasi metode post-hoc calibration, membandingkan model object detection lain, atau menguji dataset dari domain berbeda
   
5. Rencana Topik
   Analisis Reliabilitas Confidence YOLOv8 sebagai One-Stage Detector pada Berbagai Tingkat Degradasi Citra. Berikut Tujuan Penelitian.
   - Menganalisis perubahan performa deteksi YOLOv8 pada berbagai tingkat degradasi citra.
   - Menganalisis perubahan confidence score YOLOv8 akibat degradasi citra.
   - Mengevaluasi hubungan confidence score dengan kebenaran hasil deteksi.
   - Membandingkan reliabilitas confidence pada citra original dan citra terdegradasi menggunakan metrik evaluasi yang sesuai.

7. Sumber Data
   - Nama Repository Dataset Riset Saya
     riset-yolov8-reliability
   - Alamat Github/Kaggle dll
     1. Ultralytics YOLO
        https://github.com/ultralytics/ultralytics
        Digunakan sebagai sumber implementasi model YOLO untuk inferensi dan evaluasi deteksi objek.
     2. Uncertainty Object Detection — Huseljic et al.
        https://github.com/ies-research/uncertainty-object-detection
        Repository implementasi penelitian terdahulu mengenai evaluasi uncertainty calibration pada object detector.
   - Referensi Jurnal
     1. Huseljic, D., Herde, M., Hahn, P., Müjde, M., & Sick, B. (2025). Systematic Evaluation of Uncertainty Calibration in Pretrained Object Detectors. International Journal of Computer Vision, 133, 1033–1047. https://doi.org/10.1007/s11263-024-02219-z
     2. Yoon, Y. D., & Kim, H. (2026). Non-linear Performance Degradation Mechanism and Quantitative Inflection Point Identification of AI-based Pedestrian and Vehicle Detection Reliability under Image Data Degradation: A Case Study on the COCO Dataset with YOLOv8. The Journal of the Korea Contents Association, 26(8), 71–85. https://kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003372848
     3. Zheng, W., Li, J., & Zuo, Y. (2026). Confidence-calibrated semantic resource allocation for multi-UAV low-altitude networks. Journal on Wireless Communications and Networking, 2026, Article 112. https://doi.org/10.1186/s13638-026-02655-0

