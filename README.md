# PyTorch-ve-Derin-renme-CNN-MNIST-
# CNN ile MNIST Veri Seti Üzerinde Derin Öğrenme
Bu proje, temel bir derin öğrenme uygulaması olan Convolutional Neural Network (CNN) kullanarak MNIST veri setindeki el yazısı rakamlarını sınıflandırmayı amaçlamaktadır. Proje, PyTorch kütüphanesini kullanarak bir CNN modeli oluşturur, eğitir ve test eder.

## Requirements
* Python 3.x
* PyTorch
* torchvision
* OpenCV
* matplotlib
* Pillow (PIL)
* numpy

### You can install the required packages using pip:
pip install torch torchvision opencv-python matplotlib pillow numpy

## Veri Setinin İndirilmesi
Proje, MNIST veri setini torchvision.datasets modülü ile otomatik olarak indirir. Bunun için kodunuzu çalıştırdığınızda, veri seti otomatik olarak indirilecektir.

## Model Mimarisi
Model, iki katmanlı bir Convolutional Neural Network'ten (CNN) oluşmaktadır:

#### İlk Convolutional Katman (cnn1): 1 giriş kanalı (gri seviyeli görüntü) ve 8 filtre ile 3x3 çekirdek boyutuna sahip.
#### İkinci Convolutional Katman (cnn2): 8 giriş kanalı ve 32 filtre ile 5x5 çekirdek boyutuna sahip.
#### Max-Pooling: Her bir Convolutional katmandan sonra 2x2 Max-Pooling uygulanır.
#### Tam Bağlantılı (Fully Connected) Katmanlar: 600 ve 10 nöronlu iki adet tam bağlantılı katman.
Modelin her katmanı ReLU aktivasyon fonksiyonu kullanır. Ayrıca, modelin aşırı öğrenme (overfitting) yapmasını engellemek için Dropout katmanı eklenmiştir.

## Eğitim ve Test Süreci
### Veri Seti Yükleme:
Eğitim ve test için MNIST veri seti PyTorch'un datasets.MNIST() modülü ile yüklenir. Görüntüler normalize edilir ve tensör haline getirilir.

### Modelin Eğitimi:
Model, 25 epoch boyunca CrossEntropyLoss kayıp fonksiyonu ve Stochastic Gradient Descent (SGD) optimizasyon algoritması ile eğitilmektedir. Her epoch sonunda eğitim doğruluğu ve kaybı hesaplanır.

### Test Süreci:
Test aşamasında, model daha önce görmediği veri ile sınanır ve doğruluk oranı hesaplanır.

## Sonuçlar
Kod, modelin eğitim ve test performansını görselleştirir ve modelin tahmin yeteneğini değerlendirir. Eğitim ve test kayıpları, doğruluk oranları ve tahmin sonuçları grafiklerle gösterilir.
Modelin eğitim ve test süreçleri sonunda elde edilen doğruluk ve kayıplar aşağıdaki gibidir:
Eğitim Doğruluğu: %98.6
Test Doğruluğu: %98.75

