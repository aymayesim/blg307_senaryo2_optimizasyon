# BLG-307 Yapay Zeka Sistemleri – 1. Proje Ödevi  
## Genetik Algoritma ile Endüstriyel Boya Karışımı Optimizasyonu  
*Öğrenci:* YEŞİM AYMA
*Senaryo:* 2 – Pigment A ve Pigment B Karışımı Optimizasyonu  

---

## 📌 Proje Açıklaması
Bu projede Genetik Algoritma (GA) kullanılarak endüstriyel boya üretiminde kullanılan  
Pigment A ve Pigment B karışımlarının *renk kalitesi skorunu maksimize eden*
en uygun karışım oranı bulunmuştur.

Verilen amaç fonksiyonu senaryoya özel olarak tanımlanmıştır:

\[
y = 5x_1 + 2x_2 - x_1x_2
\]

Bu fonksiyon *maksimize edilecektir.*

---

## 📌 Değişkenler (Decision Variables)

| Değişken | Açıklama | Aralık |
|---------|----------|--------|
| x₁ | Pigment A oranı (%) | 30–100 |
| x₂ | Pigment B oranı (%) | 0–70 (100 - x₁’den gelir) |

---

## 📌 Kısıtlar

- *x₁ + x₂ = 100*  
  (Karışım toplamı her zaman %100 olmalı)
- *x₁ ≥ 30*  
  (A pigmenti en az %30 kullanılmalıdır)
- *0 ≤ x₁, x₂ ≤ 100*

Bu nedenle x₂ her zaman:

\[
x_2 = 100 - x_1
\]

şeklinde hesaplanmıştır.

---

## 📌 Genetik Algoritma Tasarımı

### ✔ Birey Temsili  
Her birey:[x1, x2] şeklinde tutulur.  
x₂ = 100 – x₁ olarak hesaplanır.

---

### ✔ Popülasyon  
- Popülasyon büyüklüğü: *30*

---

### ✔ Seçim Mekanizması  
*Turnuva seçimi (k = 3)* kullanılmıştır.

---

### ✔ Çaprazlama (Crossover)  
Sayısal GA için uygun *aritmetik crossover* uygulanmıştır:
- Çocuk 1 → ebeveynlerin ortalaması  
- Çocuk 2 → ağırlıklı ortalama  

Çaprazlama olasılığı: *0.8*

---

### ✔ Mutasyon  
Mutasyon esnasında x₁ değeri küçük bir miktar değiştirilir (±1, ±2, ±3).  
Sonrasında x₂ tekrar 100 − x₁ olarak hesaplanır.  
Mutasyon olasılığı: *0.2*

---

### ✔ Kısıt Onarımı (Repair Function)  
Yeni oluşturulan her birey şu kurallara göre düzeltilir:
- x₁ aralık dışına çıkarsa sınır içine çekilir  
- x₂ = 100 – x₁  
- Kısıt ihlali varsa birey yeniden düzenlenir  

---

### ✔ Nesil Sayısı  
- Toplam nesil: *100*

---

## 📌 Sonuçlar

Genetik algoritmanın sonunda elde edilen en iyi çözüm:

- *Pigment A (x₁): 100%*  
- *Pigment B (x₂): 0%*  
- *Maksimum renk kalitesi skoru: 500.00*

Bu sonuç amaç fonksiyonunun doğasına uygundur.  
Pigment A’nın katsayısı daha yüksek olduğu için en iyi kaliteyi saf A pigmenti üretmektedir.

---

## 📈 Fitness Grafiği

GA nesiller boyunca çalıştığında:

- İlk birkaç nesilde fitness hızla artmış  
- Yaklaşık 5. nesilden sonra optimuma ulaşılmış  
- 100. nesile kadar kararlı bir plato oluşmuştur  

Bu durum GA’nın optimum çözümü bulduğunu göstermektedir.

---

## 📁 Dosya Yapısı

```text
├── README.md
└── proje_genetik.ipynb
