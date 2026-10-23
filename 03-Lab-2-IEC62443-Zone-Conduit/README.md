# 🌐 LABORATUVAR 2 · IEC 62443 Mini Workshop
**Üretilen Çıktı:** Zone / Conduit Diagram (Evidence Pack EP 05 Zone & Conduit)  
**Makine:** Optimak STU – Otomatik Üstten Baskılı Palet Çemberleme Makinesi  

---

## Görev A — Varlıkları Bölgelere (Zone) Ayırın

**1. Hangi varlıklar aynı bölgede? Bölgeleri adlandırıp gruplandırın.**
* **Kurumsal / Ofis Bölgesi:** Ofis ağı (ERP/e-posta).
* **DMZ / Dış Erişim ve Güvensiz Bölge:** İnternete açık uzak bakım modülü, bulut telemetri, Wi-Fi AP.
* **Denetim ve Mühendislik Bölgesi:** SCADA istemcisi, mühendislik istasyonu.
* **Makine Kontrol Bölgesi:** Üretim PLC'si, HMI (Port 80 web arayüzü), servo ve motor sürücüleri.
* **Emniyet Bölgesi (Safety Zone):** Safety PLC (Emniyet PLC'si), ışık perdeleri, E-stop zinciri.

**2. Safety PLC'yi hangi bölgeye koydunuz — neden? (Açık uzak bakım modülü orada kalabilir mi?)**
* **Safety PLC:** Kendine özel "Emniyet Bölgesi" içine konmuştur. İnsan hayatını koruyan son katman olduğu için diğer ağlardan bağımsız çalışabilmelidir.
* **Açık Uzak Bakım Modülü:** İnternete doğrudan açık olduğu için Güvensiz Bölgeye düşer ve makine bölgesinde kesinlikle kalamaz.

**3. Bölgeler arası geçişler (Conduit) nerede? Her geçişte ne kontrol edilecek?**
* **Conduit 1 (Dış Uzak Bakım ↔ Makine Bölgesi):** İçeri kimin girdiği (MFA/yetki) ve şifreli tünel (VPN) kontrol edilir.
* **Conduit 2 (Makine Kontrol Bölgesi ↔ Emniyet Bölgesi):** Safety PLC'ye dışarıdan konfigürasyon yazma (write) istekleri engellenir; yalnızca salt okunur duruma izin verilir.

---

## Görev B — Uzak Erişim Kararı

| Karar | Seçiminiz + Nedeni |
| :--- | :--- |
| **Aracı?** | **Jump server:** Makineye doğrudan bağlantı çok risklidir; kontrollü bir ara sunucu üzerinden geçiş yapılmalıdır. |
| **Tünel?** | **VPN:** Açık ağ üzerinden veri göndermek trafiğin dinlenmesine yol açar; şifreli tünel şarttır. |
| **Kimlik?** | **MFA:** Tek parola çalınabilir ("admin/admin"); çok faktörlü doğrulama zorunlu olmalıdır. |
| **Hesap?** | **Kişisel:** Ortak hesap kullanılırsa tehlikeli bir parametreyi kimin değiştirdiği tespit edilemez. |
| **Kayıt?** | **Tam oturum kaydı:** Fiziksel iş kazası yaşandığında geriye dönük denetim kanıtı için oturum kaydedilmelidir. |
| **Zamanlama?**| **Varsayılan kapalı:** Sürekli açık kapı saldırganlara davetiye çıkarır; bağlantı yalnızca bakım süresince açılmalıdır. |
