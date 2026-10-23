# CloudShelf Reader v0.4.0

**Payment gateway: CHIP (FPX)**

- Bayaran kini melalui **CHIP Collect** — page FPX yang lebih stabil, dan pengesahan dibuat **di server** (bukan di client lagi)
- Buku di-unlock hanya selepas CHIP sahkan bayaran benar-benar berjaya (semakan jumlah + pemilik transaksi)
- Rekod jualan kini simpan **ID transaksi CHIP** — pembayaran yang sama tak boleh bagi akses dua kali
- Page return selepas bayaran dikemas kini — app kesan pembayaran lebih pantas

**Nota untuk user sedia ada**

- Versi lama (0.3.5) masih boleh dibeli sehingga update ini selesai digulirkan
- Selepas update, **semua pembelian mesti melalui CHIP**; kaedah lama tidak lagi digunakan

**Teknikal**

- Edge Function `chip` (create_purchase / verify_and_grant / get_purchase)
- RPC `complete_book_purchase_internal` — `service_role` sahaja
- Migration dipisah: `chip_payment_prep` (selamat) dan `chip_payment_rollout` (revoke client-side grant)
