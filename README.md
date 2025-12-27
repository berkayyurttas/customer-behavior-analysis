# Müşteri Davranış Analizi ve Segmentasyonu (RFM & K-Means)

Bu proje, Python ve Makine Öğrenmesi teknikleri kullanılarak bir e-ticaret şirketinin müşterilerini davranışlarına göre gruplara ayırmayı (segmentasyon) ve her grup için özel pazarlama stratejileri geliştirmeyi hedefler.

Projede geleneksel **RFM Analizi** ile modern **K-Means Kümeleme (Clustering)** algoritması birlikte kullanılmıştır.

---

## 🎯 Projenin Amacı

Şirketin pazarlama bütçesini verimli kullanabilmesi için müşterileri tanımak:
* En çok kazandıran VIP müşterileri belirlemek.
* Terk etme eğiliminde olan müşterileri tespit etmek.
* Müşteri davranışlarını matematiksel verilerle modellemek.

## 📂 Veri Seti Bilgisi

Projede **Online Retail II** veri seti kullanılmıştır.
* **İçerik:** İngiltere merkezli bir online hediyelik eşya mağazasının 2010-2011 yılları arasındaki gerçek satış verileri.
* **Veri Boyutu:** Yaklaşık 500.000+ işlem satırı.
* **Değişkenler:** Fatura Numarası, Ürün Kodu, Miktar, Fiyat, Müşteri ID, Ülke.

---

## 🚀 Proje Süreci

Proje aşağıdaki 4 ana aşamada gerçekleştirilmiştir:

**1. Veri Temizliği (Data Cleaning)**
* Eksik müşteri bilgileri (Null CustomerID) temizlendi.
* İade işlemleri (Negatif Miktar) ve hatalı kayıtlar veri setinden çıkarıldı.
* Analiz için gerekli olan "Toplam Harcama" (TotalPrice) sütunu oluşturuldu.

**2. RFM Metriklerinin Çıkarılması**
Her müşteri için üç kritik metrik hesaplandı:
* **Recency:** Müşteri en son kaç gün önce alışveriş yaptı?
* **Frequency:** Toplam kaç kez alışveriş yaptı?
* **Monetary:** Şirkete toplam ne kadar kazandırdı?

**3. Veri Ön İşleme (Preprocessing)**
* Verilerdeki uçurumları engellemek için Logaritmik Dönüşüm uygulandı.
* Tüm veriler aynı standarta getirilmek için ölçeklendirildi (StandardScaler).

**4. Yapay Zeka ile Modelleme (K-Means)**
* Elbow (Dirsek) yöntemi ile ideal küme sayısı 3 olarak belirlendi.
* K-Means algoritması çalıştırılarak müşteriler davranışlarına göre 3 sınıfa ayrıldı.

---

## 📊 Analiz Sonuçları

Yapay zeka algoritması, müşterileri harcama ve sadakat durumuna göre 3 ana gruba ayırdı:

**🏆 Grup 1: Şampiyonlar (VIP Müşteriler)**
* **Özellikleri:** Çok yakın zamanda alışveriş yapmış, alışveriş sıklığı yüksek ve harcama ortalaması en yüksek olan grup.
* **Aksiyon Önerisi:** Bu müşterilere özel sadakat programları uygulanmalı, yeni ürünlere erken erişim hakkı verilmeli ve kaybedilmemeleri için VIP destek sağlanmalıdır.

**🌟 Grup 0: Potansiyel Müşteriler**
* **Özellikleri:** Ortalama sıklıkta gelen ve ortalama harcama yapan, geliştirilmeye açık grup.
* **Aksiyon Önerisi:** Sepet tutarını artırıcı (Cross-sell/Up-sell) kampanyalar yapılmalı, ikinci ürüne indirim gibi fırsatlarla sadık müşteriye dönüştürülmeye çalışılmalıdır.

**😴 Grup 2: Uykudakiler / Kaybedilenler**
* **Özellikleri:** En son alışverişinin üzerinden uzun zaman geçmiş (ortalama 6 ay) ve harcama limitleri düşük olan grup.
* **Aksiyon Önerisi:** Yüksek bütçeli reklamlar yerine, e-posta pazarlaması ile kendimizi hatırlatma çalışmaları yapılmalıdır.

---

## 🛠️ Kullanılan Teknolojiler

* **Dil:** Python 3
* **Veri İşleme:** Pandas, NumPy
* **Görselleştirme:** Matplotlib, Seaborn
* **Makine Öğrenmesi:** Scikit-learn (K-Means, StandardScaler)
