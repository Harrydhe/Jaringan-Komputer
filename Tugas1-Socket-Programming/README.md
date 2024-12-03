# Socket-Programming

# Analisis TCP pada Simple Socket Programming

Tutorial ini menjelaskan bagaimana TCP bekerja pada Socket Programming dengan bantuan **Wireshark**. Dalam tutorial ini, Anda akan membuat program socket sederhana dan menggunakan Wireshark untuk menganalisis paket TCP yang dikirimkan selama komunikasi antara client dan server.

## Persiapan Program Socket

Ikuti langkah-langkah berikut untuk mempersiapkan program socket:

1. **Buka direktori Program Socket**
   - Masuk ke direktori `/simple-socket-programming`:
     ```bash
     cd /simple-socket-programming
     ```

2. **Sesuaikan Port Number di File Server**
   - Buka file `server.c` dan sesuaikan port number pada baris ke-40:
     ```c
     const uint16_t port_number = 50000;
     ```
   - Pastikan port number yang digunakan adalah `50000`.

3. **Sesuaikan Port Number di File Client**
   - Buka file `client.c` dan sesuaikan nilai port number pada baris ke-19:
     ```c
     portno = 50000;
     ```
   - Pastikan nilai port number di file client sama dengan file server.

## Menjalankan Program Socket

1. **Buka Terminal**
   - Buka terminal pada aplikasi Anda.

2. **Masuk ke Direktori Program**
   - Arahkan terminal ke direktori tempat program berada:
     ```bash
     cd {path_to_root_dir}/tugas-1/simple-socket-programming
     ```

3. **Kompilasi Program**
   - Jalankan perintah `make` untuk mengompilasi program:
     ```bash
     make
     ```

4. **Jalankan Aplikasi Wireshark**
   - Untuk menganalisis lalu lintas jaringan menggunakan Wireshark, jalankan Wireshark dengan perintah:
     ```bash
     sudo wireshark
     ```

5. **Pilih Loopback Interface**
   - Di Wireshark, pilih interface **Loopback: lo0** untuk menangkap paket yang dikirimkan melalui jaringan lokal.

   ![Loopback](https://github.com/Harrydhe/Tugas1-Socket-Programming/blob/main/assets/gambar1.jpg)


6. **Jalankan Aplikasi Server**
   - Jalankan aplikasi server dengan perintah berikut:
     ```bash
     sudo ./server
     ```

7. **Jalankan Aplikasi Client**
   - Jalankan aplikasi client dengan perintah berikut:
     ```bash
     sudo ./client
     ```

8. **Kirim Plaintext ke Server**
   - Setelah aplikasi client berjalan, kirimkan pesan plaintext ke server. Anda dapat memasukkan teks atau pesan apa pun yang ingin dikirimkan melalui socket ke server.

    ![plaintext](https://github.com/Harrydhe/Tugas1-Socket-Programming/blob/main/assets/gambar2.jpg)

## Menganalisis Wireshark

Untuk menganalisis paket TCP yang dikirimkan antara client dan server menggunakan Wireshark, ikuti langkah-langkah berikut:

1. **Klik Kanan pada Paket yang Akan Di-stream**
   - Cari paket yang menggunakan port address **50000**.
   - Klik kanan pada paket tersebut.

2. **Follow -> TCP Stream**
   - Pilih opsi `Follow -> TCP Stream` untuk melihat semua paket yang terkait dengan koneksi TCP tersebut.

    ![TCPstream](https://github.com/Harrydhe/Tugas1-Socket-Programming/blob/main/assets/gambar3.jpg)


3. **Tampilkan Hanya Paket yang Di-stream**
   - Wireshark akan memfilter dan menampilkan hanya paket TCP yang terkait dengan stream tersebut.
  
        ![Tampil](https://github.com/Harrydhe/Tugas1-Socket-Programming/blob/main/assets/gambar4.jpg)
 

4. **Pilih Menu Statistic -> Flow Graph**
   - Klik menu `Statistic` di bagian atas aplikasi Wireshark.
   - Pilih opsi `Flow Graph` untuk menampilkan grafik alur TCP.
  
      ![Flowgraph](https://github.com/Harrydhe/Tugas1-Socket-Programming/blob/main/assets/gambar5.jpg)


5. **Tampilkan Hasil Flow Graph TCP**
   - Di jendela Flow Graph, centang **Limit to display filter**.
   - Pilih **Flow type: TCP Flows** untuk memvisualisasikan alur paket TCP.
  
      ![Flowgraph](https://github.com/Harrydhe/Tugas1-Socket-Programming/blob/main/assets/gambar6.jpg)


Dengan langkah-langkah di atas, Anda dapat menganalisis alur komunikasi TCP secara mendalam menggunakan Wireshark dan memvisualisasikannya dalam bentuk grafik.




