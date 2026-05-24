# plant-disease-classification
Bu proje, bitki yapraklarındaki hastalıkları görüntü işleme ve derin öğrenme yöntemleriyle tespit etmek amacıyla geliştirilmiştir. Model, sağlıklı ve hastalıklı yaprak görüntülerini birbirinden ayırt edebilmek için konvolüsyonel sinir ağları (CNN) mimarisini kullanır.

## Proje İçeriği

Proje kapsamında aşağıdaki aşamalar gerçekleştirilmiştir:

* **Veri Seti Hazırlığı:** Kaggle üzerindeki PlantVillage veri seti kullanılarak 15 farklı sınıfa ait bitki görüntüleri indirilmiş ve işlenmiştir.
* **Veri Artırma (Data Augmentation):** Modelin genelleme yeteneğini artırmak için eğitim verileri üzerinde döndürme, yakınlaştırma, parlaklık değişimi ve kaydırma gibi işlemler uygulanmıştır.
* **Model Mimarisi:** Projede "PlantDiseaseNet" adıyla özelleştirilmiş, derinlik bazlı ayrılabilir konvolüsyon (Depthwise Separable Convolution) blokları içeren hafif ve etkili bir CNN mimarisi kurulmuştur.
* **Eğitim:** Model, Adam optimizasyon algoritması ve Cross-Entropy kayıp fonksiyonu ile eğitilmiştir. Aşırı öğrenmeyi (overfitting) önlemek için Early Stopping ve Learning Rate Scheduler teknikleri kullanılmıştır.
* **Analiz:** Eğitim sonrası modelin başarısı konfüzyon matrisi ve Grad-CAM görselleştirme teknikleriyle analiz edilmiştir.

## Teknik Gereksinimler

Notebook dosyasının çalıştırılabilmesi için aşağıdaki kütüphanelerin yüklü olması gerekmektedir:

* TensorFlow 2.x
* NumPy
* Matplotlib
* Scikit-learn
* Seaborn
* Kaggle API (Veri setini otomatik indirmek için)

## Nasıl Kullanılır?

1.  Notebook dosyasını Google Colab veya benzeri bir Jupyter ortamında açın.
2.  Kaggle API anahtarınızı ilgili hücreye tanımlayın veya veri setini manuel olarak yükleyin.
3.  Hücreleri sırasıyla çalıştırarak veri setini hazırlayın, modeli eğitin ve sonuçları görselleştirin.
4.  Eğitim sonunda oluşan `plant_disease_final_model.keras` dosyası ile yeni görüntüler üzerinde tahminleme yapabilirsiniz.

## Model Performansı

Model, test verileri üzerinde yüksek doğruluk oranına ulaşmaktadır. Grad-CAM sonuçları, modelin yaprak üzerindeki hastalık belirtilerine (lekeler, renk değişimleri vb.) odaklandığını doğrulamaktadır.
