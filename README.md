# GKPS Tangerang - Website dengan CMS

Website gereja GKPS Tangerang dengan sistem Content Management System (CMS) untuk mengelola konten secara mudah.

## 🌟 Fitur

### Website Frontend
- ✅ Design formal dan elegan
- ✅ Responsive (mobile-friendly)
- ✅ Animations dengan GSAP
- ✅ Hero section dengan parallax
- ✅ Jadwal Ibadah dengan 3D cards
- ✅ Pengumuman dengan masonry layout
- ✅ Tata Ibadah dengan horizontal scroll
- ✅ CTA section dengan corner frames
- ✅ Footer lengkap dengan informasi kontak

### CMS (Content Management System)
- ✅ **Decap CMS** - Interface seperti WordPress
- ✅ Kelola Jadwal Ibadah (Tambah, Edit, Hapus)
- ✅ Kelola Pengumuman (Tambah, Edit, Hapus)
- ✅ Kelola Tata Ibadah (Tambah, Edit, Hapus)
- ✅ Buat Halaman Baru
- ✅ Pengaturan Website (Info Gereja, Hero Section)
- ✅ Upload Gambar
- ✅ Editorial Workflow (Draft → Review → Publish)

## 📁 Struktur Folder

```
📁 gkps-tangerang/
├── 📁 content/              # Data konten (Markdown + JSON)
│   ├── 📁 jadwal-ibadah/    # File jadwal ibadah
│   ├── 📁 pengumuman/       # File pengumuman
│   ├── 📁 tata-ibadah/      # File tata ibadah
│   ├── 📁 halaman/          # File halaman statis
│   └── 📁 pengaturan/       # File pengaturan
├── 📁 public/
│   ├── 📁 admin/            # CMS Dashboard
│   │   └── 📄 index.html    # Decap CMS
│   ├── 📁 data/             # Generated JSON (auto)
│   ├── 📄 hero-bg.jpg
│   └── 📄 cta-bg.jpg
├── 📁 scripts/
│   └── 📄 build-content.js  # Parser markdown → JSON
├── 📁 src/
│   ├── 📁 components/
│   ├── 📁 hooks/
│   │   └── 📄 useContent.ts # Hooks untuk baca data
│   ├── 📁 sections/
│   └── 📄 App.tsx
└── 📄 package.json
```

## 🚀 Cara Deploy ke Netlify

