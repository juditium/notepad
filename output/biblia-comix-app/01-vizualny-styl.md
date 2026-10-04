# Biblia v komikse – vizuálny štýl comixovej predlohy

Pracovný názov štýlu: **„Svetlo a línia“**
Princíp: jeden rozpoznateľný rukopis značky, tri „intenzity“ podľa vekovej úrovne. Čitateľ, ktorý vyrastie z detskej úrovne, spozná tie isté postavy a svet aj v úrovni pre teenagerov a dospelých.

---

## 1. Spoločná DNA (platí pre všetky tri úrovne)

### 1.1 Kresba
- **Kontúra:** uzavretá, čistá línia v tradícii európskej *ligne claire* (Hergé, Uderzo), ale s premenlivou hrúbkou ťahu (štetcová linka). Hrúbka kontúry rastie s úrovňou: deti tenká a mäkká, dospelí hrubšia, lámaná.
- **Svetlo:** jednotný zdroj „teplého svetla zhora“. Je to vizuálny motív celej série – prítomnosť Boha sa nikdy nezobrazuje ako postava, ale ako svetlo, zlatý lesk alebo zlaté písmo.
- **Boh Otec:** nikdy antropomorfne. Hlas Boha = zlaté písmo bez bubliny, s jemnou žiarou okolo. Duch Svätý = svetlo, vietor, holubica (podľa textu). Anjeli = ľudské postavy so svetelnou aurou, bez gýčových krídel; krídla len tam, kde ich text výslovne uvádza (cherubíni, serafíni).
- **Ježiš:** jediná postava s pevne definovaným dizajnom naprieč všetkými úrovňami (tzv. *character bible*). Semitské črty, tmavé vlasy a oči, olivová pleť, prostý odev prvého storočia. Žiadny blond ani modrooký Ježiš. Rozpoznateľný siluetou, nie svätožiarou (svätožiara sa používa len ako svetelný efekt pri Premenení a po Zmŕtvychvstaní).

### 1.2 Farebná paleta „Pôda a nebo“
Základ je zemitý a teplý (Judská púšť, kameň Jeruzalema, olivové háje), nebo a voda sú hlboké modré, zlato je výhradný akcent pre posvätno.

| Rola | Názov | HEX | Použitie |
|---|---|---|---|
| Primárna | Jeruzalemský kameň | `#D9B98A` | pozadia, architektúra |
| Primárna | Terakota | `#B5553A` | odevy, akcenty, zem |
| Primárna | Olivová | `#6F7B3E` | vegetácia, odevy |
| Sekundárna | Hlboká galilejská modrá | `#1F3A5F` | nebo, voda, noc |
| Sekundárna | Púštna okrová | `#C9893B` | piesok, svetlo podvečera |
| Akcent | Posvätné zlato | `#E6B84A` | Božia prítomnosť, hlas Boha, zázraky |
| Neutrál | Atramentová | `#1A1714` | kontúra, text |
| Neutrál | Pergamen | `#F6EEDD` | bubliny, pozadie UI |
| Akcent (len dospelí) | Krvavá purpurová | `#6B1F2A` | utrpenie, obeť, Apokalypsa |

Pravidlo: zlato nikdy ako dekorácia, vždy ako význam. Ak je na paneli zlato, je tam Boh.

### 1.3 Typografia a lettering
Všetky písma musia pokrývať **Latin Extended-A** (slovenské ď ť ľ ĺ ŕ ô ä, české ě ř ů, poľské ą ę ł ń ś ź ż, maďarské ő ű) a byť pripravené na neskoršie rozšírenie (cyrilika, hebrejčina/arabčina RTL).

| Použitie | Odporúčané písmo | Poznámka |
|---|---|---|
| Názvy príbehov (display) | vlastný lettering na mieru alebo *Fraunces* / *Alegreya SC* | ručne kreslený charakter, variabilné |
| Bubliny – deti | *Nunito* (Bold/ExtraBold) | zaoblené, veľmi čitateľné, nízkoprahové pre začínajúcich čitateľov |
| Bubliny – teenageri | *Barlow Semi Condensed* | dynamické, komiksové, úsporné pri dlhšom texte |
| Bubliny – dospelí | *Literata* alebo *Source Serif 4* | knižný, grafický román |
| Narácia (captions) | rovnaké ako bubliny, kurzíva | |
| Prístupnosť | *Atkinson Hyperlegible* ako voliteľný „ľahko čitateľný“ režim | pre dyslexiu a slabozrakých |

