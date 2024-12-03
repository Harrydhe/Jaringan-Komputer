# DNS dan SMTP

# Apa Itu DNS?

**DNS (Domain Name System)** adalah sistem yang berfungsi menerjemahkan nama domain yang mudah diingat oleh manusia (seperti `google.com`) menjadi alamat IP yang merupakan serangkaian angka yang digunakan komputer untuk berkomunikasi di internet. Bayangkan DNS sebagai buku telepon raksasa yang menghubungkan nama dengan nomor telepon.

## Mengapa DNS Penting?

- **Kemudahan Pengingat**: Kita lebih mudah mengingat "google.com" daripada "142.250.186.142".
- **Efisiensi**: DNS membuat pencarian alamat IP menjadi lebih cepat.
- **Fleksibilitas**: Perubahan alamat IP tidak langsung memengaruhi akses ke situs web.


## Diagram Alir Kerja DNS

![Cara kerja DNS](https://github.com/Harrydhe/Tugas4--DNS/blob/main/assets/DNS.png)

## Komponen Utama DNS

- **DNS Resolver**: Komputer atau perangkat lunak yang melakukan pencarian alamat IP.
- **Root Server**: Server tingkat atas yang mengarahkan permintaan ke server DNS otoritatif.
- **Server DNS Otoritatif**: Server yang memiliki informasi lengkap tentang nama domain.
- **Cache**: Tempat penyimpanan sementara untuk menyimpan hasil pencarian DNS.


**DNS (Domain Name System)** adalah sistem yang berfungsi untuk menerjemahkan nama domain yang mudah diingat (seperti `google.com`) menjadi alamat IP yang digunakan oleh komputer untuk berkomunikasi di internet.

## 1. Hierarki DNS

DNS memiliki struktur hierarkis yang mirip dengan sistem direktori pada komputer. Hierarki ini dimulai dari:

- **Root Server**: Tingkat paling atas dalam hierarki DNS. Ada beberapa root server di seluruh dunia yang berfungsi sebagai titik awal untuk semua permintaan DNS.
- **TLD Server (Top-Level Domain)**: Server yang menangani domain tingkat atas seperti `.com`, `.net`, `.org`, dan sebagainya.
- **Authoritative Server**: Server yang memiliki informasi spesifik tentang sebuah domain. Biasanya dikelola oleh pemilik domain.
- **Recursive Resolver**: Server yang melakukan pencarian DNS atas nama klien.

## 2. Jenis-Jenis Record DNS

Selain alamat IP (tipe A), DNS juga mendukung berbagai jenis record lainnya, seperti:

- **AAAA**: Untuk alamat IPv6.
- **CNAME**: Alias untuk nama domain lain.
- **MX**: Untuk server mail exchange (server email).
- **NS**: Untuk server name server (server DNS otoritatif).
- **TXT**: Untuk menyimpan teks, sering digunakan untuk verifikasi domain.

## 3. DNS Caching

**DNS caching** adalah proses menyimpan hasil pencarian DNS secara sementara untuk mempercepat permintaan DNS di masa mendatang. Cache DNS dapat berada di berbagai tingkat, mulai dari browser, sistem operasi, hingga DNS resolver.

## 4. DNS Over HTTPS (DoH)

**DoH (DNS Over HTTPS)** adalah protokol yang mengenkripsi lalu lintas DNS melalui HTTPS, sehingga meningkatkan privasi pengguna. Dengan DoH, ISP tidak dapat melihat situs web yang Anda kunjungi.

## 5. DNS Over TLS (DoT)

**DoT (DNS Over TLS)** juga merupakan protokol yang mengenkripsi lalu lintas DNS, tetapi menggunakan TLS sebagai protokol transport.

## 6. DNSSEC

**DNSSEC (DNS Security Extensions)** adalah mekanisme keamanan yang dirancang untuk melindungi DNS dari pemalsuan. DNSSEC menggunakan tanda tangan digital untuk memverifikasi integritas data DNS.

## 7. Masalah Umum pada DNS

Beberapa masalah umum yang terjadi pada DNS antara lain:

- **DNS Hijacking**: Serangan di mana peretas mengalihkan lalu lintas DNS ke server palsu.
- **DNS Amplification**: Serangan DDoS yang memanfaatkan DNS untuk memperkuat serangan.
- **DNS Cache Poisoning**: Serangan yang menyuntikkan data palsu ke dalam cache DNS.

## Cara Kerja DNS Secara Lebih Detail

### Proses Resolusi DNS

1. **Pengguna Memasukkan Nama Domain**:
   - Pengguna mengetikkan nama domain di browser.
   
2. **Permintaan ke DNS Resolver**:
   - Browser mengirimkan permintaan ke DNS resolver yang terdekat.

3. **Pencarian di Cache Lokal**:
   - DNS resolver memeriksa cache lokalnya terlebih dahulu. Jika ditemukan, alamat IP langsung diberikan.

4. **Permintaan ke Root Server**:
   - Jika tidak ditemukan di cache lokal, permintaan diteruskan ke root server.

5. **Permintaan ke TLD Server**:
   - Root server mengarahkan permintaan ke TLD server yang sesuai.

6. **Permintaan ke Authoritative Server**:
   - TLD server mengarahkan permintaan ke authoritative server untuk domain tersebut.

7. **Mendapatkan Alamat IP**:
   - Authoritative server memberikan alamat IP kepada DNS resolver.

8. **Kembali ke Browser**:
   - DNS resolver mengembalikan alamat IP ke browser.

9. **Koneksi ke Server Web**:
   - Browser menggunakan alamat IP untuk terhubung ke server web.

## Contoh Kasus Penggunaan DNS

- **Akses ke Situs Web**: Setiap kali Anda mengunjungi situs web, DNS menerjemahkan nama domain menjadi alamat IP.
- **Email**: DNS digunakan untuk menemukan server mail exchange (MX) untuk mengirim dan menerima email.
- **Aplikasi Jaringan**: Banyak aplikasi jaringan menggunakan DNS untuk menemukan server yang diperlukan.

## Kesimpulan

DNS adalah komponen penting dalam infrastruktur internet. Dengan memahami cara kerjanya, Anda akan lebih memahami bagaimana internet berfungsi dan bagaimana data mengalir dari satu perangkat ke perangkat lainnya.


# SMTP: Simple Mail Transfer Protocol

SMTP (Simple Mail Transfer Protocol) adalah protokol standar yang digunakan untuk mengirimkan email dari satu server ke server lainnya. Secara sederhana, SMTP berfungsi seperti "kurir" yang mengantarkan pesan email dari pengirim ke penerima.

## Cara Kerja SMTP

### Komposisi Pesan Email
Pengguna membuat pesan email yang berisi:
- **Alamat email pengirim**
- **Alamat email penerima**
- **Subjek**
- **Isi pesan**
- **Lampiran** (jika ada)

### Pengiriman ke Server SMTP
Klien email (misalnya, Outlook, Gmail) akan mengirimkan pesan ke server SMTP yang dikelola oleh penyedia email (misalnya, Google, Yahoo).

### Proses di Server SMTP
1. **Penerimaan Pesan**: Server SMTP menerima pesan dan melakukan verifikasi awal terhadap alamat email pengirim dan penerima.
2. **Pencarian Server Penerima**: Server SMTP mencari tahu server SMTP mana yang menangani alamat email penerima. Ini dilakukan dengan menggunakan DNS (Domain Name System).
3. **Transfer Pesan**: Pesan email diteruskan ke server SMTP penerima.
4. **Pengantaran ke Kotak Masuk**: Server SMTP penerima menyimpan pesan email di kotak masuk penerima.

### Notifikasi Pengiriman
Server SMTP pengirim mengirimkan notifikasi kepada pengirim mengenai status pengiriman pesan (berhasil atau gagal).

## Diagram Alir Kerja SMTP
![SMTP Workflow Diagram](https://www.afternerd.com/smtp-workflow)

### Keterangan Diagram:
- **MUA (Mail User Agent)**: Klien email yang digunakan pengguna (misalnya, Outlook, Gmail).
- **MTA (Mail Transfer Agent)**: Server SMTP yang mengelola pengiriman email.
- **DNS**: Domain Name System yang digunakan untuk mencari alamat IP server SMTP penerima.

## Fungsi Utama SMTP
- **Mentransfer Pesan Email**: SMTP bertanggung jawab atas pengiriman pesan email dari satu server ke server lainnya.
- **Verifikasi Alamat Email**: SMTP memverifikasi apakah alamat email penerima valid atau tidak.
- **Pengiriman Notifikasi**: SMTP mengirimkan notifikasi kepada pengirim mengenai status pengiriman pesan.

## Kelebihan SMTP
- **Standar Industri**: SMTP sudah menjadi protokol standar di seluruh dunia.
- **Keamanan**: SMTP mendukung berbagai mekanisme keamanan seperti TLS/SSL untuk melindungi data yang dikirimkan.
- **Fleksibilitas**: SMTP dapat digunakan untuk mengirimkan berbagai jenis lampiran.

## Kekurangan SMTP
- **Hanya untuk Pengiriman**: SMTP hanya digunakan untuk mengirimkan email, tidak untuk menerima email.
- **Tidak Real-time**: Proses pengiriman email menggunakan SMTP tidak selalu real-time.

