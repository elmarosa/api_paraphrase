README – Menjalankan API Paraphrase Model mt5-small

Menjalankan API Paraphrase dengan Model mt5-smallDokumen ini menjelaskan cara menjalankan API Paraphrase Generation Bahasa Indonesia menggunakan model mt5-small yang telah melalui proses fine-tuning. API dibangun menggunakan Flask dan dapat diakses secara publik menggunakan Ngrok.

1. Struktur Model
Model hasil fine-tuning disimpan secara lokal pada Google Drive dengan direktori berikut:

MODEL_DIR = "/content/drive/MyDrive/UAS DEEPL FIX/best_mt5_paraphrase"

Direktori tersebut berisi file model hasil pelatihan (best model) yang akan dimuat oleh API pada saat server dijalankan.

2. Persiapan Lingkungan
Pastikan lingkungan telah memenuhi kebutuhan berikut:
Python 3.x
- Library utama:
- torch
- transformers
- flask
- pyngrok
Akses ke Google Drive (jika dijalankan di Google Colab)
Pastikan Google Drive telah di-mount agar path MODEL_DIR dapat diakses dengan benar.

3. Menjalankan API
API dijalankan menggunakan Flask dengan memuat model dari direktori MODEL_DIR. Setelah server Flask aktif, Ngrok digunakan untuk membuat public URL sehingga API dapat diakses dari luar lingkungan lokal.
Endpoint utama yang disediakan oleh API adalah:

POST /paraphrase

Endpoint ini menerima input teks dan mengembalikan hasil parafrase dalam format JSON.

5. Format Response
Jika request berhasil diproses, API akan mengembalikan respons dalam format JSON:
{
  "input": "Teks asli",
  "paraphrase": "Hasil parafrase dari model"
}
Status 200 OK menandakan bahwa model berhasil memproses input dan menghasilkan keluaran yang valid.

6. Catatan
- Model yang digunakan adalah mt5-small yang telah di-fine-tune khusus untuk tugas paraphrase generation Bahasa Indonesia.
- API ini dirancang untuk kebutuhan pengujian dan demonstrasi model, serta dapat dikembangkan lebih lanjut untuk integrasi ke sistem lain.
- Pastikan path MODEL_DIR sesuai dengan lokasi penyimpanan model agar proses pemuatan model tidak mengalami error.