# 🛡️ Serdivan Belediyesi E-İmza Yardımcısı (Chrome Extension)

Bu Google Chrome eklentisi, belediye personelinin EBYS (Elektronik Belge Yönetim Sistemi) ve Bakanlık kurumsal sistemlerinde yaşadığı e-imza entegrasyon sorunlarını en aza indirmek, yerel servislerin durumunu anlık izlemek ve teknik aksaklıkları kendi kendilerine çözebilmelerini sağlamak amacıyla **Serdivan Belediyesi Bilgi İşlem Müdürlüğü** tarafından geliştirilmiştir.

---

## 🚀 Özellikler

* **Anlık Port ve Servis Taraması:** `ArkSigner` ve `IBSigner` (Bakanlık İstemcisi) servislerinin yerel portlarını (`8443`, `8080`, `9595`) arka planda tarayarak aktiflik durumlarını raporlar.
* **Sürücü Altyapı Kontrolü (AKİA):** İmza motorlarının ve akıllı kart kitaplıklarının (DLL) işletim sistemi üzerindeki hazır bulunma durumunu mantıksal olarak analiz eder.
* **Akıllı Önbellek ve Çerez Temizleyici:** Tüm tarayıcı geçmişini silmeden, **sadece** e-imza kilitlenmelerine sebep olan kurumsal devlet ve kurum domainlerinin (`KamuSM`, `e-Devlet` vb.) çerezlerini ve yerel depolamasını tek tıkla temizler.
* **Hızlı Erişim İstasyonu:** Personelin şifre bloke/kilit çözme (PUK işlemleri) ve PIN değiştirme gibi KamuSM sayfalarına doğrudan eklenti içerisinden güvenli bir şekilde ulaşmasını sağlar.
* **Kurumsal ve Modern Arayüz:** Belediye logosu filigranlı, Cam Efekti (Glassmorphism) tasarım trendlerine uygun ve kullanıcı dostu arayüz.

---

## 📂 Proje Yapısı

Proje, Google Chrome **Manifest V3** standartlarına tamamen uyumlu ve sunucu bağımsız (Sıfır Bakım Maliyetli) olarak geliştirilmiştir:

```text
├── manifest.json       # Eklenti izinleri ve tarayıcı yapılandırması
├── popup.html          # Modern CSS3 ve HTML5 arayüzü
├── popup.js            # Port tarama ve önbellek temizleme lojikleri
└── icon.png            # Kurumsal logo / Eklenti ikonu

🛠️ Kurulum ve Canlıya Alma
1. Geliştirici Modu ile Manuel Kurulum (Test İçin)
	1.	Bu depoyu (repository) bilgisayarınıza indirin veya clone'layın.
	2.	Google Chrome'u açın ve adres çubuğuna chrome://extensions/ yazın.
	3.	Sağ üst köşede bulunan "Geliştirici Modu" (Developer Mode) seçeneğini aktif hale getirin.
	4.	Sol üstte çıkan "Paketlenmemiş eklenti yükle" (Load unpacked) butonuna tıklayın.
	5.	İndirdiğiniz proje klasörünü seçerek eklentiyi tarayıcınıza dahil edin.
2. GPO (Group Policy) ile Kurumsal Dağıtım (Bilgi İşlem İçin)
Eklentiyi belediye bünyesindeki tüm bilgisayarlara merkezden tek tıkla dağıtmak için:
	1.	Projeyi .crx formatında paketleyin veya kurumsal bir eklenti hesabı ile Chrome Web Mağazası'na (gizli/unlisted olarak) yükleyin.
	2.	Windows Server üzerinde Group Policy Management panelini açın.
	3.	User Configuration -> Policies -> Administrative Templates -> Google -> Google Chrome -> Extensions yolunu takip edin.
	4.	"Configure the list of force-installed apps and extensions" politikasını aktif ederek eklenti kimliğini (ID) ve güncelleme URL'sini ekleyin.
🛡️ Güvenlik ve Gizlilik Politikası
•	Bu eklenti tamamen istemci taraflı (client-side) çalışır.
•	Hiçbir uzak sunucuya veri göndermez, kullanıcı verilerini işlemez veya dışarıya sızdırmaz.
•	Masaüstü uygulamalarının kilitlenmesini önlemek adına harici script (.bat vb.) tetiklemez; tamamen Chrome Sandbox güvencesi altındadır.
💡 Serdivan Belediyesi Bilgi İşlem Müdürlüğü tarafından kurumsal verimliliği artırmak adına açık kaynak vizyonuyla geliştirilmiştir.
