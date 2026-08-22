<div align="center">

<img src="https://img.shields.io/badge/Platform-Android_8%2B-3DDC84?logo=android&logoColor=white" alt="Android">
<img src="https://img.shields.io/badge/Kotlin-2.x-7F52FF?logo=kotlin&logoColor=white" alt="Kotlin">
<img src="https://img.shields.io/badge/Jetpack%20Compose-Material%203-4285F4?logo=jetpackcompose&logoColor=white" alt="Compose">
<img src="https://img.shields.io/badge/Status-Geliştirme_Aşamasında-FFC94D" alt="Durum">

# 🐦 AnkaMC

### Minecraft sunucun artık cebinde

Android telefonunda **tek tıkla** Minecraft Java Edition sunucusu kur, dünyanı yönet,
arkadaşlarını tünel üzerinden davet et. Root yok, Termux yok, bilgisayar yok.

🌐 [ankamc.org](https://ankamc.org)

</div>

---

## ✨ Ne yapar?

| | |
|---|---|
| ⚡ **Tek tıkla kurulum** | Paper · Purpur · Leaf · Folia · Fabric · Forge · NeoForge — sürüm seç, gerisi otomatik |
| 🌍 **Dünyaya açıl** | playit.gg entegrasyonu ile port açmadan internete çık; adres veya QR paylaş |
| 📟 **Canlı konsol** | Komut gönder, logları izle, oyuncuları anlık gör |
| 📈 **Canlı performans** | TPS · MSPT · RAM · çevrimiçi oyuncular — renk kodlu gerçek zamanlı kartlar |
| 💾 **World yedekleme** | Dünyaları zip'e al, geri yükle ya da dışa aktar |
| 🛡️ **Crash Recovery** | Çökme halinde otomatik yeniden başlatma (ayarlanabilir) |
| 🔧 **Dosya yöneticisi** | Plugin/mod yükleme (SAF) + dahili metin editörü + server.properties editörü |
| 🚀 **Optimizasyon sihirbazı** | FerriteCore · Lithium/Canary · ModernFix'i tek dokunuşla kur |

## 🧠 Kaputun altında

AnkaMC'nin en zorlu problemi şuydu: **Android uygulamalar kendi veri dizininde
binary çalıştıramaz** (W^X) ve bionic libc glibc binary'lerini yürütemez.

Bu yüzden AnkaMC;

- **Termux'un bionic OpenJDK 25 jmod'larından** `jlink` ile özel bir runtime image üretir ve APK içine gömer
- Android 10+ W^X kısıtını `/system/bin/linker64` fallback'iyle aşar
- TPS/MSPT için sunucuya **ASM tabanlı bir Java agent** enjekte eder (konsolu kirletmeden, sıfır ek yükle)
- Aikar tarzı G1 GC bayrakları + büyük çekirdek pinning (`taskset`) ile telefon donanımından maksimum performans çıkarır
- Modlu sunucularda glibc gerektiren native modları (örn. Valkyrien Skies) binary-patch + shim katmanıyla çalıştırır

> Uygulama hiçbir Mojang kodunu içermez/dağıtmaz; tüm sunucu yazılımları kurulum
> sırasında resmî kaynaklardan indirilir.

## 🗺️ Yol haritası

- [x] Gömülü JRE runtime (OpenJDK 25, aarch64)
- [x] 7 yazılım · çoklu sunucu profilleri
- [x] Canlı konsol + TPS/MSPT/RAM izleme
- [x] playit.gg tüneli + QR
- [x] Crash Recovery · World Backup · optimizasyon modları
- [ ] Google Play yayını *(yakında)*
- [ ] Otomatik periyodik world yedekleme
- [ ] Eklenti mağazası

## 📜 Yasal Not

AnkaMC, Mojang Studios veya Microsoft ile bağlantılı değildir ve onlar tarafından
desteklenmemektedir. "Minecraft", Mojang Synergies AB'nin tescilli markasıdır.
Tünel hizmeti [playit.gg](https://playit.gg) altyapısını kullanır.

---

<div align="center">

**⭐ Projeyi beğendiysen yıldız vermeyi unutma — yayın haberini ilk alan sen ol!**

</div>
