# Avatar-Chat-YouTube-streaming
Overlay OBS berbasis HTML untuk menampilkan pesan live chat YouTube sebagai avatar animasi. Unggah sprite sheet karakter, masukkan API key dan ID video untuk memulai. Dibuat 100% Dengan AI.

**Cara Penggunaan:**

1.  **Unduh File:** Unduh file `index.html` dari repositori ini.
2.  **Siapkan Sprite Sheet Karakter:** Siapkan file gambar PNG atau GIF yang berisi sprite sheet karakter animasi yang ingin Anda gunakan. Anda dapat mengunggah beberapa file sekaligus.
3.  **Dapatkan YouTube API Key:**
    * Buka [Google Cloud Console](https://console.cloud.google.com/).
    * Buat proyek baru atau pilih proyek yang sudah ada.
    * Aktifkan YouTube Data API v3.
    * Buat kredensial (API key).
    * Salin API key yang telah dibuat.
4.  **Dapatkan ID Video YouTube:**
    * Buka video live streaming YouTube yang ingin Anda gunakan.
    * Salin ID video dari URL (biasanya berupa rangkaian karakter setelah `v=`). Contoh: `abcdefg12345`.
5.  **Buka File HTML:** Buka file `index.html` di browser Anda.
6.  **Masukkan Informasi:**
    * Klik tombol "Pilih File" dan unggah file sprite sheet karakter Anda.
    * Masukkan API key YouTube yang telah Anda dapatkan ke kolom "Kunci API YouTube".
    * Masukkan ID video YouTube ke kolom "ID Video YouTube".
7.  **Mulai:** Klik tombol "Mulai". Status akan berubah menjadi "Terhubung ke live chat..." jika berhasil.
8.  **Setup di OBS:**
    * Buka OBS Studio.
    * Tambahkan "Browser Source" baru.
    * Pada pengaturan "Sumber Browser", atur:
        * **URL:** Arahkan ke lokasi file `index.html` yang telah Anda unduh (Anda bisa menggunakan opsi "Local File").
        * **Width:** Atur lebar sesuai keinginan Anda (misalnya 1920).
        * **Height:** Atur tinggi sesuai keinginan Anda (misalnya 1080).
        * Centang **"Shutdown source when not visible"**.
        * Pastikan **"Enable custom CSS"** tidak dicentang (atau sesuaikan jika perlu).
        * Aktifkan **"Transparency"** jika ada opsi.
    * Klik "OK".
9.  **Tambahkan Filter Warna (Opsional):**
    * Klik kanan pada "Browser Source" yang baru Anda buat di OBS.
    * Pilih "Filters".
    * Klik ikon "+" di bagian bawah dan pilih "Color Key".
    * Atur pengaturan "Color Key" sebagai berikut (sesuaikan jika perlu):
        * **Key Color Type:** Pilih "Custom Color".
        * **Custom Color:** Klik kotak warna dan masukkan `#000000` (hitam).
        * **Similarity:** Sekitar 150.
        * **Smoothness:** Sekitar 80.
        * **Color Spill Reduction:** Sekitar 10.
    * Klik "Close".

Sekarang, setiap kali ada pesan baru di live chat YouTube, avatar animasi akan muncul di overlay OBS Anda.

