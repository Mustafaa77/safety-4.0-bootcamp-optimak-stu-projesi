# 🤖 LABORATUVAR 7 · AI Safety Challenge
**Çıktı:** AI Fail-Safe Decision (Evidence Pack EP 03 + EP 15)  
**Makine:** Optimak STU – Otomatik Üstten Baskılı Palet Çemberleme Makinesi  

---

## Senaryo
Optimak STU makinesine, gelen paletlerin düzgün dizilip dizilmediğini ve çemberin doğru sarıldığını kontrol eden yapay zeka (YZ) destekli bir kamera eklenmesi planlanıyor.

---

## Görev — Üç Başarısızlıkta Güvenli Davranış

**1. Model yanlış sınıflandırdı: Kusurlu parçaya OK verdi. Sistem ne yapmalı? İkinci kontrol / insan onayı var mı?**
YZ bozuk/eğri palete yanlışlıkla OK verse bile, baskı tablasındaki mekanik tork ve gerginlik sensörleri ikinci kontrolü yapmalıdır. Ayrıca emniyet zinciri (ışık perdeleri ve Safety PLC) YZ'den tamamen bağımsız çalışmalı ve operatörün HMI ekrandan sistemi durdurma yetkisi (human override) olmalıdır.

**2. Girdi manipüle edildi: Kamera verisi bozuk/sahte. Nasıl fark edilir? Şüpheli girdide ne yapılır?**
Kamera görüntüsünün donması veya girişteki fotosel "palet yok" derken kameranın "palet var" demesi izleme (monitoring) ile hemen fark edilir. Şüpheli durumda sistem güvenli hata (fail-safe) moduna geçerek baskı tablasını durdurmalı ve uyarı vermelidir.

**3. Confidence düştü: Model "emin değilim" diyor. Eşik ne olmalı? Altında: dur / insana sor / fallback?**
Güven eşiği (confidence threshold) en az %85 olmalıdır. Karar bu oranın altına düşerse sistem risk almamalı, yedek moda (fallback) geçerek işlemi bekletmeli ve ekrandan operatör onayı (insana sor) istemelidir.

---

## Karar Tablosu — AI Fail-Safe Decision

| Başarısızlık | Tanımladığınız güvenli davranış (hangi kavramla?) |
| :--- | :--- |
| **Model yanlış sınıflandırdı** | **Human Override:** Mekanik sensörlerle ikinci kontrol yapılır, operatöre müdahale yetkisi verilir ve Safety PLC bağımsız çalışır. |
| **Girdi manipüle edildi** | **Monitoring & Fail-Safe:** Kamera ve sensör uyumu izlenir; bozuk/sahte veride makine güvenli duruma (Safe State) geçip durur. |
| **Confidence düştü** | **Confidence Threshold & Fallback:** Güven %85'in altına düşerse makine durur, standart sensör moduna döner ve operatöre sorar. |
