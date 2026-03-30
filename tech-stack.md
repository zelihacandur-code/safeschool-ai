## SafeSchool AI: Başlangıç Seviyesi Teknoloji Yığını

### 1. Önerilen Teknoloji Yığını (Stack)
* **Framework:** [Next.js](https://nextjs.org/) (React tabanlı)
* **Dil:** TypeScript veya JavaScript
* **Veritabanı & Auth:** [Supabase](https://supabase.com/) (PostgreSQL + Hazır Auth)
* **Yapay Zeka:** [Google Gemini API](https://ai.google.dev/) (SDK aracılığıyla)
* **Stil:** [Tailwind CSS](https://tailwindcss.com/)
* **Deployment:** [Vercel](https://vercel.com/)

---

### 2. Neden Bu Teknolojileri Seçiyoruz?
* **Next.js:** Hem ön yüzü (öğrenci formu) hem de arka yüzü (API rotaları/Gemini bağlantısı) tek bir projede toplar. Başlangıç için "Full-stack" karmaşasını azaltır.
* **Supabase:** Veritabanı kurmakla uğraşmazsınız. Rehber öğretmen girişi için hazır üyelik sistemi sunar ve bildirimleri saklamak için çok kolay bir arayüzü vardır.
* **Gemini API:** Google'ın en güncel ve performanslı modeli; Türkçe metin analizi ve özetleme konusunda çok başarılıdır.
* **Vercel:** Projenizi canlıya almak sadece birkaç saniye sürer ve Next.js ile tam uyumludur.

---

### 3. Adım Adım Kurulum ve Geliştirme Planı

#### Adım 1: Projeyi Başlatma
Terminalinizi açın ve temel Next.js yapısını kurun:
```bash
npx create-next-app@latest safeschool-ai
# Çıkan seçeneklerde Tailwind CSS ve App Router'ı "Yes" olarak seçin.
```

#### Adım 2: Bağımlılıkları Yükleme
Veritabanı bağlantısı ve Yapay Zeka SDK'sını ekleyin:
```bash
npm install @supabase/supabase-js @google/generative-ai
```

#### Adım 3: Çevresel Değişkenleri Ayarlama
Projenin ana dizinine `.env.local` dosyası oluşturun ve anahtarlarınızı ekleyin:
```text
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_key
GEMINI_API_KEY=your_gemini_api_key
```

#### Adım 4: Veritabanı Tablosunu Oluşturma
Supabase panelinde `reports` adında bir tablo oluşturun:
* `id` (int8)
* `content` (text) - Öğrencinin mesajı
* `severity_score` (int4) - AI'ın verdiği puan
* `summary` (text) - AI özeti
* `status` (text) - Varsayılan: "Beklemede"
* `tracking_code` (text) - Benzersiz takip kodu

#### Adım 5: Gemini API Entegrasyonu (API Route)
`app/api/analyze/route.ts` dosyasında, gelen öğrenci metnini Gemini'ye gönderen ve sonucu Supabase'e kaydeden fonksiyonu yazın.

#### Adım 6: Öğretmen Paneli ve Koruma
Supabase Auth kullanarak bir giriş sayfası yapın. Sadece giriş yapmış kullanıcıların (Öğretmenler) `reports` tablosunu görmesini sağlayacak bir dashboard sayfası oluşturun.

#### Adım 7: Yayına Alma
Kodlarınızı GitHub'a yükleyin ve Vercel hesabınıza bağlayarak `safeschool-ai.vercel.app` gibi bir adreste canlıya alın.

---

### Bir sonraki adımda ne yapmak istersin?
Gemini API için kullanacağın **"Prompt" (Yapay zekaya verilecek komut)** taslağını mı hazırlayalım, yoksa **Supabase bağlantı kodlarını** mı yazalım?
