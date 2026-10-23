# 🎯 LABORATUVAR 3 · Threat & Risk + Risk Matrix
**Üretilen Çıktı:** Risk Register (Evidence Pack EP 04 Cyber Risk Assessment)  
**Makine:** Optimak STU – Otomatik Üstten Baskılı Palet Çemberleme Makinesi  

---

## Görev — Üç Senaryo Kurun ve Puanlayın

| # | Senaryo (Kim → Kapı → Eylem & Zincir → Fiziksel Sonuç) | L | S | E | Skor | Öncelik |
| :--- | :--- | :---: | :---: | :---: | :---: | :--- |
| **1** | **Fırsatçı Dış Saldırgan** → İnternete açık uzak bakım modülü ve `"admin/admin"` hesabı → Dijital kesişim noktasından PLC'ye ulaşıp ışık perdesi gecikmesini değiştirir → Üst baskı tablası durmaz ve **operatörü ağır şekilde ezer**. | 3 | 3 | 3 | **27** | **KRİTİK** |
| **2** | **Meraklı İçeriden Çalışan** → Wi-Fi parolası ve Port 80 HMI arayüzü → Üretim hızını artırmak için çember gerginliğini limit üstüne çıkarır → Çember koparak fırlar ve **operatörde yaralanmaya yol açar**. | 2 | 2 | 2 | **8** | **ORTA** |
| **3** | **Bakımcı (Tedarik Zinciri)** → Servis dizüstü bilgisayarı / Kilitsiz USB → Bozuk firmware yüklenerek E-stop mantığı bozulur → Sıkışmaya müdahale için kapı açıldığında bıçak durmaz, **operatörün elini keser**. | 1 | 3 | 1 | **3** | **DÜŞÜK (Öne Alınır - S=3 Kuralı)** |

---

## Değerlendirme Soruları

**1. En yüksek öncelikli senaryonuz hangisi? Bir cümleyle: neden bu?**
1. Senaryo (Skor: 27). Uzak bakım modülü internete doğrudan açık (E=3) ve varsayılan parolayla çok kolay istismar edilebilir (L=3) durumdayken, sonucunda ezilme gibi ölümcül bir fiziksel yaralanmaya (S=3) yol açmaktadır.

**2. S=3 olup skoru düşük kalan senaryonuz var mı? Nasıl görünür kılacaksınız?**
Evet, 3. Senaryo. Olasılık (L=1) düşük olduğu için matematiksel skoru 3 çıkmıştır; ancak fiziksel sonucu uzuv kesilmesi (S=3) olduğu için Risk Register tablosunda "S=3 Kritik Emniyet Etkisi - Öne Alınır" etiketiyle üst sıraya taşınır.
