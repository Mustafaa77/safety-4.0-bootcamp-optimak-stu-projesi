# 🛡️ Safety 4.0: Optimak STU - Otomatik Üstten Baskılı Palet Çemberleme Makinesi

**Hazırlayan:** Mustafa DÜRÜ (235541012)  
**Grup:** GECE  
**Kapsam:** Makine Tüzüğü (AB) 2023/1230, Siber Dayanıklılık Yasası (CRA), EN ISO 12100 ve IEC 62443 Kapsamında Makine Emniyeti & Siber Güvenlik Analizi

---

## 📌 Proje Özeti
Bu depo, SAMİB üyesi **Optimak STU** firmasının **Otomatik Üstten Baskılı Palet Çemberleme Makinesi** üzerinde yürütülen **Safety 4.0** laboratuvar çıktılarını ve **Evidence Pack (Kanıt Paketi)** dokümantasyonunu içerir. Siber güvenlik açıklarının emniyet fonksiyonlarını nasıl bozabileceği ve fiziksel yaralanmalara (ezilme, uzuv kaybı) nasıl yol açabileceği analiz edilmiştir.

---

## 📂 Klasör Yapısı ve Evidence Pack Eşleşmesi

| Klasör / Laboratuvar | Üretilen Çıktı | Evidence Pack Karşılığı | Teslim Durumu |
| :--- | :--- | :--- | :--- |
| `01-Makine-Tanitimi` | Asset Inventory & SWOT | EP 01 Asset Inventory | ✅ Tamamlandı |
| `02-Lab-1-Safety-Architecture` | Safety Function Map | EP 03 Safety Functions | ✅ Tamamlandı |
| `03-Lab-2-IEC62443-Zone-Conduit` | Zone / Conduit Diagram | EP 05 Zone & Conduit | ✅ Tamamlandı |
| `04-Lab-3-Threat-Risk-Matrix` | Risk Register | EP 04 Cyber Risk Assessment | ✅ Tamamlandı |
| `05-Lab-4-Secure-Remote-Access` | Secure Architecture | EP 02 Network + EP 06 Remote Access | ✅ Tamamlandı |
| `06-Lab-5-SBOM-CVE-Patch` | Vulnerability Decision | EP 09 SBOM · EP 10 CVE · EP 11 Patch | ⏳ Planlandı |
| `07-Lab-6-CRA-Incident` | Incident Workflow | EP 13 Incident Response | ⏳ Planlandı |

---

## 📊 Safety 4.0 Odaklı SWOT Analizi

| **GÜÇLÜ YÖNLER (Strengths)** | **ZAYIF YÖNLER (Weaknesses)** |
| :--- | :--- |
| • **Fiziksel Emniyet Donanımı:** Palet giriş/çıkışında ışık perdeleri ve STO/kontaktör altyapısı mevcuttur.<br>• **Ayrılabilir Mimari:** Üretim PLC'si ile Safety PLC birbirinden ayrılabilir yapıdadır. | • **Kontrolsüz Uzak Erişim:** Uzak bakım modülü doğrudan internete açık ve ortak hesap kullanıyor.<br>• **Saldırı Yüzeyi:** HMI web arayüzü açık ve pano üzerinde kilitsiz USB portları bulunuyor. |
| **FIRSATLAR (Opportunities)** | **TEHDİTLER (Threats)** |
| • **AB Mevzuatlarına Uyum:** Makine Tüzüğü (AB) 2023/1230 için CE siber güvenlik ön şartı sağlanmaktadır.<br>• **Güvenli Uzak Bakım:** Jump server, VPN ve MFA yapısına geçiş imkanı vardır. | • **Fiziksel İş Kazası:** Siber müdahale ile emniyet bozularak ağır ezilme ve uzuv kaybı yaşanması riski.<br>• **Yasal Yaptırımlar:** CRA bildirim yükümlülüklerine uyulmaması halinde ağır idari para cezaları. |
