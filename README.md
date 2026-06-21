# Dot Generator — by Venice studio

Studio efek dot generatif. Satu file statis (`index.html`), tanpa build, tanpa dependensi eksternal — bisa di-host di mana saja.

## Isi paket

- `index.html` — aplikasi studio (mandiri: HTML + CSS + JS dalam satu file).
- `vercel.json` — konfigurasi opsional (clean URLs + cache header). Boleh dihapus; situs statis tetap jalan tanpanya.
- `README.md` — file ini.

> Pastikan ketiganya berada dalam **satu folder** yang sama saat deploy.

## Deploy ke Vercel

Tidak ada langkah build. Framework preset = **Other**, Build Command = kosong, Output Directory = `.` (root).

### Cara 1 — Drag & drop (paling cepat, tanpa CLI)
1. Buka https://vercel.com/new
2. Tarik folder berisi `index.html` ke area unggah (atau pilih foldernya).
3. Klik **Deploy**. Selesai — Vercel memberi URL `*.vercel.app`.

### Cara 2 — Vercel CLI
```bash
npm i -g vercel        # sekali saja
cd path/ke-folder-ini
vercel                 # deploy preview, ikuti prompt (semua default)
vercel --prod          # deploy ke produksi
```
Saat ditanya pengaturan, terima default (no build command, output directory root).

### Cara 3 — Git (GitHub/GitLab/Bitbucket)
1. Push folder ini ke sebuah repo.
2. Di Vercel: **Add New → Project → Import** repo tersebut.
3. Framework Preset: **Other**. Build Command: kosongkan. Output Directory: `.`
4. **Deploy**. Setiap push berikutnya akan auto-deploy.

## Catatan

- Efek yang dibuat di studio bisa diekspor lewat tombol **Copy Embed Code**, lalu ditempel sebagai HTML embed di Framer atau situs lain — kode embed-nya juga mandiri.
- Tema Dark/Light (toggle di header) hanya memengaruhi tampilan studio, bukan kode embed yang diekspor.
- Tidak ada pemanggilan jaringan eksternal; font memakai system-ui sebagai fallback.
