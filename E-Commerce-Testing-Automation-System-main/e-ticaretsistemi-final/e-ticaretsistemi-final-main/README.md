# 🛍️ E-Ticaret Sistemi Test ve Kalite Güvence Projesi

## 🎓 Proje Bilgileri

| Bilgi | Değer |
|--------|--------|
| 👤 Öğrenci | meriç aydemir|
| 🆔 Öğrenci No | 20230108049 |
| 🏫 Üniversite | Piri Reis Üniversitesi |
| 💻 Bölüm | Bilgisayar Programcılığı |
| 📚 Ders | MTH2005 Yazılım Test ve Kalitesi |
| 👨‍🏫 Öğretim Görevlisi | Emrah Sarıçiçek |
| 📅 Teslim Tarihi | 12.06.2026 |

---

# 🎯 Projenin Amacı

Bu proje, modern yazılım geliştirme süreçlerinde kritik öneme sahip olan **Yazılım Testi**, **Kalite Güvence (QA)** ve **Hata Analizi** kavramlarını uygulamalı olarak göstermek amacıyla geliştirilmiştir.

Gerçek bir e-ticaret sisteminin temel akışı modellenmiş ve sistem içerisine bilinçli olarak hatalar yerleştirilmiştir. Amaç yalnızca çalışan kod yazmak değil, aynı zamanda:

✅ Hataları tespit etmek  
✅ Hataların etkilerini analiz etmek  
✅ Test süreçlerini yönetmek  
✅ Yazılım kalitesini ölçmek  
✅ Test raporları oluşturmak  

olarak belirlenmiştir.

---

# 🏗️ Sistem Mimarisi

Proje klasik bir e-ticaret sürecini simüle etmektedir.

🛒 Ürün Yönetimi

⬇️

🧺 Sepet İşlemleri

⬇️

📦 Sipariş Oluşturma

⬇️

💳 Ödeme Kontrolü

⬇️

📊 Sonuç ve Test Raporlama

---

# 📂 Proje Klasör Yapısı

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
İş kurallarının bulunduğu ana katmandır.

### 📌 Tests Katmanı
NUnit kullanılarak hazırlanan test senaryolarını içerir.

### 📌 Program.cs
Test sonuçlarını konsol ekranında raporlayan giriş noktasıdır.

---

# 🧪 Kullanılan Test Teknikleri

Bu proje kapsamında farklı seviyelerde yazılım testleri uygulanmıştır.

### ⚪ Black Box Testing
Sistemin iç yapısı bilinmeden yapılan testler.

### ⚪ White Box Testing
Kodun iç mantığını inceleyen testler.

### ⚪ Gray Box Testing
Hem iş mantığını hem kullanıcı davranışlarını değerlendiren testler.

### ⚪ Integration Testing
Modüllerin birlikte çalışmasının doğrulanması.

### ⚪ Boundary Value Analysis (BVA)
Sınır değerlerin test edilmesi.

### ⚪ Equivalence Partitioning (EP)
Verilerin eşdeğer sınıflara ayrılarak test edilmesi.

---

# 🐞 Sisteme Yerleştirilen Kritik Hatalar

## 🔴 1. İndirim Hesaplama Hatası

Beklenen:
```csharp
total * 0.9m
```

Mevcut:
```csharp
total * 0.5m
```

Etkisi:
💸 Müşteriye olması gerekenden fazla indirim uygulanır.

---

## 🔴 2. Kargo Hesaplama Hatası

Beklenen:
```csharp
total + 25
```

Mevcut:
```csharp
total - 25
```

Etkisi:
📉 Sipariş tutarı yanlış hesaplanır.

---

## 🔴 3. Stok Kontrol Hatası

0 stoklu ürünlerin satışı engellenmemektedir.

Etkisi:

📦 Stok miktarı negatif değerlere düşebilir.

---

## 🔴 4. Minimum Sipariş Limiti Hatası

Gereksinim:
100 TL

Kod:
10 TL

Etkisi:

⚠️ Geçersiz siparişlerin sisteme kabul edilmesi.

---

## 🔴 5. Ödeme Doğrulama Hatası

Eksik ödeme kabul edilmekte, fazla ödeme reddedilmektedir.

Etkisi:

💳 Finansal süreçlerin yanlış çalışması.

---

# 📊 Test Sonuçları

Toplam Test Sayısı: 20

🟢 Başarılı Testler: 11

🔴 Başarısız Testler: 9

Başarı Oranı:

55%

---

# 🔍 Başarısız Testlerin Analizi

### ❌ İndirim ve Kargo Senaryoları

TC03

TC04

TC05

TC06

Yanlış indirim ve kargo hesaplaması nedeniyle başarısız olmuştur.

### ❌ Stok Senaryosu

TC13

Sıfır stok kontrolü hatalıdır.

### ❌ Minimum Sipariş Kontrolü

TC16

99 TL siparişin geçmesine izin verilmiştir.

### ❌ Ödeme Senaryoları

TC10

TC11

Ödeme doğrulama mantığı ters çalışmaktadır.

### ❌ Çoklu Ürün Senaryoları

TC18

TC20

Toplam tutar hatalı hesaplanmıştır.

---

# ✅ Başarılı Testler

✔ Sepete ürün ekleme

✔ Sepetten ürün çıkarma

✔ Boş sepet kontrolü

✔ Geçerli sipariş oluşturma

✔ Negatif stok doğrulaması

✔ Geçerli ödeme senaryoları

✔ Sipariş akışı doğrulaması

---

# 🛠️ Kullanılan Teknolojiler

💜 .NET 9

🧪 NUnit

🖥️ Visual Studio 2022

📊 STLC

📋 Test Management

📈 QA Analysis

---

# 🚀 Projeyi Çalıştırma

1️⃣ Projeyi indir veya klonla

2️⃣ Visual Studio ile aç

3️⃣ Test Explorer ekranını aç

4️⃣ Run All Tests çalıştır

5️⃣ Sonuçları analiz et

---

# 🎯 Bu Projede Kazanılan Yetkinlikler

✅ Test senaryosu hazırlama

✅ Hata tespiti

✅ Hata analizi

✅ STLC süreçleri

✅ Test raporlama

✅ Yazılım kalite kontrolü

✅ Unit ve Integration Testing

✅ QA dokümantasyonu

---

# 📌 Sonuç

Bu çalışma kapsamında bir e-ticaret sistemi üzerinde profesyonel test süreçleri uygulanmış, bilinçli olarak eklenen kritik yazılım hataları farklı test teknikleri ile başarıyla tespit edilmiştir.

Proje; yazılım test süreçlerinin, kalite güvence çalışmalarının ve hata analizlerinin gerçek projelerde ne kadar önemli olduğunu göstermektedir.

⭐ Amaç yalnızca çalışan bir yazılım üretmek değil, güvenilir ve sürdürülebilir yazılım geliştirme kültürünü kazanmaktır.
