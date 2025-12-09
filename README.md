# VTuber Full Body & Hand Tracking System

Sistem tracking VTuber full body + finger tracking menggunakan **MediaPipe** dan **OSC** untuk dikirim ke **VSeeFace**.

## ✨ Fitur Utama

* Full body tracking (kepala, badan, tangan, kaki)
* Finger tracking (jari lengkap kiri & kanan)
* Output OSC ke VSeeFace
* Kompatibel untuk VTuber 2D & 3D
* Real-time motion tracking menggunakan webcam

---

## 📦 Requirements

Pastikan sudah terinstall:

```
Python 3.8 - 3.11
OpenCV
MediaPipe
Python-OSC
NumPy
```

### Cara Install Library

```bash
pip install opencv-python mediapipe python-osc numpy
```

---

## 🚀 Cara Menjalankan

1. Buka terminal / PowerShell
2. Jalankan script Python:

```bash
python main.py
```

3. Buka **VSeeFace → General Settings → Receive Tracking Data via OSC**
4. Atur OSC Tracker Port = **39539**
5. Aktifkan **VMC Protocol Receiver** jika perlu
6. Kamera akan aktif otomatis dan model akan mengikuti gerakan Anda

---

## 🧠 Cara Kerja Tracking

| Komponen       | Teknologi       | Fungsi                   |
| -------------- | --------------- | ------------------------ |
| Pose Landmark  | MediaPipe Pose  | Tracking full body       |
| Hands Landmark | MediaPipe Hands | Tracking jari kanan kiri |
| OSC Sender     | Python-OSC      | Kirim data ke VSeeFace   |
| Webcam         | OpenCV          | Ambil video input        |

---

## ⚙️ Konfigurasi OSC

Default konfigurasi:

```
IP  : 127.0.0.1
PORT: 39539
```

Bisa diubah pada bagian config script:

```python
OSC_IP = ("192.168.1.8", 39539)  # Ganti dengan IP VSeeFace kamu
```

---

## 📍 Mapping untuk VSeeFace

| OSC Parameter        | Bagian Tubuh      |
| -------------------- | ----------------- |
| /VMC/Ext/Root/Pos    | Posisi root model |
| /VMC/Ext/Hips        | Pinggul           |
| /VMC/Ext/LeftHand    | Tangan kiri       |
| /VMC/Ext/RightHand   | Tangan kanan      |
| /VMC/Ext/LeftHand/*  | Jari tangan kiri  |
| /VMC/Ext/RightHand/* | Jari tangan kanan |

---

## 🎥 Tips Penggunaan

* Gunakan pencahayaan terang
* Latar belakang rapi (lebih mudah tracking)
* Kamera minimal 720p 30fps
* Jarak full body ± 1.5 – 2 meter dari kamera

---

## 🧩 Troubleshooting

| Masalah               | Solusi                                   |
| --------------------- | ---------------------------------------- |
| Tangan tidak bergerak | Pastikan jari terlihat jelas pada kamera |
| Model gerak aneh      | Kalibrasi ulang posisi kamera & cahaya   |
| OSC tidak terbaca     | Cek port & enable OSC pada VSeeFace      |

---

## 📄 Lisensi

Free to use dan bebas di modifikasi.

---

## ❤️ Support

Jika ada masalah atau pertanyaan, buat issue di GitHub repository ini.

Selamat mencoba VTuber tracking system 🎉
