# Interview & Career Coach Agent (Mülakat & Kariyer Koçu)

Mülakata gireceğiniz yetkilinin unvanına (Title) göre özel soru havuzu ve canlı interaktif simülasyon sağlayan; tamamlanan eğitim içeriklerini analiz ederek beceri açığı, kurs/sertifika ve uygulamalı proje odaklı bir sonraki adım kariyer yol haritasını oluşturan yapay zeka destekli koçluk platformu.

## User Review & Critical Decisions

> [!IMPORTANT]
> Kullanıcı ile yapılan ön değerlendirme sonucunda aşağıdaki kararlar kesinleştirilmiştir:

- **Odak Alan**: Yazılım, Veri ve Yapay Zeka Teknolojileri (Software, Data & AI Tech) ekosistemi öncelikli olarak hedeflenmiştir; genel roller için de esnek başlık desteği sağlanacaktır.
- **Mülakat Deneyimi**: Sadece statik soru listesi değil; kullanıcının yanıtlarını girebildiği, STAR metodolojisiyle anlık puanlama, yapıcı eleştiri ve ideal yanıt rehberi sunan **canlı interaktif simülasyon modu** uygulanacaktır.
- **Eğitim Analizi ve Kariyer Çıktısı (3'ü Bir Arada)**:
  1. *Beceri Açığı Analizi ve Aşamalı Yol Haritası* (Mevcut yetkinlikler vs. hedef rol gereksinimleri)
  2. *Sertifika, Kurs ve Kaynak Önerileri* (Spesifik konu ve platform bazlı tavsiyeler)
  3. *Uygulamalı Portföy Projeleri* (GitHub/iş başvurularında öne çıkacak somut projeler)

---

## 1. Overview & Core Concept

- **Ne Yapar (What It Does)**:
  - **Unvan Bazlı Mülakat Simülasyonu**: Kullanıcı mülakatçının unvanını (örn. *Engineering Manager, Staff AI Engineer, VP of Technology, Lead Data Scientist, Senior HR Partner*) ve hedef pozisyonu girdiğinde, Gemini o unvanın değerlendirme perspektifini benimser (teknik derinlik, liderlik, sistem tasarımı, kültür uyumu). Olası soruları, "Mülakatçı neyi ölçüyor?" içgörülerini ve canlı yanıt değerlendirmesini sunar.
  - **Eğitim İçeriği & Kariyer Analizi**: Kullanıcı aldığı kursları, bootcamp içeriklerini veya sertifika başlıklarını girdiğinde; yapay zeka bu müfredatı ayrıştırır, kullanıcının mevcut kıdem seviyesini belirler ve hedeflenen üst rol için somut sonraki adım eğitim planı çıkarır.
- **Hedef Kitle**: Yazılım mühendisleri, veri bilimciler, yapay zeka geliştiricileri ve teknoloji sektöründe mülakata hazırlanan ya da kariyerinde bir üst seviyeye geçmek isteyen profesyoneller.
- **Temel Değer**: Mülakatçı masasının diğer tarafındaki kişinin beklentilerine nokta atışı hazırlık + rastgele kurs seçmek yerine kanıtlanmış eksikliklere göre kişisel eğitim müfredatı.

---

## 2. User Experience & Visual Design

### Key User Flows
1. **Mod Seçimi (Workspace Hub)**:
   - Üst sekmede iki temel çalışma alanı: **"Mülakat & Canlı Simülasyon Koçu"** ve **"Eğitim Analizi & Kariyer Haritası"**.
2. **Akış 1: Mülakatçı Unvanı & Simülasyon**:
   - Kullanıcı mülakatçı unvanını girer (örn. *Lead Machine Learning Engineer*) veya hızlı unvan şablonlarından seçer (*Engineering Manager, Talent Acquisition Lead, Staff Architect, Head of AI*).
   - Şirket tipi / seviye opsiyonel olarak belirlenir (Startup, Scale-up, Big Tech / Mid-level, Senior).
   - Gemini, o unvanın psikolojisini ve değerlendirme matrisini yansıtan 5-7 odaklı soru üretir.
   - Kullanıcı **"Canlı Simülasyonu Başlat"** dediğinde soru sırayla yöneltilir; kullanıcı yazarak veya sesle yanıt verir; yapay zeka anında STAR analizi (Durum, Görev, Eylem, Sonuç) ve puanlama yapar.
3. **Akış 2: Eğitim Geçmişi & Sonraki Adım Analizi**:
   - Kullanıcı tamamladığı eğitimlerin içeriğini/müfredatını metin olarak yapıştırır veya hazır örnek veri (ör. *Python Veri Analizi, LLM Temelleri, Docker/K8s Bootcamp*) yükler.
   - Hedeflediği unvanı seçer (örn. *Senior MLOps Engineer*).
   - Sonuç ekranı 3 sekmeli zengin bir analiz sunar:
     - **Aşama 1: Beceri Matrisi & Eksiklik Analizi** (Kazanılanlar vs. Eksik olanlar)
     - **Aşama 2: Sonraki Adım Öğrenme Planı & Sertifikasyonlar** (Önerilen spesifik kurs modülleri, yetkinlikler)
     - **Aşama 3: Portföy Projeleri** (İş görüşmesinde sunulabilecek 3 üretim kalitesinde proje fikri ve mimarisi)

### Visual Identity & Theme
- **Tasarım Dili**: SaaS & Executive Dashboard ilkelerine sadık, dikkati dağıtmayan koyu arduvaz (`slate-900`/`slate-950`) ve nötr gri zeminler, yüksek kontrastlı okunaklı tipografi, zero-pill disiplini (etiketler hap kutusu şeklinde değil, zarif `·` ayraçlı metinlerle sunulur).
- **Tipografi**: `Plus Jakarta Sans` başlık ve gövde hiyerarşisi, veri ve puan göstergelerinde `tabular-nums` ve `font-mono`.
- **Top Bar Sözleşmesi**: Sol tarafta temiz tek satır logo `Interview & Career Coach Agent`, ortada sade görünüm bağlantıları, sağ tarafta aktif oturumu sıfırlama/yeni analiz başlatma aksiyonu.
- **Anti-Slop Kuralları**: Sahte inovasyon skorları veya anlamsız yeşil yanıp sönen noktalar yok; her buton somut bir işlev gerçekleştirir.

---

## 3. Key Product Decisions & Trade-Offs

- **Karar 1: Gerçek Sunucu Taraflı Gemini API Çağrıları (`gemini-3.8-flash`)**:
  - *Yaklaşım*: Vite arkasında çalışan güvenli `/api/*` endpoint'leri üzerinden `@google/genai` kütüphanesi ile iletişim kurma.
  - *Neden*: API anahtarının tarayıcıya sızmasını engeller; sistem komutları (System Instructions) ve yapılandırılmış JSON şemaları (responseSchema) ile tutarlı, yüksek kaliteli sonuçlar üretir.
- **Karar 2: Canlı Simülasyonda Adım Adım İnteraktif Mod**:
  - *Yaklaşım*: Soruların hepsini bir anda okuyup geçmek yerine, mülakatçı gibi tek tek sorma, kullanıcının yanıtını alma ve anında geri bildirim üretme imkanı.
  - *Neden*: Gerçek mülakat stresini ve anlık düşünme refleksini simüle eder.
- **Karar 3: Hazır Örnek Senaryolar (Demo Presets)**:
  - *Yaklaşım*: Kullanıcının hemen denemesi için "Tech Lead Mülakatı", "HR Partner Kültür Mülakatı", "Junior -> Senior Data Scientist Eğitimi" gibi tek tıkla dolan hazır şablonlar ekleme.
  - *Neden*: Boş form yorgunluğunu önler ve uygulamanın kabiliyetlerini anında sergiler.

---

## 4. Technical Architecture & Data Strategy

```
┌────────────────────────────────────────────────────────────────────────┐
│                          Client (React 19)                             │
│                                                                        │
│  ┌──────────────────────┐  ┌─────────────────┐  ┌──────────────────┐  │
│  │   Top Bar Header     │  │ Workspace Nav   │  │ Preset Selector  │  │
│  └──────────────────────┘  └─────────────────┘  └──────────────────┘  │
│                                                                        │
│  ┌──────────────────────────────────┐ ┌─────────────────────────────┐  │
│  │ 🎙️ Interview Persona & Sim View  │ │ 🧭 Training & Roadmap View  │  │
│  │  - Interviewer Title Input       │ │  - Completed Training Input │  │
│  │  - Perspective & Focus Areas     │ │  - Target Role Selection    │  │
│  │  - Question Bank & STAR Answers  │ │  - 3-Way Roadmap Display    │  │
│  │  - Live Interactive Mock Coach   │ │    (Gaps, Courses, Projects)│  │
│  └──────────────────────────────────┘ └─────────────────────────────┘  │
└──────────────────────────────────┬─────────────────────────────────────┘
                                   │ HTTP POST /api/...
                                   ▼
┌────────────────────────────────────────────────────────────────────────┐
│                  Server Layer (Vite Dev Server Proxy)                  │
│                                                                        │
│  POST /api/interview/generate   -->  gemini-3.8-flash (Question Bank) │
│  POST /api/interview/evaluate   -->  gemini-3.8-flash (Mock Feedback) │
│  POST /api/career/roadmap       -->  gemini-3.8-flash (3-Way Roadmap) │
└──────────────────────────────────┬─────────────────────────────────────┘
                                   │ @google/genai SDK
                                   ▼
                    Google Gemini 3.8 Flash API
```

### Data Models & State
- **InterviewSession**:
  - `interviewerTitle`: string (örn. "Engineering Director")
  - `targetRole`: string (örn. "Senior Backend Engineer")
  - `companyType`: string (örn. "Fast-Growing FinTech")
  - `interviewerPersona`: { perspective, evaluationCriteria, keyRedFlags }
  - `questions`: Array<{ id, question, whyTheyAsk, whatTheyExpect, idealStarResponse, userResponse, feedback }>
  - `simulationState`: { activeQuestionIndex, isRecording, score, finished }
- **CareerAnalysis**:
  - `completedTrainingsText`: string
  - `targetRole`: string
  - `currentProficiencyAssessment`: string
  - `skillGaps`: Array<{ skill, currentLevel, requiredLevel, priority }>
  - `learningPath`: Array<{ stepNumber, title, description, estimatedWeeks, recommendedTopics, certificationsOrCourses }>
  - `portfolioProjects`: Array<{ title, problemStatement, architectureTechStack, keyDeliverable }>

### Interactive State Transitions
- Tab geçişlerinde aktif oturumlar korunur.
- Simülasyon modunda soru ilerleme çubuğu, zamanlayıcı ve kullanıcının yanıtını kaydetme butonları aktiftir.
- Sonuçlar temiz metin/Markdown olarak dışa aktarılabilir ve kopyalanabilir.
