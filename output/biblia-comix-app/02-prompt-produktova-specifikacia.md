# PROMPT – Produktová špecifikácia aplikácie „Biblia v komikse“

> Použitie: tento prompt je určený pre vývojársky tím alebo AI nástroj (Claude Code, Cursor, Lovable a pod.). Skopíruj celý text pod čiarou. Prílohou k nemu je dokument `01-vizualny-styl.md`, na ktorý sa prompt odvoláva.

---

## ROLA

Si senior produktový architekt a vedúci vývojár mobilných aplikácií s hlbokou skúsenosťou s obsahovými (čítacími) aplikáciami, lokalizáciou, detskými aplikáciami a ich reguláciou (GDPR, GDPR-K, COPPA, App Store / Google Play pravidlá pre deti). Tvojou úlohou je navrhnúť a následne postaviť natívne pôsobiacu mobilnú aplikáciu pre iOS a Android podľa špecifikácie nižšie. Pracuj systematicky: najprv architektúra a dátový model, potom MVP, až potom rozšírenia. Pri každom nejasnom bode urob rozhodnutie, zdôvodni ho a pokračuj.

## 1. VÍZIA PRODUKTU

Aplikácia **„Biblia v komikse“** (pracovný názov) sprístupňuje jednotlivé príbehy Starého a Nového zákona vo forme komiksu. Každý príbeh existuje v **troch úrovniach** podľa veku čitateľa – pre malé deti, teenagerov a dospelých – a vo **viacerých jazykových mutáciách**. Všetky tri úrovne zdieľajú jeden vizuálny svet a tie isté postavy, líšia sa kresliarskou „intenzitou“, dĺžkou textu, hĺbkou a spôsobom zobrazenia citlivých tém.

Konfesionálne zameranie je **ekumenické a neutrálne**: aplikácia je verná biblickému textu, nepresadzuje výklad žiadnej denominácie a umožňuje užívateľovi vybrať kánon (protestantský 66 kníh / katolícky s deuterokánonickými knihami).

Hodnotová propozícia:
- Rodina s jednou aplikáciou pre všetky generácie (rodičovský účet, detské profily).
- Čitateľ „rastie“ s aplikáciou – ten istý príbeh si prečíta v 6, 14 aj 30 rokoch, vždy v inej hĺbke.
- Vysoká výtvarná kvalita, nie lacná ilustrácia; historická a kultúrna vernosť.

## 2. CIEĽOVÉ SKUPINY A ÚROVNE

| Úroveň | Vek | Čitateľ | Charakter obsahu |
|---|---|---|---|
| L1 – Deti | 4–8 | číta rodič alebo audio, dieťa počúva/listuje | 1–3 panely na obrazovku, 1–2 vety, audio rozprávanie so zvýrazňovaním slov, zvierací sprievodca, humor, žiadne explicitné násilie |
| L2 – Teenageri | 11–17 | samostatný čitateľ | 4–6 panelov na stranu, plné dialógy, dramatické kompozície, otázky na zamyslenie, slovníček pojmov |
| L3 – Dospelí | 18+ | samostatný čitateľ | grafický román, citácie biblického textu, poznámky s historickým a jazykovým kontextom, krížové odkazy SZ/NZ |

Vek 9–10 rokov: profil si volí rodič medzi L1 a L2 (predvolene L2 s rodičovským filtrom „zjemnené scény“).

## 3. OBSAHOVÁ ARCHITEKTÚRA

### 3.1 Hierarchia
`Zákon (SZ / NZ) → Zbierka (napr. Patriarchovia, Exodus, Králi, Proroci, Život Ježiša, Podobenstvá, Skutky) → Príbeh → Kapitola (voliteľne) → Strana → Panel`

Každý **Príbeh** má:
- `id`, `canonical_order`, `testament`, `collection`, biblické referencie (kniha, kapitola, verše),
- tri **Verzie** (L1, L2, L3), každá so svojím scenárom a sadou strán/panelov,
- pre každú verziu N **lokalizácií** (text bublín, captions, onomatopoje, audio),
- metadáta: témy (tagy), postavy, miesta, odhadovaný čas čítania, úroveň citlivosti, odporúčaný vek,
- doplnky podľa úrovne: kvíz (L1 obrázkový, L2 textový), otázky na zamyslenie (L2/L3), poznámky (L3), slovníček (L2/L3).

### 3.2 Počiatočný katalóg príbehov (MVP = označené ★)

