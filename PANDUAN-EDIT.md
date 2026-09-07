# PANDUAN EDIT & MAINTAIN WEB PORTOFOLIO — tanpa bot / tanpa kode

Fokus: kamu bisa mengubah isi website ini **sendiri lewat browser GitHub** —
tidak perlu terminal, tidak perlu bot/AI. Hosting (GitHub Pages) otomatis
memperbarui website setiap kamu menyimpan perubahan.

> Alamat web: `https://{username}.github.io/web-portofolio/`

---

## 1. Mengubah TEKS (nama, bio, kontak, judul karya)

1. Buka `github.com/{username}/web-portofolio`.
2. Klik file **`konten.json`** → tombol **edit (pensil)** di kanan atas.
3. Ubah teks di dalam tanda kutip `"..."` — JANGAN sampai menghapus koma.
   Contoh: `"nama": "Agung Yohana"` → ganti sesuai keinginan.
4. Tekan **Commit changes** → isi kotak "Update konten.json" → **Commit changes**.
5. Tunggu ±1 menit, buka websitenya lagi → teks sudah berubah.

> Format isi `konten.json`:
> - `nama`, `role`, `tagline`, `bio`, `lokasi` — profil.
> - `kontak.email` / `kontak.wa` — kosongkan (`""`) kalau belum ingin muncul.
> - `karya.Desain` dan `karya.Fotografi` — daftar karya:
>   `{ "file", "judul", "tag" }` = file gambar, judul, dan label kategori.
>     - Tambah karya = salin satu baris `{...},` lalu ubah isinya.
>     - Kurangi karya = hapus barisnya.
>     - **Perhatian:** baris terakhir dalam daftar TIDAK boleh pakai koma setelahnya.

## 2. Menambah / mengganti GAMBAR

1. Buka folder `assets/foto` atau `assets/desain`.
2. **Add file → Upload files** → pilih gambar → **Commit changes**.
3. Buka `konten.json` → tambahkan `"file": "assets/foto/namagambar.jpg"` ke karya yang mau memakai gambar itu.
4. Commit (langkah sama seperti bagian 1).

> Tips: sembunyikan karya sementara = hapus barisnya dari `konten.json`, bukan hapus gambarnya.
> Gambar yang sudah dipakai tidak akan mendistribusikan ulang.

## 3. Mengubah WARNA / tema (ada di `index.html`)

Bagian paling atas file `index.html` ada blok `:root`:
```
--navy:#00296B;  --blue:#00509D;  --yellow:#F0D000;
```
Ubah kode warna di belakang `#` untuk mengganti tema. (Biasanya tidak perlu.)

## 4. Custom domain (nanti, kalau mau)

1. Beli domain (mis. dari `niagahoster.co.id`, `idwebhost`, dll).
2. Buka `github.com/{username}/web-portofolio` → **Settings → Pages**.
3. Isi **Custom domain** dengan nama domainmu → Save.
4. Di panel domain (registrar), tambahkan CNAME/records mengikuti petunjuk yang
   ditampilkan GitHub (misal 4 record A `185.199.108.153` dst & TXT `_github-pages-challenge`).
5. Aktifkan **Enforce HTTPS**.

## 5. Kembalikan website (jika rusak/menghilang)

- Isi asli tersedia di `konten.json` versi lama: GitHub **History** file ini → pilih versi → Restore.
- Seluruh source juga ada di folder lokal:
  `MONEY GROWTH/website builder business/demo/PORTOFOLIO/`.

## 6. Menghapus / menghentikan website

- Nonaktifkan: GitHub **Settings → Pages → unpublish** (website hilang, file tetap ada).
- Hapus total: **Settings → Danger Zone → Delete this repository**.

---

## Catatan keamanan & kualitas
- Semua isi website ada di file statis — tidak ada basis data yang bisa di-hack kontennya.
- HTTPS aktif otomatis oleh GitHub (bagian dari kemudahan "public domain").
- Kalau gambar berat, upload versi kompres (maks lebar 1.400 px) supaya tetap cepat.