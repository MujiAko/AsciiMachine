# Tugas Individu: Konversi Bahasa Mesin
**Nama:** Ramzy Fadlil Agusanddawi
**NIM:** 242502040052
**Kelas:** 3TI01

---

# Dokumentasi: LexiCode Data Translator

LexiCode adalah aplikasi web sederhana yang dirancang untuk menerjemahkan input teks bahasa manusia ke dalam representasi data komputer (bahasa mesin dan enkoding) secara *real-time*.

## Cara Penggunaan
1. Buka file `index.html` menggunakan web browser (Google Chrome, Mozilla Firefox, atau Safari). Tidak perlu instalasi atau kompilasi server.
2. Masukkan kata atau kalimat pada kolom **Bahasa Manusia (Teks Input)**.
3. Aplikasi akan langsung memproses ketikan tanpa perlu menekan tombol konversi, dan hasilnya akan muncul di kartu output bagian bawah.

## Cara Kerja Sistem

Aplikasi ini menggunakan JavaScript DOM (*Document Object Model*) Event Listener untuk mendeteksi perubahan ketikan, kemudian mengeksekusi tiga tahap transformasi data:

* **Nilai ASCII (Desimal):**
  Sistem mengambil setiap karakter yang diketik, kemudian mencocokkannya dengan tabel standar ASCII menggunakan fungsi bawaan `charCodeAt()`. Contoh: Huruf "A" akan diubah menjadi angka desimal `65`.
* **Bahasa Mesin (Biner 8-bit):**
  Nilai desimal ASCII yang didapat kemudian dikonversi menjadi bilangan basis-2 (biner) menggunakan `toString(2)`. Untuk menjaga standar struktur data komputasi, sistem menambahkan fungsi `padStart(8, '0')` agar biner yang dihasilkan selalu utuh dalam format 1 *byte* (8-bit) berturut-turut.
* **Enkoding Base64:**
  Sistem mengeksekusi fungsi bawaan browser `btoa()` (Binary to ASCII) untuk merangkum representasi teks tersebut ke dalam format 64 karakter standar. Format ini biasa digunakan oleh mesin server untuk mengirim data secara aman melalui URL atau JSON.