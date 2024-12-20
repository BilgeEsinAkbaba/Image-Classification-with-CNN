# Image-Classification-with-CNN

## **🐾 Hayvan Türlerini Sınıflandırma ve Model Performansı Değerlendirme Projesi**

## **📖 Proje Açıklaması**

Bu proje, Convolutional Neural Network (CNN) kullanarak hayvanlara ait görüntüleri 10 farklı sınıfa sınıflandırmayı hedeflemektedir. Çalışma kapsamında CNN modellerinin temel yapıları öğrenilmiş ve model performansı manipülasyonlar ile renk sabitliği algoritmalarının etkileri altında analiz edilmiştir.

Proje boyunca kullanılan veri seti, Kaggle'da yer alan "Animals with Attributes 2" veri setidir. Bu veri setinde farklı hayvan türlerine ait binlerce görüntü bulunmaktadır. Sınıflandırma işlemi için toplam 10 hayvan sınıfı seçilmiştir:

🐕 collie

🐬 dolphin

🐘 elephant

🦊 fox

🦌 moose

🐇 rabbit

🐑 sheep

🐿️ squirrel

🐼 giant panda

🐻‍❄️ polar bear

Bu proje, veri ön işleme adımlarından başlayarak model tasarımına, modelin eğitilmesine ve çeşitli test senaryoları ile performansının değerlendirilmesine kadar kapsamlı bir süreç sunmaktadır.

## **🔍 Proje Aşamaları**

### 1️. **Veri Setinin Kullanımı**

Kaggle'dan indirilen Animals with Attributes 2 veri seti projede kullanılmak üzere düzenlenmiştir.
Seçilen 10 hayvan sınıfı üzerinde çalışılmış, her sınıf için 650 görüntü alınmıştır.
Görüntüler, modelin giriş boyutuna uygun olarak 128x128 piksel boyutuna yeniden boyutlandırılmıştır.
Görüntüler normalize edilerek (0-1 aralığı) modelin daha iyi öğrenmesi sağlanmıştır.

### 2. **Veri Setinin Hazırlanması**

Veri seti, modelin işlem yapabileceği şekilde etiketlenmiştir. Etiketler, sayısal değerlere dönüştürülerek modelin giriş verisine uygun hale getirilmiştir.
Veri, eğitim (%70) ve test (%30) olmak üzere ikiye ayrılmıştır. Bu rastgele ayrımın her çalıştırmada aynı sonucu vermesi için sabit bir rastgelelik ayarı uygulanmıştır.
Eğitim seti, data augmentation teknikleriyle zenginleştirilmiştir. Döndürme, boyut değiştirme, yatay çevirme gibi teknikler kullanılarak modelin farklı veri türlerine dayanıklılığı artırılmıştır.

### 3. **CNN Modelinin Tasarımı**

Model, üç konvolüsyon katmanından oluşmaktadır.
Her bir konvolüsyon katmanının ardından, modelin öğrenme parametrelerini azaltmak için bir havuzlama (pooling) katmanı eklenmiştir.
Fully connected (tam bağlantılı) katmanlarla sınıflandırma işlemi gerçekleştirilmiştir.
Dropout katmanları eklenerek aşırı öğrenme (overfitting) engellenmiştir.
Çıkış katmanı, seçilen 10 sınıf için softmax aktivasyon fonksiyonu ile tasarlanmıştır.

### 4. **Modelin Eğitilmesi**

Model, eğitim seti üzerinde toplam 20 epoch boyunca eğitilmiştir.
Eğitim sırasında doğruluk (accuracy) ve kayıp (loss) değerleri izlenmiş ve değerlendirilmiştir.
Eğitim verisi, veri artırma teknikleri ile çeşitlendirilmiş ve modelin daha dayanıklı bir öğrenme süreci geçirmesi sağlanmıştır.

### 5. **Modelin Test Edilmesi**

Test seti üzerinde modelin performansı ölçülmüş ve doğruluk oranı hesaplanmıştır.
Modelin, her bir sınıf üzerindeki başarısı ayrı ayrı değerlendirilmiş ve genel performans analizi yapılmıştır.

### 6. **Resimlerin Manipüle Edilmesi**

Test setindeki görüntülere parlaklık artırma ve bulanıklaştırma gibi manipülasyonlar uygulanmıştır.
Manipüle edilmiş test seti, modelin farklı koşullara dayanıklılığını ölçmek için kullanılmıştır.

### 7. **Renk Sabitliği Algoritmasının Uygulanması**

Manipüle edilmiş görüntülere Gray World Algoritması uygulanarak renk dengesizlikleri giderilmiştir.
Renk sabitliği uygulanmış görüntüler ile model performansı tekrar test edilmiştir.

### 8. **Sonuçların Karşılaştırılması ve Raporlama**

**Normal Test Seti**: Model, bu set üzerinde en yüksek doğruluk oranına ulaşmıştır.

**Manipüle Edilmiş Test Seti**: Parlaklık ve bulanıklaştırma manipülasyonları sonrası doğruluk oranı bir miktar düşüş göstermiştir.

**Renk Sabitliği Test Seti**: Performans artışı sağlanmış ve manipülasyon etkisi azalmıştır.

## **💻 Kullanılan Teknolojiler ve Kütüphaneler**

Python

- **TensorFlow ve Keras**: Model tasarımı, eğitimi ve değerlendirilmesi için kullanılmıştır.

- **OpenCV**: Görüntü işleme adımlarında kullanılmıştır.

- **NumPy**: Sayısal veri işlemleri için kullanılmıştır.

- **Matplotlib**: Sonuçların görselleştirilmesi için kullanılmıştır.

## **📊 Proje Çıktıları ve Analiz**

**Normal Test Seti**: En yüksek doğruluk oranı elde edilmiştir.

**Manipüle Edilmiş Test Seti**: Manipülasyonlar sonrası doğruluk oranında düşüş gözlemlenmiştir.

**Renk Sabitliği Test Seti**: Performans artışı sağlanmış ve manipülasyon etkisi azalmıştır.

## **📈 Sonuç ve Öneriler**

Bu proje, CNN modellerinin görüntü sınıflandırmadaki gücünü ve manipülasyonlara karşı dayanıklılığını analiz etmiştir. Gelecekteki çalışmalar için şu öneriler sunulabilir:

Eğitim setine manipülasyonlu görüntüler eklenerek modelin dayanıklılığı artırılabilir.
Daha büyük ve çeşitli veri setleri ile model yeniden eğitilebilir.
Farklı renk sabitliği algoritmaları test edilerek daha etkili sonuçlar elde edilebilir.

Kaggle Linki: https://www.kaggle.com/code/bilgeesinakbaba/image-classification-with-cnn
