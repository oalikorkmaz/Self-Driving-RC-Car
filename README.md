# Otonom RC Araba Projesi

Bu proje, görüntü işleme ve ultrasonik sensörlerin entegrasyonu ile şerit takip ve engel algılama yeteneklerine sahip bir otonom RC araba geliştirmeyi amaçlamaktadır.

## Proje Hakkında

Geliştirilen sistem, bir Raspberry Pi ve Arduino Nano platformları kullanılarak oluşturulmuştur. Kamera ile alınan görüntüler Raspberry Pi tarafından işlenerek şerit çizgileri tespit edilmekte ve araç yönlendirme için gerekli açılar hesaplanmaktadır. Ayrıca, TensorFlow Lite ile eğitilmiş yapay zeka modeli sayesinde trafik işaretleri gibi nesneler algılanmakta ve bu bilgiler Arduino Nano'ya iletilerek aracın hareketi kontrol edilmektedir.

Ultrasonik sensörler, 30 cm ve altındaki mesafelerde engelleri algılayarak aracı durdurmaktadır. Bu sistemlerin entegrasyonu sayesinde, otonom araç hem şerit takibi yapabilmekte hem de önünde engel geldiğinde durarak güvenliğini sağlamaktadır.

## Temel Özellikler

  * **Şerit Takibi:** Görüntü işleme teknikleri (HSV renk uzayı, Canny algoritması, ROI belirleme, Hough Dönüşümü) kullanılarak yol üzerindeki şeritler tespit edilir ve aracın şerit içinde kalması sağlanır.
  * **Engel Algılama:** Ultrasonik sensörler aracılığıyla 30 cm ve altındaki engeller algılanır ve araç durdurulur.
  * **Nesne Algılama:** TensorFlow Lite ile eğitilmiş yapay zeka modeli sayesinde "dur" işareti, kırmızı, sarı ve yeşil ışık gibi trafik işaretleri algılanır ve aracın hareketine buna göre yön verilir.
  * **Mikrodenetleyici Entegrasyonu:** Raspberry Pi (görüntü işleme ve yapay zeka) ve Arduino Nano (sensör verileri ve motor kontrolü) arasındaki seri haberleşme ile sistem entegrasyonu sağlanmıştır.

## Kullanılan Teknolojiler

  * **Donanım:**
      *  Raspberry Pi 4 B+ 8GB
      *  Arduino Nano
      *  Raspberry Pi Kamera Modül 3
      *  BTS7960B 40 Amper Motor Sürücü Kartı
      *  11.1 V 3S LiPo Batarya
      *  Ultrasonik Mesafe Sensörü HC-SR04
      *  DC Motor
      *  Servo Motor
      *  3D Yazıcı ile üretilmiş özel şasi ve parçalar
  * **Yazılım & Algoritmalar:**
      *  Python 
      *  OpenCV (Görüntü İşleme)
      *  TensorFlow Lite (Nesne Algılama)
      *  YOLOv5/YOLOv8 tabanlı model (Trafik işaretleri tespiti için)
      *  PID Kontrol Algoritması (Şerit takibi için)

## Proje Yapısı
 * `lanes.py`     : Şerit algılama ana betiği
 * `pi_driver.py` : Raspberry Pi sürücü betiği (seri haberleşme vb.)
 * `main.cpp`     : Arduino Nano için motor ve sensör kontrol kodları.
 * `sign.tflite`  : Eğitilmiş TensorFlow Lite modeli

## Görseller

<img width="800" height="600" alt="IMG_3674" src="https://github.com/user-attachments/assets/49fee763-a615-4302-af99-713d1eb07fbd" />

## Sonuçlar ve Gelecek Çalışmalar

 Yapılan testler sonucunda, sistemin belirli şartlar altında stabil çalıştığı ve otonom sürüş için potansiyel taşıdığı görülmüştür.  Ancak, parke parlaması nedeniyle oluşan görüntü bozulmaları ve USB seri haberleşmedeki veri kaybı gibi sorunlar tespit edilmiştir.  Ayrıca Raspberry Pi'nin işlem gücünün bazı yapay zeka entegrasyonları için yetersiz kaldığı gözlemlenmiştir.

 Gelecekteki çalışmalarda, Raspberry Pi yerine Nvidia Jetson Nano gibi daha güçlü bir platform kullanılarak gerçek zamanlı görüntü işleme ve yapay zeka entegrasyonunun daha etkin bir şekilde gerçekleştirilmesi önerilmektedir.  Ayrıca, ROS2 (Robot İşletim Sistemi) dahil edilerek daha gelişmiş bir otonom araç elde edilebilir.

## Detaylı Bilgi

  * **Bitirme Çalışması Raporu:** [Otonom RC Araba Bitirme.pdf](https://github.com/oalikorkmaz/Self-Driving-RC-Car/blob/main/Otonom%20RC%20Araba%20Bitirme.pdf)
  * **Tanıtım Videosu:** [Youtube Videosu](https://youtu.be/4ZLqJI96rJo)