**Starý zákon:** Stvorenie ★, Adam a Eva ★, Kain a Ábel, Noe a potopa ★, Babylonská veža, Abrahám a Izák ★, Jakub a Ezau, Jozef a jeho bratia ★, Mojžiš – narodenie a horiaci ker ★, Egyptské rany a Exodus ★, Desatoro na Sinaji, Jozue a Jericho, Gedeon, Samson, Rút, Samuel, Dávid a Goliáš ★, Dávid a Šaul, Šalamún, Eliáš na Karmeli, Elizeus, Jonáš ★, Daniel – ohnivá pec a jama levov ★, Ester, Jób, Nehemiáš. Deuterokánonické (voliteľný kánon): Tobiáš, Judita, Makabejci.

**Nový zákon:** Zvestovanie a Narodenie ★, Mudrci a útek do Egypta, Ježiš v chráme, Krst a pokušenie, Povolanie učeníkov ★, Svadba v Káne, Kázeň na vrchu, Podobenstvá: Milosrdný Samaritán ★, Márnotratný syn ★, Rozsievač, Stratená ovca; Zázraky: Utíšenie búrky ★, Nasýtenie zástupu, Uzdravenia, Lazár; Zachej, Premenenie, Vstup do Jeruzalema, Posledná večera ★, Getsemani, Ukrižovanie ★, Zmŕtvychvstanie ★, Emauzy, Nanebovstúpenie, Turíce, Štefan, Pavlovo obrátenie, Pavlove cesty, Zjavenie (len L3, symbolicky).

MVP: 20 príbehov × 3 úrovne × 6 jazykov.

### 3.3 Politika citlivého obsahu
Nič sa nezamlčuje, mení sa spôsob zobrazenia. Riadi sa tabuľkou v `01-vizualny-styl.md`, kap. 1.6. Každý príbeh má `sensitivity_level` (0–3) a každá verzia prechádza kontrolou pred publikovaním. Rodič môže v detskom profile zapnúť filter, ktorý skryje príbehy s úrovňou citlivosti nad zvolený prah.

## 4. VIZUÁLNY ŠTÝL

Záväzný dokument: `01-vizualny-styl.md` („Svetlo a línia“). Kľúčové body pre implementáciu:
- Jeden štýl, tri intenzity (deti „Mäkké svetlo“, teenageri „Moderná ligne claire“, dospelí „Tuš a akvarel“). Všetky tri sú svetlé a čisté; žiadna úroveň nie je pochmúrna. Vizuálna identita aplikácie (ikona, obaly, marketing) používa jazyk plochej grafiky podľa kap. 4.1 vizuálneho štýlu.
- Paleta „Pôda a nebo“ a design tokeny z dokumentu sa použijú aj v UI (pergamenová svetlá téma predvolená, atramentová tmavá voliteľná).
- **Text sa nikdy nevypaľuje do obrázka.** Panel = obrazové vrstvy + vektorová textová vrstva (bubliny, captions, onomatopoje) s pozíciou, tvarom a maximálnym rozmerom. Lokalizácia mení len textovú vrstvu.
- Panely sa dodávajú ako samostatné assety (2048 px na dlhšej strane, formát 4:5), strana je definovaná layoutom panelov, nie jedným obrázkom.
- Dva režimy čítania: **guided view** (panel po paneli, swipe, jemná paralaxa) a **page view** (celá strana, pinch-zoom).

## 5. LOKALIZÁCIA

### 5.1 Jazyky prvej verzie
Slovenčina (sk), čeština (cs), angličtina (en), nemčina (de), poľština (pl), maďarčina (hu). Zdrojový jazyk scenárov: slovenčina, pivot pre prekladateľov: angličtina.

### 5.2 Požiadavky
- Architektúra pripravená na ľubovoľný počet jazykov vrátane RTL (hebrejčina, arabčina) a cyriliky – žiadne pevné šírky, žiadne texty v obrázkoch, všetky písma s Latin Extended-A.
- Jazyk obsahu je nezávislý od jazyka UI (dieťa môže čítať po anglicky s UI v slovenčine – jazykové učenie).
- Automatické prispôsobenie bublín dĺžke textu (nemčina a maďarčina +25–35 % oproti angličtine); QA nástroj v CMS, ktorý upozorní na pretečenie.
- Onomatopoje sú lokalizovaný obsah (každý jazyk má vlastné).
- Audio rozprávanie pre každý jazyk a úroveň (L1 povinne ľudský hlas, L2/L3 môže byť kvalitné neurónové TTS s ľudskou korektúrou), s časovými značkami na zvýrazňovanie slov.
- Biblické citácie (L3 a referencie): každý jazyk používa konkrétny preklad; primárne voľné preklady, viď 9.3. Dátový model musí umožniť viac prekladov na jazyk a výmenu prekladu bez zmeny komiksu.

