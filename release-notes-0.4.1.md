# CloudShelf Reader v0.4.1 / v0.3.1

**Langganan 6 bulan, bukan pembelian kekal**

- Setiap buku kini diberi akses selama **6 bulan** dari tarikh bayaran disahkan
- Bila tempoh tamat, buku dikeluarkan dari senarai langganan dan salinan offline dipadam automatik pada sambungan berikutnya
- **Nota anda kekal boleh dibaca** selepas tamat tempoh — hanya akses buku yang ditarik
- Buku bertanda kekal, dan akaun pensyarah, tidak luput
- Boleh perbaharui bila-bila masa dengan melanggan semula

**Status akses pada setiap buku**

- `Access until 25 Apr 2027` — akses masih sah
- `Access until 12 Nov 2026 (18 days left)` — oren, bila tinggal 30 hari atau kurang
- `Access expired 25 Oct 2026` — merah
- `Permanent access` — buku kekal / akaun pensyarah

**Istilah baharu dalam app**

- My Collection → **My Subscription**
- Buy Book → **Subscribe**
- Owned ✓ → **Subscribed ✓**

**Pembetulan**

- **"PDF Not Available"** tidak lagi muncul untuk buku yang anda memang miliki. Senarai buku kini hanya membawa penanda `has_file`; pautan fail sebenar diminta secara berasingan semasa muat turun
- Teks skrin kosong pada My Subscription dikemas kini — tiada lagi rujukan kepada aliran PIN yang sudah dibuang

**Android**

- Cap jari peranti kini menggunakan **ANDROID_ID** dengan awalan baharu `A2-`
- Penghijrahan dibuat sekali sahaja di server — peranti sedia ada tidak dihijrah dua kali dan tidak perlu log masuk semula
- APK Huawei dan APK standard kini berkongsi cap jari yang sama (satu akaun, satu peranti)

**Dokumen**

- Terma Perkhidmatan dan Polisi Privasi dikemas kini: pembayaran CHIP (FPX), tempoh akses dan luput, **polisi bayaran balik**, **polisi penghantaran (kandungan digital melalui app)**, data diagnostik, dan pengikatan satu peranti

**Nota untuk pengguna sedia ada**

- Buku yang sudah dimuat turun sebelum ini masih boleh dibuka selepas update
- Padam dan muat turun semula berfungsi seperti biasa

**Teknikal**

- RPC `get_my_library_books()` kini memulangkan `has_file`
- RPC baharu `get_book_download_info(p_book_id)` — hanya untuk pengguna yang sah aksesnya
- `books.access_validity_months` (NULL = ikut global, 0 = kekal, N = N bulan) dan `app_config.access_validity_months`
- `profiles.is_lecturer` — akses tanpa luput
- Manifest APK: `versionName 0.3.1`, `versionCode 3001`, minSdk 24
