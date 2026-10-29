# Buffett Kural Rehberi

Kaynak: Mary Buffett & David Clark — *Warren Buffett ve Finansal Tabloların Yorumlanması*

Bu dosya projenin **tek resmi kural kaynağıdır**. Analiz, skorlama ve yorum yalnızca buradaki maddelere dayanır. Kitapta olmayan bir kriter eklenmeden önce kullanıcıya sorulur ve onay alındıktan sonra buraya yazılır.

Genel ayarlar (ayrıntı: `docs/project_decisions.md`):

- Analiz penceresi: **5 yıl** (yıllık finansal tablolar)
- Skor **konsolide** tablodan okunur. Kârlı bir bölüm, konsolide ihlali kapatmaz.
- Kurallar **core** evrene uygulanır; moonshot hisselerin ayrı skor kartı vardır
- "Sektör medyanı" her yerde iki ayrı evrende hesaplanır: **Tech** ve **AI enerji + kimya/malzeme**
- Skor ağırlığı: **risk ağırlıklı** (cezalar baskın, moat sinyalleri orta)

---

## Gelir tablosu

### Bölüm 8 — Gelir: süreklilik

**Kitap:** Gelirde süreklilik arz etmeli.

**Kural (seçim B):**

- 5 yıllık gelir CAGR > 0 → olumlu
- 1–2 yıl gelir düşüşü tolere edilir
- 3+ yıl düşüş veya CAGR ≈ 0 / negatif → olumsuz (ağır ceza)

### Bölüm 9 — Satışların maliyeti

**Kitap:** Satışların maliyeti ne kadar azsa o kadar iyidir.

**Kural (seçim A — sabit eşik yok):**

- Metrik: COGS / gelir
- 5 yıl trendi düşüyor veya stabil → olumlu; yükseliyor → olumsuz
- Sektör medyanının belirgin üstü → olumsuz
- Gelir artarken COGS/gelir yükseliyorsa → "büyüme var, kalite zayıf" uyarısı

### Bölüm 10 — Brüt kâr marjı: istikrar

**Kitap:** Warren ısrarla "sürekli" kelimesini vurgular; güvenli tarafta kalmak için yıllık brüt kâr marjını 5 veya 10 yıl izler ve istikrar olduğundan emin olur.

**Kural (seçim C — güvenli taraf):**

- 5 yıl brüt marj CAGR ≥ 0
- En fazla 1 yıl marj düşüşü
- 5 yıl marj standart sapması düşük (evren içinde göreli)
- Sektör medyanından hızlı kötüleşme → ek uyarı

Bölüm 9'dan ayrı skor kalemidir (9 = seviye, 10 = istikrar).

### Bölüm 11 — Faaliyet giderleri

**Kitap:** Faaliyet giderleri gider kaleminde yüksekse bu şirketlerden uzak durun.

**Kural (seçim A):**

- Metrik: faaliyet giderleri / gelir
- 5 yıl trendi düşüyor veya stabil → olumlu; yükseliyor → olumsuz
- Sektör medyanının belirgin üstü → ağır ceza

### Bölüm 12 — Pazarlama, satış, dağıtım ve genel yönetim giderleri (SG&A)

**Karar:** Bölüm 11 ile aynı kural (trend + sektör medyanı).

- Bölüm 11 ile **tek skor kalemi** (çift ceza yok)
- Hisse kartında SG&A ayrı satır olarak gösterilir

### Bölüm 13 — Araştırma ve geliştirme (Ar-Ge)

**Kitap:** Ar-Ge için yüklü harcamalar yapmak zorunda olan şirketlerin rekabet üstünlüklerinde içsel bir bozukluk vardır. Bu kusur uzun vadeli ekonomilerini riske atar; bu da onların şüpheli olduğu anlamına gelir.

**Kural:**

- R&D / gelir **> %15** → "yüklü Ar-Ge" → **şüpheli** (ağır ceza)
- 5 yıl boyunca oran artıyorsa → ek uyarı
- Teknoloji hisseleri için muafiyet **yok**

### Bölüm 15 — Faiz giderleri

**Kitap:**

- Faiz ödemelerinin faaliyet giderlerine oranı, şirketin içinde bulunduğu ekonomik tehlikenin seviyesi bakımından oldukça bilgilendiricidir.
- Faaliyet gelirine göre en düşük finansman giderine sahip şirket genelde ve büyük ihtimalle rekabet üstünlüğüne sahiptir.
- Buffett'ın en beğendiği sürekli rekabet üstünlüğüne sahip şirketlerin hepsi faaliyet gelirlerinin **%15'inden azını** faiz ödemelerine kullanır.