## 6. FUNKCIE

### 6.1 Spoločné
- Knižnica príbehov s filtrom podľa zákona, zbierky, témy, postavy, času čítania; časová os biblických dejín; mapa miest.
- Čítačka s guided/page view, záložky, posledná pozícia, nastavenie veľkosti textu, režim „ľahko čitateľné písmo“, vysoký kontrast.
- Audio rozprávanie so zvýrazňovaním, tlačidlo „prečítať verš v Biblii“ (odkaz na plný biblický text v zvolenom preklade).
- Offline balíčky (stiahnutie príbehu alebo celej zbierky), správa úložiska.
- Vyhľadávanie (názvy, postavy, biblické referencie).
- Prepínač úrovne priamo v čítačke (ak profil dovoľuje): tá istá strana sa zobrazí v inej úrovni – kľúčová „wow“ funkcia.
- Čitateľské plány (napr. „Advent: 24 príbehov“, „Veľký týždeň“, „Život Dávida“), príbeh dňa, pripomienky (opt-in).

### 6.2 Podľa úrovne
- **L1:** veľké dotykové plochy, žiadne textové menu bez ikon, obrázkový kvíz po príbehu, nálepky za dočítanie, režim „číta rodič“ (vypne audio, zobrazí text pre rodiča väčším písmom), rodičovská brána pre všetko mimo čítania.
- **L2:** otázky na zamyslenie, slovníček, zbieranie „postáv“ do vlastného albumu, zdieľanie panelu ako obrázka (s watermarkom, bez osobných dát), voliteľný denník odpovedí (lokálne, šifrované).
- **L3:** poznámky pod čiarou, hebrejské/grécke pojmy, krížové odkazy SZ/NZ, porovnanie prekladov, export poznámok.

### 6.3 Účty a profily
- Jeden účet (dospelý), až 6 profilov; detský profil bez e-mailu a bez zberu osobných údajov; prihlásenie Apple / Google / e-mail; voliteľný anonymný režim bez účtu (lokálne dáta).
- Rodičovský panel: úroveň a filter citlivosti pre každý profil, časové limity, prehľad prečítaného.

## 7. TECHNICKÉ POŽIADAVKY

- **Platformy:** iOS 16+, Android 9+ (API 28), telefón aj tablet. Odporúčaný framework: **Flutter** (vlastný rendering panelov, textovej vrstvy a animácií je konzistentný na oboch platformách); alternatíva React Native + Skia, ak tím preferuje. Rozhodnutie zdôvodni.
- **Obsahový backend:** headless CMS (napr. Strapi, Sanity alebo vlastné) s modelom z kap. 3; verzovanie obsahu; workflow stavov (návrh → recenzia teologická → recenzia jazyková → publikované); viacjazyčný editor bublín s náhľadom na panel.
- **Distribúcia obsahu:** CDN, balíčky podpísané a verzované; aplikácia sťahuje delta aktualizácie; offline-first lokálna databáza (SQLite/Drift alebo Realm).
- **Formát panelu:** obrazové vrstvy (WebP/AVIF, viac rozlíšení), textová vrstva ako JSON (pozícia, tvar bubliny, typ: speech/thought/caption/sfx, text per jazyk, štýl), audio (AAC/Opus) s časovými značkami.
- **Analytika:** len agregovaná a anonymizovaná; v detských profiloch žiadne sledovanie tretích strán, žiadne reklamné SDK.
- **Výkon:** otvorenie príbehu < 1 s z cache, plynulý swipe 60 fps, prefetch ďalších panelov.
- **Prístupnosť:** VoiceOver/TalkBack popisy panelov (alt-text je súčasť obsahu v CMS, lokalizovaný), dynamická veľkosť písma, kontrast WCAG AA, redukcia pohybu.
- **Bezpečnosť:** rodičovská brána (matematická úloha / biometria), šifrované lokálne dáta, žiadne externé odkazy v detskom režime.

## 8. MONETIZÁCIA

- Freemium: 5 príbehov zdarma vo všetkých úrovniach a jazykoch; ďalší obsah cez predplatné (mesačné / ročné / rodinné pre 6 profilov) alebo jednorazový nákup zbierok.
- **Žiadne reklamy** nikde v aplikácii; v detskom režime žiadne nákupné výzvy (rodičovská brána).
- Inštitucionálne licencie (školy, farnosti, zbory) – hromadné kódy, neskoršia fáza.
- Natívne platobné systémy (StoreKit 2, Google Play Billing), správa predplatného cez RevenueCat alebo ekvivalent.

