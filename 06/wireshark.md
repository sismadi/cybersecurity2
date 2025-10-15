## **Deskripsi Wireshark**

**Wireshark** adalah aplikasi *network protocol analyzer* (penganalisis protokol jaringan) yang bersifat **open-source** dan gratis. Program ini memungkinkan pengguna untuk **menangkap (capture)** dan **menganalisis paket data** yang melintasi jaringan secara real-time atau dari file hasil tangkapan sebelumnya.

Wireshark dapat digunakan pada berbagai sistem operasi seperti **Linux, Windows, dan macOS**, dan mendukung ratusan protokol jaringan (TCP, UDP, HTTP, DNS, ARP, ICMP, SSL/TLS, dan lain-lain).

---

## **Fungsi Wireshark**

| Fungsi                                      | Penjelasan                                                                                                   |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| **1. Network Troubleshooting**              | Menganalisis masalah jaringan seperti latensi tinggi, paket hilang (packet loss), atau koneksi tidak stabil. |
| **2. Network Security Analysis**            | Mendeteksi aktivitas mencurigakan seperti serangan *DoS*, *ARP spoofing*, atau *port scanning*.              |
| **3. Protocol Analysis**                    | Melihat dan memahami cara kerja protokol jaringan secara rinci (misalnya TCP handshake, DNS query).          |
| **4. Network Performance Monitoring**       | Mengukur kecepatan transfer data, throughput, dan latensi jaringan.                                          |
| **5. Forensik Digital (Network Forensics)** | Menelusuri bukti digital melalui lalu lintas jaringan yang ditangkap.                                        |
| **6. Pembelajaran dan Penelitian**          | Dipakai di dunia akademik untuk mempelajari arsitektur jaringan dan debugging aplikasi berbasis jaringan.    |

---

## **Implementasi & Cara Penggunaan Wireshark**

### **Langkah-langkah Dasar:**

#### **1. Instalasi**

Wireshark dapat diinstal dengan:

```bash
sudo apt install wireshark
```

(untuk Ubuntu/Debian)

#### **2. Menjalankan Wireshark**

Buka dari menu aplikasi atau terminal dengan perintah:

```bash
wireshark
```

#### **3. Memilih Interface**

Pada tampilan awal (seperti gambar Anda), pilih **interface jaringan** yang ingin dianalisis, misalnya:

* `eth0` → Ethernet
* `wlan0` → Wi-Fi
* `lo` → Loopback (localhost)
* `randpkt` → Simulasi paket acak (untuk belajar/testing)
* `sdjournal` → Menangkap log dari systemd Journal

#### **4. Memulai Capture**

Klik tombol **Start Capturing Packets** (ikon hiu biru di kiri atas) untuk mulai menangkap paket.

#### **5. Menyaring Data (Display Filter)**

Gunakan filter untuk fokus pada protokol tertentu, misalnya:

* `http` → hanya paket HTTP
* `ip.addr == 192.168.1.10` → hanya dari/alamat IP tertentu
* `tcp.port == 80` → hanya port tertentu

#### **6. Analisis Paket**

Klik salah satu paket di daftar tangkapan untuk melihat detail:

* **Frame summary** (layer fisik)
* **Ethernet header**
* **IP header**
* **Transport layer (TCP/UDP)**
* **Application layer (HTTP, DNS, dll.)**

#### **7. Simpan Hasil Capture**

Anda dapat menyimpan hasil tangkapan:

```
File → Save As → mycapture.pcapng
```

Format `.pcapng` dapat dibuka kembali untuk analisis lanjutan.

#### **8. Statistik dan Visualisasi**

Gunakan menu:

```
Statistics → Protocol Hierarchy
Statistics → Conversations
Statistics → IO Graphs
```

Untuk melihat statistik dan grafik lalu lintas jaringan.

---

## **Contoh Kasus Penggunaan**

1. **Analisis koneksi lambat:**

   * Jalankan capture di interface aktif.
   * Filter `tcp.analysis.retransmission` untuk melihat retransmisi TCP.
   * Identifikasi sumber delay (client/server).

2. **Mendeteksi serangan jaringan:**

   * Gunakan filter `icmp` atau `arp`.
   * Cek jumlah paket tidak wajar dari satu IP (indikasi DoS atau ARP spoofing).

3. **Belajar struktur protokol HTTP:**

   * Jalankan browser ke situs lokal.
   * Filter `http`.
   * Perhatikan detail header request dan response.

---

## **Kesimpulan**

Wireshark merupakan **alat utama dalam dunia jaringan dan keamanan siber** yang memungkinkan pengguna melihat setiap bit data yang mengalir di jaringan. Dengan fitur *capture*, *filtering*, *decoding*, dan *statistical analysis*, Wireshark menjadi alat standar bagi:

* Network administrator,
* Security analyst,
* Peneliti jaringan,
* Dan mahasiswa bidang informatika atau keamanan siber.

