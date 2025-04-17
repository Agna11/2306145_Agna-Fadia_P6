# 2306145_Agna-Fadia_P6
🔗 Penjelasan Forward Chaining dan Backward Chaining
Dalam sistem pakar seperti yang kamu buat dengan experta, ada dua pendekatan utama dalam penalaran berbasis aturan (rule-based reasoning), yaitu:

🔄 Forward Chaining (Penelusuran Maju)
🧠 Apa itu?
Forward chaining (penelusuran maju) adalah proses memulai dari data atau fakta awal, lalu menerapkan aturan-aturan yang cocok untuk mencapai kesimpulan.
🚀 Cocok untuk:
1. Sistem diagnosa seperti ini, di mana pengguna memasukkan gejala, dan sistem menarik kesimpulan.
2. Kondisi di mana semua data awal sudah diketahui.
🛠️ Cara kerja singkat:
1. Gunakan semua fakta/gejala yang diketahui.
2. Cek aturan yang bisa dipicu (match).
3. Jalankan aturan itu (fire rule).
4. Tambah fakta baru jika ada, ulangi sampai tidak ada aturan yang cocok lagi.
5. Tampilkan hasil diagnosis.
📌 Contoh dalam kode:
python
engine.declare(Fact(cough=True, fever=True, fatigue=True))
engine.run()

Program akan memulai dari fakta ini, dan menjalankan aturan yang sesuai, misalnya:
python
@Rule(Fact(cough=True) & Fact(fever=True) & Fact(fatigue=True))
def flu(self):
    print("Diagnosis: You may have the Flu.")
    
🔙 Backward Chaining (Penelusuran Mundur)
🧠 Apa itu?
Backward chaining adalah metode penalaran yang dimulai dari hipotesis atau tujuan (misalnya: "Apakah saya flu?"), lalu sistem menelusuri ke belakang untuk memverifikasi apakah fakta-fakta pendukungnya benar.
🔍 Cocok untuk:
1. Sistem di mana pengguna ingin memverifikasi sesuatu.
2. Situasi troubleshooting atau decision making berdasarkan tujuan tertentu.
🛠️ Cara kerja singkat:
1. Mulai dari sebuah tujuan/hipotesis.
2. Cek aturan mana yang bisa membuktikan tujuan itu.
3. Periksa apakah syarat-syarat aturan itu benar.
4. Jika syarat belum diketahui, telusuri lebih lanjut (recursive).
5. Jika semua syarat benar, tujuan terbukti.
📌 Contoh:
Tujuan: "Apakah saya kena Flu?"
Sistem akan periksa: "Apakah ada fakta bahwa batuk=True, demam=True, lelah=True?"
Jika belum diketahui, sistem akan bertanya ke pengguna untuk memverifikasi.

🤔 Perbedaan Sederhana
🔍 Perbandingan     	Forward Chaining	            Backward Chaining
💡 Dimulai dari     	Fakta/gejala	                Tujuan/hipotesis
🔄 Arah penalaran	    Maju ke kesimpulan	          Mundur ke pembuktian fakta
🎯 Tujuan	            Temukan semua kesimpulan    	Buktikan satu kesimpulan
🧪 Cocok untuk	      Diagnosa, data-driven system	Troubleshooting, goal-driven
