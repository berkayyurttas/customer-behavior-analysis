📊 Müşteri Davranış Analizi ve Segmentasyonu (RFM & K-Means)
Bu proje, bir e-ticaret şirketinin müşterilerini satın alma alışkanlıklarına göre gruplara ayırmak (segmentasyon) ve pazarlama stratejileri geliştirmek amacıyla hazırlanmıştır. Projede hem kural tabanlı RFM Analizi hem de yapay zeka tabanlı K-Means Kümeleme (Clustering) algoritmaları kullanılmıştır.

🎯 Projenin Amacı
Şirketin "kime, nasıl satış yapmalı?" sorusuna veri odaklı cevap bulmak.

En değerli müşterileri (VIP) tespit etmek.

Terk etme riski taşıyan müşterileri belirlemek.

Müşteri davranışlarını matematiksel olarak modellemek.

📂 Veri Seti
Kullanılan veri seti: Online Retail II

İçerik: İngiltere merkezli bir online hediyelik eşya mağazasının 2010-2011 yılları arasındaki satış verileri.

Boyut: ~500.000+ satır işlem verisi.

Temel Değişkenler: Fatura No, Ürün Kodu, Miktar, Fiyat, Müşteri ID.

🛠️ Kullanılan Teknolojiler
Dil: Python

Veri Analizi: Pandas, NumPy

Görselleştirme: Matplotlib, Seaborn

Makine Öğrenmesi: Scikit-learn (K-Means, StandardScaler)

🚀 Proje Adımları (Neler Yaptık?)
1. Veri Temizliği ve Hazırlık (Data Cleaning)
Veri setindeki eksik CustomerID değerleri silindi (Kimin aldığı belli olmayan işlemler).

İade edilen ürünler (Negatif Quantity) ve hatalı fiyatlar (0 veya negatif UnitPrice) veri setinden çıkarıldı.

Analiz için toplam harcamayı gösteren TotalPrice sütunu oluşturuldu.

2. RFM Metriklerinin Hesaplanması
Müşterileri analiz etmek için 3 temel metrik türetildi:

Recency (Yenilik): Müşterinin son alışverişinden bu yana geçen gün sayısı.

Frequency (Sıklık): Toplam işlem sayısı.

Monetary (Parasal Değer): Müşterinin bıraktığı toplam ciro.

3. Kural Tabanlı Segmentasyon (Rule-Based)
RFM metrikleri 1-5 arasında skorlandı.

Müşteriler, standart RFM haritasına göre "Champions", "Hibernating", "New Customers" gibi sınıflara ayrıldı.

4. Makine Öğrenmesi ile Kümeleme (K-Means Clustering)
Verilerdeki çarpıklığı gidermek için Log Transformation uygulandı.

Farklı ölçekteki verileri (Tutar vs. Adet) dengelemek için StandardScaler kullanıldı.

Elbow Yöntemi (Dirsek Metodu) ile ideal küme sayısı 3 (k=3) olarak belirlendi.

K-Means algoritması ile müşteriler 3 ana gruba ayrıldı.

📊 Sonuçlar ve Çıkarımlar
Proje sonucunda müşteriler davranışlarına göre 3 ana kümeye (Cluster) ayrılmıştır:
Küme	Tanım	Özellikler	Aksiyon Önerisi
Grup 1 (VIP / Sadık)	Şampiyonlar	Yakın zamanda gelmiş, çok sık alışveriş yapmış ve ortalama sepet tutarı çok yüksek (~7.750 Birim).	Özel sadakat programları, erken erişim hakları ve VIP müşteri desteği sağlanmalı.
Grup 0 (Potansiyel)	Gelişime Açık	Ortalama sıklıkta gelen ve harcama yapan kitle.	Sepet tutarını artırıcı (Cross-sell/Up-sell) kampanyalar ve indirimler sunulmalı.
Grup 2 (Kaybedilenler)	Uykudakiler	Uzun süredir siteye uğramayan (~171 gün) ve geçmişte az harcama yapmış kitle.	Sadece maliyeti düşük e-posta pazarlaması ile kendimizi hatırlatma yapılmalı.