## 9. PRÁVNE A COMPLIANCE POŽIADAVKY

### 9.1 Ochrana detí
GDPR čl. 8 (vek súhlasu podľa krajiny: SK 16, CZ 15, DE 16, PL 16, HU 16, UK/US pravidlá pri expanzii), COPPA pre US, Apple Kids Category a Google Families Policy. Dôsledky: žiadne osobné údaje detí, žiadne reklamné SDK, rodičovská brána, dátová minimalizácia, DPIA pred spustením.

### 9.2 Autorské práva k obsahu
Všetky ilustrácie, scenáre a audio sú originálne diela s prevedenými majetkovými právami na prevádzkovateľa (zmluvy s ilustrátormi, scenáristami, hercami). Ak sa pri tvorbe použijú generatívne nástroje, platí interná politika: AI len na skice a referencie, finálne dielo ľudský autor (dôvod: autorskoprávna ochrana a požiadavky obchodov).

### 9.3 Biblické preklady – autorské práva
Text Písma ako taký je voľný. Chránené sú však **moderné preklady** ako autorské diela prekladateľov (ochrana 70 rokov po smrti autora, prípadne práva drží biblická spoločnosť). Zásada: **primárne používať voľné preklady**, chránené len tam, kde to držiteľ práv výslovne dovoľuje bez zmluvy.

| Jazyk | Voľný preklad (public domain) | Chránený preklad (len s povolením) |
|---|---|---|
| sk | Kamaldulská biblia (18. stor., archaická); Roháčkov preklad (autor † 1962, voľný až od r. 2033) | Slovenský ekumenický preklad (SBS), Katolícky preklad (SSV), Botekov preklad |
| cs | Bible kralická (1613) | Český ekumenický překlad, Bible21, Jeruzalémská bible |
| en | King James Version (mimo UK), World English Bible, ASV | NIV, ESV, NRSV |
| de | Lutherbibel 1912, Elberfelder 1905 | Lutherbibel 2017, Einheitsübersetzung |
| pl | Biblia Gdańska (1632), Biblia Wujka (1599) | Biblia Tysiąclecia, Biblia Warszawska |
| hu | Károli (1590, revízia 1908) | RÚF 2014, Szent István Társulat |

Praktické dôsledky pre aplikáciu:
- Dialógy a narácia v bublinách sú **vlastný autorský text** (parafráza), nie citát – tam nevzniká žiadny licenčný problém.
- Priame citáty (L3, odkazy na plný text) sa predvolene berú z voľného prekladu daného jazyka. Pre slovenčinu, kde moderný voľný preklad neexistuje, sa počíta s písomným súhlasom Slovenskej biblickej spoločnosti alebo s vlastným prekladom kľúčových veršov.
- Väčšina biblických spoločností dovoľuje citovať bez zmluvy do určitého rozsahu (typicky do 500 veršov a menej než 25 % diela, s uvedením zdroja). Pri odkaze na plný text je potrebná zmluva alebo prelinkovanie na oficiálnu stránku držiteľa práv.
- Dátový model musí umožniť viac prekladov na jazyk a ich výmenu konfiguráciou.

### 9.4 Obsahová rada
Ekumenický poradný zbor (zástupcovia aspoň katolíckej, evanjelickej a pravoslávnej tradície plus biblista a detský psychológ) schvaľuje scenáre a politiku citlivosti. Proces je zdokumentovaný v CMS.

## 10. OČAKÁVANÉ VÝSTUPY (v tomto poradí)

1. **Architektonický návrh:** diagram systému (aplikácia, CMS, CDN, auth, platby), výber frameworku so zdôvodnením, dátový model (ERD) pre obsah, profily a lokalizáciu.
2. **Špecifikácia formátu panelu/strany** (JSON schéma textovej vrstvy a layoutu strany) a návrh CMS editora bublín.
3. **Mapa obrazoviek a user-flow** pre tri úrovne (onboarding, výber profilu, knižnica, čítačka guided/page, kvíz, rodičovský panel, predplatné), wireframy.
4. **Design systém** odvodený z `01-vizualny-styl.md`: tokeny farieb, typografia, komponenty, svetlá/tmavá téma, ikony.
5. **Plán MVP** (20 príbehov × 3 úrovne × 6 jazykov): míľniky, odhad prácnosti, riziká, čo sa odloží do v1.1 (inštitucionálne licencie, denník, časová os).
6. **Implementácia MVP** podľa plánu, s testami (unit, widget, integračné pre offline a lokalizáciu), CI/CD, príprava na App Store Connect a Google Play Console vrátane detských kategórií.
7. **Produkčná príručka pre obsah:** ako sa pripravuje príbeh od scenára cez vrstvy po lokalizáciu a QA.

