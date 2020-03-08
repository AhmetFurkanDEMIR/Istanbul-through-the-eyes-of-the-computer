# Nesne Tanıma - Bölge önerisi

![Screenshot_2020-03-06_14-37-22](https://user-images.githubusercontent.com/54184905/76167234-3fa47880-6176-11ea-8146-fbdbc7fc8b83.png)

Pencere sol üst köşeden ilerlemeye başlar Kedi, köpek vb. bir nesne tespit edemezse Arka plan olarak işaretler.

Bu işlemi bir pencerede yapmaz farklı farklı boyutlarda çok sayıda pencere ile tarama yapar.

* Nesne bulunma olasılığı olan bölgeler belirleniyor.
* 2000 civarında öneri bir kaç saniye içersinde yapılır.

Bölge önerisi yapılırken yapay zeka kullanılmaz, geleneksel resim işleme algoritmaları kullanılır.

![Screenshot_2020-03-06_14-43-14](https://user-images.githubusercontent.com/54184905/76167342-ee48b900-6176-11ea-9f99-904be5219146.png)

# Region-Based Conolutional Nerual Network (R-CNN)

* Bölge önerisi kullanılır.
* 2000 e yakın bölge tespit edilir.
* Bu bölgelerin boyutları eşitlenir ve CNN ağından geçirilir.
* Her bölge Convret 'ten geçer.
* SVM ile sınıflandırma yapılır (Gözetimli öğrenme kullanan makine öğrenmesi)
* Sınıflar için linear regrasyon (Bir veya birden fazla bağımsız değişken ile başka bir bağımlı değişken arasındaki bağlantıyı moddelemek için kullanılan yöntem.) kullanırız.


