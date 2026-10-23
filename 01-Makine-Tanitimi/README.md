# 🏭 Makine Tanıtımı, Saldırı Yüzeyi Envanteri ve Kaynaklar

**Makine Adı:** Optimak STU – Otomatik Üstten Baskılı Palet Çemberleme Makinesi  
**Üretici Birlik Üyeliği:** SAMİB (Sakarya Makina İmalatçıları Birliği)

---

## 1. Makinenin Çalışma Prensibi ve Fiziksel Tehlike Analizi
Otomatik Üstten Baskılı Palet Çemberleme Makinesi, konveyör hattından gelen paletli yüklerin dağılmasını önlemek amacıyla önce yukarıdan **hidrolik/elektromekanik üst baskı tablası (500 kg'a kadar baskı kuvveti)** ile yükü sıkıştırır, ardından hareketli çemberleme kafası ile paletin etrafına yüksek gerginlikte PP/PET plastik çember sarıp sürtünme kaynağı ile birleştirir ve keser.

* **Kritik Fiziksel Tehlikeler:**
  1. Üstten inen ağır baskı tablasının altında kalarak **ezilme ve sıkışma**.
  2. Yüksek hızda hareket eden çemberleme kafası ve sıcak kesme bıçağı nedeniyle **el/parmak kesilmesi ve yanma**.
  3. Yüksek gerginlikteki çemberin koparak operatöre **çarpması**.

---

## 2. Altı Kategorili Saldırı Yüzeyi ve Varlık Envanteri (Asset Inventory - EP 01)
"Görmediğin kapıyı kilitleyemezsin" ilkesi doğrultusunda makinenin 6 kategorili varlık envanteri çıkarılmıştır:

| # | Kategori | Tespit Edilen Varlıklar ve Açık Kapılar |
| :--- | :--- | :--- |
| **1** | **Donanım** | • Üretim PLC'si (Siemens SIMATIC S7-1200)<br>• Emniyet PLC'si (Siemens SIMATIC S7-1200F Safety PLC)<br>• Operatör Paneli (SIMATIC HMI KTP700 Basic)<br>• Servo Sürücüler (STO destekli)<br>• SICK C4000 Işık Perdeleri, E-Stop Butonları ve Kapı Kilitleri<br>• Uzak Bakım Modülü (Endüstriyel 4G/VPN Router)<br>• Pano üzerinde 2 adet kilitsiz USB portu |
| **2** | **Yazılım / Firmware** | • PLC Firmware (V4.2) ve TIA Portal proje yazılımı<br>• HMI gömülü işletim sistemi ve açık Web Sunucusu (Port 80)<br>• Uzak bakım modülü firmware yazılımı |
| **3** | **Hesaplar** | • HMI üzerinde paylaşılan operatör hesabı<br>• Uzak bakım ve PLC arayüzünde varsayılan `"admin/admin"` servis hesabı |
| **4** | **Sertifika / Anahtar** | • Doğrulanmamış / imzasız firmware güncelleme paketleri<br>• Pano içindeki kartonda yazılı Wi-Fi parolası |
| **5** | **Dış Bağlantı** | • İnternete doğrudan açık uzak bakım modülü<br>• Fabrika MES / SCADA üretim takip bağlantısı<br>• Dışarı akan bulut telemetri verisi |
| **6** | **Kritik Veri Akışı** | • HMI ↔ PLC arası baskı kuvveti ve hız verileri<br>• Uzak Bakım ↔ PLC arası konfigürasyon trafiği |
