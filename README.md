# NEON-Aerial-Imaging-Dataset-Analysis-and-Feature-Extraction
Bu proje, PLOS Computational Biology dergisinde yayınlanan NEON Havadan Görüntüleme Veri Seti'ni kullanarak çok-modlu (RGB, LiDAR, Hipespektral) uzaktan algılama verilerinin entegrasyonu, görselleştirilmesi ve analizini içerir. Projenin ana odağı, hiperspektral veriden ağaçlara ait anlamlı spektral ve sayısal özelliklerin çıkarılmasıdır.

Genel Bakış
Proje, farklı sensörlerden gelen verileri bir araya getirerek ham veriden anlamlı ve nicel bilgilere ulaşmayı amaçlayan adımları takip eder. İş akışı, veri entegrasyonu, 3B yapısal analiz, hiperspektral imza çıkarımı ve vejetasyon indeksi hesaplamalarını kapsar.

Metodoloji ve İş Akışı
Analiz süreci, aşağıdaki mantıksal adımlardan oluşmaktadır:

Veri Entegrasyonu ve Ön İnceleme: Yüksek çözünürlüklü RGB, üç boyutlu LiDAR ve zengin spektral bilgi içeren Hipespektral (HSI) verileri aynı coğrafi alanda birleştirilmiştir. Bu farklı veri kaynaklarının birbiriyle uyumunu doğrulamak için görsel bir panel oluşturulmuştur.

3B Yapısal Analiz: Arazinin topografyası ve ağacın dikey yapısı hakkında detaylı bilgi edinmek için LiDAR nokta bulutu verisi üç boyutlu olarak görselleştirilmiştir.

Hiperspektral İmza Çıkarımı: Veri setiyle birlikte sağlanan XML anotasyonları işlenerek, "Ağaç" olarak etiketlenmiş bölgelerden alınan spektral verilerin ortalaması alınmıştır. Bu işlem, tek bir pikseldeki gürültüyü ortadan kaldırarak sınıfa özgü, güvenilir bir "spektral parmak izi" elde etmeyi sağlamıştır.

Not: Anotasyonların yapıldığı RGB görüntüler ile HSI verisi arasındaki çözünürlük farkını gidermek için özel bir ölçeklendirme fonksiyonu kullanılmıştır.

Nicel Analiz: Son adımda, elde edilen ortalama spektral imzadan, bitki sağlığı ile ilişkili iki temel vejetasyon indeksi hesaplanmıştır: NDVI ve Red-Edge Eğim Değeri.

Sonuçlar ve Görselleştirmeler
1. Çok-Modlu Genel Bakış Paneli
RGB, HSI (yaklaşık RGB) ve Kanopi Yüksekseklik Modeli (CHM) verilerinin yan yana görselleştirilmesi, verilerin tutarlılığını ve mekansal uyumunu teyit eder.

2. LiDAR Nokta Bulutu
Ağacın ve çevresindeki arazinin üç boyutlu yapısı.

3. Spektral İmzalar
Tek bir pikselin gürültülü spektral imzası ile 20 ağaç örneğinin ortalaması alınarak elde edilen temiz ve temsili "Ağaç Sınıfı" imzası arasındaki fark.

Tek Piksel Spektrumu	Ortalama Tür Spektral İmzası (n=20)


4. Nicel Metrikler
Çıkarılan ortalama spektral imzadan hesaplanan sayısal vejetasyon metrikleri:

== Kısa Sayısal Özet ==
 • Tree         | NDVI≈0.680 | Red‑edge slope≈12.8972 | n=20
Kullanım
Bu analizi kendi sisteminizde çalıştırmak için:

Bu projeyi klonlayın veya indirin.

Gerekli Python kütüphanelerini yükleyin:

Bash

pip install rasterio laspy lxml matplotlib numpy pandas
NEON Veri Seti'ni indirin ve NEON_Veri_Gorsellestirme_ve_Analiz.ipynb dosyasındaki BASE_DIR değişkenini kendi dosya yolunuzla güncelleyin.

Jupyter Notebook veya Google Colab üzerinden Untitled14.ipynb dosyasını çalıştırın.
