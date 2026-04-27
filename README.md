# 🎡 Dönen Çark Oyunu (Assembly x86)

![Assembly](https://img.shields.io/badge/Language-Assembly_x86-blue.svg)
![Environment](https://img.shields.io/badge/Environment-emu8086-green.svg)
![Platform](https://img.shields.io/badge/Platform-DOS-orange.svg)

Marmara Üniversitesi Bilgisayar Mühendisliği bölümü için geliştirilmiş, düşük seviyeli (low-level) programlama prensiplerini temel alan interaktif bir şans oyunudur. 

## 📝 Proje Hakkında
Bu proje, **emu8086** ortamında x86 Assembly dili kullanılarak geliştirilmiştir. Yüksek seviyeli dillerin hazır kütüphaneleri yerine doğrudan donanım kesmeleri (interrupts) ve Video RAM (VRAM) manipülasyonu kullanılarak oyun mantığı oluşturulmuştur.

### 🚀 Temel Özellikler
- **8 Dilimli Çark:** Farklı puan değerleri ve "İFLAS" riskleri içeren dinamik çark yapısı.
- **VRAM Grafik Yönetimi:** `0B800h` adresine doğrudan erişim sağlayarak akıcı animasyonlar ve renklendirme.
- **Kalıcı Rekor Sistemi:** `REKOR.DAT` dosyası üzerinden en yüksek skorun kalıcı olarak saklanması.
- **Rastgele Hız:** Her turda sistem saatinden alınan salise verisiyle belirlenen farklı dönüş hızları.
- **Bloklanmayan Girdi:** `INT 16h` kullanılarak animasyonu dondurmadan yapılan klavye kontrolü.

## 🎮 Oynanış ve Kontroller

Oyun başladığında çark dönmeye başlar. Amacınız en doğru zamanda çarkı durdurup en yüksek puanı toplamaktır!

- **[SPACE] (Boşluk):** Çarkı durdurur.
- **[E]:** Yeni tur başlatır (Hak varsa).
- **[ESC]:** Ana menüye döner.
- **[Q]:** Oyundan çıkış yapar.

> **Dikkat:** 3 hakkınız var! "İFLAS" dilimine denk gelirseniz o ana kadar topladığınız tüm puanlar sıfırlanır.

## 🛠 Teknik Detaylar
Proje kapsamında kullanılan bazı kritik Assembly teknikleri:
- **Video Modu:** 80x25 Renkli Text Modu (`INT 10h, AH=00h, AL=03h`)
- **Doğrudan Ekran Erişimi:** Ekrana yazı basmak yerine renkli karakterlerin VRAM adreslerine (`Satır*160 + Sütun*2`) yazılması.
- **Dosya Yönetimi:** Rekor bilgisinin yazılması ve okunması için `INT 21h` (3Dh, 3Ch, 3Fh, 40h) fonksiyonları.
- **Zaman Kontrolü:** Animasyon hızı için sistem saati takibi (`INT 21h, AH=2Ch`).





## 📦 Kurulum ve Çalıştırma
1. Bilgisayarınıza **emu8086** emülatörünü kurun.
2. `DonenCark.asm` dosyasını emülatör ile açın.
3. **Emulate** ve ardından **Run** butonuna basın.
4. *Opsiyonel:* Ses efektlerini duymak isterseniz Virtual Devices -> PC Speaker penceresini açık tutun.



---
⭐ Bu projeyi beğendiyseniz yıldız vermeyi unutmayın!
