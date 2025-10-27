```markdown
# TA-BNTG-2025

Tugas Akhir BTNG 2025 — Halaman demo / dokumentasi proyek.

Deskripsi singkat
- Repository ini berisi halaman statis (index.html) sebagai halaman awal proyek Tugas Akhir BTNG 2025. Halaman menggunakan modal untuk menampilkan detail proyek dan JavaScript kecil untuk mengatur buka/tutup modal.
- README ini dibuat berdasarkan potongan kode HTML/JavaScript yang dikirim oleh pemilik repo, dengan penjelasan cara menjalankan, struktur, dan rekomendasi aksesibilitas/performa.

Fitur utama (berdasarkan kode)
- Halaman statis sederhana (index.html) sebagai landing awal.
- Modal dialog untuk menampilkan informasi proyek atau detail item.
- Penanganan klik overlay dan tombol tutup.
- Skrip modular (disarankan: external modal.js) yang mendukung:
  - Pemulihan fokus ke tombol pemicu,
  - Penjebakan fokus (focus trap),
  - Penutupan via tombol Esc,
  - Mencegah scroll latar saat modal terbuka.

Struktur berkas (usul)
- index.html                — Halaman utama (sudah ada)
- modal.js                  — Skrip modal aksesibel (jika dipisah)
- assets/                   — Gambar, font, ikon
- css/                      — stylesheet (styles.css)
- README.md                 — Dokumentasi proyek (file ini)

Cara menjalankan secara lokal
1. Clone repository:
   git clone https://github.com/burongbalap/TA-BNTG-2025.git
2. Masuk folder:
   cd TA-BNTG-2025
3. Jalankan server lokal sederhana (pilih salah satu):
   - Python 3:
     python -m http.server 8000
     lalu buka http://localhost:8000
   - Node (http-server):
     npx http-server -c-1 . -p 8000
4. Buka index.html via browser untuk cek tampilan dan modal.

Integrasi skrip modal (ringkasan)
- Jika Anda memisahkan skrip modal menjadi modal.js, tambahkan sebelum tag penutup </body>:
<script src="modal.js" defer></script>

- Pastikan struktur modal sesuai:
<div id="projectModal" class="modal" role="dialog" aria-modal="true" aria-labelledby="projectModalLabel" aria-hidden="true" tabindex="-1">
  <div class="modal-dialog">
    <h2 id="projectModalLabel">Judul Modal</h2>
    <button class="close-modal">Tutup</button>
    <!-- konten modal -->
  </div>
</div>

- Tombol pembuka harus punya atribut:
<button data-modal-target="#projectModal">Buka Modal</button>

Catatan aksesibilitas & UX penting
- Tambahkan atribut ARIA:
  - role="dialog", aria-modal="true", aria-labelledby (untuk judul), dan toggle aria-hidden saat buka/tutup.
- Fokus:
  - Simpan elemen yang memicu modal dan kembalikan fokus ke elemen itu saat modal ditutup.
  - Trap fokus saat modal terbuka agar tab tidak berpindah ke elemen di belakang.
- Keyboard:
  - Pastikan Esc menutup modal.
  - Tautan/form dalam modal dapat dioperasikan via keyboard.
- Scroll background:
  - Saat modal terbuka, cegah scroll latar dengan menambahkan `.modal-open { overflow: hidden; }` ke selector html/body.
- Kontras warna dan alt text untuk gambar.

Saran performa & SEO
- Kompres gambar dan gunakan format modern (webp) jika memungkinkan.
- Minify CSS/JS untuk production.
- Tambahkan meta tags dasar (title, description, og:image) untuk sharing.
- Gunakan Lighthouse untuk audit performa, aksesibilitas, best practices, dan SEO.

Checklist cepat testing
- [ ] Buka modal dengan mouse.
- [ ] Buka modal dengan keyboard (Tab lalu Enter/Space).
- [ ] Tab/Shift+Tab tetap berada dalam modal.
- [ ] Tekan Esc untuk menutup modal.
- [ ] Klik overlay menutup modal (klik area luar dialog).
- [ ] Fokus kembali ke tombol pemicu setelah menutup.
- [ ] Tidak ada scroll latar saat modal terbuka.
- [ ] Mobile responsiveness — tampil baik di ponsel/tablet.

Cara kontribusi singkat
- Buat branch baru untuk perubahan:
  git checkout -b fitur/modal-accessibility
- Commit perubahan dan push, lalu buat Pull Request.
- Jika perubahan kecil, Anda juga dapat menggunakan GitHub web editor.

Lisensi
- (Tambahkan lisensi yang sesuai, mis. MIT — file LICENSE)

Kontak
- Author / maintainer: burongbalap
- Masukkan email atau kontak lain di sini jika perlu.
```
