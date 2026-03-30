# 📝 PRD: Güvenli Okul Bildirim Platformu (V1.0)

## 1. Ürün Vizyonu
Öğrencilerin korkmadan sesini duyurabildiği, yapay zekanın rehber öğretmenlere "dijital asistanlık" yaptığı, okullarda zorbalığı minimize etmeyi hedefleyen bir web platformu.

---

## 2. Kullanıcı Tipleri ve Görevleri

| Kullanıcı | Ne Yapar? | Temel İhtiyacı |
| :--- | :--- | :--- |
| **Öğrenci** | Kayıt olmadan, anonim şekilde olay bildirir. | Gizlilik ve anlaşılma hissi. |
| **Rehber Öğretmen** | Paneline düşen yapay zeka analizli raporları inceler. | Hızlı aksiyon ve vaka takibi. |
| **Yönetici** | Okulun genel zorbalık karnesini (grafikler) görür. | Stratejik karar verme ve denetim. |

---

## 3. Temel Özellikler (Scope)

### A. Bildirim Sihirbazı (Öğrenci Arayüzü)
* **Anonim Form:** Sadece metin alanı ve (varsa) görsel yükleme alanı. İsim/Soyisim istenmez.
* **Takip Kodu:** Bildirim yapıldığında verilen özel bir kod ile öğrenci, raporunun durumunu ("İncelendi", "İşlem Yapılıyor") anonimce sorgulayabilir.

### B. AI Analiz Motoru (Arka Plan)
* **Ciddiyet Puanlama:** Metni analiz eder ve $0$ (düşük) ile $10$ (kritik) arası bir risk skoru atar.
* **Otomatik Özetleme:** Uzun ve karmaşık anlatımları, rehber öğretmenin hızlıca anlayabileceği 3-4 maddelik özetlere dönüştürür.
* **Kategori Etiketleme:** Olayın türünü (Siber zorbalık, fiziksel şiddet, sözel taciz vb.) otomatik olarak belirler.

### C. Yönetim Paneli (Öğretmen & Yönetici)
* **Vaka Havuzu:** Gelen bildirimlerin ciddiyet skoruna göre (en acilden normale) sıralandığı liste görünümü.
* **Vaka Takibi:** Vakaları "Beklemede", "İncelemede" veya "Çözüldü" olarak işaretleme sistemi.
* **İstatistik Dashboard:** Okul genelinde hangi zorbalık türlerinin yaygın olduğunu gösteren grafikler.

---

## 4. Teknik ve Güvenlik Gereksinimleri

* **Dil:** Tamamen Türkçe arayüz ve yerelleştirilmiş AI modellemesi.
* **Gizlilik:** Veritabanında hiçbir IP adresi veya kişisel veri tutulmayacaktır (KVKK %100 uyum).
* **Erişilebilirlik:** Mobil öncelikli (Mobile-First) tasarım; öğrencilerin her ortamdan kolayca ulaşabilmesi için.
* **Yapay Zeka:** Güçlü bir LLM (GPT-4 vb.) entegrasyonu ile metin işleme.

---

## 5. Başarı Metrikleri (KPI)

1.  **Analiz Hızı:** Bildirim yapıldıktan sonra AI raporunun 5 saniye içinde öğretmene ulaşması.
2.  **Skor Doğruluğu:** AI'nın belirlediği ciddiyet puanının, uzman görüşüyle %85 oranında örtüşmesi.
3.  **Kullanım Oranı:** Tanıtım sonrası ilk ay içinde hedeflenen öğrenci kitlesinden en az %10 etkileşim.

---

## 6. Yol Haritası (MVP Fazları)

* **Faz 1:** Anonim bildirim formunun ve AI analiz modülünün (Backend) kurulması.
* **Faz 2:** Rehber öğretmen giriş sistemi ve vaka listeleme ekranının geliştirilmesi.
* **Faz 3:** Yönetici paneli için veri görselleştirme ve istatistik araçlarının eklenmesi.
