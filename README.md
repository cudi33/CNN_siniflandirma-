# 🧠 CNN Tabanlı Görüntü Sınıflandırma Projesi

## 📌 Proje Konusu
Bu projede, kendi oluşturduğum görüntü veri seti kullanılarak **Convolutional Neural Network (CNN)** tabanlı bir sınıflandırma modeli geliştirilmiştir.  
Amaç; günlük hayatta kullanılan **kaşık, çatal ve bıçak** nesnelerini görüntüler üzerinden otomatik olarak sınıflandırmaktır.

Proje kapsamında üç farklı model geliştirilmiş ve performansları karşılaştırılmıştır:
- Model 1: Transfer Learning (VGG16)
- Model 2: Temel CNN Mimarisi
- Model 3: Geliştirilmiş CNN (Data Augmentation + Hiperparametre Optimizasyonu)

---

## 👤 Öğrenci Bilgileri
- **Ad Soyad:** cudi şami
- **Okul Numarası:** 2012721308
---

## 📂 Veri Seti Bilgisi

### 🔹 Veri Seti İçeriği
Veri seti tamamen tarafımdan oluşturulmuştur ve internetten indirilen hazır veri setleri **kullanılmamıştır**.

Sınıflar:
- Kaşık
- Çatal
- Bıçak

Her sınıf için farklı:
- Açı
- Işık koşulu
- Arka plan

özelliklerine sahip görüntüler kullanılmıştır.

### 🔹 Görüntü Özellikleri
- Minimum boyut: 64x64
- Kullanılan boyut: **128x128**
- Toplam sınıf sayısı: **3**

---

---

## 🧩 Model 1 – Transfer Learning (VGG16)

Bu modelde, ImageNet veri seti üzerinde önceden eğitilmiş **VGG16** mimarisi kullanılmıştır.

### Kullanılan Yaklaşım:
- VGG16 temel katmanları dondurulmuştur
- Üzerine özel Dense ve Dropout katmanları eklenmiştir
- Softmax çıkış katmanı ile 3 sınıf tahmini yapılmıştır

### Amaç:
- Küçük veri setlerinde yüksek başarı elde etmek
- Eğitimi hızlandırmak

---

## 🧩 Model 2 – Temel CNN Mimarisi

Bu modelde sıfırdan oluşturulmuş bir CNN mimarisi kullanılmıştır.

### Mimari Yapı:
- 3 adet Convolution + MaxPooling katmanı
- Flatten + Dense katmanları
- Dropout ile overfitting kontrolü

### Amaç:
- CNN mimarisinin temel mantığını göstermek
- Transfer learning olmadan performansı gözlemlemek

---

## 🧩 Model 3 – Geliştirilmiş CNN Modeli

Bu model, Model 2 temel alınarak geliştirilmiştir ve projenin **en önemli aşamasıdır**.

### Uygulanan Geliştirmeler:

#### ✅ Data Augmentation
Eğitim verisi aşağıdaki işlemlerle çeşitlendirilmiştir:
- Rotation
- Width / Height Shift
- Zoom
- Horizontal Flip

#### ✅ Hiperparametre Denemeleri
Farklı kombinasyonlar test edilmiştir:
- Filtre sayıları (32-64-128 / 64-128-256)
- Öğrenme oranı (0.001 / 0.0005)
- Dropout oranı (0.3 / 0.5)
- Dense katman birim sayısı (128 / 256)

#### ✅ Early Stopping
- Doğrulama kaybı iyileşmediğinde eğitim durdurulmuştur
- En iyi ağırlıklar geri yüklenmiştir

---

## 📊 Deney Sonuçları ve Karşılaştırma

Tüm deneylerin sonuçları tablo haline getirilmiş ve doğrulama doğrulukları karşılaştırılmıştır.

| Deneme | Filtreler     | LR    | Dropout | Dense | En İyi Val Accuracy |
|------|---------------|-------|---------|-------|---------------------|
| Exp A | 32-64-128     | 1e-3  | 0.5     | 128   | ~0.69 |
| Exp B | 64-128-256    | 5e-4  | 0.5     | 256   | **~0.78** |
| Exp C | 32-64-128     | 5e-4  | 0.3     | 256   | ~0.78 |

---

## 🏆 En İyi Model ve Yorum

Deney sonuçlarına göre **Model 3 (Exp B)** en yüksek doğrulama doğruluğunu vermiştir.

### Genel Yorum:
- Data augmentation modelin genelleme yeteneğini artırmıştır
- Daha derin CNN mimarisi daha başarılı sonuçlar üretmiştir
- Model 3, Model 1 ve Model 2’ye göre daha dengeli ve stabil sonuçlar vermiştir

---

## ⚠️ Akademik Dürüstlük Beyanı
Bu projede kullanılan:
- Veri seti
- Kodlar
- Model mimarileri

tamamen bana aittir.  
Hazır notebook veya internetten indirilen veri seti **kullanılmamıştır**.

---

## ✅ Sonuç
Bu projede CNN tabanlı görüntü sınıflandırma problemi başarıyla çözülmüş, farklı model mimarileri karşılaştırılmış ve en iyi performansı veren yapı detaylı şekilde analiz edilmiştir.



