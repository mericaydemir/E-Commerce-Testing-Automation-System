# 🛒 E-Ticaret Uygulaması Test ve Kalite Güvence Çalışması

## 🎓 Proje Bilgileri

| Bilgi                 | Açıklama                                  |
| --------------------- | ----------------------------------------- |
| 👤 Öğrenci            | Meriç Aydemir                             |
| 🆔 Öğrenci Numarası   | 20230108049                             |
| 🏫 Üniversite         | Piri Reis Üniversitesi                    |
| 💻 Bölüm              | Bilgisayar Programcılığı                  |
| 📚 Ders               | MTH2005 Yazılım Testi ve Kalite Güvencesi |
| 👨‍🏫 Öğretim Elemanı | Emrah Sarıçiçek                           |
| 📅 Teslim Tarihi      | 12.06.2026                                |

---

## 🎯 Projenin Amacı

Bu çalışma, yazılım geliştirme süreçlerinde önemli bir yere sahip olan test faaliyetleri, kalite güvence uygulamaları ve hata analizlerinin pratik olarak incelenmesini amaçlamaktadır.

Proje kapsamında gerçek bir e-ticaret sisteminin temel işleyişi modellenmiş ve sistem içerisine çeşitli yazılım hataları bilinçli olarak yerleştirilmiştir. Böylece yalnızca çalışan bir uygulama geliştirmek yerine, yazılım kalitesinin nasıl değerlendirildiği ve hataların nasıl tespit edildiği gösterilmiştir.

Çalışmanın temel hedefleri aşağıdaki gibidir:

* ✅ Yazılım hatalarını belirlemek
* ✅ Hataların sistem üzerindeki etkilerini incelemek
* ✅ Test süreçlerini planlamak ve uygulamak
* ✅ Yazılım kalitesini değerlendirmek
* ✅ Test sonuçlarını raporlamak

---

## 🏗️ Sistem Yapısı

Proje, standart bir e-ticaret uygulamasında bulunan temel süreçleri içermektedir.

📦 Ürün Yönetimi

⬇️

🛒 Sepet İşlemleri

⬇️

📑 Sipariş Oluşturma

⬇️

💳 Ödeme İşlemleri

⬇️

📊 Test Sonuçları ve Raporlama

Bu yapı sayesinde kullanıcıların ürün seçmesinden ödeme aşamasına kadar olan süreçler test edilebilmektedir.

---

## 📂 Proje Dizini

```text
ECommerceApp
│
├── Core
│   ├── Product.cs
│   ├── Cart.cs
│   └── OrderService.cs
│
├── Tests
│   └── NUnit Test Senaryoları
│
└── Program.cs
```

### 📌 Core Katmanı

Sistemin temel iş kurallarını ve uygulama mantığını içeren katmandır.

### 📌 Tests Katmanı

NUnit altyapısı kullanılarak hazırlanan birim ve entegrasyon testlerini barındırır.

### 📌 Program.cs

Uygulamanın başlangıç noktasıdır ve test sonuçlarının konsol ekranında görüntülenmesini sağlar.

---

## 🧪 Uygulanan Test Yaklaşımları

Proje kapsamında farklı test yöntemlerinden yararlanılmıştır.

### ⚪ Black Box Testing

Sistemin iç yapısına bakılmaksızın giriş ve çıkışların doğrulanmasını amaçlayan test yöntemidir.

### ⚪ White Box Testing

Kodun iç yapısını ve karar mekanizmalarını inceleyen test yaklaşımıdır.

### ⚪ Gray Box Testing

Hem kullanıcı perspektifini hem de sistem mantığını birlikte değerlendiren test türüdür.

### ⚪ Integration Testing

Birden fazla modülün birlikte doğru çalışıp çalışmadığını doğrulamak için uygulanmıştır.

### ⚪ Boundary Value Analysis (BVA)

Sınır değerlerde meydana gelebilecek hataları ortaya çıkarmak amacıyla kullanılmıştır.

### ⚪ Equivalence Partitioning (EP)

Benzer davranış gösteren veri grupları oluşturularak test kapsamı optimize edilmiştir.

---

## 🐞 Sisteme Eklenen Kritik Hatalar

### 🔴 1. İndirim Hesaplama Problemi

**Beklenen Hesaplama**

```csharp
total * 0.9m
```

**Mevcut Hesaplama**

```csharp
total * 0.5m
```

**Etkisi**

💸 Müşterilere olması gerekenden daha yüksek indirim uygulanmaktadır.

---

### 🔴 2. Kargo Ücreti Hesaplama Hatası

**Beklenen**

```csharp
total + 25
```

**Mevcut**

```csharp
total - 25
```

**Etkisi**

