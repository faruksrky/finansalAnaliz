# Proje Kararları

Finansal tabloları Warren Buffett'ın kitaptaki kurallarıyla analiz edip ABD hisselerinde sürekli rekabet üstünlüğü olan şirketleri ve moonshot adaylarını tespit eden bot.

Kurallar: `docs/buffett_rules.md` · Kodun okuyacağı ayarlar: `config/rules.yaml`

## Kapsam

| Konu | Karar |
|------|-------|
| Pazar | Sadece ABD hisseleri |
| Sektör 1 | Teknoloji (NVDA, MSFT, AAPL, AMD, AVGO …) |
| Sektör 2 | Yapay zeka altyapısına hizmet eden enerji ve malzeme |
| Enerji örnekleri | Veri merkezlerine enerji sağlayanlar: CEG, VST, NRG; utility + veri merkezi bağlantısı olanlar: NEE, DUK |
| Kimya / malzeme örnekleri | Yapay zeka kablo ve altyapısına malzeme üretenler: DD, DOW, LIN (kısmen), GLW |
| Hariç | Klasik petrol & gaz (XOM, CVX vb.) — kullanıcı eklemedikçe evrene girmez |
| Analiz penceresi | **5 yıl** (başta 10 yıldı; moonshot'lar da olduğu için 5 yıla çekildi) |

## Core ve moonshot

| | Core | Moonshot |
|---|------|----------|
| Profil | Sürekli rekabet üstünlüğü, kitap kuralları | Erken büyüme, yüksek risk / yüksek potansiyel |
| Skor | Buffett skor kartı | Ayrı skor kartı (kuralları henüz tanımlanmadı) |
| Veri | 5 yıl | ≥ 2 yıl → skor hesaplanır; < 2 yıl → sadece izleme listesi |
| Yorum katmanı | Bölüm 53–54 moat kontrol listesi | Moonshot'a özel yorum (henüz tanımlanmadı) |
| Liste | Haftalık core listesi | Haftalık ayrı moonshot listesi |

Kullanıcı moonshot'lara kesin yatırım yapacak; moonshot'lar core listesinde kaybolmamalı.

## Mimari

```
Veri (5 yıl) → Nicel skor (kitap kuralları) → Yüksek skor? → Moat yorumu (Böl. 53–54) → Rapor
```

- Oran hesaplama ve eşik kontrolü: deterministik kod
- Yorum katmanı (ajan): yalnızca yüksek skorlu hisseler için; kitabın dışına çıkmaz

## Skorlama

- **Risk ağırlıklı (seçim C):** Önce "şüpheli mi?" filtrelenir. Ar-Ge (13), PP&E/CapEx (28, 50), faiz/borç (15, 39, 41), gelir sürekliliği (8) ve faaliyet giderleri (11–12) cezaları ağır; Bölüm 53–54 moat sinyalleri orta ağırlıkta.
- **Sektör medyanı:** İki ayrı evren — Tech ve AI enerji + kimya/malzeme.
- **Negatif net kâr:** 5 yıl içinde en az 1 yıl zarar varsa Bölüm 50 "hesaplanamaz / şüpheli"; Bölüm 39 o yıl için şüpheli.
- **Eksik veri:** Halka arzı 5 yıldan yeni hisselerde mevcut tüm yıllar kullanılır ve raporda "X yıl veri" uyarısı gösterilir.
- **Kaldıraç tuzağı (seçim B):** ROE eşiği geçip Bölüm 15, 39 ve 41 içinden iki veya üçü olumsuzsa şüpheli. Yalnız biri olumsuzsa uyarı. Bölüm 48 metni gelince gözden geçirilir.
- **Konsolide tablo:** Gelir, kâr, Ar-Ge, CapEx, borç ve faiz konsolide finansal tablodan okunur. Bir bölümün kârı skora girmez ve konsolide ihlali silmez.

## Veri kaynağı (tasarruf paketi)

| Katman | Kaynak | Maliyet |
|--------|--------|---------|
| Ana | yfinance | $0 |
| Doğrulama | Financial Modeling Prep (Free veya Starter) | $0–22/ay |
| İleride (isteğe bağlı) | FMP Premium | ~$59/ay |

Kritik metrikler (net kâr, CapEx, R&D, EPS) FMP ile çapraz kontrol edilir.

## Helal eleme (kitap dışı kapı)

Kullanıcı faiz geliri elde etmez ve faizli araç almaz. Bu kapı Buffett skorundan önce çalışır. Geçemeyen hisse core ve moonshot listesine girmez. Eşikler kitaba eklenmiş kriter değildir.

Kaynak: AAOIFI Şer'i Standart 21 (oran ve arınma) ve ABD İslami endeks uygulaması Dow Jones Islamic Market (iş kolları, payda, alacak oranı). Eylül 2026'da endeks, borç ve nakit tavanını %33'ten %30'a indirdi; bu AAOIFI ile aynı çizgidir.

Faizli tahvil, bono ve faiz getiren mevduat alınmaz. Hisse, faizle borçlanarak (marj) alınmaz. Mali öncelik taşıyan imtiyazlı hisse alınmaz.

### İş kolu

Ana faaliyet aşağıdakilerden biri ise elenir. Bu kalemlerden gelen gelir, toplam gelirin %5'ini aşarsa da elenir.

- Alkol
- Tütün
- Domuz ürünleri
- Konvansiyonel finans (faizli banka, konvansiyonel sigorta)
- Silah ve savunma
- Eğlence: kumar, otel, sinema, pornografi, müzik

### Oranlar

Payda: son 24 ayın ortalama piyasa değeri. Son doğrulanmış mali tablo. Oran ölçülemiyorsa hisse geçmez; "hesaplanamaz" işaretlenir.

| Test | Tavan |
|------|-------|
| Faizli borç / 24 ay ortalama piyasa değeri | %30 |
| Faizli nakit ve faiz getiren menkul kıymet / 24 ay ortalama piyasa değeri | %30 |
| Ticari alacaklar / 24 ay ortalama piyasa değeri | %33 |
| Haram gelir / toplam gelir | %5 |

### Arınma

Eşiğin altındaki faiz ve diğer haram gelir de kazanç sayılmaz. Dönem sonunda hissesi duran kişi şu tutarı ayırır ve harcamaz:

```
(şirketin haram geliri ÷ hisse sayısı) × elde tutulan hisse
```

Kâr dağıtılmamış olsa da tutar hesaplanır. Vergiye mahsup edilmez. Dönem bitmeden satan kişi bu dönem için arındırmaz.

## Çıktı (seçim C)

1. Haftalık core listesi — top 10–20, skor + kısa moat notu
2. Haftalık moonshot listesi — ayrı skor + kısa yorum
3. Hisse kartı — tüm kurallar, 5 yıl metrikler, moat/moonshot yorumu, bayraklar

## Açık konular

- [ ] Moonshot skor kuralları
- [ ] Core / moonshot etiketleme yöntemi (manuel mi, otomatik mi — ör. halka arz yaşı, piyasa değeri)
- [ ] Başlangıç ticker listesi
- [x] Bölüm 54 değerlemesinde faiz oranı: güncel kurumsal faiz (seçim A; FRED `BAMLC0A0CMEY`)
- [ ] Kitabın kalan bölümleri; öncelik sırası: 48 (kaldıraç), 17–20 (vergi, EPS), 49 (nakit akışı), 23/27 (nakit, cari oran), 44–45/51 (birikmiş kâr, geri alım), 55–56 (al/sat — ikinci faz)
