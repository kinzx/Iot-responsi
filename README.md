# Project IoT: Sistem Monitoring Suhu & Deteksi Gerakan

## 📌 Deskripsi Proyek
Proyek Internet of Things (IoT) ini dibuat untuk memenuhi tugas Responsi 1 Mata Kuliah Internet of Things. Sistem ini menggunakan ESP32 sebagai mikrokontroler utama yang berfungsi untuk membaca data dari dua sensor, memprosesnya, dan menampilkannya melalui Serial Monitor serta terhubung ke jaringan WiFi.

## 🧰 Komponen yang Digunakan
1. **ESP32 DevKit V1 (Mikrokontroler):** Sebagai otak sistem, memproses data sensor, dan menghubungkan perangkat ke jaringan WiFi.
2. **Sensor DHT22 (Sensor A):** Berfungsi untuk membaca data suhu (°C) dan kelembapan (%) di sekitar lingkungan.
3. **Sensor PIR (Sensor B):** Berfungsi untuk mendeteksi pergerakan (gerakan manusia/hewan) berdasarkan perubahan radiasi infra merah.

## 🔌 Skema Wiring (Koneksi)
| Sensor | Pin Sensor | Pin ESP32 |
| :--- | :--- | :--- |
| **DHT22** | VCC (+) | 3V3 |
| | DATA (OUT) | GPIO 4 *(atau GPIO 5 jika bermasalah)* |
| | GND (-) | GND |
| **PIR** | VCC | VIN (5V) |
| | OUT | GPIO 15 |
| | GND | GND |

## ⚙️ Alur Kerja Sistem (Logika)
1. **Inisialisasi:** ESP32 menyalakan sensor DHT22 dan PIR, lalu mencoba terhubung ke jaringan WiFi yang telah ditentukan.
2. **Pembacaan Sensor:** Setiap 2 detik, ESP32 membaca data suhu & kelembapan dari DHT22, serta mendeteksi status gerakan (HIGH/LOW) dari sensor PIR.
3. **Validasi Data:** Sistem memeriksa apakah data dari DHT22 valid (bukan `NaN`). Jika gagal, sistem menampilkan pesan error.
4. **Logika Peringatan:** Jika suhu melebihi 35°C **DAN** PIR mendeteksi gerakan, sistem akan menampilkan peringatan `[ALERT] ⚠ Suhu tinggi + gerakan terdeteksi!`.
5. **Output:** Data suhu, kelembapan, status gerakan, dan status koneksi WiFi ditampilkan secara rapi pada Serial Monitor.

## 🚀 Cara Menjalankan
1. Buka file `.ino` menggunakan Arduino IDE.
2. Pastikan library `DHT sensor library` dan `Adafruit Unified Sensor` sudah terinstall.
3. Ubah variabel `ssid` dan `password` di dalam kode sesuai dengan WiFi Anda.
4. Pilih board **DOIT ESP32 DEVKIT V1** dan port COM yang sesuai.
5. Upload kode dan buka Serial Monitor dengan baud rate **115200**.
