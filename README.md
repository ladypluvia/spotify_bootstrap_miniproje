# Spotify_Bootstrap_MiniProje
Bu mini projede, sınırlı ve normal dağılmayan bir örneklem üzerinden Spotify kullanıcılarının dinleme alışkanlıklarını analiz eder. Güvenilir istatistiksel çıkarımlar için Bootstrap ve Permütasyon Testi yöntemleri kullanılmıştır.
***

# 🎧 Spotify Wrapped: Kullanıcı Alışkanlıkları ve Bootstrap Analizi

## 📖 Proje Özeti
Bu proje, kısıtlı ve sağa çarpık bir örneklem üzerinden güvenilir istatistiksel çıkarımlar yapmayı amaçlayan simülasyon tabanlı bir veri analizi çalışmasıdır. Spotify kullanıcılarının günlük dinleme süreleri ve uygulama kullanım sıklıkları, **Bootstrap** ve **Permütasyon Testi** gibi modern yeniden örnekleme (resampling) yöntemleri kullanılarak incelenmiştir. İstatistiksel geçerliliği yüksek bu analiz, sınırlı veriyle (n=75) parametrik varsayımlar ihlal edildiğinde bile popülasyon hakkında nasıl sağlam öngörülerde bulunulabileceğini göstermektedir.

## 🎯 Temel Amaçlar ve Veri Seti Hikâyesi
Yıl sonu "Spotify Wrapped" kampanyası öncesinde, Türkiye'deki kullanıcıların (Z ve Y kuşağı) dinleme alışkanlıklarını analiz etmek için 75 kişilik rastgele bir örneklem toplanmıştır (40 Z kuşağı, 35 Y kuşağı). 

Çoğu kullanıcı 30-60 dakika bandında kalsa da, günde 3 saati aşan "süper-dinleyicilerin" varlığı veri dağılımının çan eğrisinden uzaklaşarak sağa doğru uzun bir kuyruk (right-skew) oluşturmasına neden olmuştur. Analiz, bu çarpıklığın yarattığı yanıltıcı ortalama değerlerini aşmak üzerine kurgulanmıştır.

## 🛠️ Kullanılan İstatistiksel Yöntemler
* **Keşifçi Veri Analizi (EDA) ve Normallik Kontrolü:** Ortalama ve medyan kıyaslaması ile dağılımın çarpıklığının tespit edilmesi.
* **Bootstrap Güven Aralıkları (Confidence Intervals):**
  * Z Kuşağı (18-25 yaş) ve Y Kuşağı (30-40 yaş) için %95 ortalama ve medyan güven aralıklarının 10.000 iterasyonla (percentile yöntemi) hesaplanması.
  * Aykırı değerlere (outliers) karşı dirençli olan medyanın, ortalamaya kıyasla neden daha güvenilir bir konum ölçüsü olduğunun karşılaştırmalı olarak kanıtlanması.
* **Permütasyon Testi (A/B Testi Alternatifi):** İki kuşak arasındaki günlük dinleme süresi farkının istatistiksel olarak anlamlı olup olmadığını test etmek için iki yönlü (two-tailed) hipotez testi uygulanması.
* **Korelasyon Analizi:** Dinleme süresi ile uygulamanın haftalık açılış sıklığı (session sayısı) arasındaki ilişkinin Pearson korelasyon katsayısı hesaplanarak Bootstrap güven aralığı ile doğrulanması.

## 📊 Çıktılar ve Temel Bulgular
* **Kuşak Farkı:** Permütasyon testi sonucunda p-değeri 0.0000 bulunmuş olup, Z kuşağının platformda geçirdiği sürenin Y kuşağına göre istatistiksel olarak (0.05 anlamlılık düzeyinde) anlamlı derecede daha yüksek olduğu saptanmıştır.
* **Metrik Güvenilirliği:** Y kuşağı verisinin medyan güven aralığı genişliği (17 dakika), Z kuşağına (52 dakika) göre çok daha dardır. Bu durum, Y kuşağı verisinin varyansının daha düşük olduğunu ve elde edilen tahminlerin istatistiksel açıdan daha güvenilir olduğunu göstermektedir.
* **Kullanıcı Etkileşimi:** Dinleme süresi ile oturum (session) açma sıklığı arasında güçlü bir pozitif ilişki (r = 0.84) tespit edilmiştir. Bootstrap analizi, bu yüksek korelasyonun %95 güven düzeyinde [0.75, 0.90] aralığında olduğunu doğrulamıştır.

## 💻 Teknolojiler
* **Programlama Dili:** Python 3
* **Kütüphaneler:** NumPy, Pandas, Matplotlib, Seaborn, SciPy

## 🚀 Kurulum ve Çalıştırma
1. Repoyu bilgisayarınıza klonlayın.
2. Gerekli bağımlılıkların yüklü olduğundan emin olun (`pip install numpy pandas matplotlib seaborn scipy`).
3. `Bootstrap_Mini_Proje_Spotify_soru.ipynb` dosyasını Jupyter Notebook ortamında açarak kod hücrelerini sırasıyla çalıştırın.
