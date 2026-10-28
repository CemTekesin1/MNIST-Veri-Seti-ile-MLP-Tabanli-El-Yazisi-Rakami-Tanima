# El Yazısı Rakam Tanıma (MNIST) - Multi-Layer Perceptron (MLP)

Bu proje, PyTorch kullanarak MNIST veri setindeki el yazısı rakamları (`0-9`) tanımak amacıyla geliştirilmiş bir **Çok Katmanlı Algılayıcı (Multi-Layer Perceptron - MLP)** yapay sinir ağı modelidir. Proje kapsamında hiçbir Evrişimli Sinir Ağı (CNN) mimarisi kullanılmamış, tamamen tam bağlantılı (Fully Connected / Linear) katmanlar tercih edilmiştir.

---

## 🚀 Proje Mimarisi ve Özellikleri

* **Model Türü:** Multi-Layer Perceptron (MLP)
* **Girdi Katmanı:** 784 nötron (28x28 piksel düzleştirilmiş görüntü)
* **Gizli Katman 1:** 256 nötron + **ReLU** aktivasyon fonksiyonu
* **Gizli Katman 2:** 128 nötron + **ReLU** aktivasyon fonksiyonu
* **Çıkış Katmanı:** 10 nötron (0 ile 9 arasındaki sınıflar için)
* **Optimizasyon:** Adam Optimizer (Öğrenme oranı: `0.001`)
* **Kayıp Fonksiyonu:** CrossEntropyLoss
* **Veri Bölümleme:** MNIST Eğitim setinin %80'i Eğitim, %20'si Doğrulama (Validation) olarak ayrılmıştır.

---

## 📊 Eğitim ve Performans Sonuçları

Model, Google Colab ortamında 10 Epoch boyunca eğitilmiş ve test veri seti üzerinde yüksek bir doğruluk oranına ulaşmıştır:

* **Toplam Eğitim Süresi:** ~181.39 saniye
* **Final Test Doğruluk Oranı (Test Accuracy):** **%97.37**

### Eğitim Adımları Özet Tablosu:
* **Epoch [1/10]:** Train Loss: 0.2561 | Train Acc: 92.22% | Val Acc: 95.85%
* **Epoch [5/10]:** Train Loss: 0.0424 | Train Acc: 98.62% | Val Acc: 97.38%
* **Epoch [10/10]:** Train Loss: 0.0203 | Train Acc: 99.33% | Val Acc: **97.57%**

---

## ✍️ Kendi El Yazısı Rakam Testi Sonuçları

Modelin genelleştirme yeteneğini test etmek amacıyla, gerçek hayatta kağıda yazılıp dijital ortama aktarılan özel test görselleri model üzerinden geçirilmiş ve başarılı sonuçlar elde edilmiştir:

* **Dosya 2:** Tahmin: **3** (Güven Oranı: %99.99)
* **Dosya 4:** Tahmin: **2** (Güven Oranı: %99.02)
* **Dosya 7:** Tahmin: **3** (Güven Oranı: %99.97)
* **Dosya 10:** Tahmin: **3** (Güven Oranı: %91.73)
* **Dosya 11:** Tahmin: **7** (Güven Oranı: %84.18)

---

## 🛠️ Kurulum ve Çalıştırma

Projeyi kendi yerel ortamınızda veya Google Colab üzerinde çalıştırmak için şu adımları izleyebilirsiniz:

1. Gerekli kütüphanelerin yüklenmesi:
   ```bash
   pip install torch torchvision pillow matplotlib