📉 Sipariş toplamı yanlış hesaplanmakta ve gelir kaybı oluşabilmektedir.

---

### 🔴 3. Stok Kontrol Eksikliği

Stok miktarı sıfır olan ürünlerin sipariş edilmesine izin verilmektedir.

**Etkisi**

📦 Stok değerleri negatif seviyelere düşebilmektedir.

---

### 🔴 4. Minimum Sipariş Tutarı Hatası

**Gereksinim**

```text
100 TL
```

**Kodda Tanımlanan**

```text
10 TL
```

**Etkisi**

⚠️ Minimum sipariş koşulunu sağlamayan işlemler sistem tarafından kabul edilmektedir.

---

### 🔴 5. Ödeme Doğrulama Sorunu

Ödeme doğrulama mekanizması ters çalışacak şekilde tasarlanmıştır.

**Etkisi**

💳 Eksik ödemeler kabul edilirken, fazla ödemeler reddedilmektedir.

---

## 📊 Test Sonuçları

| Ölçüt              | Sonuç |
| ------------------ | ----- |
| Toplam Test Sayısı | 20    |
| Başarılı Testler   | 11    |
| Başarısız Testler  | 9     |
| Başarı Oranı       | %55   |

---

## 🔍 Başarısız Testlerin Değerlendirilmesi

### ❌ İndirim ve Kargo Testleri

* TC03
* TC04
* TC05
* TC06

Yanlış indirim ve kargo hesaplama algoritmaları nedeniyle başarısız olmuştur.

### ❌ Stok Yönetimi Testi

* TC13

Stok kontrolünün eksik uygulanmasından dolayı başarısız sonuç vermiştir.

### ❌ Minimum Sipariş Kontrolü

* TC16

99 TL tutarındaki siparişin sistem tarafından kabul edilmesi hata olarak tespit edilmiştir.

### ❌ Ödeme Doğrulama Testleri

* TC10
* TC11

Ödeme mantığının ters çalışması nedeniyle başarısız olmuştur.

### ❌ Çoklu Ürün İşlemleri

* TC18
* TC20

Sipariş toplamının yanlış hesaplanması sonucu başarısızlık gözlemlenmiştir.

---

## ✅ Başarıyla Geçilen Testler

* ✔ Sepete ürün ekleme işlemleri
* ✔ Sepetten ürün silme işlemleri
* ✔ Boş sepet kontrolü
* ✔ Geçerli sipariş oluşturma
* ✔ Negatif stok senaryoları
* ✔ Normal ödeme senaryoları
* ✔ Sipariş akışının doğrulanması

---

## 🛠️ Kullanılan Teknolojiler

* 💜 .NET 9
* 🧪 NUnit
* 🖥️ Visual Studio 2022
* 📊 STLC (Software Testing Life Cycle)
* 📋 Test Yönetimi Teknikleri
* 📈 Kalite Güvence ve Hata Analizi Yaklaşımları

---

## 🚀 Projenin Çalıştırılması

1. Proje dosyalarını bilgisayarınıza indirin veya klonlayın.
2. Visual Studio 2022 ile projeyi açın.
3. Test Explorer penceresini görüntüleyin.
4. Tüm testleri çalıştırmak için **Run All Tests** seçeneğini kullanın.
5. Oluşan sonuçları inceleyerek hata analizlerini değerlendirin.

---

## 🎯 Proje Sürecinde Kazanılan Beceriler

Bu çalışma sayesinde aşağıdaki alanlarda deneyim kazanılmıştır:

* ✅ Test senaryosu geliştirme
* ✅ Hata tespiti ve hata analizi
* ✅ Yazılım kalite değerlendirme süreçleri
* ✅ STLC uygulamaları
* ✅ Test raporlama teknikleri
* ✅ Birim ve entegrasyon testleri
* ✅ QA dokümantasyonu hazırlama
* ✅ Test planlama ve yönetimi

---

## 📌 Genel Değerlendirme

Bu proje kapsamında bir e-ticaret uygulaması üzerinde çeşitli test yöntemleri uygulanmış ve sisteme kasıtlı olarak eklenen kritik yazılım hataları başarıyla ortaya çıkarılmıştır.

Elde edilen sonuçlar, yazılım geliştirme sürecinde test faaliyetlerinin ve kalite güvence çalışmalarının ne kadar önemli olduğunu göstermektedir. Güvenilir, sürdürülebilir ve hatalara karşı dayanıklı yazılımlar geliştirebilmek için kapsamlı test süreçlerinin vazgeçilmez olduğu görülmüştür.

⭐ Bu çalışmanın temel amacı yalnızca çalışan bir yazılım üretmek değil, aynı zamanda kalite odaklı yazılım geliştirme anlayışını benimsemektir.
