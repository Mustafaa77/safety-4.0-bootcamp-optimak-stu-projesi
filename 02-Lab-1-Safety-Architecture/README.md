# 🛡️ LABORATUVAR 1 · Safety Architecture
**Üretilen Çıktı:** Safety Function Map (Evidence Pack EP 03 Safety Functions)  
**Makine:** Optimak STU – Otomatik Üstten Baskılı Palet Çemberleme Makinesi  

---

## Kavramsal Çerçeve ve Kontrol Yolları
Makinede iki ayrı kontrol yolu bulunur:
1. **Normal Kontrol Yolu (Üretim):** `Sensör ➔ PLC (Normal Kumanda) ➔ Aktüatör (Üst Baskı Tablası + Çemberleme Kafası)`
2. **Safety Yolu (Koruma - Ayrı ve Bağımsız):** `E-stop / Işık Perdesi / Kapı Kilidi ➔ Safety PLC (Emniyet Kumandası) ➔ STO / Kontaktör (Gücü Keser) ➔ Safe State`

* **Dijital Kesişim Noktası:** Bakım ve güncelleme amacıyla kullanılan **IPC / Uzak Erişim Modülü**, normal kontrol yolu üzerinden emniyet kumandasına (Safety PLC) dijital olarak dokunabildiği noktadır.

---

## Görev Soruları ve Cevapları

**1. Bu makinede tehlike nedir? İnsan neyden zarar görür?**
Tehlike; paleti sıkıştırmak için inen hareketli üst baskı tablası, yüksek hızda hareket eden çemberleme kafası ve sıcak çember yapıştırma bıçağıdır. Operatör palet giriş-çıkış alanına girdiğinde ezilme, sıkışma veya kesilme nedeniyle fiziksel zarar görür.

**2. Safety function (emniyet fonksiyonu) hangisidir?**
Palet giriş-çıkış hattındaki güvenlik ışık perdeleri (light curtain), bakım kapısı emniyet kilidi ve acil durdurma (E-stop) butonlarının ihlal algıladığı anda makineyi durduran koruma zinciridir.

**3. Safety-related control system nerede? Şemada işaretleyin.**
Normal üretim kontrol yolunun altında yer alan, üretimden ayrı ve bağımsız çalışan **"E-stop / Işık Perdesi ➔ Safety PLC (emniyet kumandası) ➔ STO / Kontaktör ➔ Safe State"** zincirinin tamamıdır.

**4. Normal PLC ile Safety PLC farkı nedir?**
Normal PLC üretimin devamlılığını yönetirken; Safety PLC insan hayatını korumayı öncelik alır. Yedekli mimarisiyle ışık perdesi ve E-stop sinyallerini denetleyerek tehlike anında doğrudan gücü keser.

**5. PLr / SIL neden var? Bu fonksiyon için neden önemli?**
Korumanın güvenilirliğinin makinenin barındırdığı riskle orantılı olması gerektiği için vardır. Üst baskı tablası ölümcül yaralanmaya yol açabileceği için bu makinede yüksek güvenilirlik seviyesi (PLd/PLe veya SIL 2/3) hayati önem taşır.

**6. Safe state (güvenli durum) nedir?**
Emniyet sensörleri tetiklendiğinde STO (Safe Torque Off) üzerinden motorların enerjisinin tamamen kesilip makinenin hareketsiz duruma geçmesidir.

**7. Safety function hangi dijital bağımlılıklara sahip?**
Safety PLC içindeki dijital konfigürasyona (algılama gecikme süreleri) bağlıdır. Bu yapı da IPC ve uzak bakım modülü ile dijital kesişim noktasına sahiptir.

**8. Siber müdahale hangi noktadan bu fonksiyonu bozar?**
İnternete açık uzak bakım modülü veya IPC üzerinden sızan bir saldırgan, "dijital kesişim noktası" üzerinden Safety PLC'ye ulaşıp ışık perdesi tepki parametrelerini değiştirerek bu fonksiyonu bozabilir.