## 11. KRITÉRIÁ PRIJATIA

- Ten istý príbeh sa dá otvoriť v L1, L2 a L3 a prepnúť úroveň priamo v čítačke bez straty pozície v deji.
- Prepnutie jazyka obsahu zmení všetok text v bublinách, captions, onomatopojach a audio bez prekreslenia panelov; žiadna bublina nepretečie v nemčine ani maďarčine.
- Detský profil nevyžaduje a neukladá žiadne osobné údaje; audit SDK nenájde reklamné ani sledovacie knižnice.
- Stiahnutá zbierka funguje kompletne offline vrátane audia a kvízov.
- Čítačka drží 60 fps pri swipe na strednom zariadení (napr. 4 roky starý Android stred. triedy).
- VoiceOver/TalkBack prečíta každý panel zmysluplne (alt-text) v jazyku obsahu.
- Preklad biblického textu je v dátach vymeniteľný konfiguráciou, nie zmenou kódu.

## 12. OBMEDZENIA A ZÁSADY

- Neutralita: žiadne denominačné výkladové poznámky, žiadne modlitby špecifické pre jednu tradíciu, žiadne politické odkazy.
- Boh Otec sa nikdy nezobrazuje ako postava (viď vizuálny štýl).
- Žiadny gamifikačný tlak (streaky s trestom, FOMO notifikácie); odmeny v L1 sú jemné a nesúťažné.
- Žiadne reklamy, žiadny predaj dát, žiadne externé odkazy v detskom režime.
- Všetky rozhodnutia, ktoré v tomto zadaní nie sú určené, urob sám, zdôvodni ich v krátkej poznámke a pokračuj; nezastavuj prácu kvôli otázkam, ktoré sa dajú rozumne rozhodnúť.

---

## PRÍLOHA A – Art-direction prompty pre ilustrátorov / generatívne nástroje (skice a referencie)

Schválené 4. 10. 2026 na základe ukážok scény Utíšenie búrky (viď `01-vizualny-styl.md`, kap. 7).

Spoločný základ (pripoj ku každému): *„European clear-line comic art, bright daylight feel, warm single light source from above, earthy palette of Jerusalem stone, terracotta, olive green, turquoise water and clear Galilean blue, gold used only for divine presence, historically accurate Near-Eastern setting, Semitic features, Jesus with dark hair, dark eyes, olive skin and a simple first-century robe, no text in image, portrait 4:5, layered composition.“*

- **L1 Deti – „Mäkké svetlo“:** *„…children's picture-book style, soft rounded shapes, 1:3 head-to-body proportions, big expressive eyes, thin warm-brown outline like a pencil crayon, pastel lightened palette, flat colors with one soft shadow step, bright and friendly, a small animal companion in the scene, no violence.“*
- **L2 Teenageri – „Moderná ligne claire“:** *„…modern ligne claire, clean confident black outline of even weight, flat vivid colors with minimal cel shading, bright daylight palette, dynamic diagonal composition, stylized 1:6 proportions, energetic and cheerful like a contemporary animated adventure film, expressive faces, in the spirit of Asterix, Tintin and Blake and Mortimer.“*
- **L3 Dospelí – „Tuš a akvarel“:** *„…elegant ink-and-watercolor graphic novel, fine expressive ink line with varied weight, loose luminous watercolor washes that leave white paper breathing, soft granulating pigment texture, realistic 1:7.5 proportions with individual weathered faces, contemplative but hopeful, lots of light and space, sophisticated European bande dessinée feel in the spirit of Sempé and Emmanuel Guibert.“*
- **Značka / identita (nie komiks):** *„…bold flat graphic illustration like a modern screen-printed poster, five flat colors (cream, terracotta, olive, deep blue, one pure gold for light), subtle risograph grain, no outlines, confident simple shapes, mid-century sensibility in the spirit of Tom Haugomat and Malika Favre.“*

Negatívne pokyny pre všetky úrovne: *„no dark or gloomy mood, no chiaroscuro, no heavy black shadows, no gritty texture, no blond Jesus, no halos except Transfiguration/Resurrection, no medieval European castles or knights, no cartoon wings on angels, no anthropomorphic God the Father, no text or lettering, no watermark.“*
