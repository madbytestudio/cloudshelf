# CloudShelf Reader v0.4.2 / v0.3.2

**Pembetulan: "Update required v0.4.1" pada Android**

- Buku berenkripsi tidak lagi meminta pengguna Android mengemas kini kepada versi yang tidak wujud untuk Android
- Sebelum ini app bertanya "apakah versi minimum?" tanpa menyatakan platform, jadi rekod Windows yang paling baharu menang. Android 0.3.1 diminta naik ke 0.4.1 — versi yang hanya ada untuk Windows
- Kini setiap platform menyemak rekodnya sendiri: Android menyemak Android, Windows menyemak Windows
- Tiada perubahan pada akaun, langganan, atau buku yang sudah dimuat turun

**Notifikasi tidak lagi memaksa kemas kini**

- Notifikasi yang dihantar kepada semua pengguna tidak lagi boleh mengunci app pada sesuatu versi
- Sebabnya mudah: satu notifikasi global tidak tahu platform penerimanya. Ia boleh memberitahu, tetapi tidak boleh memaksa
- Sekatan versi kini hanya datang dari dua tempat yang memang tahu platform: semakan kemas kini dan semakan muat turun buku

**Nota untuk pengguna sedia ada**

- Buku yang sudah dimuat turun masih boleh dibuka seperti biasa
- Padam dan muat turun semula berfungsi seperti biasa
- Tiada log masuk semula diperlukan

**Teknikal**

- `fetchMinVersion(platform)` kini menapis `.eq("platform", platform)` pada `app_releases`
- Pemanggil menghantar platform sendiri: `windows-x86_64`, `android-universal`, `android-huawei`, atau arch Mac
- `setForceUpdate()` dibuang dari pengendali realtime `app_notifications` dalam keempat-empat app
- Manifest APK: `versionName 0.3.2`, `versionCode 3002`, minSdk 24
- MSI: `0.4.2`, 64-bit
