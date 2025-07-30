Avatar Chat YouTube (Versi Gratis Stream Avatars)

Overlay OBS berbasis HTML ini memungkinkan Anda menampilkan pesan dari live chat YouTube sebagai avatar animasi yang bergerak. Ini adalah alternatif gratis dan sangat dapat disesuaikan untuk fitur Stream Avatars yang populer, dibuat sepenuhnya dengan bantuan AI!

---

## ✨ Fitur Utama & Update Terbaru:

* **Avatar Animasi Random:** Unggah beberapa sprite sheet karakter (PNG/GIF), dan avatar akan muncul secara acak dari koleksi Anda.
* **Animasi Gerakan Alami:** Avatar bergerak secara horizontal, memantul di dinding, dan memiliki sedikit efek gravitasi.
* **Lompat Berbasis Komentar:** Avatar akan melompat secara periodik setiap 2 detik hanya jika komentar yang memicu kemunculannya mengandung kata "lompat" (tidak case-sensitive).
* **Bubble Chat Kustom:**
    * **Warna Bervariasi Subscriber:** Bubble chat dari subscriber memiliki warna yang bervariasi untuk mudah dibedakan.
    * **Bubble Chat Pemilik Channel Unik:** Pesan dari pemilik channel ditampilkan dengan bubble chat berwarna emas dan ikon mahkota di atasnya.
    * **Anti-Tumpuk (Tumpang Tindih):** Bubble chat akan otomatis menyesuaikan posisi Y (naik) untuk menghindari tumpang tindih dengan bubble chat lain, memastikan semua komentar tetap terlihat jelas.
    * **Pointer Runcing:** Bubble chat memiliki pointer runcing yang mengarah tepat di atas kepala karakter, dan akan memanjang jika bubble chat terpaksa naik akibat tumpukan.
* **Panel Kontrol Penuh:**
    * **Hide/Show Panel:** Panel kontrol dapat disembunyikan/ditampilkan dengan tombol toggle (☰ / ✕) yang selalu terlihat.
    * **Panel Scrollable:** Panel kontrol dapat di-scroll jika kontennya terlalu banyak, memastikan semua pengaturan tetap dapat diakses.
    * **Ukuran Canvas Dinamis:** Atur lebar dan tinggi canvas melalui slider. Ukuran canvas akan otomatis menyesuaikan agar tidak melebihi ukuran viewport browser Anda (berguna untuk OBS).
    * **Kontrol Realtime:**
        * **Ukuran Avatar:** Sesuaikan ukuran avatar secara realtime.
        * **Durasi Avatar:** Tentukan berapa lama avatar dan bubble chat akan bertahan di layar (dalam detik).
        * **Kecepatan Gerak Avatar:** Kontrol kecepatan horizontal semua avatar secara realtime.

---

## 🚀 Cara Penggunaan:

1.  **Unduh Aplikasi:**
    * Unduh seluruh folder/repositori ini. Pastikan Anda mendapatkan semua file, terutama `index.html`.
    * Anda bisa mengunduhnya sebagai file ZIP atau melakukan `git clone`.

2.  **Siapkan Sprite Sheet Karakter:**
    * Buat atau dapatkan file gambar **PNG** atau **GIF** yang berisi sprite sheet karakter animasi Anda.
    * Untuk sprite sheet PNG, disarankan setiap frame karakter berukuran **100x100 piksel**. Aplikasi akan memecah gambar Anda menjadi frame-frame 100x100px secara otomatis.
    * Anda dapat mengunggah **beberapa** file sprite sheet sekaligus.

