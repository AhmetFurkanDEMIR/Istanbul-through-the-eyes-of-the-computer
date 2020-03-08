# Nesne Tanıma - Bölge önerisi

![Screenshot_2020-03-06_14-37-22](https://user-images.githubusercontent.com/54184905/76167234-3fa47880-6176-11ea-8146-fbdbc7fc8b83.png)

Pencere sol üst köşeden ilerlemeye başlar Kedi, köpek vb. bir nesne tespit edemezse Arka plan olarak işaretler.

Bu işlemi bir pencerede yapmaz farklı farklı boyutlarda çok sayıda pencere ile tarama yapar.

* Nesne bulunma olasılığı olan bölgeler belirleniyor.
* 2000 civarında öneri bir kaç saniye içersinde yapılır.

Bölge önerisi yapılırken yapay zeka kullanılmaz, geleneksel resim işleme algoritmaları kullanılır.

![Screenshot_2020-03-06_14-43-14](https://user-images.githubusercontent.com/54184905/76167342-ee48b900-6176-11ea-9f99-904be5219146.png)


# Region-Based Conolutional Nerual Network (R-CNN)

![Screenshot_2020-03-06_14-52-28](https://user-images.githubusercontent.com/54184905/76167447-c9087a80-6177-11ea-9db7-9f7d64b63ad8.png)

* Bölge önerisi kullanılır.
* 2000 e yakın bölge tespit edilir.
* Bu bölgelerin boyutları eşitlenir ve CNN ağından geçirilir.
* Her bölge Convret 'ten geçer.
* SVM ile sınıflandırma yapılır (Gözetimli öğrenme kullanan makine öğrenmesi)
* Sınıflar için linear regrasyon (Bir veya birden fazla bağımsız değişken ile başka bir bağımlı değişken arasındaki bağlantıyı moddelemek için kullanılan yöntem.) kullanırız.

* Eğitim aşaması:
1-) Softmax sınıflandırıcı ile ağ eğitimi (Log loss)

2-) SVM eğitimi (Hinge loss)

3-) Sınırlayıcı eğitimi (least squares)


# Fast R-CNN

![maxresdefault](https://user-images.githubusercontent.com/54184905/76167657-5ef0d500-6179-11ea-898e-b07853fa47cd.jpg)

* Resmi ConvNet ağından geçirip özellik haritası çıkartırız.
* Selective Sercah ile 2000 e yakın bölge belirleriz.
* Artık her bölgeyi CNN den geçirmiyoruz, Buda bize hız kazandırır.
* Özelliklerde boyut eşitlemesi yaparız. (Rol Pooling)
* Sınıflandırma yapılır. (Softmax sınıflandırıcı)


# Faster R-CNN

![Screenshot_2020-03-06_15-05-47](https://user-images.githubusercontent.com/54184905/76167779-5947bf00-617a-11ea-8ce8-4d6e02877288.png)

* Resmi ConvNet ağından geçirip özellik haritası çıkartırız.
* Ayrı bir bölge önerisi ağı oluştururuz ve bu bölgeleri bu ağda tespit ederiz.
* Tespit işleminden sonra Fast R-CNN ile aynı işleme devam eder.
* Bölge önerisi bulma yolumuzdaki farklılıktan dolayı hız kazanırız.
* iki Ağ eğitiriz (ConvNet, Bölge önerisi ağı)

# Nesne tanıma ve sınıflandırma süreleri

![Screenshot_2020-03-06_15-08-30](https://user-images.githubusercontent.com/54184905/76167992-feaf6280-617b-11ea-91c5-8b733c9eee33.png)

* En uzun sürede işlemi yapan R-CNN


# Single Shot Multibox Detecton (SSD)

* Tek seferde nesne tanıma yapar
* Resim CNN den geçirilir.
* Farklı boyutlarda özellik haritaları çıkartılır.
* 3x3 filitre ile az miktarda dikdörtgensel sınırlar tespit ederiz. Bu işlemde hem sınırlar hemde sınıflandırmalar belli olur.
* Eğitim esnasında doğru olan sınırlar ve tahmin olan sınırlar karşılaştırılır, en iyi tahmini yapan ve 0.5 oranının üstündeki dikdörtgenleri pozitif olarak işaretler

![Screenshot_2020-03-06_15-10-49](https://user-images.githubusercontent.com/54184905/76167930-7a5cdf80-617b-11ea-8f8d-e5fb80b6c81a.png)

![Screenshot_2020-03-06_15-14-54](https://user-images.githubusercontent.com/54184905/76168017-5f3e9f80-617c-11ea-8116-47d8b2694f60.png)

* Hız önemli ise SSD, isabet önemli ise Faster R-CNN 'i öneririm


# Mask R-CNN

* Amaç resim içindeki nesneyi tespit edip tüm pixellerine ulaşmak.
* Temelinde Faster R-CNN vardır.
* Mask R-CNN de maskelemek için farklı bir dal vardır.
* Maske olan pixeller 1 ile maske olmayan pixeller 0 ile işaretlenir ve bir matris elde ederiz.


