# Analisis TCP pada Sample Capture HTTP

Tutorial ini akan membantu Anda menganalisis alur komunikasi TCP pada sebuah sample capture HTTP menggunakan **Wireshark**. Langkah-langkah berikut akan menunjukkan cara membuka file capture dan memvisualisasikan aliran data TCP.

## Langkah-langkah Analisis

1. **Buka Aplikasi Wireshark**
   - Jalankan aplikasi **Wireshark** di komputer Anda.

2. **Buka File Capture**
   - Pilih menu **Open** di Wireshark dan cari file `http.cap` yang ingin dianalisis.
   - Klik **Open** untuk memuat file tersebut.
     # Tugas 1 - Socket Programming

Berikut adalah gambar yang menunjukkan alur komunikasi TCP pada socket programming:

![Gambar 1](https://github.com/Harrydhe/Tugas2/blob/main/assets/gambar1.jpg)


3. **Tampilkan Flow Graph**
   - Setelah file berhasil dimuat, pilih menu **Statistic** di bagian atas jendela Wireshark.
   - Klik opsi **Flow Graph** untuk menampilkan grafik aliran komunikasi TCP.
     ![Gambar 2](https://github.com/Harrydhe/Tugas2/blob/main/assets/gambar2.jpg)


Dengan langkah-langkah ini, Anda dapat dengan mudah memvisualisasikan alur komunikasi TCP yang terjadi selama proses HTTP menggunakan Wireshark. Grafik ini akan memberikan gambaran yang jelas tentang bagaimana paket TCP dikirimkan antara client dan server selama sesi HTTP.


