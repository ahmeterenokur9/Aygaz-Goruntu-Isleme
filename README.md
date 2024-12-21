# Aygaz Görüntü Işleme

### Proje Adı: Hayvan Sınıflandırma ve Görüntü İşleme Projesi

Bu proje, Kaggle'dan alınan *Animals with Attributes 2* veri seti kullanılarak belirli hayvan türlerini sınıflandırmaya yönelik bir makine öğrenimi modelinin geliştirilmesini, eğitilmesini ve değerlendirilmesini kapsamaktadır. Ayrıca, farklı ışık koşullarında performansı artırmak için görüntü manipülasyonu ve renk sabitliği algoritmalarını içermektedir.  

---

### Proje Özeti

Proje dört temel aşamadan oluşmaktadır:  
1. **Veri Hazırlama**: Seçilen hayvan türlerine ait görselleri organize etmek ve eğitim/test setlerine ayırmak.  
2. **Makine Öğrenimi Modeli**: Bir Convolutional Neural Network (CNN) modeli tasarlamak, eğitmek ve değerlendirmek.  
3. **Görüntü Manipülasyonu**: Görsellerin parlaklık seviyelerini manipüle ederek model performansını farklı koşullarda test etmek.  
4. **Renk Sabitliği**: Görseller üzerinde Gray World algoritması uygulayarak renk dengesi sağlamak ve model başarımını analiz etmek.  

---

### Kullanılan Veri Seti

- **Veri Kaynağı**: Kaggle - *Animals with Attributes 2*  
- **Seçilen Hayvan Türleri**:  
  `Collie, Dolphin, Elephant, Fox, Moose, Rabbit, Sheep, Squirrel, Giant Panda, Polar Bear`  
- **Veri Sayısı**:  
  Her türden maksimum 650 görüntü, bunların %70'i eğitim ve %30'u test için ayrılmıştır.  

---

### Kullanılan Kütüphaneler

Projede aşağıdaki Python kütüphaneleri ve araçlar kullanılmıştır:  
- **Veri İşleme**: `os`, `shutil`, `Pillow`  
- **Makine Öğrenimi**: `TensorFlow`, `scikit-learn`, `ImageDataGenerator`  
- **Görselleştirme**: `Matplotlib`, `OpenCV`  

---

### Analiz ve Uygulamalar

1. **CNN Modeli**:  
   - 3 Katmanlı bir Convolutional Neural Network (CNN) tasarlanmıştır.  
   - Model, `categorical_crossentropy` kaybı ve `adam` optimizasyon yöntemi ile eğitilmiştir.  
   - Modelin doğruluğu eğitim ve test setleri üzerinde hesaplanmıştır.  

2. **Görüntü Manipülasyonu**:  
   - Görseller farklı parlaklık seviyelerine (0.5, 1.0, 1.5) göre manipüle edilmiştir.  
   - Manipüle edilmiş veri seti üzerinde model performansı analiz edilmiştir.  

3. **Renk Sabitliği**:  
   - Gray World algoritması kullanılarak görsellerde renk sabitliği sağlanmıştır.  
   - Bu işlem sonucunda model performansındaki değişiklikler değerlendirilmiştir.  

---
# CNN Modeli Performans Analizi ve Çözüm Önerileri

## Mevcut Durumun Analizi

Test sonuçlarımız, modelin farklı veri setleri üzerindeki performansında dikkat çekici bir düşüş eğilimi göstermektedir. Orijinal test setinde %60.71 olan başarı oranı, ışık manipülasyonları sonrasında %57.16'ya, renk sabitliği uygulaması sonrasında ise %50.66'ya gerilemiştir. Bu düşüş trendi, önemli teknik ve metodolojik çıkarımlar yapmamızı gerektirmektedir.

## Performans Düşüşünün Olası Nedenleri

1. **Renk Sabitliği Algoritmasının Etkisi**
   - Renk sabitliği algoritmasının görüntülerdeki önemli özellikleri beklenmedik şekilde değiştirmiş olması muhtemeldir
   - Algoritmanın aşırı normalizasyon yaparak ayırt edici özellikleri kaybetmiş olabileceği düşünülmektedir
   - Model eğitiminde kullanılan veriler ile işlenmiş test verileri arasında tutarsızlık oluşmuş olabilir

2. **Model Mimarisinin Dayanıklılığı**
   - Mevcut CNN modelinin ışık değişimlerine karşı yeterince dayanıklı olmadığı görülmektedir
   - Feature extraction katmanlarının çeşitli ışık koşullarında tutarlı özellikler çıkaramadığı anlaşılmaktadır

## Önerilen Çözüm Yolları

### 1. Veri Augmentasyonu Geliştirmeleri
- Eğitim setine çeşitli ışık koşullarında manipüle edilmiş görüntüler eklenmelidir
- Parlaklık, kontrast ve renk dönüşümleri içeren veri çoğaltma teknikleri uygulanmalıdır
- Random brightness ve random contrast augmentasyonları modele dahil edilmelidir

### 2. Model Mimarisi İyileştirmeleri
- Batch normalization katmanları eklenerek model dayanıklılığı artırılmalıdır
- Dropout oranları gözden geçirilmeli ve gerekirse artırılmalıdır
- Daha derin ve geniş bir mimari kullanılarak model kapasitesi artırılabilir

### 3. Renk Sabitliği Yaklaşımının Revizyonu
- Mevcut renk sabitliği algoritması yerine daha az agresif normalizasyon teknikleri denenmelidir
- Histogram eşitleme gibi alternatif görüntü ön işleme teknikleri değerlendirilmelidir
- Renk sabitliği işlemi eğitim setine de uygulanarak tutarlılık sağlanmalıdır

### 4. Ensemble Öğrenme Yaklaşımı
- Farklı ışık koşullarında eğitilmiş multiple modeller oluşturulabilir
- Bu modellerin tahminleri birleştirilerek daha gürbüz bir sistem elde edilebilir



PROJE KAGGLE LİNKİ : https://www.kaggle.com/code/ahmeteren9/aygaz-g-r-nt-leme-bootcamp-projesi
