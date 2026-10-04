# Biblia v komikse – vizuálny štýl comixovej predlohy

Pracovný názov štýlu: **„Svetlo a línia“** (verzia 2, schválená 4. 10. 2026)
Princíp: jeden rozpoznateľný rukopis značky, tri „intenzity“ podľa vekovej úrovne. Spoločný menovateľ všetkých troch úrovní je **čistá kontúra a svetlo**: žiadna úroveň nie je pochmúrna, ani tá pre dospelých. Vážnosť sa dosahuje tichom, kompozíciou a priestorom, nie tmou. Čitateľ, ktorý vyrastie z detskej úrovne, spozná tie isté postavy a svet aj v úrovni pre teenagerov a dospelých.

---

## 1. Spoločná DNA (platí pre všetky tri úrovne)

### 1.1 Kresba
- **Kontúra:** uzavretá, čistá línia v tradícii európskej *ligne claire* (Hergé, Uderzo). Deti: tenká mäkká hnedá linka. Teenageri: rovnomerná čierna linka strednej hrúbky. Dospelí: jemná tušová linka s premenlivou hrúbkou, miestami prerušená. Kontúra nikdy nie je „špinavá“ ani lámaná do šrafúry.
- **Svetlo:** jednotný zdroj „teplého svetla zhora“ a celkovo **svetlý, denný charakter obrazu** vo všetkých úrovniach. Noc je modrá, nie čierna; búrka je dramatická, nie temná. Svetlo je vizuálny motív celej série – prítomnosť Boha sa nikdy nezobrazuje ako postava, ale ako svetlo, zlatý lesk alebo zlaté písmo.
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
| Akcent (len dospelí, striedmo) | Tmavá purpurová | `#6B1F2A` | utrpenie, obeť, Apokalypsa – vždy len malá plocha |
| Doplnková | Tyrkysová voda | `#3FA7A3` | Galilejské jazero za dňa, more (najmä L1, L2) |

Pravidlo: zlato nikdy ako dekorácia, vždy ako význam. Ak je na paneli zlato, je tam Boh.

### 1.3 Typografia a lettering
Všetky písma musia pokrývať **Latin Extended-A** (slovenské ď ť ľ ĺ ŕ ô ä, české ě ř ů, poľské ą ę ł ń ś ź ż, maďarské ő ű) a byť pripravené na neskoršie rozšírenie (cyrilika, hebrejčina/arabčina RTL).

| Použitie | Odporúčané písmo | Poznámka |
|---|---|---|
| Názvy príbehov (display) | vlastný lettering na mieru alebo *Fraunces* / *Alegreya SC* | ručne kreslený charakter, variabilné |
| Bubliny – deti | *Nunito* (Bold/ExtraBold) | zaoblené, veľmi čitateľné, nízkoprahové pre začínajúcich čitateľov |
| Bubliny – teenageri | *Barlow Semi Condensed* | dynamické, komiksové, úsporné pri dlhšom texte; v duchu ligne claire veľké písmená pri zvolaniach |
| Bubliny – dospelí | *Literata* alebo *Source Serif 4* | knižný, pokojný; captions v kurzíve pôsobia ako rukopis na akvareli |
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

## 3. Úroveň 2 – Teenageri (11–17 rokov): „Moderná ligne claire“ (schválený variant A)

