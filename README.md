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

### Sonuçlar ve Performans

- **Eğitim Doğruluğu**: Eğitim setindeki doğruluk %... olarak hesaplanmıştır.  
- **Test Doğruluğu**: Test setindeki doğruluk %... olarak hesaplanmıştır.  
- **Manipüle Edilmiş Test Doğruluğu**: Manipüle edilmiş veri seti üzerinde doğruluk %... olarak gözlemlenmiştir.  
- **Renk Sabitliği Performansı**: Gray World algoritması sonrası model doğruluğu %... olarak kaydedilmiştir.  

---

### Çalıştırma Talimatları

1. Kaggle veri setini indirip proje klasöründe uygun yere yerleştirin.  
2. Kodları parça parça çalıştırarak aşağıdaki adımları takip edin:  
   - **Veri Hazırlama**: Görselleri eğitim ve test setlerine ayırın.  
   - **Model Eğitimi**: CNN modelini eğiterek kaydedin.  
   - **Görüntü Manipülasyonu**: Farklı ışık koşulları için manipüle edilmiş veri setini oluşturun.  
   - **Renk Sabitliği**: Gray World algoritmasını uygulayın ve performansı karşılaştırın.  

---

PROJE KAGGLE LİNKİ : https://www.kaggle.com/code/ahmeteren9/aygaz-g-r-nt-leme-bootcamp-projesi