Zásadné technické pravidlo: **text sa nikdy nevypaľuje do obrázka.** Bubliny a captions sú samostatná vektorová/textová vrstva nad ilustráciou, s automatickým prispôsobením veľkosti bubliny textu (nemčina a maďarčina sú o 25–35 % dlhšie než angličtina). Zvukové efekty (onomatopoje) sú tiež lokalizovateľná vrstva – sú v každom jazyku iné.

### 1.4 Historická a kultúrna vernosť
- Odev, architektúra, nástroje, krajina a zvieratá zodpovedajú Blízkemu východu príslušnej doby (doba bronzová pre patriarchov, doba železná pre kráľov, rímska Judea pre Nový zákon). Žiadne stredoeurópske stredoveké hrady, žiadni rytieri.
- Pre každú epochu vzniká referenčný „world bible“ (mapa, panoráma Jeruzalema, Galilejské jazero, Sinaj, Babylon, Egypt).
- Postavy sú etnicky verné regiónu (semitské, egyptské, núbijské, rímske, grécke typy).

### 1.5 Formát a kompozícia pre mobil
- Natívny formát panelu: **portrét 4:5** (telefón), s bezpečnou zónou pre tablet 3:4.
- Dva režimy čítania, pre ktoré sa predloha kreslí od začiatku:
  1. **Guided view:** panel po paneli, swipe, s možnosťou jemnej animácie (paralaxa, pohyb kamery) – pre deti a teenagerov predvolený.
  2. **Page view:** celá dvojstrana s tradičnou mriežkou panelov – pre dospelých predvolený, pre ostatných voliteľný.
- Každá strana sa teda tvorí ako sada samostatných panelov vo vysokom rozlíšení, ktoré sa skladajú do strany (nie naopak).
- Export panelov: 2048 px na dlhšej strane, vrstvy: pozadie / postavy / efekty / text.

### 1.6 Politika citlivého obsahu (spoločný rámec)
Biblia obsahuje násilie, smrť, sexualitu a utrpenie. Pravidlo: **nič sa nezamlčuje, mení sa iba spôsob zobrazenia.**

| Téma | Deti | Teenageri | Dospelí |
|---|---|---|---|
| Násilie, smrť | mimo panel, symbolicky (tieň, zlomený meč) | naznačené, bez krvi v detaile | zobrazené s vážnosťou, nikdy samoúčelne (vzor: Caravaggio, nie akčný film) |
| Ukrižovanie | kríž na diaľku, dôraz na smútok a nádej | stredný záber, rany náznakovo | plný záber, chiaroscuro, bolesť aj dôstojnosť |
| Sexualita (Dávid a Betsabe, Pieseň piesní) | príbeh vynechaný alebo zredukovaný | eticky zarámcovaný, bez nahoty | zobrazené s rešpektom, bez explicitnosti |
| Démoni, Apokalypsa | nezobrazené | symbolicky | plná symbolická vizualita, žiadny horor |

---

## 2. Úroveň 1 – Deti (4–8 rokov): „Mäkké svetlo“

- **Proporcie:** hlava : telo = 1 : 3. Veľké oči, zaoblené tvary, krátke končatiny. Žiadne ostré rohy, ani na architektúre.
- **Kontúra:** tenká, mäkká, hnedo-atramentová (nie čierna), pôsobí ako pastelka.
- **Farby:** paleta „Pôda a nebo“ zosvetlená o 20–30 %, vyššia sýtosť, pastelové tiene. Jednoduché ploché farby, max. jeden stupeň tieňa.
- **Svetlo:** celý panel je svetlý, noc je tmavomodrá, nikdy čierna.
- **Kompozícia:** 1 až 3 panely na obrazovku, jedna myšlienka na panel, postava vždy čitateľná v silueta teste.
- **Text:** max. 1–2 krátke vety na panel, veľké písmo, kľúčové slovo zvýraznené farbou. Vždy s audio rozprávaním a zvýrazňovaním čítaného slova.
- **Postavy navyše:** v každom príbehu je „sprievodca“ – zvieratko alebo malé dieťa z doby príbehu (napr. baránok pri Dávidovi, holubica pri Noemovi), ktorý kladie otázky a odľahčuje. Nikdy nenahrádza biblickú postavu, len sprevádza.
- **Emócie:** prehnane čitateľné, humor dovolený (zvieratá v arche, Jonáš vo veľrybe).
- **Referencie štýlu:** detské knihy Olivera Jeffersa, animované seriály „Puffin Rock“, „Hilda“ (len mäkkosť tvarov), biblické ilustrácie Kees de Kort (jednoduchosť).

