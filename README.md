# BLG-307 Yapay Zeka Sistemleri – 1. Proje Ödevi

## Genetik Algoritma ile Endüstriyel Boya Karışımı Optimizasyonu

**Öğrenci:** Yeşim Ayma  
**Numara:** 2312721002  
**Senaryo:** 2 – Endüstriyel Boya Karışımı  

---

## 📌 Proje Açıklaması

Bu projede **Genetik Algoritma (GA)** kullanılarak, iki farklı pigmentten oluşan endüstriyel bir boya karışımının **renk kalitesi skorunu maksimize edecek** en uygun oranlarının bulunması amaçlanmıştır.

Problem, doğrusal olmayan bir amaç fonksiyonu ve belirli kısıtlar içerdiği için klasik optimizasyon yöntemleri yerine **genetik algoritma** tercih edilmiştir. Genetik algoritma sayesinde çözüm uzayı popülasyon tabanlı olarak taranmış ve küresel optimum çözüme ulaşılmıştır.

---

## 🎯 Amaç Fonksiyonu

Bu proje kapsamında kullanılan amaç fonksiyonu aşağıdaki gibidir:

\[
y = 5x_1 + 2x_2 - x_1 x_2
\]

Bu fonksiyon **maksimize edilmektedir**.

---

## 🔢 Değişkenler

- **x₁:** Pigment A oranı (%)  
- **x₂:** Pigment B oranı (%)  

---

## ⚙️ Kısıtlar

- \(x_1 + x_2 = 100\)  (Karışım toplamı %100 olmalıdır)  
- \(x_1 \geq 30\)  (Pigment A en az %30 kullanılmalıdır)  
- \(0 \leq x_1, x_2 \leq 100\)

---

