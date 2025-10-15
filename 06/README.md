## **Pertemuan 6: Proteksi Jaringan Komputer**

### 🎯 **Tujuan Pembelajaran**

Setelah mengikuti pertemuan ini, mahasiswa diharapkan mampu:

1. Menjelaskan konsep dan fungsi utama proteksi jaringan komputer.
2. Mengidentifikasi jenis-jenis ancaman jaringan dan strategi mitigasinya.
3. Menganalisis mekanisme kerja firewall, IDS/IPS, NAT, segmentasi jaringan, dan VPN.
4. Melakukan konfigurasi sederhana firewall, IDS/IPS, dan VPN pada simulasi jaringan (GNS3/Wireshark).
5. Mengevaluasi hasil percobaan proteksi jaringan dan dampaknya terhadap lalu lintas data.

---

### 🧩 **Materi Pembelajaran**

#### **1. Konsep Dasar Proteksi Jaringan**

* Tujuan utama: menjaga **kerahasiaan (confidentiality)**, **integritas (integrity)**, dan **ketersediaan (availability)** jaringan.
* Lapisan proteksi meliputi: fisik, perangkat lunak, dan kebijakan.
* Ancaman umum: sniffing, spoofing, DoS/DDoS, port scanning, dan intrusi.

#### **2. Firewall**

* **Definisi:** Sistem yang memantau dan mengontrol lalu lintas jaringan berdasarkan aturan keamanan.
* **Jenis Firewall:**

  * Packet-filtering firewall
  * Stateful inspection firewall
  * Application-level gateway (proxy firewall)
  * Next Generation Firewall (NGFW)
* **Contoh konfigurasi dasar:**

  ```bash
  # Contoh pada Linux
  sudo ufw enable
  sudo ufw deny 23/tcp
  sudo ufw allow 80/tcp
  sudo ufw status
  ```
* **Tujuan praktikum:** Menganalisis paket sebelum dan sesudah diterapkan aturan firewall.

#### **3. IDS dan IPS**

* **IDS (Intrusion Detection System):** sistem deteksi aktivitas mencurigakan.
* **IPS (Intrusion Prevention System):** sistem yang mendeteksi dan mencegah intrusi secara otomatis.
* **Contoh tools:** Snort, Suricata, Zeek (Bro).
* **Praktikum:** Jalankan Snort pada GNS3 atau VM dan analisis log hasil deteksi serangan (misalnya ping flood atau scan port).

#### **4. Segmentasi Jaringan**

* **Tujuan:** Memisahkan jaringan menjadi beberapa segmen untuk membatasi dampak serangan.
* **Implementasi:** VLAN, subnetting, dan DMZ (Demilitarized Zone).
* **Simulasi:** Gunakan GNS3 untuk membuat topologi 3 segmen (LAN internal, DMZ, dan Internet).
* **Manfaat:** Meminimalkan lateral movement dari penyerang.

#### **5. NAT (Network Address Translation)**

* **Fungsi:** Menyembunyikan alamat IP internal di balik satu alamat publik.
* **Jenis:**

  * Static NAT
  * Dynamic NAT
  * PAT (Port Address Translation)
* **Praktikum:** Konfigurasi NAT pada router simulasi di GNS3 dan amati perubahan alamat IP melalui Wireshark.

#### **6. VPN (Virtual Private Network)**

* **Definisi:** Saluran komunikasi aman melalui jaringan publik menggunakan enkripsi.
* **Jenis:**

  * Site-to-Site VPN
  * Remote Access VPN
* **Protokol umum:** PPTP, L2TP, IPsec, OpenVPN.
* **Praktikum:** Konfigurasi VPN sederhana menggunakan OpenVPN atau WireGuard (simulasi antar node GNS3).
* **Analisis:** Amati perbedaan paket terenkripsi dan tidak terenkripsi melalui Wireshark.

---

### ⚙️ **Metode Pembelajaran**

| Tahapan              | Aktivitas Mahasiswa                                                                    | Media/Tools            |
| -------------------- | -------------------------------------------------------------------------------------- | ---------------------- |
| Pendahuluan (15 mnt) | Dosen menjelaskan konsep dasar proteksi jaringan dan ancaman umum.                     | Slide presentasi       |
| Inti (70 mnt)        | Praktikum: konfigurasi firewall, IDS/IPS, NAT, dan VPN pada topologi simulasi di GNS3. | GNS3, Wireshark, Snort |
| Penutup (20 mnt)     | Diskusi hasil analisis log & laporan singkat.                                          | Forum LMS / kelas      |

---

### 🧪 **Evaluasi dan Penilaian**

| Komponen                                  | Bentuk Penilaian              | Bobot   |
| ----------------------------------------- | ----------------------------- | ------- |
| Kuis teori proteksi jaringan              | Pilihan ganda di LMS / kertas | 3%      |
| Praktikum GNS3 & analisis paket Wireshark | Laporan hasil percobaan       | 5%      |
| Partisipasi diskusi dan tanya jawab       | Observasi dosen               | 2%      |
| **Total**                                 |                               | **10%** |

---

### 📘 **Sumber dan Referensi**

1. Stallings, W. (2021). *Network Security Essentials: Applications and Standards.* Pearson.
2. Easttom, C. (2022). *Computer Security Fundamentals.* Pearson IT Certification.
3. NIST SP 800-41 Rev.1 – *Guidelines on Firewalls and Firewall Policy.*
4. Dokumentasi resmi Snort: [https://snort.org](https://snort.org)
5. Dokumentasi GNS3 dan Wireshark: [https://www.gns3.com](https://www.gns3.com), [https://www.wireshark.org](https://www.wireshark.org)
 
