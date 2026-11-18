# Project IoT: Sistem Monitoring Suhu & Deteksi Gerakan

## 📌 Deskripsi Proyek
Proyek Internet of Things (IoT) ini dibuat untuk memenuhi tugas Responsi 1 Mata Kuliah Internet of Things. Sistem ini menggunakan ESP32 sebagai mikrokontroler utama untuk membaca data dari dua sensor (DHT22 dan PIR), memprosesnya, dan menampilkannya melalui Serial Monitor serta terhubung ke jaringan WiFi.

## 🧰 Komponen yang Digunakan
1. **ESP32 DevKit V1 (Mikrokontroler):** Sebagai otak sistem, memproses data sensor, dan menghubungkan perangkat ke jaringan WiFi.
2. **Sensor DHT22 (Sensor A):** Berfungsi untuk membaca data suhu (°C) dan kelembapan (%) di sekitar lingkungan.
3. **Sensor PIR (Sensor B):** Berfungsi untuk mendeteksi pergerakan berdasarkan perubahan radiasi infra merah.

## 🔌 Skema Wiring (Koneksi)
| Sensor | Pin Sensor | Pin ESP32 |
| :--- | :--- | :--- |
| **DHT22** | VCC (+) | 3V3 |
| | DATA (OUT) | GPIO 4 |
| | GND (-) | GND |
| **PIR** | VCC | VIN (5V) |
| | OUT | GPIO 15 |
| | GND | GND |

## 🖼️ Dokumentasi Hardware
Berikut adalah bentuk fisik dari rangkaian yang telah dibuat:

![[esp.jpeg]]
## 📊 Hasil Pengujian (Serial Monitor)
Berikut adalah bukti bahwa sistem berjalan dengan baik. Sensor membaca suhu/kelembapan, mendeteksi gerakan, dan terhubung ke WiFi:
![[hasil.png]]

## ⚙️ Alur Kerja Sistem (Logika)
1. **Inisialisasi:** ESP32 menyalakan sensor DHT22 dan PIR, lalu terhubung ke jaringan WiFi.
2. **Pembacaan Sensor:** Setiap 2 detik, ESP32 membaca data suhu & kelembapan dari DHT22, serta status gerakan dari PIR.
3. **Validasi Data:** Sistem memeriksa apakah data dari DHT22 valid. Jika gagal, sistem menampilkan pesan error.
4. **Output:** Data suhu, kelembapan, status gerakan, dan status koneksi WiFi ditampilkan di Serial Monitor.

## 📁 Struktur File
- `sketch_nov18a.ino` : File kode program Arduino IDE.
- `Laporan_Praktikum_IoT.pdf` : Laporan lengkap praktikum.
