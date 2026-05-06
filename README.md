# ⚙️ Database Trigger Documentation

Dokumentasi ini berisi trigger utama yang digunakan dalam sistem **Sistem Informasi Ekstrakurikuler** untuk menjaga konsistensi data.

---

## 🔒 1. Cegah Duplikasi Peserta

**Event:** `BEFORE INSERT ON peserta`

**Tujuan:**
Mencegah satu siswa terdaftar lebih dari satu kali pada ekskul yang sama.

**Logika:**

* Cek kombinasi `id_siswa` dan `id_ekskul`
* Jika sudah ada → batalkan insert

---



## 📅 2. Validasi Absensi

**Event:** `BEFORE INSERT ON absensi`

**Tujuan:**
Memastikan data absensi valid dan tidak kosong.

**Logika:**

* Cek apakah `id_peserta` valid
* Jika `status` kosong → set default `"Hadir"`

---
