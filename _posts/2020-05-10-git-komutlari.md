---
title: Git Komutları ve Kullanımı !
updated: 2020-1510-05 15:56
---

### Git komutları hakkında
#### GIT Nedir ?
Versiyon kontrol sistemidir. Açık kaynak özgür yazılım ürünüdür. Dilediğiniz gibi indirip  kullanabilirsiniz.
İndirmek için [https://git-scm.com/downloads](https://git-scm.com/downloads) resmi internet sayfasından kullandığınız `OS` sistemine uygun paketi indirebilirsiniz.

#### GIT Kullanımı ve Yapılandırılması
Git sistemini kurduktan sonra `terminal` veya `git bash` uygulaması üzerinden kullanıcı adı ve email adresimizi tanımlayacağız.

`git config --global user.name "Rıdvan Berçin"`  | _kullanıcı adı tanımlamak için_
`git config --global user.email "rbercin@gmail.com"` | _email adresi tanımlamak için_

<div class="divider"></div>

##### GIT akış şeması

`Çalışma Dizini` ----- add ----- `Geçiş Bölgesi` ----- commit ----- `Git deposu`

Temel akış şeması bu şekildedir.

#### GIT Projesi Oluşturma
****
#### | git init
Git proje dosyası oluşturmak için  terminalden masaüstüne oluşturduğumuz `bercin.org` dizinine disilir. `git init` komutu yazılır ve burada git deposu oluşturulur. 

Ben burada github'da depoladığım jeykll blog sitemin dosyalarını github'dan indirip git deposunda depolayacağım. indirmek için `git clone https://github.com/bercin/bercin.github.io.git` komutunu kullanıyoruz. 

****
#### | git add
Şimdi git deposuna ekleyelim `git add .` burada kullandığımız nokta  ` . `  bulunduğumuz dizinde ki dosyaları ekle anlamına gelmektedir. Şuan dosyalarımız geçiş bölgesindedir. Git deposuna eklemek için ise **commit** yapmamız gerekmektedir. `git commit -m "mesaj içeriği" `  _mesaj içeriği_ aldığımız versiyonu belirtir nitelikte olabilir. Aldığımız versiyonları listelemek için ` git log ` komutunu kullanabiliriz.

****

#### | git status
` git status ` komutu projede yapılan herhangi bir değişikliği gösterir. Git deposu ile projeniz arasında değişiklik var ise bunu size gösterecektir. Projemizde yeni bir sayfa oluşturup depoya eklemek için geçiş bölgesine ekleyelim ` git add yeniSayfa.md ` şimdi ` git staus ` dediğimizde geçiş bölgesinde commit edilmeyi bekleyen dosya olduğunu göreceğiz. 
Gördükten sonra git deposuna ` git commit -m "yeniSafya eklendi" ` komutuyla ekleyebiliriz. 

****
#### | git diff
`git diff` komutu yapılan değişiklikleri `status` komutundan farklı olarak değişikliğin detayını da bizi göstermektedir. **Örnek;** Blog sayfamızda bulunan makalemize ekleme yaptık, git depomuza göndereceğiz göndermede önce kontrol etmek istersek `git diff` komutu ile eklenen satırları + ve yeşil renkte bize gösterecektir, silinen satırlar var ise de - kırmızı renkte gösterecektir.

**Not:**  **git diff** `Çalışma Dizini` ile `Geçiş Bölgesi` arasında ki farkları gösterir.
**git diff --staged** ise `Geçiş Bölgesi` ile `Git Deposu` arasındaki farkları gösterir.

****
#### | git rm (dosya silme)
İki farklı şekilde dosya silme işlemi vardır.
1. Elle dosya silme
2. Komut ile dosya silme

**1. Elle dosya silme ;** Proje dosyasını açıp  `yeniSayfa.md` dosyasını silelim.
` git status ` ile kontrol ettiğimizde yapılan silme işlemini `add/rm` ile geçiş bölgesine eklememiz gerektiğini söylemektedir. Biz `git rm yeniSayfa.md`  komutuyla silme işlemini geçiş bölgesine bildirelim. Sonrasında değişikliği/silme işlemini `git commit -m "yeniSafta.md dosyası silindi."` ile git deposuna ekleyelim/bildirelim.

Bu işlem görüldüğü gibi uzun bir yöntem, 2. işlem ise daha kısadır.

**2. Komut ile dosya silme;** Burada yapmamız gereken tek şey terminal komut satırından `git rm yeniSayfa.md` yazmak ve sonrasında `git commit -m "yeniSafta.md dosyası silindi."` komutu ile git deposuna eklemek/bildirmek. 

Dizin/Klasör silmek için ise `git rm -r DizinKlasörAdı/` komutunu çalıştırmak ve git deposuna eklemek/bildirmek.

****
#### | git mv (dosya adı değiştirme / dosya taşıma)
İki farklı şekilde dosya silme işlemi vardır.
1. Elle dosya silme
2. Komut ile dosya silme

**1. Elle dosya adı değiştirme / dosya taşıma ;** Proje dosyasını açıp  `yeniSayfa.md` dosyasının adını `yeniSayfa_duzeltme.md` yapalım. ` git status ` ile kontrol ettiğimizde yapılan dosya adı değiştirme işlemini `add` ile geçiş bölgesine ekleyelim. Sonrasında dosya adı değişikliği `git commit -m "yeniSafta_düzeltme.md dosya adı değişikliği."` ile git deposuna ekleyelim/bildirelim.

Bu işlem görüldüğü gibi uzun bir yöntem, 2. işlem ise daha kısadır.

**2. Komut ile dosya adı değiştirme / dosya taşıma;** Burada yapmamız gereken tek şey terminal komut satırından `git mv yeniSayfa.md yeniSafta_düzeltme.md` yazmak ve sonrasında `git commit -m "yeniSafta_düzeltme.md dosya adı değişikliği."` komutu ile git deposuna eklemek/bildirmek.
Git deposuna göndermeden önce  `git status` ile isin değişikliği bilgisini ekrandan görebiliriz.

Dizin/Klasör/Dosya taşımak için ise `git mv DizinKlasörDosyaAdı/ yeniDizinKlasorDosyaadi/` komutunu çalıştırmak ve git deposuna eklemek/bildirmek.

****

#### | git checkout (değişiklikleri geri alma)
###### Çalışma Dizini
`git rm yeniSayfa.md` dosyasını komut yada elle sildiğimizi düşünelim. Yada dosya içinde değişiklik yapıldığını düşünelim. `git status` ile kontrol ettiğimiz de **yeniSayfa.md** dosyasının bize silindiğini yada içerisinde değişiklik yapıldığını gösterecektir.
Bu değişiklikleri yada silinen dosyayı geri almak için `git checkout -- yeniSayfa.md` komutunu kullanırız.


###### Geçiş Bölgesi
Burada **Çalışma Dizini**'n de ki senaryonun aynısı dosyayı sildiğimizi yada değişiklik yaptığımızı farz edelim. `git add .` ile Geçiş bölgesine ekledik. `git status` ile kontrol ettiğimiz de eklendiğini gördük fakat yanlış bir işlem yaptığımızı fark ettik geri almak için `git reset HEAD yeniSayfa.md` komutunu kullanırız. Tekrar konrol ettiğimiz de işlemin **Geçiş bölgesinden** geri alındığını gördük fakat hala **Çalışma dizininden** geri alındığını görmedik burada `git checkout -- yeniSayfa.md` komutunu kullanırız ve tamamen silme/değiştirme işlemini geri almış oluruz.

###### Versiyon Geri almak
Bir önceki versiyona geçmek için `git log` komutu ile alınan versiyonları listeliyoruz.
hangi versiyona geçmek istiyorsak o versiyonun hash kodunu kullanıp o versiyone geçeceğiz.
`git checkout 55dvm5kmm5fdffsdf88f8d8fd8f8sdfv  -- . ` Son daki nokta (.) projemde ki tüm dosyaları bir önceki versiyondaki haline getir anlamına gelmektedir. Nokta  yerine dosya ismi yazıp sadece o dosyayı eski haline getirebiliriz. Sonrasında `git status ` ile dosyalardaki değişiklikleri görürüz ve commit ederiz. `git commit -m " **bir önceki versiyona dönüş yaıldı.** " `

****

### | github 'a proje gönderme 
Github'da projeniz var ise onu local'inize clone edebilir, `git clone https://github.com/bercin/bercin.github.io.git` yada yeni bir repository oluşturabilirsiniz. 

Yeni repository oluşturmak için github hesabınınıza girip Repositories > New > create a new repository diyerek, repository name belirleyerek repositorymizi oluşturabiliriz.
Oluşturduğumuz repositorynin linkini kopyalarız. 

Göndermek istediğimiz projenin dizinin de ` git remote add bercinBlog https://github.com/bercin/bercin.github.io.git ` burada yazdığımız `bercinBlog`gitbub bağlantısının takma adı buraya herhangi bir şey de yazıla bilir. Bağlantımız oluştu mu kontrol edelim `git remote ` dediğimiz de ekrana `bercinBlog`

Github'a projemizin dosyalarını göndermek için `git push -u bercinBlog master ` komutunu gireriz. -u : Bütün dosyaları gönder anlamında kullanılır. master ise github projemizin ana dalıdır. 

şimdi kullanıcı adımızı istiyor burada github kullanıcı adımızı sonrasında ise şifremizi yazıyoruz. ve ekranda projenin gönderilip gönderilmediği ile ilgili bilgilerden projemizin github'a yüklendiğini anlıyoruz.


****


### | .gitignore kullanımı

GIT tarafından takip edilmesini istemediğimiz dosyalar var ise .gitignore adlı dosya oluşturup içeriine takip edilmesini istemediğimiz dosya isimlerini yazıyoruz, git daha sonra bu dosyaları görmezden geliyor. 

Bir tane örnek yapalım ; projemizde database dosyası olduğunu düşünelim `db_config` adında `.gitignore` dosyası oluşturalım, bu dosyanın başında (.) olduğu için linux sistemlerde gizli dosya anlamına gelmektedir, o yüzden ekrandan gözükmeyecektir terminal ile açıp düzenleye bilirsiniz. windows sistemlerde normal dosya olarak gözükeceği için herhangi bir text editörü ile açıp düzenleye bilirsiniz. Bu dosyayı ouşturup içine de `db_config` yazdık, `git status` ile kontrol ettiğimizde sadece git depoya gönderilmesi gereken dosyanın `.gitignore` olduğunu göreceksiniz. 

Şimdi gelişmiş bir başka örnek yapalım ; Bir tane klasör  var içinde de 3 tane dosya var biz bu klasör ve içinde ki 3 dosyayı depoya göndermeyelim bunun için  `.gitignore` dosyasına `klasörIsmi/*` yazdığımızda bu klasör ve dosyaları göndermeyecektir. peki 1 tanesini göndermek ister ise bu sefer de `!klasötIsmi/abc_conf` şeklinde ekleme yaptığımızda sadece klasör içinde ki `abc_conf` dosyasını depoya göndermiş oluruz. 


****


### | Branches (Dallar)

`git branch` ile projede ki mevcut dalları listeler, uzak depoda bulunan dalları listelemek için `git branch --all`  komutunu kullanırız. Yeni bir dal oluşturmak için `git branch yenidal2` komutunu kullandık, tekrar oluştuğunu görmek için `git branch` dediğimizde mevcut dalları listeleyecektir ve burada yeni oluşan dalı göreceğiz.

Yeni oluşturulan `yandal2` dalına geçmek için `git checkout yandel2` komutunu kullanırız. Kontrol için `git branch` komutunu kullanırız. yenidal2 de dosya oluşturup `git add .` sonra `git commit -m "yenidal2 de yeni dosya" ` kaydederiz. Şimdi brancları birleşterelim bunun için master branch a geçmemiz gerekmektedir. `git checkout master` ile master dalına geçeriz. master ile yandal2 arasında ki farkları görmek için `git diff master yandal2` dediğimizde ekranda arasındaki farkları gösterecektir. master ile yandal2 yi birleştirmek için  `git merge yandal2` komutunu kullanırız. Bu değişiklikleri github'a göndermek için `git push -u bercinBlog master` komutunu kullanırız. 



Bilgiyle kalın..
