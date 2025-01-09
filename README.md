# Derin Öğrenme ile Hava Durumu Tahmini

Bu proje, geçmiş hava durumu verilerini kullanarak gelecekteki hava durumu koşullarını tahmin etmek için **Uzun Kısa Süreli Bellek (LSTM)** ağlarını kullanmaktadır. Model, sıcaklıkları üç kategoriye ayırarak sınıflandırır: `soğuk`, `orta`, `sıcak`.

## Proje Genel Bakışı
Bu projenin amaçları:
1. Geçmiş hava durumu verilerini analiz ederek gelecekteki sıcaklıkları tahmin etmek.
2. Tahmin edilen sıcaklıkları önceden tanımlanmış kategorilere (`soğuk`, `orta`, `sıcak`) sınıflandırmak.
3. Verileri görselleştirerek tahminler ve model performansı hakkında bilgi edinmek.

### Ana Özellikler:
- **Veri Hazırlama**: Sıralı sıcaklık verileri normalize edilir ve eğitim için sınıflandırılır.
- **Derin Öğrenme Modeli**: LSTM tabanlı bir mimari, hava durumu desenlerindeki zaman bağımlılıklarını yakalamak için uygulanmıştır.
- **Görselleştirme**: Tahminler ve model performansı Matplotlib ve Seaborn ile görselleştirilmiştir.
- **Özel Tahminler**: Geçmiş desenlere dayalı olarak belirli bir tarih için tahminler yapılabilir.

## Veri Seti
Bu projede kullanılan veri seti, 2018 ile 2023 yılları arasındaki İstanbul hava durumu verilerinden oluşmaktadır. Veri seti toplamda 2000 adet sıcaklık kaydı içermektedir.
Daha dengeli ve anlamlı bir eğitim sağlamak için veri artırımı teknikleri uygulanmış, eksik veya yetersiz veriler sentetik olarak üretilmiştir. Bu sayede modelin farklı sıcaklık desenlerini daha iyi öğrenmesi sağlanmıştır.

## Kullanılan Teknolojiler
- Python (Pandas, NumPy, Matplotlib, Seaborn)
- TensorFlow/Keras
- Scikit-learn

## Nasıl Çalışır?
1. **Veri Ön İşleme**: Geçmiş sıcaklık verileri normalize edilir ve sıcaklık kategorilerine sınıflandırılır.
2. **Model Eğitimi**: LSTM modeli, geçmiş sıcaklık verileri üzerinde eğitilerek gelecekteki kategorileri tahmin eder.
3. **Tahmin**: Eğitimli model, bir tarih için sıcaklık kategorisini yüksek güvenilirlik oranıyla tahmin eder.

## Örnek Tahmin
`2024-06-08` tarihi için modelin tahmini:
- **Sıcaklık Kategorisi**: Sıcak
- **Güvenilirlik**: %92,72
- **Tarihsel Bilgi**: Bu tarihteki geçmiş sıcaklıklar ortalama 22.1°C (aralık: 20.0°C - 24.9°C).

## Sonuçlar
- **Model Doğruluğu**: Test veri setinde ~%85 doğruluk sağlandı.
- **Tahmin Güvenilirliği**: Model, geçmiş verilere dayalı olarak tutarlı ve yüksek güvenilirlikte tahminler üretiyor.

