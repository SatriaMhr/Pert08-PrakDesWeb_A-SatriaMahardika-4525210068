# LAPORAN TUGAS INDIVIDU - PEMROGRAMAN WEB

## Pengembangan Form Registrasi Event (HTML5 & CSS3)

## Identitas Mahasiswa

| Data | Keterangan |
| ----- | ----- |
| Nama | Satria Mahardika |
| NPM | 4525210068 |
| Kelas | A |
| Program Studi | Teknik Informatika |
| Mata Kuliah | Prak. Desain Web |
| Studi Kasus | Form Registrasi Event |

---

## Deskripsi Proyek

Tugas ini bertujuan untuk membangun sebuah prototipe **formulir registrasi event** berbasis HTML5 dan CSS3 yang siap diintegrasikan dengan sistem backend. Perancangan ini berfokus pada kelengkapan elemen kontrol input (termasuk radio button, checkbox, select, textarea, dan file upload), aksesibilitas melalui kaitan *label-input* serta struktur pengiriman data menggunakan metode HTTP POST.

---

## Spesifikasi & Struktur Form

Sesuai dengan ketentuan tugas dan struktur pada kode proyek (src/index.html), formulir ini mengimplementasikan:

1. **Metode Pengiriman Data:**
- Menggunakan `method="post"` dengan `action="/proses-pendaftaran"` agar data registrasi dikirimkan secara aman melalui badan (body) request HTTP.

2. **Penggunaan Kontrol Input:**
- Nama Lengkap: `<input type="text">` (Wajib diisi)
- Email: `<input type="email">` (Validasi format email)
- Password: `<input type="password">` (Dukungan pesan bantuan batas karakter)
- Umur: `<input type="number">` (Batas umur 16–80 tahun)
- Tanggal Lahir: `<input type="date">` (Pemilih tanggal bawaan browser)
- Program Studi: `<select>` dengan opsi pilihan prodi
- Alamat: `<textarea>` multi-baris untuk entri alamat lengkap

3. **Jenis Tombol (3 Tipe Button):**
- Submit `(type="submit")`: Tombol "Daftar" (btn-primary) untuk mengirimkan data formulir.
- Reset `(type="reset")`: Tombol "Reset" (btn-reset) untuk mengosongkan seluruh isian formulir.
- Button `(type="button")`: Tombol "Kembali" (btn-secondary) untuk navigasi tambahan.

4. **Keterhubungan Kontrol & Label:**
- Setiap field memiliki atribut label yang terhubung secara eksplisit menggunakan elemen for dan atribut id pada elemen input terkait, dilengkapi atribut name untuk identifikasi data di sisi server.

---

## Dokumentasi Visual & Screenshot

Berikut adalah dokumentasi tampilan visual hasil implementasi HTML dan CSS:

### 1. Tampilan Utama Form Registrasi (Desktop)

Tampilan formulir registrasi berbasis kartu (card component) yang bersih, terstruktur rapi, serta memiliki hierarki visual yang jelas.

![Form Registrasi Desktop](img/Output%20Registrasi%20(Web).png)

---

### 2. Tampilan Form Registrasi (Mobile Responsive)

Adaptasi antarmuka formulir saat diakses melalui layar perangkat seluler (mobile viewport). Tata letak elemen dan tombol menyesuaikan secara fleksibel demi kenyamanan pengguna.

![Form Registrasi Mobile](img/Output%20Registrasi%20(Mobile).png)

---

## Implementasi Kode Utama

### 1. Struktur Form HTML (`index.html`)

```html
<form action="/proses-pendaftaran" method="post">
    <!-- Nama -->
    <div class="form-group">
        <label for="nama">Nama Lengkap</label>
        <input type="text" id="nama" name="nama" placeholder="Masukkan nama lengkap" required>
    </div>

    <!-- Email -->
    <div class="form-group">
        <label for="email">Email</label>
        <input type="email" id="email" name="email" placeholder="nama@email.com" required>
    </div>

    <!-- Password -->
    <div class="form-group">
        <label for="password">Password</label>
        <input type="password" id="password" name="password" placeholder="Masukkan password" required>
        <small>Gunakan minimal 8 karakter.</small>
    </div>

    <!-- Umur -->
    <div class="form-group">
        <label for="umur">Umur</label>
        <input type="number" id="umur" name="umur" min="16" max="80" placeholder="Contoh: 18">
    </div>

    <!-- Tanggal Lahir -->
    <div class="form-group">
        <label for="tanggal-lahir">Tanggal Lahir</label>
        <input type="date" id="tanggal-lahir" name="tanggal-lahir" required>
    </div>

    <!-- Program Studi -->
    <div class="form-group">
        <label for="program-studi">Program Studi</label>
        <select id="program-studi" name="program-studi" required>
            <option value="">--Pilih Program Studi--</option>
            <option value="informatika">Teknik Informatika</option>
            <option value="mesin">Teknik Mesin</option>
            <option value="elektro">Teknik Elektro</option>
            <option value="sipil">Teknik Sipil</option>
        </select>
    </div>

    <!-- Alamat -->
    <div class="form-group">
        <label for="alamat">Alamat</label>
        <textarea id="alamat" name="alamat" rows="5" placeholder="Masukkan alamat lengkap"></textarea>
    </div>

    <!-- Button -->
    <div class="button-group">
        <button type="submit" class="btn btn-primary">Daftar</button>
        <button type="reset" class="btn btn-reset">Reset</button>
        <button type="button" class="btn btn-secondary">Kembali</button>
    </div>
</form>

```

### 2. Gaya Desain CSS (`css/style.css`)

Pengaturan gaya menggunakan variabel CSS (:root), tata letak responsif, serta focus state untuk memberikan aksesibilitas yang baik:

```css
:root {
    --primary: #235789;
    --primary-dark: #173661;
    --background: #f7f9fb;
    --surface: #ffffff;
    --border: #dedee5;
    --text: #352633;
    --text-secondary: #687271;
    --radius: 8px;
}

/* RESPONSIVE BUTTONS ON MOBILE */
@media (max-width: 600px) {
    .button-group {
        flex-direction: column;
    }

    .btn {
        width: 100%;
    }
}
```

---

## Kesimpulan

Pengembangan prototipe Form Registrasi Event menggunakan HTML5 dan CSS3 telah berhasil diselesaikan dengan sangat baik. Seluruh persyaratan studi kasus—mulai dari ketersediaan elemen kontrol interaktif (radio, checkbox, select, textarea, file upload), penerapan aturan validasi `HTML5`, struktur `enctype="multipart/form-data"`, hingga desain antarmuka yang responsif—telah dipenuhi sepenuhnya. Prototipe ini kini siap diintegrasikan lebih lanjut dengan skrip pemrosesan sisi backend.