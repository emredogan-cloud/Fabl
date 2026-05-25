# Fabl

**Küçük Masallar** · *İlk Defter · Birinci Derleme*

> *"Her küçük hikâye de bir şey bilir; yeter ki acele edilmesin."*

Bağımsız okunabilen kısa fabller derlemesi. Her metin tek başına tamamdır: tek bir dramatik eylem, tek bir çekirdek fikir, sembolik ama açık. Ders dayatmaz; bir gözlem bırakır. Aesop ve Beydeba geleneğine bakar, ama taklit etmez.

Motor, **Tuzun Hafızası** dijital kodeksinden devralınmıştır; biçim disiplini (sayfa çevirme, dizgi, okuma deneyimi, performans) korunmuş, yalnızca kimlik — renk, atmosfer, kapak, üst-veri — değiştirilmiştir.

---

## Yapısı

- **Tür:** Kısa fabl derlemesi (roman değil)
- **Çerçeve:** Hafif — üç tematik küme yalnızca düzen verir, süreklilik yükü getirmez
  - **I · Kendilik** — kişinin kendisiyle ilişkisi
  - **II · Birlikte** — birlikte yaşamak
  - **III · Yapmak ve Bırakmak** — el, ustalık, vazgeçiş
- **Ölçek:** Her fabl ~500–900 kelime (2–3 sayfa)
- **Şu anki üretim:** 3 fabl yazıldı (her kümeden bir tane)

### Yazılan fabller

| # | Fabl | Küme | Çekirdek |
|---|------|------|----------|
| I | Yankıyı Besleyen Çoban | Kendilik | Sevdiğimiz yoldaş bazen yalnızca kendi sesimizdir |
| II | İki Saatin Kasabası | Birlikte | Uzlaşma, haklı çıkmak değil bir paya razı olmaktır |
| III | Düğümü Çözmeyen Denizci | Yapmak ve Bırakmak | Ustalık, neyi olduğu gibi bırakacağını bilmektir |

---

## Dosya Yapısı

```
Fabl/
├── index.html                — Dijital kitap arayüzü
├── content/
│   ├── novel-data.js         — Kitap meta'sı, üç küme tanımı
│   ├── fable-01.js           — Yankıyı Besleyen Çoban
│   ├── fable-02.js           — İki Saatin Kasabası
│   ├── fable-03.js           — Düğümü Çözmeyen Denizci
│   └── finalize.js           — Küme sıralayıcı
├── scripts/
│   ├── storage.js            — LocalStorage (ilerleme, izler, tema)
│   ├── book.js               — Sayfa motoru (paginasyon, 3D çevirme)
│   └── app.js                — Üst denetleyici
├── styles/
│   ├── themes.css            — Sabah / Gündüz / Alaca temaları
│   ├── main.css              — Ana stil (değişmedi — format LOCK)
│   └── animations.css        — Hareket katmanı (değişmedi)
└── assets/
    └── cover.svg             — Kapak görseli
```

## Kullanım

`index.html` dosyasını bir tarayıcıda aç. Yerel sunucu gerekmez — saf vanilla JS, build adımı yok. Vercel'e statik kök olarak deploy edilir (yapılandırma gerektirmez).

### Klavye Kısayolları

| Tuş | Eylem |
|-----|-------|
| `←` / `→` | Sayfa çevir |
| `Space` / `PageDown` | İleri |
| `Home` / `End` | Başa / Sona |
| `F` | Fihrist |
| `K` | Sayfaya iz koy |
| `İ` | İzleri aç |
| `T` | Tema değiştir |
| `Y` | Yazı boyutu |
| `E` | Tam ekran |
| `P` | Performans modu |
| `Esc` | Kapı kapat / Tam ekran çık |

### Temalar — "Sabah Mavisi" ailesi

- **Sabah** — Varsayılan. Gün ağarmadan önceki mavi saat; kâğıt loşlukta parıldar.
- **Gündüz** — Aydınlık okuma; açık mavi-gri ve krem, ferah.
- **Alaca** — Akşam okuması; lacivert dinginliği, parşömen sayfa.

## Yeni Fabl Eklemek

1. `content/fable-04.js` oluştur; `window.FABL.entries.push({ id, title, subtitle, category, themes, content: [...] })`.
   - `category`: `"kendilik"`, `"birlikte"` veya `"yapmak"`.
   - `content`: paragraf dizgileri; sahne kırılımı için `{ style: "hr" }`, vurgulu tek satır için `{ style: "quote", text: "…" }`.
2. `index.html` içinde `finalize.js`'ten **önce** `<script src="content/fable-04.js"></script>` ekle.
3. Hepsi bu — paginasyon, fihrist ve folio otomatik.

## Lisans

Çalışma henüz yayım aşamasında değildir. Hiçbir parçası izinsiz dağıtılamaz.
