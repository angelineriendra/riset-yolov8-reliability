RENCANA EVALUATION METRIC

[METRIK PERFORMA DETEKSI]
1. mAP

   Tujuan       : mengukur performa deteksi secara keseluruhan

   Interpretasi : nilai lebih tinggi artinya menunjukkan performa deteksi lebih baik
2. Precision

   Tujuan       : mengukur proporsi prediksi positif yang benar

   Interpretasi : precision tinggi menunjukkan lebih sedikit false positive relatif terhadap jumlah prediksi positif
3. Recall

   Tujuan       : mengukur proporsi objek ground truth yang berhasil ditemukan

   Interpretasi : recall tinggi menunjukkan lebih sedikit objek yang terlewat

Untuk mAP, penelitian akan menggunakan protokol evaluasi COCO yang sesuai. Precision dan recall juga dihitung menggunakan aturan evaluasi yang konsisten.

[METRIK RELIABILITAS CONFIDENCE]
1. Distribusi Confidence
   Tujuan       : mengamati sebaran skor confidence

   Interpretasi : menunjukkan perubahan skor pada kondisi yang berbeda
2. Expected Calibration Error (ECE)

   Tujuan       : mengukur selisih confidence rata-rata dan proporsi prediksi benar pada kelompok confidence

   Interpretasi : nilai lebih rendah menunjukkan kalibrasi lebih baik
4. Reliability Diagram

   Tujuan       : memvisualisasikan confidence dan proporsi prediksi benar

   Interpretasi : kurva yang lebih dekat dengan garis ideal menunjukkan kalibrasi yang lebih baik

ECE bukan ukuran performa deteksi secara langsung. Penghitungan ECE untuk object detection harus menetapkan cara pencocokan prediksi dengan ground truth, definisi prediksi benar, pembagian bin confidence, dan perlakuan terhadap false positive serta objek yang tidak terdeteksi.

Brier Score dapat dipertimbangkan sebagai metrik tambahan jika definisi target kebenaran dan skema penghitungan probabilistik telah ditetapkan secara tepat.
