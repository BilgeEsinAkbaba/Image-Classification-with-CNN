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

**Normal Test Seti**: Model, bu set üzerinde en yüksek doğruluk oranına ulaşmıştır. Normal veriler üzerinde eğitildiği için model, bu tür verilere en iyi şekilde uyum sağlamıştır.

**Manipüle Edilmiş Test Seti**: : Parlaklık artırma ve bulanıklaştırma manipülasyonları sonrası modelin doğruluk oranında önemli bir düşüş gözlemlenmiştir. Bu durum, modelin manipülasyonlar karşısında dayanıklı olmadığını göstermektedir.

**Renk Sabitliği Test Seti**:  Renk sabitliği algoritması uygulanan test setinde beklenen performans artışı gerçekleşmemiştir. Bunun nedeni, modelin eğitim aşamasında renk sabitliği uygulanmış görüntülerle eğitilmemiş olmasıdır. 

## **💻 Kullanılan Teknolojiler ve Kütüphaneler**

Python

- **TensorFlow ve Keras**: Model tasarımı, eğitimi ve değerlendirilmesi için kullanılmıştır.

- **OpenCV**: Görüntü işleme adımlarında kullanılmıştır.

- **NumPy**: Sayısal veri işlemleri için kullanılmıştır.

- **Matplotlib**: Sonuçların görselleştirilmesi için kullanılmıştır.

## **📈 Sonuç ve Öneriler**

Bu proje, Convolutional Neural Network (CNN) modellerinin görüntü sınıflandırma görevlerindeki başarısını ve manipülasyonlar ile renk sabitliği gibi dış faktörlerin model performansı üzerindeki etkisini kapsamlı bir şekilde incelemiştir. Elde edilen sonuçlar, modelin manipülasyonlar karşısında dayanıklılığının artırılması gerektiğini ve renk sabitliği algoritmalarının daha etkili bir şekilde entegre edilmesinin önemini göstermektedir.

Gelecekteki çalışmalar için şu öneriler sunulabilir:

**Eğitim Setinin Manipülasyonlu Görüntülerle Zenginleştirilmesi**:
Eğitim setine manipülasyonlu (parlaklık artırılmış, bulanıklaştırılmış) görüntülerin dahil edilmesi, modelin bu tür değişikliklere karşı dayanıklılığını artırabilir. Bu, modelin gerçek hayatta karşılaşabileceği veri çeşitliliği ile başa çıkma yeteneğini geliştirecektir. 

**Daha Büyük ve Çeşitli Veri Setleri Kullanımı**:
Veri setinin boyutu ve çeşitliliği artırılarak modelin genel performansı iyileştirilebilir. Daha fazla sınıf içeren ve çeşitli aydınlatma, açı, kalite gibi faktörlere sahip görüntüler içeren bir veri seti kullanmak modelin daha genel özellikler öğrenmesini sağlayabilir.

**Alternatif Renk Sabitliği Algoritmalarının Test Edilmesi**:
Gray World algoritması yerine daha gelişmiş ve etkili renk sabitliği algoritmaları test edilebilir. 

**Transfer Learning ile Model Performansının Artırılması**:
Önceden eğitilmiş bir CNN modeli (örneğin, ResNet, VGG veya EfficientNet) kullanarak transfer öğrenimi yapılabilir. Bu, daha küçük veri setleri üzerinde bile yüksek performans elde etmeyi sağlar. Bu modeller, genellikle geniş ve çeşitli veri setleri üzerinde eğitildiği için manipülasyonlara ve renk değişikliklerine karşı daha dayanıklıdır. Eğitim süresi önemli ölçüde azaltılabilir.

**Model Mimarisi Optimizasyonu**:
Daha derin ve karmaşık CNN mimarileri test edilebilir.
Dropout oranları optimize edilerek aşırı öğrenme (overfitting) riski azaltılabilir.
Farklı optimizasyon algoritmaları (örneğin, SGD, RMSprop) kullanılarak eğitim performansı iyileştirilebilir.

**Farklı Manipülasyon Tekniklerinin Entegrasyonu**:
Parlaklık ve bulanıklaştırma dışındaki manipülasyonlar da (örneğin, döndürme, kırpma, renk değişimi) test edilebilir.

**Ayrıntılı Performans Analizi ve Görselleştirme**:
Modelin hangi sınıflarda daha iyi veya kötü performans gösterdiği detaylı bir şekilde analiz edilmelidir.
Görselleştirme teknikleri (örneğin, t-SNE, confusion matrix) kullanılarak modelin zayıf ve güçlü yönleri daha iyi anlaşılabilir.

**Gerçek Zamanlı Uygulamalar için Optimize Edilmesi**:
Modelin daha hızlı ve hafif bir versiyonu oluşturularak mobil veya IoT cihazlarda kullanımı sağlanabilir.
Quantization ve pruning gibi tekniklerle model boyutu küçültülebilir.

**Manipülasyon ve Renk Sabitliği için Özel Eğitim Süreçleri**:
Manipüle edilmiş ve renk sabitliği uygulanmış görüntülerle ayrı ayrı eğitim yapılarak bu tür durumlar için özel modeller oluşturulabilir.
Ensemblling (birden fazla modeli birleştirme) yöntemleriyle bu modellerin sonuçları birleştirilebilir.

## Kaggle Linki: https://www.kaggle.com/code/bilgeesinakbaba/image-classification-with-cnn
