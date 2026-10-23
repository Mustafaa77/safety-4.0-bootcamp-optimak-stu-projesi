# 🔒 LABORATUVAR 4 · Secure Remote Access
**Üretilen Çıktı:** Secure Architecture (Evidence Pack EP 02 Network Architecture + EP 06 Remote Access Procedure)  
**Makine:** Optimak STU – Otomatik Üstten Baskılı Palet Çemberleme Makinesi  

---

## Görev A — Mevcut ➔ Hedef Mimariyi Yeniden Tasarlayın

**❌ MEVCUT (Savunmasız Mimari)**
`[Makine (PLC + HMI)] <---> [İnternete Doğrudan Açık Uzak Bakım Modülü] <---> [İnternet]`
* Uzak bakım modülü doğrudan internete açıktır.
* Tedarikçiler ortak `"admin/admin"` hesabını kullanmaktadır ve bağlantı 7/24 sürekli açıktır. Oturum log kaydı yoktur.

**✅ HEDEF (Beş İlkeyle Yeniden Tasarlanmış Mimari)**
`[Tedarikçi (Kişisel Hesap + MFA)] ➔ [Şifreli VPN] ➔ [Jump Server (Varsayılan Kapalı + Kayıt)] ➔ [Firewall] ➔ [Üretim PLC]`
* **Uygulanan İlkeler:** Makine doğrudan internetten koparılarak Jump Server arkasına alınmıştır. Ortak hesaplar iptal edilmiş, VPN ve MFA zorunlu tutulmuştur. Erişim varsayılan kapalı hale getirilmiş ve tüm oturum video log olarak kaydedilmektedir.

---

## Görev B — Functional Safety Köprüsü

**1. Saldırgan tüm önlemlere rağmen içeri girerse: emniyet fonksiyonu etkilenir mi? Neden?**
Eğer mevcut dijital kesişim noktası (konfigürasyon erişimi) açık bırakılmışsa evet, etkilenir. Çünkü Jump Server'ı aşan saldırgan, üretim ağından Safety PLC ayarlarına dokunup emniyet parametrelerini manipüle edebilir.

**2. Emniyet fonksiyonunun kontrol sisteminden bağımsız çalışması için GEREKSİNİMİ yazın.**
Makinenin insan hayatını koruyan emniyet fonksiyonları (ışık perdeleri, kapı kilitleri ve E-stop zinciri), normal üretim kontrol sisteminden ve her türlü uzaktan bakım ağından mantıksal ve fiziksel olarak tamamen bağımsız çalışmalıdır. Ağ ele geçirilse dahi emniyet fonksiyonu dış müdahaleye kapalı kalmalıdır.