- **Proporcie:** 1 : 6, štylizované, ale vierohodné. Výrazná mimika a gestá, dynamické pózy.
- **Kontúra:** čistá, čierna, rovnomernej strednej hrúbky, uzavreté tvary. Žiadne šrafovanie; pohyb sa vyjadruje líniami pohybu a kompozíciou, nie špinou.
- **Farby:** plná paleta „Pôda a nebo“ v **dennom svetle**: tyrkysová voda, teplý piesok, terakota, olivová, jasná obloha. Ploché farby s jedným, najviac dvoma stupňami cel-shadingu. Farebný kľúč scény sa mení náladou (búrka = sýta modrá a tyrkys, nie čierna a fialová).
- **Svetlo a nálada:** optimistická, dobrodružná. Aj dramatický moment (búrka, Goliáš, Getsemani) sa inscenuje tak, aby bolo v obraze svetlo a smer von. Strach postáv je čitateľný, obraz sám nestraší.
- **Kompozícia:** 4–6 panelov na stranu, diagonály, striedanie detailu a celku, občasný celostranový „splash“ pri vrchole. Humor dovolený (reakcie učeníkov, zvieratá, vedľajšie postavy).
- **Text:** plné dialógy, narácia v captions, cca 40–60 slov na stranu. Na konci príbehu „Otázky na zamyslenie“ a slovníček.
- **Tematický dôraz:** identita, odvaha, pochybnosť, priateľstvo, zlyhanie a druhá šanca (Jozef, Dávid, Peter, Pavol, Ester, Rút). Ježiš ako ten, kto sa pýta a prekvapuje, nie len poučuje.
- **Referencie štýlu (držíme sa ich):** Asterix (Uderzo) a Tintin (Hergé) pre kontúru a farebnosť; Blake a Mortimer pre architektúru a scény davu; animovaný film „Mitchellovci“ (Sony) pre tempo a humor; moderné francúzsko-belgické album série (Lou!, Seuls) pre vzťah k teenagerom. Vyhýbame sa: temnému superhrdinskému realizmu, mange s extrémnou štylizáciou.
- **Prečo tento variant:** zdieľa s detskou úrovňou čistú kontúru a svetlo, takže čitateľ, ktorý prejde z L1 do L2, ostáva v tom istom svete. Je najľahšie lokalizovateľný (ploché farby, čisté bubliny) a najlacnejší na produkciu pri zachovaní kvality.

## 4. Úroveň 3 – Dospelí (18+): „Tuš a akvarel“ (schválený variant A)

- **Proporcie:** realistické 1 : 7,5, individuálne tváre s vekom a históriou, ale kreslené s ľahkosťou, nie fotorealisticky.
- **Kontúra:** jemná tušová linka s premenlivou hrúbkou, miestami prerušená, aby ju dokončila farba. Linka zostáva čistá a čitateľná, nikdy sa nerozpadá do šrafúry.
- **Farby:** voľné, svietivé akvarelové laverky, ktoré nechávajú **biely papier dýchať**. Paleta „Pôda a nebo“ v prirodzenej sýtosti: jeruzalemský kameň, okrová, olivová, jasná galilejská modrá. Zlato len na svetle. Tmavá purpurová iba ako malý akcent pri utrpení. Jemná granulácia pigmentu, žiadna digitálna textúra navyše.
- **Svetlo a nálada:** vzdušná, kontemplatívna, plná svetla. Vážnosť sa dosahuje tichom, priestorom a kompozíciou, nie temnotou. Noc je modrá laverka s teplým svetlom lampy či ohňa, nie čierna plocha. Utrpenie (Pašie, Jób, exil) sa zobrazuje s dôstojnosťou a s bielym priestorom okolo, ktorý dáva čitateľovi miesto na dych.
- **Kompozícia:** voľná mriežka, veľké tiché panely bez textu, dvojstranové akvarelové splashe (Stvorenie, prechod cez more, Zmŕtvychvstanie, Emauzy). Pomalé tempo, striedanie detailu tváre a širokej krajiny.
- **Text:** úryvky biblického textu v captions (voľné preklady, viď produktová špecifikácia 9.3), dialógy literárne, nie modernizované. Poznámky pod čiarou s historickým a jazykovým kontextom (hebrejské a grécke pojmy), krížové odkazy Starý zákon – Nový zákon.
- **Tematický dôraz:** utrpenie a nádej, spravodlivosť, exil, viera v neistote (Jób, Žalmy, Jeremiáš, Kazateľ, Pašie, Zjavenie symbolicky).
- **Referencie štýlu (držíme sa ich):** Jean-Jacques Sempé (ľahkosť linky, biely priestor), akvarelové albumy bande dessinée „Aya z Yopougonu“ a Emmanuela Guiberta („Alanova vojna“, „Fotograf“), akvarelové cestopisy (Urban Sketchers), Quentin Blake vo vážnejšej polohe. Pre svetlo a krajinu: Turnerove akvarely. Vyhýbame sa: Rembrandtovmu šerosvitu, hutnej maľbe, „gritty“ grafickým románom.
- **Prečo tento variant:** je literárny a dôstojný, unesie ťažké scény bez temnoty a čistou linkou nadväzuje na L1 a L2. Výtvarne je najvhodnejší pre tlačenú verziu (knižná edícia ako neskorší produkt).

