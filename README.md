<p align="center"><img src="ND.png" width="250" height="250" align="center"></p>

# ⚡ Command Center SPKLU PLN Nusa Daya NTB (Helpdesk Otomatis)

Web sederhana berbasis **GitHub Pages** untuk menghubungkan pengguna SPKLU langsung ke **teknisi piket yang sedang bertugas** melalui WhatsApp, hanya dengan **scan QR Code** di lokasi SPKLU.

Sistem ini membaca **jadwal piket dari file CSV**, mencocokkan **tanggal & jam real-time**, lalu otomatis mengarahkan ke nomor teknisi yang aktif.

---

## 🚀 Cara Kerja Sistem

1. User scan **QR Code** di SPKLU
2. Link mengarah ke GitHub Pages dengan parameter lokasi, contoh:  
   ```
   https://islahulanwar.github.io/SPKLU_NDNTB/?id=SPKLU01
   ```
3. Website membaca `jadwal.csv`
4. Sistem cek:
   - Tanggal hari ini
   - Jam saat ini
5. Jika cocok dengan jadwal piket → otomatis buka WhatsApp teknisi aktif

---

## 📁 Struktur Repository

```
SPKLU_NDNTB/
│
├── index.html      # Source utama web helpdesk
├── jadwal.csv      # Jadwal piket teknisi (dibaca otomatis)
└── README.md
```

---

## 🗓️ Format File `jadwal.csv` (WAJIB)

Gunakan format **persis** seperti ini:

```
tanggal,jam_mulai,jam_selesai,teknisi,nomor_whatsapp
12-04-2026,08:00,16:00,Budi,6281234567890
12-04-2026,16:00,23:59,Andi,6289876543210
```

### ⚠️ Ketentuan penting

- Format tanggal: **dd-mm-yyyy**
- Jam: **HH:MM** (24 jam)
- Nomor WhatsApp: awali dengan **62**, tanpa `+`
- Tidak boleh ada spasi tambahan

---

## 📍 Mapping ID Lokasi SPKLU

Parameter `id` pada URL menentukan lokasi:

Contoh:
```
?id=SPKLU01
```

Sudah terpetakan otomatis di dalam `index.html` hingga `SPKLU46`.

---

## 🌐 Aktivasi GitHub Pages

1. Masuk ke repo **SPKLU_NDNTB**
2. Buka **Settings → Pages**
3. Source: `Deploy from branch`
4. Branch: `main` / root
5. Save

Akses:
```
https://islahulanwar.github.io/SPKLU_NDNTB
```

---

## 🧪 Contoh Pengujian

Buka:
```
https://islahulanwar.github.io/SPKLU_NDNTB/?id=SPKLU01
```

Jika waktu sesuai jadwal, akan otomatis redirect ke WhatsApp teknisi.

Jika tidak ada jadwal aktif, muncul pesan:
> Tidak ada teknisi piket saat ini

---

## 🎯 Kegunaan di Lapangan

- Tidak perlu call center
- Tidak perlu aplikasi tambahan
- Tidak perlu login
- Cukup scan QR → langsung ke teknisi aktif

Sangat cocok ditempel di setiap unit SPKLU.

---

## 🛠️ Kustomisasi

Yang bisa diubah tanpa ubah program:

- Edit jadwal → cukup ubah `jadwal.csv`
- Tambah teknisi → edit CSV
- Ganti nomor → edit CSV

Tidak perlu edit HTML.

---

## 🧠 Teknologi yang Dipakai

- HTML + CSS + JavaScript murni
- GitHub Pages (gratis hosting)
- WhatsApp API (`wa.me`)

---

## 👤 Author

Islahul Anwar  
PLN Nusa Daya UP Nusra – NTB
