# FATOREADY Platform (`fatoready.store`)

Platform operasional dan transaksi end-to-end untuk **FATOREADY** (Digital Products, Document Services & Event Organizer).

## Fitur Utama
- **Checkout & Penguncian Kode Unik 3 Digit**: Otomatis mencegah tabrakan nominal selama 24 jam.
- **Verifikasi Manual DANA Bisnis QRIS & Transfer Bank**: Validasi binary magic-byte file gambar, deteksi duplikasi hash SHA-256 struk, dan lock konkurensi optimistik.
- **Invoice PDF Otomatis (`INV/FR/YYYYMM/00001`)**: Dibuat otomatis saat pembayaran disetujui lengkap dengan tanda tangan integritas HMAC-SHA256.
- **Buku Besar Pajak Otomatis (PP 20/2026 & Coretax CSV)**: Melacak batas omzet bebas pajak Rp 500 juta (Orang Pribadi), tarif PPh Final UMKM 0,5%, peringatan plafon Rp 4,8 miliar, dan export CSV bulanan.
- **WhatsApp Automation Adapter**: Idempoten, mendukung mode `SANDBOX_LOG_ONLY` hingga kredensial provider terpasang.

## Cara Menjalankan Lokal
```bash
cp .env.example .env
npm install
npx prisma generate
npx prisma migrate dev --name init_fatoready
npm run db:seed
npm test
npm run dev
```
