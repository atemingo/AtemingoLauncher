YENİ SÜRÜM YAYINLAMA
====================
Windows:
1) Launcher'da sürümü artırın: src-tauri/tauri.conf.json ve src-tauri/Cargo.toml içindeki "version".
2) DERLE.bat ile kurulum dosyasını alın: src-tauri\target\release\bundle\nsis\AtemingoLauncher_X.Y.Z_x64-setup.exe
3) GitHub'da Releases -> "minecraft" (Windows) sürümünü düzenleyin. Yeni setup dosyasını
   AtemingoLauncher-setup.exe adıyla asset olarak ekleyin; eski exe asset'ini kaldırın.
   İndirme adresi hep aynı kalır:
   https://github.com/atemingo/AtemingoLauncher/releases/download/minecraft/AtemingoLauncher-setup.exe
4) Hash hesaplayın (PowerShell):
     Get-FileHash .\AtemingoLauncher-setup.exe -Algorithm SHA1
     Get-FileHash .\AtemingoLauncher-setup.exe -Algorithm SHA256
   Değerleri updates/version.json içindeki "sha1" ve "sha256" alanlarına yazın.
5) updates/version.json içinde "version" ve "notes" alanlarını güncelleyin.
6) Siteyi yükleyin. Açık launcher'lar bir sonraki açılışta güncelleme şeridini gösterir.

Linux:
1) v2.0.0-linux benzeri yeni bir tag ile Release oluşturun.
2) AtemingoLauncher-X.Y.Z-linux-x64.AppImage ve .deb dosyalarını asset olarak yükleyin.
3) Hash hesaplayın (Linux'ta):
     sha256sum AtemingoLauncher-X.Y.Z-linux-x64.AppImage AtemingoLauncher-X.Y.Z-linux-x64.deb
     sha1sum  AtemingoLauncher-X.Y.Z-linux-x64.AppImage AtemingoLauncher-X.Y.Z-linux-x64.deb
4) updates/version.json içindeki linux_url, linux_deb, linux_sha256, linux_sha1,
   linux_deb_sha256 ve linux_deb_sha1 alanlarını yeni değerlerle güncelleyin.
   Hash alanları boşsa launcher otomatik güncelleme yapmaz.
5) Siteyi yükleyin. AppImage sürümü kendini indirip yerine yazar ve yeniden açılır;
   .deb kurulumunda indirilen paket sistem kurucusunda açılır.

Not: downloads/ klasörü kaldırıldı; kurulum dosyaları yalnızca Release asset'i olarak tutulur.
Not: version.json, sürüm numarası launcher'dakinden büyükse "yeni sürüm" sayılır.
Sürüm numarası "0.1.10" gibi de yazılabilir; parçalar sayı olarak karşılaştırılır.