### Step 1: Buat Akun GitHub
1. Buka [github.com](https://github.com)
2. Daftar akun baru (gratis)
3. Verifikasi email

### Step 2: Buat Repository Baru
1. Klik tombol "+" → "New repository"
2. Nama repository: `gkps-tangerang`
3. Pilih "Public"
4. Klik "Create repository"

### Step 3: Upload File ke GitHub

**Cara A: Upload ZIP**
1. Download file website ini sebagai ZIP
2. Extract ZIP di komputer Anda
3. Buka folder hasil extract
4. Pilih SEMUA file dan folder
5. Compress menjadi ZIP baru: `gkps-tangerang.zip`
6. Di GitHub, klik "uploading an existing file"
7. Upload ZIP file
8. Klik "Commit changes"

**Cara B: Git Command Line**
```bash
cd gkps-tangerang
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/gkps-tangerang.git
git push -u origin main
```

### Step 4: Deploy ke Netlify

1. Buka [netlify.com](https://netlify.com) dan login
2. Klik "Add new site" → "Import an existing project"
3. Pilih "GitHub"
4. Authorize Netlify untuk akses GitHub Anda
5. Pilih repository `gkps-tangerang`
6. Konfigurasi build:
   - **Build command:** `npm run build`
   - **Publish directory:** `dist`
7. Klik "Deploy site"

### Step 5: Ganti Nama Domain
1. Di dashboard Netlify, klik site Anda
2. Klik "Site settings"
3. Pilih "General" → "Site details"
4. Klik "Change site name"
5. Ketik: `gkps-tangerang`
6. Klik "Save"

**Website live di:** `https://gkps-tangerang.netlify.app`

### Step 6: Setup CMS (Wajib!)

Agar CMS bisa digunakan, Anda perlu setup Netlify Identity dan Git Gateway:

#### 6.1 Aktifkan Netlify Identity
1. Di dashboard Netlify, klik tab "Identity"
2. Klik "Enable Identity"
3. Klik "Settings and usage"
4. Di "Registration", pilih "Invite only" (lebih aman)
5. Di "External providers", aktifkan "GitHub" dan "Google" (opsional)

#### 6.2 Aktifkan Git Gateway
1. Di tab "Identity", scroll ke bawah
2. Klik "Enable Git Gateway"
3. Klik "Save"

#### 6.3 Invite Admin
1. Di tab "Identity", klik "Invite users"
2. Masukkan email admin
3. Pilih role: "Admin"
4. Klik "Send invite"

#### 6.4 Akses CMS
1. Buka: `https://gkps-tangerang.netlify.app/admin`
2. Klik "Login with Netlify Identity"
3. Masukkan email dan password
4. Dashboard CMS siap digunakan!

## 📝 Cara Menggunakan CMS

### Akses Dashboard Admin
1. Buka: `https://gkps-tangerang.netlify.app/admin`
2. Login dengan akun yang di-invite

### Menu CMS

#### 📅 Jadwal Ibadah
- **Tambah:** Klik "New Jadwal Ibadah"
- **Edit:** Klik item yang ingin diedit
- **Hapus:** Klik item → "Delete"

Field:
- Judul Ibadah
- Hari (dropdown)
- Waktu (contoh: 08:00 WIB)
- Lokasi
- Ikon (pilih icon)
- Warna Tema
- Aktif (ya/tidak)
- Urutan (1-10)

#### 📢 Pengumuman
- **Tambah:** Klik "New Pengumuman"
- **Edit:** Klik item yang ingin diedit
- **Hapus:** Klik item → "Delete"

Field:
- Judul Pengumuman
- Tanggal (picker)
- Kategori (dropdown)
- Featured (centang untuk tampil di atas)
- Ringkasan (singkat)
- Konten Lengkap (markdown editor)
- Gambar (upload)
- Link Tindakan (opsional)
- Aktif (ya/tidak)

#### 📖 Tata Ibadah
- **Tambah:** Klik "New Tata Ibadah"
- **Edit:** Klik item yang ingin diedit

Field:
- Tema
- Hari (dropdown)
- Tanggal
- Bahan Alkitab (contoh: Efesus 4:1-6)
- Ringkasan
- Konten Lengkap (markdown editor)
- Aktif (ya/tidak)

#### 📄 Halaman Statis
- **Tambah:** Klik "New Halaman"
- Buat halaman seperti: Tentang Kami, Sejarah, Visi Misi, dll

Field:
- Judul Halaman
- URL Slug (contoh: tentang-kami)
- Deskripsi Meta (untuk SEO)
- Tampilkan di Navigasi (ya/tidak)
- Urutan di Navigasi
- Konten (markdown editor)
- Gambar Header

#### ⚙️ Pengaturan Website

**Informasi Gereja:**
- Nama Gereja
- Tagline
- Alamat Lengkap
- Telepon
- Email
- Link Live Streaming
- Link Social Media (FB, IG, YouTube)

**Hero Section:**
- Eyebrow Text
- Headline (2 baris)
- Subheadline
- Gambar Background
- Tombol Primary & Secondary

### Workflow Publish

1. **Buat Draft:** Tulis konten → Klik "Save" (otomatis draft)
2. **Set Status:** Pilih status:
   - **Draft** - Masih dikerjakan
   - **In Review** - Siap direview
   - **Ready** - Siap publish
3. **Publish:** Klik "Publish" → "Publish now"
4. **Auto Deploy:** Website otomatis update dalam 1-2 menit

## 🔄 Update Website

Setelah edit konten di CMS:
1. Klik "Publish"
2. Tunggu 1-2 menit
3. Website otomatis update!

**Tidak perlu upload ulang file!**

## 🛠️ Troubleshooting

### CMS tidak bisa login
- Pastikan Netlify Identity sudah di-enable
- Pastikan Git Gateway sudah di-enable
- Pastikan email sudah di-invite

### Konten tidak muncul di website
- Pastikan field "Aktif" = true
- Cek browser console untuk error
- Clear browser cache (Ctrl+Shift+R)

### Deploy gagal
- Cek build logs di Netlify
- Pastikan `npm run build` berhasil di local
- Cek apakah semua dependencies terinstall

### Gambar tidak muncul
- Pastikan gambar sudah di-upload
- Cek path gambar di markdown
- Pastikan folder `public/uploads` ada

## 📞 Butuh Bantuan?

Jika mengalami kesulitan:
1. Cek [Decap CMS Docs](https://decapcms.org/docs/)
2. Cek [Netlify Docs](https://docs.netlify.com/)
3. Tanyakan ke developer

## 📄 Lisensi

MIT License - Free for personal and commercial use.

---

**Dibuat dengan ❤️ untuk GKPS Tangerang**
