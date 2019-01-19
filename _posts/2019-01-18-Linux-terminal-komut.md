---
title: Linux Terminal Komutları
updated: 2019-01-18 11:59
---

### Temel Komutlar

**pwd** : (_print working directory_) çalışılan dizini yazdır, anlamına gelmektedir.

![pwd](../assets/pwd.png)

**ls** : İçinde bulunduğumuz dizinin altında hangi dizinler ve dosyalar var onları listelememize yarıyor. "ls" komutu artı olarak parametre almaktadır.

- **ls -l** : Uzun liste long list anlamına gelir.
- **ls -la** : (All) Artı olarak gizli dosyalarıda listelemektedir. (_linux dosya yapısında ".dosya" nokta ile başlayanlar gizlidir._ ) **Not** : "ls -al" olarakda aynı işlemi yapabilirsiniz.
- **ls -lar** : (r -reverse) Gizli dosyalar da dahil  alfabetik sıraya göre sondan başlayarak içerikleri listeler.
- **ls -lt** : (t -time) Zamana göre listeliye biliyoruz.
-  **ls -ltr** : (t -time) Zamana göre tersine listeliye biliyoruz.
  
**cd** : (_Change Directory_) Dizin değiştirme işlemi yapabiliyoruz. Kullanımı : cd "yol" ,  Ör ; cd Desktop (Masaüstü dizinine gider) cd .. bir dizin geri gelir.

**mkdir** : (_Make Directory_) Dizin oluşturma işlemi yapabiliyoruz. Kullanımı : mkdir _klasör adı_ , boşluk içeren bir dizin adı vereceksek 1.yol ; **mkdir "test deneme"** 2. yol ; mkdir test\ deneme şeklinde kullanmalıyız.