**Kural:**

- Faiz / faaliyet geliri (5 yıl ort.) **< %15** → olumlu; **≥ %15** → olumsuz (kitap eşiği, ana test)
- Faiz / faaliyet giderleri → 5 yıl trend + sektör medyanı (seçim A, destekleyici)
- Her iki oranda yükselen trend → ek uyarı

---

## Bilanço

### Bölüm 28 — Arazi, tesis, makine ve cihazlar (PP&E)

**Kitap (s. 140):** Wrigley vs GM örneği. Değiştirmeye gerek duyulmayan bir ürünü sürekli üretmek sürekli kâr demektir. Sürekli bir ürün, rekabetçi kalabilmek için tesis, makine ve teçhizata tonlarca para harcayıp bunları yenilemeye ihtiyaç duymamak demektir. Çok para kazanmanın yollarından biri de başkalarıyla aşık atmak için tonlarca para harcamaya ihtiyaç duymamaktır.

**Kural (seçim 2 + 3 — sabit PP&E % eşiği yok):**

1. Ana test: Bölüm 50 (CapEx / net kâr)
2. Trend uyarıları (5 yıl):
   - PP&E büyümesi > gelir büyümesi → uyarı
   - CapEx büyümesi > gelir büyümesi → uyarı
   - CapEx / amortisman > 1,5 (pencere boyunca sürekli) → uyarı
3. Sektör medyanı:
   - PP&E / toplam varlık > medyan → olumsuz sinyal
   - CapEx / gelir > medyan → olumsuz sinyal

### Bölüm 39 — Uzun vadeli borçlar

**Kitap:** Bilançodaki uzun vadeli borçlanma kontrol edilmeli; sadece cari yıl değil, şirketin yıllar içinde taşıdığı uzun vadeli borç yüküne bakılmalı. Uzun süre düşük borçla ya da borçsuz faaliyet iyi bir şeydir. Warren'ın satın almaları gösteriyor ki herhangi bir yılda şirket tüm uzun vadeli borcunu **3–4 yılda** kapatabilecek yıllık dönem kârına sahip olmalıdır.

**Kural (süre: 5 yıl):**

- Uzun vadeli borç / net kâr **≤ 4** (her yıl ve 5 yıl ort.) → olumlu; > 4 → olumsuz
- 5 yıl boyunca düşük borç veya borçsuz → olumlu
- Borç trendi yükseliyorsa → uyarı
- Negatif net kâr yılında test "hesaplanamaz / şüpheli"

### Bölüm 41 — Toplam yükümlülükler ve borç / öz kaynak oranı

**Kitap (s. 186–189):**

- Borç / Öz kaynak = Toplam yükümlülükler ÷ Toplam öz kaynaklar
- Sürekli rekabet üstünlüğü olan şirket faaliyetlerini kazanç gücüyle finanse eder → yüksek öz kaynak, düşük yükümlülük. Olmayan şirket borçlanır → düşük öz kaynak, yüksek yükümlülük.
- Güçlü şirketler birikmiş kârlarını geri alımda kullanır, öz kaynak tabanı küçülür ve oran yapay olarak yükselir (Moody's'in eksi öz kaynağı). Bu yüzden **geri alınmış paylar öz kaynağa geri eklenerek düzeltilmiş oran** kullanılır.
- Düzeltilmiş oranlar: Coca-Cola 0,51 · Moody's 0,63 · Wrigley 0,68 · P&G 0,71 · Goodyear 4,35 · Ford 38,0
- Bankalar yapısal olarak yüksek kaldıraçlıdır (ort. 10; M&T 7,7).
- **Basit kural:** Finansal kurum değilse, düzeltilmiş borç/öz kaynak **0,80'in altında** (ne kadar düşükse o kadar iyi) ise sürekli rekabet üstünlüğü ihtimali çok yüksektir.

**Kural (seçim B):**

- Düzeltilmiş D/E = Toplam yükümlülükler ÷ (Öz kaynak + geri alınmış paylar)
- 5 yıl ortalaması **< 0,80** → olumlu; ≥ 0,80 → olumsuz (ağır ceza)
- Trend yükseliyorsa → uyarı

### Bölüm 46 — Öz kaynaklar

**Kitap (s. 208–209):**