## 3. Úroveň 2 – Teenageri (11–17 rokov): „Dynamická línia“

- **Proporcie:** 1 : 6 až 1 : 7, realistické, ale štylizované. Výrazné gestá a mimika.
- **Kontúra:** stredná, s premenlivou hrúbkou, čierny atrament. Rýchlostné a dôrazové čiary dovolené.
- **Farby:** plná paleta „Pôda a nebo“, dvojstupňové cel-shading tiene, dramatické farebné kľúče scény (napr. oranžovo-fialová pri horiacom kríku, studená modrá pri Getsemani).
- **Kompozícia:** 4–6 panelov na stranu, dynamické uhly (podhľad, nadhľad, diagonály), občasný celostranový „splash“ pri vrchole príbehu.
- **Text:** plné dialógy, narácia v captions, dĺžka cca 40–60 slov na stranu. Na konci príbehu „Otázky na zamyslenie“ a slovníček pojmov.
- **Tematický dôraz:** identita, odvaha, pochybnosť, priateľstvo, zlyhanie a druhá šanca (Jozef, Dávid, Peter, Pavol, Ester, Rút). Ježiš ako niekto, kto sa pýta a provokuje, nie len poučuje.
- **Referencie štýlu:** „Spider-Man: Into the Spider-Verse“ (energia, nie koláž), európske komiksy „Blacksad“ (farebné kľúče scény), webtoonová čitateľnosť na mobile, ale v klasickej panelovej mriežke.

## 4. Úroveň 3 – Dospelí (18+): „Grafický román“

- **Proporcie:** realistické 1 : 7,5, individuálne tváre s vekom a históriou.
- **Kontúra:** hrubšia, lámaná, štetcová, miestami rozpustená do šrafúry a atramentového laveru. Textúra papiera a pigmentu.
- **Farby:** paleta „Pôda a nebo“ stlmená, nižšia sýtosť, väčší rozsah tmavých tónov. Chiaroscuro – svetlo vychádza z jediného zdroja v scéne. Zlatý akcent zostáva jediným „čistým“ pigmentom na strane. Pridaná krvavá purpurová.
- **Kompozícia:** voľná mriežka, veľké tiché panely bez textu, dvojstranové splashe (Stvorenie, Exodus cez more, Ukrižovanie, Zmŕtvychvstanie). Odvaha k pomalému tempu.
- **Text:** úryvky z pôvodného biblického textu v captions (licencovaný preklad), dialógy literárne, nie modernizované. Poznámky pod čiarou s historickým a jazykovým kontextom (hebrejské a grécke pojmy), odkazy medzi Starým a Novým zákonom.
- **Tematický dôraz:** utrpenie, spravodlivosť, exil, viera v tme (Jób, Žalmy, Jeremiáš, Kazateľ, Pašie, Zjavenie).
- **Referencie štýlu:** „Maus“ (vážnosť), „Habibi“ Craiga Thompsona (kaligrafia a ornament), „Blankets“, maľby Rembrandta a Caravaggia (svetlo), ikonopis (statická dôstojnosť vo vrcholných scénach).

---

## 5. Identita aplikácie (UI)

- **Ikona:** otvorená kniha, ktorej strany tvoria rečovú bublinu; posvätné zlato na hlbokej galilejskej modrej.
- **UI téma:** pergamenová svetlá téma (predvolená pre deti a teenagerov), atramentová tmavá téma (predvolená pre dospelých). UI je zámerne tiché, aby neprekričalo komiks.
- **Prepínač úrovne:** vizuálne ako tri „štetce“ s rastúcou hrúbkou ťahu – metafora, ktorá je zrozumiteľná bez slov a vo všetkých jazykoch.
- **Mikro-animácie:** zlaté svetlo pri otvorení príbehu, stránky sa „otáčajú“ v page view, v guided view jemná paralaxa vrstiev.

## 6. Produkčný postup ilustrácií

1. Scenár príbehu v troch verziách (deti / teen / dospelí) od jedného autora, aby ostala jednotná dejová línia.
2. Storyboard v nízkej vernosti pre všetky tri úrovne naraz (rovnaké kľúčové zábery, iná inscenácia).
3. Character & world bible pre každý príbeh (model-sheety postáv, lokácie, rekvizity).
4. Finálna kresba vo vrstvách (pozadie / postavy / efekty), bez textu.
5. Lettering v CMS, jazykové mutácie, QA dĺžky textu v bublinách.
6. Teologická a historická recenzia (ekumenický poradný zbor) pred publikovaním.
