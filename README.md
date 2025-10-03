# 📝 Pembuat Tabel HTML untuk Google Sites (HTML Table Maker)

Ini adalah aplikasi web sederhana yang dibangun dengan **Streamlit** untuk membantu pengguna membuat tabel HTML yang bersih dan bergaya tanpa perlu menulis kode apa pun. Aplikasi ini dirancang khusus untuk menghasilkan kode yang mudah disalin dan ditempelkan ke dalam **Google Sites** atau platform web lainnya.

Aplikasi ini bersifat **interaktif**, memungkinkan Anda untuk melihat pratinjau tabel secara langsung saat Anda mengubah pengaturan dan memasukkan data.

![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=Streamlit&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)

## 🎥 Demo Aplikasi

Berikut adalah video demo yang menunjukkan cara menggunakan aplikasi ini:

[![Demo Pembuat Tabel HTML](https://img.shields.io/badge/🎥-Tonton_Demo_Video-red?style=for-the-badge)](./demo/RecordIkanTabel.gif)

*Video demo menunjukkan langkah-langkah lengkap dari instalasi hingga penggunaan aplikasi*

## ✨ Fitur Utama

- **Konfigurasi Dinamis**: Atur jumlah baris dan kolom sesuai kebutuhan Anda.
- **Kustomisasi Tampilan**: Ubah warna latar belakang header, warna baris ganjil/genap, warna teks, dan warna garis batas dengan mudah menggunakan color picker.
- **Desain Responsif**: Atur lebar tabel dalam persentase (%) agar sesuai dengan layout halaman Anda.
- **Pilihan Font**: Pilih dari berbagai jenis font standar web (sans-serif, serif, monospace) untuk menyesuaikan dengan gaya situs Anda.
- **Antarmuka Multi-bahasa**: Ganti bahasa antarmuka antara Bahasa Inggris (EN) dan Bahasa Indonesia (ID) dengan satu klik.
- **Pratinjau Langsung**: Lihat perubahan pada tabel Anda secara real-time.
- **Hasilkan Kode HTML**: Dapatkan kode HTML yang bersih dan siap pakai, lengkap dengan inline CSS, untuk disalin dan ditempel.

## 🚀 Instalasi dan Cara Menjalankan

Untuk menjalankan aplikasi ini di komputer lokal Anda, ikuti langkah-langkah berikut.

### Prasyarat

- **Python** (versi 3.7 atau lebih baru) sudah terinstal.
- **pip** (package installer for Python) sudah terinstal.

### 1. Instal Streamlit

Buka terminal atau command prompt Anda dan jalankan perintah berikut untuk menginstal library Streamlit:

```bash
pip install streamlit
```

### 2. Simpan Kode Aplikasi

Simpan kode aplikasi Python ke dalam sebuah file bernama `streamlit_table_maker.py`.

### 3. Jalankan Aplikasi

Arahkan terminal Anda ke direktori tempat Anda menyimpan file `streamlit_table_maker.py`, lalu jalankan perintah berikut:

```bash
streamlit run streamlit_table_maker.py
```

Setelah perintah dijalankan, tab baru akan otomatis terbuka di browser Anda dengan alamat seperti `http://localhost:8501`. Aplikasi Table Maker Anda sekarang siap digunakan!

## 📄 Cara Menggunakan Aplikasi

1. **Buka Aplikasi**: Jalankan aplikasi sesuai petunjuk di atas.

2. **Atur Konfigurasi**: Gunakan panel di sebelah kiri (sidebar) untuk mengatur jumlah baris, kolom, warna, dan gaya tabel lainnya.

3. **Masukkan Data**: Ketikkan data Anda langsung ke dalam kotak input yang tersedia. Baris pertama adalah untuk header, dan baris berikutnya adalah untuk isi tabel.

4. **Lihat Pratinjau**: Periksa pratinjau tabel di bagian bawah untuk memastikan tampilannya sesuai dengan yang Anda inginkan.

5. **Salin Kode HTML**: Salin seluruh kode dari kotak "Copy HTML Code".

6. **Tempel di Google Sites**:
   - Buka editor Google Site Anda.
   - Pilih **Sisipkan** > **Sematkan Kode**.
   - Tempelkan kode HTML yang sudah Anda salin.
   - Simpan perubahan, dan tabel Anda akan muncul di halaman.

## 🎯 Contoh Penggunaan

Berikut adalah contoh kode HTML yang dihasilkan oleh aplikasi ini:

```html
<table style="width: 100%; border-collapse: collapse; font-family: Arial, sans-serif;">
  <thead>
    <tr style="background-color: #4CAF50; color: white;">
      <th style="border: 1px solid #ddd; padding: 8px; text-align: left;">Nama</th>
      <th style="border: 1px solid #ddd; padding: 8px; text-align: left;">Usia</th>
      <th style="border: 1px solid #ddd; padding: 8px; text-align: left;">Kota</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color: #f9f9f9;">
      <td style="border: 1px solid #ddd; padding: 8px;">Andi</td>
      <td style="border: 1px solid #ddd; padding: 8px;">25</td>
      <td style="border: 1px solid #ddd; padding: 8px;">Jakarta</td>
    </tr>
    <tr style="background-color: #ffffff;">
      <td style="border: 1px solid #ddd; padding: 8px;">Budi</td>
      <td style="border: 1px solid #ddd; padding: 8px;">30</td>
      <td style="border: 1px solid #ddd; padding: 8px;">Bandung</td>
    </tr>
  </tbody>
</table>
```

## 📁 Struktur Proyek

```
streamlit-table-maker/
│
├── streamlit_table_maker.py  # File utama aplikasi Streamlit
├── demo/                     # Folder berisi materi demo
│   └── table-maker-demo.mp4  # Video demo aplikasi
├── README.md                 # Dokumentasi proyek (file ini)
└── requirements.txt          # Daftar dependensi Python
```

## 🎥 Panduan Video

Untuk panduan visual yang lebih detail, tonton video demo yang tersedia di folder [`demo/`](./demo/). Video ini mencakup:

- 📋 **Instalasi dan setup**
- ⚙️ **Konfigurasi tabel**
- 🎨 **Kustomisasi tampilan**
- 📊 **Input data tabel**
- 📋 **Menyalin kode HTML**
- 🌐 **Paste ke Google Sites**

## 🤝 Berkontribusi

Kontribusi selalu diterima! Jika Anda ingin berkontribusi pada proyek ini, silakan:

1. Fork repository ini
2. Buat branch fitur baru (`git checkout -b fitur/namafitur`)
3. Commit perubahan Anda (`git commit -m 'Menambahkan fitur baru'`)
4. Push ke branch (`git push origin fitur/namafitur`)
5. Buat Pull Request

## 📝 Lisensi

Proyek ini dilisensikan di bawah [MIT License](LICENSE).

## 💬 Dukungan

Jika Anda mengalami masalah atau memiliki pertanyaan, silakan buat [issue](https://github.com/username/repository/issues) di repository GitHub ini.

---

**Selamat mencoba!** 🎉
