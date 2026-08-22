<div align="center">

<img src="https://img.shields.io/badge/Platform-Android_8%2B-3DDC84?logo=android&logoColor=white" alt="Android">
<img src="https://img.shields.io/badge/Kotlin-2.x-7F52FF?logo=kotlin&logoColor=white" alt="Kotlin">
<img src="https://img.shields.io/badge/Jetpack%20Compose-Material%203-4285F4?logo=jetpackcompose&logoColor=white" alt="Compose">
<img src="https://img.shields.io/badge/Status-In_Development-FFC94D" alt="Status">

# 🐦 AnkaMC

### Your Minecraft server, right in your pocket

Set up a Minecraft Java Edition server on your Android phone with **one tap**,
manage your world, and invite your friends through a tunnel. No root, no Termux,
no PC required.

🌐 [ankamc.org](https://ankamc.org) · [🇹🇷 Türkçe sürüm için tıklayın](#tr-t%C3%BCrk%C3%A7e)

</div>

---

## ✨ What does it do?

| | |
|---|---|
| ⚡ **One-tap setup** | Paper · Purpur · Leaf · Folia · Fabric · Forge · NeoForge — pick a version, the rest is automatic |
| 🌍 **Go global** | playit.gg integration — go online without opening ports; share a link or QR code |
| 📟 **Live console** | Send commands, watch logs, see players join/leave in real time |
| 📈 **Live performance** | TPS · MSPT · RAM · online players — color-coded real-time cards |
| 💾 **World backups** | Zip your worlds with one tap, restore or export anytime |
| 🛡️ **Crash Recovery** | Automatic restart on crash (configurable) |
| 🔧 **File manager** | Plugin/mod upload via SAF + built-in text editor + server.properties editor |
| 🚀 **Optimization wizard** | Installs FerriteCore · Lithium/Canary · ModernFix with one tap |

## 🧠 Under the hood

AnkaMC's hardest problem was this: **Android apps cannot execute binaries in
their own data directory** (W^X), and bionic libc can't run glibc binaries.

So AnkaMC:

- Builds a custom runtime image from **Termux's bionic OpenJDK 25 jmods** with
  `jlink` and ships it inside the APK
- Bypasses the Android 10+ W^X restriction with a `/system/bin/linker64` fallback
- Injects an **ASM-based Java agent** into the server for TPS/MSPT metrics
  (zero console noise, zero overhead)
- Squeezes maximum performance out of phone hardware with Aikar-style G1 GC flags
  + big-core pinning (`taskset`)
- Runs glibc-dependent native mods (e.g. Valkyrien Skies) on modded servers via
  binary-patch + shim layers

> The app contains and distributes no Mojang code; all server software is
> downloaded from official sources during setup.

## 🗺️ Roadmap

- [x] Embedded JRE runtime (OpenJDK 25, aarch64)
- [x] 7 server software · multi-server profiles
- [x] Live console + TPS/MSPT/RAM monitoring
- [x] playit.gg tunnel + QR sharing
- [x] Crash Recovery · World Backup · optimization mods
- [ ] Google Play release *(coming soon)*
- [ ] Automatic scheduled world backups
- [ ] Plugin marketplace

## 📜 Legal Notice

AnkaMC is not affiliated with, endorsed by, or associated with Mojang Studios or
Microsoft. "Minecraft" is a trademark of Mojang Synergies AB. Tunneling is
powered by [playit.gg](https://playit.gg).

---

<div align="center">

**⭐ If you like the project, drop a star — be the first to hear about the release!**

</div>

---

<a id="tr-türkçe"></a>

<div align="center">

## 🇹🇷 TR — Türkçe

### Minecraft sunucun artık cebinde

Android telefonunda **tek tıkla** Minecraft Java Edition sunucusu kur,
dünyanı yönet, arkadaşlarını tünel üzerinden davet et.
Root yok, Termux yok, bilgisayar yok.

[English version above](#top) · 🌐 [ankamc.org](https://ankamc.org)

</div>

---

## ✨ Ne yapar?

| | |
|---|---|
| ⚡ **Tek tıkla kurulum** | Paper · Purpur · Leaf · Folia · Fabric · Forge · NeoForge — sürümü seç, gerisi otomatik |
| 🌍 **Dünyaya açıl** | playit.gg entegrasyonu ile port açmadan internete çık; adres veya QR paylaş |
| 📟 **Canlı konsol** | Komut gönder, logları izle, oyuncuları anlık gör |
| 📈 **Canlı performans** | TPS · MSPT · RAM · çevrimiçi oyuncular — renk kodlu gerçek zamanlı kartlar |
| 💾 **World yedekleme** | Dünyaları tek dokunuşla zip'e al, istediğinde geri yükle ya da dışa aktar |
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
- Modlu sunucularda glibc gerektiren native modları (örn. Valkyrien Skies) binary-patch + shim katmanlarıyla çalıştırır

> Uygulama hiçbir Mojang kodunu içermez ve dağıtmaz; tüm sunucu yazılımları
> kurulum sırasında resmî kaynaklardan indirilir.

## 🗺️ Yol haritası

- [x] Gömülü JRE runtime (OpenJDK 25, aarch64)
- [x] 7 yazılım · çoklu sunucu profilleri
- [x] Canlı konsol + TPS/MSPT/RAM izleme
- [x] playit.gg tüneli + QR paylaşımı
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
