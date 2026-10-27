# CloudShelf Reader v0.4.3

**Pembetulan: kemas kini dalam app gagal dengan "Signature verification failed"**

- Menekan butang kemas kini dalam app berhenti dengan mesej *"Signature verification failed. The installer may have been tampered with."* — walaupun fail pemasang tidak diusik
- Punca: Tauri menulis fail `.sig` sebagai **base64**, tetapi penyemak dalam app membaca format teks minisign mentah. Ia tidak pernah berjaya membaca tandatangan itu, jadi setiap kemas kini dalam app ditolak
- Kini kedua-dua format diterima: base64 dinyahkod dahulu, teks mentah terus digunakan
- Fail pemasang 0.4.2 yang dimuat turun sebelum ini memang sah — tandatangan disahkan betul. Yang rosak hanya cara app membacanya

**Nota penting**

- Versi 0.4.1 dan lebih lama **tidak boleh** mengemas kini sendiri. Sila muat turun pemasang `.msi` di bawah dan pasang sekali secara manual
- Selepas 0.4.3 terpasang, kemas kini dalam app berfungsi seperti biasa
- Tiada perubahan pada akaun, langganan, atau buku yang sudah dimuat turun

**Teknikal**

- `verifyUpdateSignature()` menyahkod `.sig` base64 sebelum memanggil `verify_update_signature`, dan menerima teks minisign mentah jika sudah dinyahkod
- Tambah semakan `data.byteLength === 0` supaya muat turun kosong gagal awal
- MSI: `0.4.3`, 64-bit
