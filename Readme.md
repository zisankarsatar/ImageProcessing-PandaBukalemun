<h1 align="center">Panda-Bukalemun</h1>

> Adım adım algoritmayı iyileştirerek görüntü işleme.

### ✨ CNN-Maxpool nedir, nasıl çalışır?
<div>
Sınıflandırma (sınıflandırma), sınıflandırma+lokalize etme (classification+localization), nesne tespiti (object detection) ve resim bölütleme (segmentation) işlemlerine yönelik çalışmalarının neredeyse tamamı CNN algoritması kullanılarak gerçekleştirilmektedir.
CNN tüm katmanları birbirine tam bağlantılı olarak tasarlanmış ve her bir evrişimsel filtre öğrenilmesi gereken öznitelikleri oluşturmaktadır. Bu evrişimsel katmalar “pooling” katmaları sayesinde hem boyut hem eğitim süresinde optimizasyonu sağlamaktadır.
</div>

### ✨ Data Augmentation Nedir?

Bazı uygulamalarda mevcut veri setinin az olması yöntem başarısının düşürü. Bu durumu önlemek amacıyla mevcut veri setinden sentetik veriler üretilerek örnek sayısı artırılmaktadır, buna da “Data Augmentation” adı verilmektedir.Nesne tanıma problemlerinde genellikle orjinal resmi döndürme (rotation), öteleme (translation), ölçekleme (scaling), resme gürültü (Gauss vb.) ekleme (add noise), resmi belirli bölgeden kırpma (cropping) gibi farklı teknikler uygulanmaktadır.

### ✨ Drop-out Yönetimi Nedir?

Kısaca eğitim sırasında aşırı öğrenmeyi(overfitting) engellemek için bazı nöronları unutmak için kullanılanılır diyebiliriz.

/// Epoch kesmek nedir ne işe yarar?

## VeriSeti

```sh
https://www.kaggle.com/zisankarsatar/panda-chameleon
```

## Toplu Resim İnderme

Toplu resim indirmek için yararlandığım kaynak: https://medium.com/@ozgurs/h%C4%B1zl%C4%B1-%C5%9Fekilde-resim-dataseti-olu%C5%9Fturma-cfccf4a40c79

/* Tüm fotoğrafları eit boyutlara getirmek için kullandığım uygulama: [Fotosizer] https://www.fotosizer.com/ */

/*
* Ödevin adımları:<br>
A) İLK ADIM : Normal olarak CNN-maxpool olayı sürecinde örneğin 20-30 epoch seçilerek <br>
		* Train/validation accuracy grafiği<br>
		* train/validation  loss grafiği<br>
B) İKİNCİ ADIM: Data augmentation yöntemi ile deney tekrarlanmalı<br>
		* Train/validation accuracy grafiği<br>
		* train/validation  loss grafiği<br>
C) ÜÇÜNCÜ ADIM: Drop-out  ile deney tekrarlanmalı (augmentation dan devam ediyoruz en baştan başlamıyoruz!)  yani:  augmentation + drop_out etkisi gözlenecek! <br>
		* Train/validation accuracy grafiği<br>
		* train/validation  loss grafiği<br>
D) Overfitt eden nokta gözleniyorsa train süreci erken bir EPOCH’ta kesilerek  (artık augmentation, drop-out üzerine bir de epoch etkisi gözlenecek!)    <br>
		* Train/validation accuracy grafiği<br>
		* train/validation  loss grafiği<br>
*/
