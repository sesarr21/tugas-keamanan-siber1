# tugas-keamanan-siber1
# Laporan Insiden Keamanan Siber: NetSupport Manager RAT

## 1. Ringkasan Kejadian
Pada 28 Februari 2026 pukul 19:55 UTC, ditemukan indikasi serangan malware NetSupport Manager RAT pada jaringan internal domain EASYAS123 (easyas123.tech)

## 2. Temuan Analisis (Evidence)
Berdasarkan analisis file packet capture (PCAP) pada baris nomor 3808, ditemukan komputer internal yang berkomunikasi aktif dengan server penyerang (C2):

* **IP Komputer Terinfeksi (Korban):** `10.2.28.88`
* **IP Server Penyerang (C2):** `45.131.214.85` (Port 443)
* **Segmen Jaringan LAN:** `10.2.28.0/24`
* **Domain Controller:** `10.2.28.2` (EASYAS123-DC)

## 3. Langkah Penanganan
Untuk menghentikan serangan, tindakan berikut harus dilakukan:
1. **Isolasi:** Cabut kabel LAN / putus koneksi internet pada komputer `10.2.28.88` agar malware tidak menyebar
2. **Blokir IP:** Blokir IP `45.131.214.85` di Router/Gateway (`10.2.28.1`)
3. **Pembersihan:** Scan dan hapus file NetSupport RAT dari komputer `10.2.28.88`, lalu ganti password akun user-nya
