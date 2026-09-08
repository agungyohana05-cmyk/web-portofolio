# PORTFOLIO WEBSITE EDIT & MAINTAIN GUIDE — No Code / No Bot Required

Focus: You can update this website yourself via **GitHub browser** — no terminal, no AI/bot needed. GitHub Pages auto-deploys on every commit.

> Live URL: `https://agungyohana05-cmyk.github.io/web-portofolio/`
> Repository: `github.com/agungyohana05-cmyk/web-portofolio`

---

## 1. Edit TEXT (name, bio, contact, project titles, experience, education, achievements)

1. Open `github.com/agungyohana05-cmyk/web-portofolio`.
2. Click **`konten.json`** → **Edit (pencil icon)** top right.
3. Edit text inside quotes `"..."` — **don't remove commas**.
   Example: `"nama": "I Gede Agung Yohana Dharma"` → change as needed.
4. Click **Commit changes** → fill "Update konten.json" → **Commit changes**.
5. Wait ~1 minute, refresh site → changes live.

> `konten.json` structure:
> - `nama`, `role`, `tagline`, `bio`, `lokasi` — profile.
> - `angka1`, `angka1Lb`, `angka2`, `angka2Lb` — stats in About section.
> - `kontak.email` / `kontak.wa` / `kontak.linkedin` / `kontak.behance` — leave empty (`""`) to hide.
> - `pengalaman` — work history array: `{ "posisi", "perusahaan", "periode", "lokasi", "deskripsi" }`
> - `organisasi` — organization experience: `{ "posisi", "organisasi", "periode", "lokasi", "deskripsi" }`
> - `pendidikan` — education array: `{ "institusi", "gelar", "ipk" / "nilai", "periode", "detail" }`
> - `achievements` — array of achievement strings.
> - `skills` — object with categories: `production`, `design`, `soft`, `language`.
> - `karya` — projects per category (Filmography, Graphic Design, Video Production):
>   `{ "file", "judul", "tag", "year", "desc", "isCategory" }`
>   - `isCategory: true` = first item as category cover.
>   - Add project = copy a `{...},` line and edit.
>   - Remove project = delete its line.
>   - **Important:** Last item in each array MUST NOT have a trailing comma.

---

## 2. Add / Replace IMAGES

1. Open folder `assets/desain` (photography folder removed).
2. **Add file → Upload files** → select image → **Commit changes**.
3. Open `konten.json` → add `"file": "assets/desain/your-image.jpg"` to the project using it.
4. Commit (same as step 1).

> Tip: Hide project temporarily = remove its line from `konten.json`, don't delete the image.
> Used images won't be re-distributed.

---

## 3. Change COLORS / Theme (in `index.html`)

Top of `index.html` has `:root` block:
```
--navy:#00296B;  --blue:#00509D;  --yellow:#F0D000;
```
Change hex codes after `#` to re-theme. (Usually not needed.)

---

## 4. Custom Domain (Optional)

1. Buy domain (e.g., `niagahoster.co.id`, `idwebhost`, etc).
2. Open `github.com/agungyohana05-cmyk/web-portofolio` → **Settings → Pages**.
3. Fill **Custom domain** with your domain → Save.
4. In your domain registrar panel, add CNAME/records as GitHub instructs
   (e.g., 4 A records `185.199.108.153` etc & TXT `_github-pages-challenge`).
5. Enable **Enforce HTTPS**.

---

## 5. Restore Website (If Broken / Missing)

- Original content in `konten.json` history: GitHub **History** on this file → pick version → Restore.
- Full source also in local folder:
  `MONEY GROWTH/website builder business/demo/PORTOFOLIO/`.

---

## 6. Disable / Delete Website

- Disable: GitHub **Settings → Pages → unpublish** (site down, files remain).
- Delete: **Settings → Danger Zone → Delete this repository**.

---

## Security & Quality Notes
- All site content is static files — no database to hack.
- HTTPS auto-enabled by GitHub (part of "public domain" convenience).
- If images are heavy, upload compressed versions (max width 1,400 px) for speed.

---

## Portfolio Structure (Current)

- **Filmography** (Cover: `artboard-2.jpg` → "Filmography")
  - Click → opens: Behind the Sea, Heaven Pass, Film Project
- **Graphic Design** (Cover: `artboard-4.jpg` → "Graphic Design Portfolio")
  - Click → opens: Social Media Content (4 items)
- **Video Production** (Cover: `artboard-4-copy.jpg` → "Video Production")
  - Click → opens: Fixinema Podcast Series, WKWK Project Content

---

## Local Development (Preview Before Push)

```bash
cd "/Users/yohana/Documents/AI Project/MONEY GROWTH/website builder business/demo/PORTOFOLIO"
python3 -m http.server 8080
# Open http://localhost:8080
```
**Required** for `fetch("konten.json")` to work (CORS blocks `file://`).