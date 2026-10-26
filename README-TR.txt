YENİ SÜRÜM YAYINLAMA
====================
1) Launcher'da sürümü artırın: src-tauri/tauri.conf.json ve src-tauri/Cargo.toml içindeki "version" (ör. 0.1.1).
2) DERLE.bat ile kurulum dosyasını alın: src-tauri\target\release\bundle\nsis\AtemingoLauncher_0.1.1_x64-setup.exe
3) Bu dosyayı downloads/ klasörüne AtemingoLauncher-setup.exe adıyla koyun.
4) SHA1 değerini hesaplayın (PowerShell):
     Get-FileHash .\downloads\AtemingoLauncher-setup.exe -Algorithm SHA1
   Çıkan Hash değerini küçük harfle updates/version.json içindeki "sha1" alanına yazın.
5) updates/version.json içinde "version" ve "notes" alanlarını yeni sürüme göre güncelleyin.
6) Siteyi yükleyin. Açık olan launcher'lar bir sonraki açılışta güncelleme şeridini gösterir.

Not: version.json, sürüm numarası launcher'dakinden büyükse "yeni sürüm" sayılır.
Sürüm numarası "0.1.10" gibi de yazılabilir; parçalar sayı olarak karşılaştırılır.
