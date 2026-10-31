# 🚨 LABORATUVAR 6 · CRA Incident Simulation
**Çıktı:** Incident Workflow (Evidence Pack EP 13 Incident Response)  
**Makine:** Optimak STU – Otomatik Üstten Baskılı Palet Çemberleme Makinesi  

---

## Senaryo
Saat 10:15. Servis hesabında yetkisiz erişim tespit edildi. PLC konfigürasyonu değişmiş olabilir. Makine hâlâ çalışıyor.

---

## Görev — Zaman Çizgisi Cevapları

**1. 10:15 — İlk 15 dk: Kimi ararsınız? İlk üç eyleminiz?**
Fabrika IT/OT sorumlusunu ve İSG uzmanını ararım. 
* **İlk 3 eylem:** Uzak erişim modeminin internet fişini çekerim, operatörü baskı tablası alanından uzaklaştırırım ve kanıtlar (loglar) silinmesin diye sistemi kesinlikle kapatıp açmam (resetlemem).

**2. İlk 2 saat: Emniyet güvende mi? Neyi korursunuz (kanıt!)? Hangi hesap kapatılır?**
Safety PLC'nin program kodunu (checksum) kontrol eder, ışık perdelerini fiziksel olarak test ederim. Kanıt olarak modem, firewall ve PLC giriş kayıtlarının (log) yedeğini alırım. Sızılan ortak "admin" servis hesabını hemen kapatırım.

**3. 24 saat — CRA erken uyarı: Hangi bilgi hazır olmalı?**
Olayın tespit edildiği saat, etkilenen makine (Optimak STU), yetkisiz giriş yapıldığı ve saldırının devam edip etmediği bilgisi ön rapor için hazır olmalı.

**4. 72 saat — CRA bildirim: Kök neden, etki, önlem — kim ne yapıyor?**
* **Kök neden ve etki:** Doğrudan internete açık modem ve zayıf servis şifresi yüzünden sızılmıştır.
* **Kim ne yapıyor:** IT logları inceler, OT ekibi temiz PLC yazılımını yükleyip modemi VPN arkasına alır, emniyet uzmanı ışık perdelerini doğrular, yönetim ise CRA bildirimini gönderir.

**5. 14 gün — Son rapor: Hangi loglar/kayıtlar korunmuş olmalı?**
Saldırı anındaki tüm erişim logları, PLC değişim kayıtları, alınan yeni önlemler (MFA, VPN, kişisel hesap) ve yapılan güvenlik testi sonuçları dosyada saklanmış olmalı.
