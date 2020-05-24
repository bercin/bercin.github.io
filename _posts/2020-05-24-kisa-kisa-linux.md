---
title: Kısa Kısa Gnu/Linux
updated: 2020-15-24 21:00
---

##### Terminalde uzun dosya yolunu gizleme, en son girilen dizini gösterme

Terminal komut satırında `vi .bashrc` ile .bashrc dosyasının içine giriyoruz ve  resimde de görüldüğü gibi  \w geçen yere \W (büyük W) yazıyoruz. Daha sonra `source .bashrc` komutu ile değişiklikleri aktif ediyoruz. 

![vi .bashrc](../assets/kisa-kisa-linux/dosya-yolu-gizleme.png) [Resmi Büyütmek için bu yazıya tıklayın !](../assets/kisa-kisa-linux/dosya-yolu-gizleme.png){:.lightbox}


##### Dosya veya Dizin Boyutu 
` du -sh * ` ya da `du -sh DizinAdi` şeklinde bakabilirsiniz.

Komut | Açıklama | Örnek Kullanım | Örnek Açıklaması
--- | --- | --- | --- | 
**du -sh** | Dizin, Dosya boyutu | **du -sh ** | " * " parametresini dizinde ki tüm klasör ve dosya boyununu verir.
**cat -n** | Satır sayısını öğrenmek | **cat -n rb.txt** | rb.txt dosyasının içindeki satırları satı sayısı ile birlikte gösterir.