### 4.1 Vedľajšia identita: plochá grafika (variant B) len pre značku
Variant „plochá grafika / sieťotlač“ (Tom Haugomat, Malika Favre, Charley Harper) sa pre komiks nepoužije, ale odporúča sa ako jazyk **vizuálnej identity aplikácie**: ikona, obaly zbierok, úvodné obrazovky, marketingové vizuály, čitateľské plány. Päť plochých farieb z palety, zrno risografu, žiadne kontúry. Tým vznikne silná značka, ktorá je štýlovo odlišná od samotných komiksov, ale zdieľa s nimi paletu a motív svetla.

## 5. Identita aplikácie (UI)

- **Ikona a značka:** jazyk plochej grafiky (viď 4.1). Ikona: otvorená kniha, ktorej strany tvoria rečovú bublinu, posvätné zlato a pergamen na galilejskej modrej, bez kontúr.
- **UI téma:** pergamenová svetlá téma predvolená pre všetky úrovne (zodpovedá bielemu papieru akvarelu); atramentová tmavá téma voliteľná pre nočné čítanie. UI je zámerne tiché, aby neprekričalo komiks.
- **Prepínač úrovne:** tri ikony kresliarskeho nástroja: pastelka (deti), pero s tušom (teenageri), štetec s akvarelom (dospelí). Metafora zrozumiteľná bez slov vo všetkých jazykoch.
- **Mikro-animácie:** zlaté svetlo pri otvorení príbehu, stránky sa „otáčajú“ v page view, v guided view jemná paralaxa vrstiev.

## 6. Produkčný postup ilustrácií

1. Scenár príbehu v troch verziách (deti / teen / dospelí) od jedného autora, aby ostala jednotná dejová línia.
2. Storyboard v nízkej vernosti pre všetky tri úrovne naraz (rovnaké kľúčové zábery, iná inscenácia).
3. Character & world bible pre každý príbeh (model-sheety postáv, lokácie, rekvizity).
4. Finálna kresba vo vrstvách (pozadie / postavy / efekty), bez textu.
5. Lettering v CMS, jazykové mutácie, QA dĺžky textu v bublinách.
6. Teologická a historická recenzia (ekumenický poradný zbor) pred publikovaním.

---

## 7. Schválené ukážky (4. 10. 2026)

Scéna Utíšenie búrky (Mk 4, 35–41) vo všetkých troch úrovniach, priečinok `vizual/`:

| Úroveň | Súbor | Plné rozlíšenie |
|---|---|---|
| L1 Deti – Mäkké svetlo | `L1-deti-utisenie-burky.jpg` | https://www.canva.com/M/MAHXCbH1Bb0 |
| L2 Teenageri – Moderná ligne claire | `L2A-teenageri-ligne-claire.jpg` | https://www.canva.com/M/MAHXDLa7U-0 |
| L3 Dospelí – Tuš a akvarel | `L3A-dospeli-akvarel.jpg` | https://www.canva.com/M/MAHXDJeSeUQ |
| Značka (len identita) – plochá grafika | `L3B-dospeli-flat-poster.jpg` | https://www.canva.com/M/MAHXDJNDq08 |

Zamietnuté varianty (ponechané pre archív): `L2-teenageri-utisenie-burky.jpg` a `L3-dospeli-utisenie-burky.jpg` (prvý, pochmúrnejší návrh), `L2B-teenageri-webtoon.jpg` (webtoon). Ukážky sú generované skice na zladenie smeru, finálne ilustrácie kreslí ľudský ilustrátor podľa tohto dokumentu.