- Öz kaynak = Toplam varlıklar − Toplam yükümlülükler
- Üç kaynağı vardır; bizim için en önemlisi **geçmiş yıllar kârlarının birikmesidir**.
- Hissedar olarak yönetimin paramızı ne kadar iyi tahsis ettiğiyle ilgileniriz. Analistler bunu test etmek için öz kaynak getirisi denklemini geliştirmiştir; Warren bu denklemi oldukça önemser.

### Bölüm 47 — Öz kaynak getirisi (ROE)

**Kitap (s. 211–212):**

- ROE = Dönem kârı ÷ Öz kaynaklar
- Sürekli rekabet üstünlüğü olan şirketler ortalamadan çok daha yüksek ROE gösterir: Coca-Cola %30, Wrigley %24, Hershey's %33, Pepsi %34.
- Rekabetin yoğun olduğu havayollarında: United %15, American %4; Delta ve Northwest zararda.
- Yüksek ROE, şirketin dağıtmadığı kârları iyi kullandığını gösterir; zamanla temel değer ve hisse fiyatı artar.
- Eksi öz kaynak: uzun geçmişte güçlü dönem kârı varsa büyük ihtimalle moat vardır; hem eksi öz kaynak hem dönem zararları varsa büyük ihtimalle hırpalanmış, vasat işletmedir.
- **Kural:** Yüksek ROE "gel sen de katıl", düşük ROE "uzak dur" demektir.

**Kural (seçim C):**

- 5 yıl ort. ROE **≥ %20** **ve** sektör medyanının üstünde → olumlu (ikisi birlikte)
- 5 yılda düşen trend → uyarı
- Eksi öz kaynak: 5 yıl güçlü kâr geçmişi → moat olabilir; zarar geçmişi → şüpheli
- Kaldıraç tuzağı (seçim B; iki olumsuz = şüpheli. Bölüm 48 metni gelince gözden geçirilir): ROE eşiği geçiyor ve Bölüm 15, 39, 41 içinden **iki veya üçü** olumsuz → şüpheli. Yalnız biri olumsuz → uyarı.

---

## Nakit akışı

### Bölüm 50 — Sermaye harcamaları (CapEx)

**Kitap (s. 226):** Sürekli rekabet üstünlüğüne sahip şirketler dönem kârlarının çok daha az bir yüzdesini sermaye harcamalarına kullanır. Örnekler (CapEx / dönem kârı): Wrigley %49, Altria %20, P&G %28, Pepsico %36, American Express %23, Coca-Cola %19, Moody's %5. Şirket tarihsel olarak dönem kârının **%50 veya azını** CapEx'e kullanıyorsa sürekli rekabet üstünlüğü aramak için iyi bir yerdir. İstikrarlı şekilde **%25'ten azını** kullanıyorsa büyük ihtimalle lehine çalışan sürekli bir rekabet üstünlüğü vardır.

**Kural:**

- CapEx / net kâr (5 yıl ort.):
  - ≤ %25 → güçlü olumlu (moat adayı)
  - %25 – %50 → olumlu
  - > %50 → olumsuz
- Oran sürekli yükseliyorsa → ek uyarı
- 5 yıl içinde en az 1 yıl net kâr negatifse → oran hesaplanmaz, **"hesaplanamaz / şüpheli"** işareti

---

## Sürekli rekabet üstünlüğü ve değerleme

### Bölüm 53 — Sürekli rekabet üstünlüğü sayesinde sonsuza dek artan getiriler

**Kitap (s. 239–240):** Moat'lı şirketler hisse-tahvil gibidir; alım fiyatına göre kazanç getirisi yıldan yıla artar.

| Şirket | Başlangıç EPS | Son EPS | Warren'ın maliyeti | Maliyet üzeri getiri (vergi sonrası / öncesi) |
|--------|---------------|---------|--------------------|------------------------------------------------|
| Moody's | 1998: $0,41 | 2007: $2,58 | $10,38 | %24 / %38 |
| American Express | 1998: $1,54 | 2008: $3,39 | $8,48 | %40 / %61 |
| Procter & Gamble | 1998: $1,28 | 2007: $3,31 | $10,15 | %32 / %49 |
| See's Candy | — | 2007 vergi öncesi kâr $82M | $25M (tüm işletme) | — / %328 |

Sürekli rekabet üstünlüğü kazançların her sene artmasına ve işletmenin temel değerinin yükselmesine neden olur. Piyasa bunu geç kabul eder ama eninde sonunda kabul eder.

### Bölüm 54 — Sürekli rekabet üstünlüğü ile değerlemenin diğer yolları

