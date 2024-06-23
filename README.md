## Tamamen Bağlı Sinir Ağı (FCN) ile Zaman Serisi Tahmini
Bu depo, Tamamen Bağlı Sinir Ağı (FCN) kullanarak suyun Tuzluluk seviyelerini tahmin etmek için kod içermektedir. Model, çeşitli çevresel parametrelerin bulunduğu bir veri kümesi üzerinde eğitilmiştir.

## Veri Kümesi

Veri kümesi şu sütunları içermektedir:
- Date: Gözlem tarihi
- Salinity (ppt): Binlerde tuzluluk seviyesi (ppt)
- DissolvedOxygen (mg/L): Suda çözünmüş oksijen konsantrasyonu (mg/L)
- pH: Suyun pH değeri
- SecchiDepth (m): Su berraklığı ölçümü (metre)
- WaterDepth (m): Su derinliği (metre)
- WaterTemp (C): Su sıcaklığı (Celcius)
- AirTemp (C): Hava sıcaklığı (Celcius)

## Veri Önişleme

- Veri Temizleme: Eksik değer içeren satırlar (NaN) kaldırılır.

- Özellik Seçimi: Hedef değişken olarak Salinity (ppt) kullanılır, diğer sütunlar özellik olarak seçilir.

- Veri Ölçeklendirme: Veriler MinMaxScaler kullanılarak 0 ile 1 arasında normalize edilir.

- Eğitim-Test Ayırma: Veri, %67'si eğitim ve %33'ü test için olmak üzere ikiye ayrılır.

## Model Mimarisi

Model mimarisi şu şekildedir:

- Giriş katmanı, özellik matrisindeki sütun sayısına eşittir.
- İki gizli katman: İlk katmanda 50, ikinci katmanda 25 nöron bulunur, her ikisi de ReLU aktivasyon fonksiyonu kullanır.
- Çıkış katmanı: Salinity (ppt) tahmin etmek için 1 nöron içerir.
- Model, Adam optimizerı ve Ortalama Kare Hata (MSE) kayıp fonksiyonu ile derlenir.

## Eğitim
Model, 50 epoch ve batch boyutu 1 ile eğitilir. Eğitim sırasında modelin performansı eğitim setinde izlenir.

## Değerlendirme ve Görselleştirme

Eğitim sonrasında, modelin tahminleri eğitim ve test setleri üzerinde değerlendirilir. Tahminler, gerçek değerlerle karşılaştırılabilir olması için orijinal birimlere geri ölçeklenir. Görselleştirmeler arasında şunlar yer alır:

- Eğitim ve test setleri için gerçek ve tahmin edilen değerlerin karşılaştırılması.
- Epoklar boyunca model eğitim kaybının (loss) grafiği, yakınsama ve performansı değerlendirmek için.

## Gereksinimler
- Python 3.x
- TensorFlow/Keras
- Pandas
- NumPy
- Matplotlib
- Scikit-learn


  