3.  **Dapatkan YouTube Data API Key:**
    * Buka [Google Cloud Console](https://console.cloud.google.com/).
    * Buat proyek baru atau pilih proyek yang sudah ada.
    * Navigasi ke "APIs & Services" > "Enabled APIs & Services".
    * Cari dan aktifkan **"YouTube Data API v3"**.
    * Navigasi ke "APIs & Services" > "Credentials".
    * Klik "CREATE CREDENTIALS" dan pilih "API Key".
    * **PENTING: Lindungi API Key Anda!**
        * Klik "RESTRICT KEY".
        * **Application restrictions:** Pilih "HTTP referrers (web sites)" dan tambahkan URL tempat Anda akan membuka file HTML ini (misalnya `file:///` untuk lokal, atau `*.github.io/*`, `*.netlify.app/*`, `*localhost*` jika di-hosting). Ini mencegah orang lain menggunakan kunci Anda dari situs mereka.
        * **API restrictions:** Pilih "Restrict key" dan pastikan hanya **"YouTube Data API v3"** yang diizinkan.
    * Salin API key yang telah dibuat.

4.  **Dapatkan ID Video YouTube:**
    * Buka video live streaming YouTube yang ingin Anda gunakan.
    * Salin ID video dari URL (biasanya berupa rangkaian karakter setelah `v=`).
    * Contoh: Untuk `https://www.youtube.com/watch?v=abcdefg12345`, ID videonya adalah `abcdefg12345`.

5.  **Buka Aplikasi di Browser:**
    * Buka file `index.html` dari folder yang sudah Anda unduh di browser pilihan Anda (Chrome, Firefox, Edge, dll.).

6.  **Konfigurasi Aplikasi:**
    * Di panel kontrol yang muncul di sisi kanan:
        * Klik **"Upload Sprite Sheet karakter(PNG)"** dan pilih satu atau lebih file sprite sheet Anda.
        * Masukkan **API key YouTube** Anda ke kolom yang tersedia.
        * Masukkan **ID video YouTube** live streaming Anda ke kolom yang tersedia.
    * Gunakan slider di bawah "Size Controls" untuk mengatur:
        * **Lebar Canvas** dan **Tinggi Canvas**: Sesuaikan ukuran area tampilan avatar di OBS.
        * **Ukuran Avatar**: Mengatur ukuran tampilan karakter.
        * **Durasi Avatar (detik)**: Mengatur berapa lama avatar dan bubble chat akan tetap muncul.
        * **Kecepatan Avatar**: Mengontrol kecepatan gerak horizontal avatar secara realtime.
    * Anda bisa menyembunyikan panel kontrol dengan mengklik tombol **"✕"** di pojok kanan atas, dan menampilkannya kembali dengan tombol **"☰"**.

7.  **Mulai Integrasi Live Chat:**
    * Klik tombol **"Mulai"**.
    * Status di bawah tombol akan berubah menjadi "Terhubung ke live chat..." jika koneksi berhasil.

8.  **Setup di OBS Studio:**
    * Buka OBS Studio.
    * Tambahkan "Browser Source" baru ke Scene Anda.
    * Pada jendela pengaturan "Sumber Browser", atur:
        * **URL:** Centang **"Local File"** dan klik **"Browse"** untuk memilih file `index.html` yang Anda unduh.
        * **Width:** Masukkan nilai **"Lebar Canvas"** yang Anda atur di panel kontrol aplikasi Anda.
        * **Height:** Masukkan nilai **"Tinggi Canvas"** yang Anda atur di panel kontrol aplikasi Anda.
        * Centang **"Shutdown source when not visible"** (untuk menghemat resource saat overlay tidak aktif).
        * Pastikan **"Refresh browser when scene becomes active"** juga dicentang jika Anda ingin mereset overlay setiap kali scene diaktifkan.
        * Pastikan **"Control audio via OBS"** dicentang jika Anda ingin mengelola audio overlay dari OBS.
    * Klik "OK".

9.  **Tambahkan Filter Color Key (untuk menghilangkan background hitam):**
    * Di OBS, klik kanan pada "Browser Source" yang baru Anda buat di daftar "Sources".
    * Pilih **"Filters"**.
    * Di bagian "Effect Filters", klik ikon **"+"** dan pilih **"Color Key"**.
    * Atur pengaturan "Color Key" sebagai berikut (nilai rekomendasi):
        * **Key Color Type:** Pilih "Custom Color".
        * **Custom Color:** Klik kotak warna dan masukkan `#000000` (hitam).
        * **Similarity:** Sesuaikan (mulai dari sekitar `150`).
        * **Smoothness:** Sesuaikan (mulai dari sekitar `80`).
        * **Color Spill Reduction:** Sesuaikan (mulai dari sekitar `10`).
    * Klik "Close".

---

Sekarang, setiap kali ada pesan baru dari subscriber atau pemilik channel di live chat YouTube Anda, avatar animasi akan muncul di overlay OBS Anda! Jika pesan mengandung kata "lompat", avatar akan melompat secara periodik.

---

**Dibuat menggunakan AI yang dipandu oleh Bungza.**