**Kitap (s. 241–243), Coca-Cola 1987 örneği:**

- Alım $6,50; vergi öncesi EPS $0,70, vergi sonrası $0,46 → başlangıç vergi öncesi getiri **%10,7**
- Önceki 10 yılın ortalama kazanç büyümesi (~%10) projeksiyon için kullanılır
- 2007 gerçekleşen vergi öncesi EPS $3,96 → maliyet üzeri vergi öncesi ~%60, vergi sonrası ~%40
- Tahvil eşdeğeri değer: vergi öncesi EPS ÷ kurumsal faiz oranı → $3,96 ÷ 0,065 ≈ $60 (piyasa $45–64)
- İçsel değer: 2007 getirisi %7 iskontoyla bugüne indirilir → ~%17 × $6,50 = $1,10 × F/K 14 ≈ $15,40
- $64 değerlemede yıllık bileşik getiri ~%12,11; satılmadıkça vergi ertelenir

**Nicel metrikler (5 yıl):**

1. EPS büyümesi (CAGR)
2. EPS yıllık artış tutarlılığı (kaç yılda arttı)
3. Vergi öncesi kazanç getirisi = vergi öncesi EPS ÷ güncel fiyat
4. Bu getirinin trendi
5. Tahvil eşdeğeri değer = vergi öncesi EPS ÷ güncel kurumsal faiz (seçim A). Kitaptaki Coca-Cola örneği bu oranı kullanır (`$3,96 ÷ 0,065`). Ölçü, yatırım yapılabilir seviye ABD şirket tahvili getirisidir (FRED `BAMLC0A0CMEY`); örnekteki %6,5 sabitlenmez.
6. Fiyat bu değerin altında mı

Skor ağırlığı **orta** (risk cezalarından daha hafif).

### Moat yorum katmanı (Bölüm 53–54)

Yalnızca nicel skoru yüksek **core** hisseler için çalışır. Yeni kural icat etmez; aşağıdaki kontrol listesini kanıtla yanıtlar:

1. **Sürekli mi?** EPS son 5 yılda gerçekten yıldan yıla mı büyüdü, yoksa 1–2 yıl mı taşıdı?
2. **Hisse-tahvil testi:** Vergi öncesi EPS / fiyat oranı, pencerenin başındaki orana göre yükseliyor mu?
3. **Moat kanıtı:** Kazanç artışı marj düşmeden mi geliyor? (Bölüm 10 ile birlikte)
4. **Piyasa gecikmesi:** Temel değer artıyor ama fiyat geride mi?
5. **Değerleme:** Vergi öncesi EPS / faiz oranı — fiyat bu bandın neresinde?
6. **Çelişki:** Bölüm 13 / 28 / 50 olumsuz ama EPS güçlü büyüyorsa → "moat var ama kitap profiline aykırı yapı" notu
7. **Sektör:** Rakiplere göre EPS büyümesi ve getiri trendi göreli okunur; yeni eşik icat edilmez

Çıktı formatı:

```
[HİSSE] — Moat yorumu (Böl. 53–54)
• 5 yıl EPS CAGR: %X (Y/5 yıl artış)
• Vergi öncesi getiri: pencere başı %A → bugün %B
• Hisse-tahvil değer: EPS/faiz = $T, piyasa $P (ucuz / adil / pahalı)
• Süreklilik: Güçlü / Orta / Zayıf — gerekçe (kitap maddeleri)
• Uyarı: Böl. 13 / 28 / 50 [var / yok]
```

---

## Kitap dışı kapı — helal eleme

Bu bölüm kitabın kuralı değildir. Kullanıcı kararıdır; ayrıntı `docs/project_decisions.md` içindedir. Buffett skorundan önce uygulanır. Geçemeyen hisse skorlanmaz.

AAOIFI Şer'i Standart 21 ve Dow Jones Islamic Market: faizli borç ve faizli nakit her biri piyasa değerinin %30'unun altında, ticari alacaklar %33'ün altında, haram gelir toplam gelirin %5'inin altında. Ana faaliyet alkol, tütün, domuz, konvansiyonel finans, silah ve savunma veya kumar/eğlence ise elenir. Kalan haram gelir hisse başına ayrılıp harcanmaz.

## Henüz işlenmemiş bölümler

7, 14, 16–27, 29–38, 40, 42–45, 48, 49, 51, 52, 55, 56 (ve 1–6). Kullanıcı metni paylaştıkça bu dosyaya eklenir. Kitap net eşik vermiyorsa kullanıcıya tek soru sorulur.
