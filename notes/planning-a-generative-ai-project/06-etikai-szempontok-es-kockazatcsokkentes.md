# Etikai szempontok és kockázatcsökkentés

> Kurzus: *Planning a Generative [AI] Project* \
> Lecke: *Ethical Considerations in Generative [AI]* \
> Forrás: [AWS] [Skill Builder - kurzusadatlap](https://skillbuilder.aws/learn/HU1FQRGDDZ/planning-a-generative-ai-project/SYR3SCPSHC) \
> Jegyzet készült: 2026. szeptember 12. \
> Rövidítések: [rövidítésszótár](../roviditesek.md)

## Először azt kell eldönteni, való-e ide a generatív [AI]

A generatív [AI] sok üzleti problémánál hasznos lehet, de nem minden problémát tud vagy érdemes vele megoldani. A
projekt értékelésekor a várható előnyök mellett a kockázatokat és azok csökkenthetőségét is vizsgálni kell.

A felelős mesterséges intelligencia (responsible artificial intelligence) olyan elveket és gyakorlatokat jelent,
amelyek átlátható és megbízható rendszerek készítését, valamint a lehetséges károk mérséklését segítik. Ezeket a teljes
alkalmazás-életciklusban figyelembe kell venni:

1. tervezés
2. fejlesztés
3. telepítés
4. megfigyelés
5. értékelés

## A generatív [AI] legfontosabb kockázatai

### Toxikus tartalom

A toxicitás (toxicity) sértő, felkavaró vagy más módon nem megfelelő tartalom előállításának veszélye.

### Hallucináció

A hallucináció (hallucination) hihetően hangzó, de nem ellenőrizhető vagy tényszerűen hibás állítás. Az alapmodell
(foundation model, [FM]) a saját válaszának valóságtartalmát nem tudja megbízhatóan igazolni.

### Szellemi tulajdon és adatvédelem

A nagy nyelvi modell (large language model, [LLM]) a tanítóadat egy részével azonos vagy ahhoz nagyon hasonló szöveget,
illetve kódot állíthat elő. Ez szellemi tulajdonnal (intellectual property), bizalmas adatokkal és adatvédelemmel
kapcsolatos problémát okozhat.

### Plágium és csalás

A plágium (plagiarism) és csalás (cheating) kockázatát növeli, hogy a modell által készített tartalom sokszor nehezen
különböztethető meg az ember által írt szövegtől.

### Elfogultság felerősítése

A tanítóadatban jelen lévő elfogultság (bias) átkerülhet a kimenetbe. Az automatizált előállítás és terjesztés nagy
léptékben erősítheti fel a torz mintákat.

### Személyes adatok kezelése

A modellnek átadott bemenet személyes vagy bizalmas információt tartalmazhat. Az adat bevitele sértheti az adatvédelmi
előírásokat vagy a szervezet belső szabályait.

## Az elfogultság típusai

| Típus | Jelentés |
|---|---|
| Kognitív elfogultság (cognitive bias) | Emberi döntések torzíthatják az adatválasztást, a felhasználás módját és a hozzáférést. |
| Megerősítési torzítás (confirmation bias) | A modell a várt nézet visszaadásával hibás elképzelést erősíthet meg. |
| Kulturális elfogultság (cultural bias) | Az adathalmaz előítéleteket és sztereotípiákat hordozhat. |
| Adathalmaz-elfogultság (dataset bias) | A könnyen elérhető adat használata háttérbe szoríthat egy jobban reprezentáló adathalmazt. |
| Demográfiai elfogultság (demographic bias) | Egyes faji, nemi, etnikai vagy társadalmi csoportok túl- vagy alulreprezentáltak lehetnek. |
| Politikai elfogultság (political bias) | A kimenet tükrözheti a tanítóanyag politikai vagy ideológiai nézőpontját. |
| Nyelvi elfogultság (language bias) | A nagyobb mennyiségben elérhető nyelvek erősebben jelennek meg a modellben. |
| Statisztikai elfogultság (statistical bias) | A tervezői feltételezések befolyásolják, mi és ki kerül bele a mérésbe. |
| Rendszerszintű elfogultság (systems bias) | A rendszerbe épített meglévő eljárások egyes csoportokat előnyben részesíthetnek. |
| Időbeli elfogultság (time-related bias) | A tanítóadat csak meghatározott időszakot fed le, ezért korábbi vagy későbbi változások hiányozhatnak. |

## Az elfogult kimenet következményei

### Társadalmi előítéletek megerősítése

A sztereotip kimenetek diszkriminatív élményeket hozhatnak létre, és sokszoros terjesztés esetén a társadalmi észlelést
is alakíthatják. A lecke példája a foglalkozások nemhez vagy életkorhoz kötött ábrázolása.

### Nagy kockázatú alkalmazások

Az elfogult [AI] a munkaerő-felvételben nemileg torzított álláshirdetést készíthet, az egészségügyben figyelmen kívül
hagyhat demográfiai különbségeket, a pénzügyben pedig hitelbírálatot vagy befektetési tanácsot torzíthat.

### Visszacsatolási hurkok

Visszacsatolási hurok (feedback loop) keletkezik, ha egy elfogult kimenetet más modellek tanítóadataként használnak. Az
új rendszerek továbbvihetik és erősíthetik az eredeti torzítást.

### Bizalomvesztés

Ha bizonyos felhasználói csoportok rendszeresen pontatlanabb vagy kevésbé megfelelő választ kapnak, elveszíthetik a
technológiába vetett bizalmukat. Ez részvételi szakadékot (participation gap) hozhat létre, és tovább növelheti a
digitális egyenlőtlenséget.

## A felelős [AI] nyolc területe

A lecke az alábbi, egymással összefüggő területeket sorolja fel:

1. méltányosság (fairness)
2. megmagyarázhatóság (explainability)
3. adatvédelem és biztonság (privacy and security)
4. robusztusság (robustness)
5. irányítás (governance)
6. átláthatóság (transparency)
7. biztonságosság (safety)
8. szabályozhatóság (controllability)

Ezek közül egyik sem elegendő önmagában. A méltányosság csökkenti a diszkrimináció kockázatát, az átláthatóság pedig
megismerteti az érintettekkel a fejlesztési folyamatot, a rendszer képességeit és a korlátait. A megmagyarázhatóság azt
segít feltárni, miért készített a modell egy adott kimenetet, és mely bemeneti tényezők befolyásolták.

A leckében idézett Michael Kearns szerint a generatív [AI] gazdag és nyitott végű tartalma miatt a méltányosság
meghatározása, mérése és kikényszerítése nehezebb, mint a hagyományos prediktív gépi tanulásnál (predictive machine
learning).

## Kockázatcsökkentési keret

A kockázatok kezeléséhez három eszközcsoportot érdemes együtt használni:

- technikai védelmek, például tartalomszűrés, vízjelezés és gépi tartalomfelismerés
- szabályzati keretek, például használati irányelvek, hozzáférés-vezérlés és incidenskezelési eljárás
- etikai irányelvek és a tanítás során beépített biztonsági intézkedések

### Toxikus tartalom csökkentése

- **Tanítóadat gondozása (training data curation):** a káros kifejezéseket előre fel kell ismerni és el kell távolítani
  a tanítóadatból.
- **Védőkorlátmodell (guardrail model):** külön modell észlelheti és kiszűrheti a nem kívánt tartalmat.

Ezek csökkentik a kockázatot, de önmagukban nem garantálják, hogy soha nem jelenik meg nem megfelelő kimenet.

### Hallucináció kezelése

- A felhasználóknak tudniuk kell, hogy a modell állításait ellenőrizni kell.
- A fontos tényeket független forrásból kell igazolni.
- Az ellenőrizetlen tartalmat egyértelműen jelölni kell.

### Szellemi tulajdonnal kapcsolatos védelem

- **A modellből való eltávolítás (model disgorgement):** a védett tartalom vagy annak modellre gyakorolt hatása
  eltávolítható, illetve csökkenthető.
- **Differenciális adatvédelem (differential privacy):** mérsékli, hogy a kimenet mennyire függjön egyetlen konkrét
  tanítóadattól.
- **Részekre osztás (sharding):** a tanítás kisebb részekre bontható, így egy érintett rész újratanítható anélkül, hogy
  minden mást újra kellene tanítani.
- **Szűrés (filtering):** a kimenet összehasonlítható a védett tartalommal, az egyező rész pedig eltávolítható.

A lecke szerint e kockázatok hosszabb távú kezeléséhez technikai, szabályzati és jogi megoldások együtt szükségesek.

### Plágium és csalás felismerése

Egy lehetséges módszer a modell által készített tartalom felismerhető mintázattal való megjelölése. A lecke példájában a
szavakat két listára osztják, és a generálást az egyik listára korlátozzák. Az így létrejövő statisztikai mintázat
segítheti a gépi eredet felismerését. Ez a vízjelezés (watermarking) egyik szemléltető megközelítése.

## Felelősség és működtetés

A szervezet felel azért, hogy miként építi be az [AI]-t a működésébe. A kimenetért a fejlesztésben és használatban részt
vevő csapatok közösen felelnek.

A felelős működéshez szükséges:

- eltérő hátterű fejlesztői csapat
- alapos tesztelési keretrendszer
- átlátható jelentési folyamat
- az elfogultság folyamatos figyelése és mérséklése
- a modellnek átadott információ előzetes ellenőrzése

Az utolsó pont csökkenti a bizalmas információ, a személyes adat, a biztonsági előírás és a szellemi tulajdon véletlen
megsértésének kockázatát.

## Vizsgára érdemes megjegyezni

| Magyar | English |
|---|---|
| Nem minden üzleti problémát tud vagy érdemes generatív [AI]-val megoldani, ezért az előnyök mellett a mérsékelhető és nem mérsékelhető kockázatokat is értékelni kell. | Generative [AI] cannot and should not solve every business problem, so both mitigable and unmitigable risks must be evaluated alongside the benefits. |
| A felelős [AI] elveit a tervezéstől az értékelésig a teljes alkalmazás-életciklusban alkalmazni kell. | Responsible [AI] principles must be applied throughout the application lifecycle, from design to evaluation. |
| A fő kockázatok a toxikus tartalom, a hallucináció, a szellemi tulajdon, a plágium és csalás, az elfogultság, valamint az adatvédelem. | The main risks are toxicity, hallucinations, intellectual property, plagiarism and cheating, bias, and privacy. |
| Az elfogult kimenet társadalmi előítéletet erősíthet, nagy kockázatú döntést torzíthat, visszacsatolási hurkot okozhat és rombolhatja a bizalmat. | Biased output can reinforce social prejudice, distort high-stakes decisions, create feedback loops, and erode trust. |
| A kockázatcsökkentés technikai védelmeket, szabályzati kereteket és etikai irányelveket egyaránt igényel. | Risk mitigation requires technical safeguards, policy frameworks, and ethical guidelines. |
| A hallucinációból származó fontos állításokat független forrásból kell ellenőrizni, az ellenőrizetlen tartalmat pedig jelölni kell. | Important claims affected by hallucination must be checked against independent sources, and unverified content must be labeled. |
| A generatív [AI] kimenetéért és megfelelő használatáért a szervezet, illetve az érintett csapatok felelősek. | The organization and the teams involved are accountable for generative [AI] output and its appropriate use. |

## Gyors önellenőrzés

**1. Miért kell a kockázatokat még a generatív [AI]-projekt megkezdése előtt értékelni?** \
*Why should risks be evaluated before starting a generative [AI] project?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Mert nem minden probléma alkalmas generatív [AI]-val történő megoldásra, és azt is meg kell állapítani, hogy
a felmerülő kockázatok elfogadható szintre csökkenthetők-e.

**English:** Not every problem is suitable for generative [AI], and the organization must determine whether the risks
can be reduced to an acceptable level.

</details>

**2. Melyik hat fő kockázatot sorolja fel a lecke?** \
*Which six main risks does the lesson list?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Toxikus tartalom, hallucináció, szellemi tulajdon, plágium és csalás, elfogultság, valamint adatvédelem.

**English:** Toxicity, hallucinations, intellectual property, plagiarism and cheating, bias, and privacy.

</details>

**3. Hogyan csökkenthető a toxikus kimenet kockázata?** \
*How can the risk of toxic output be reduced?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A tanítóadat gondozásával és a nem kívánt tartalmat felismerő, illetve kiszűrő védőkorlátmodellekkel.

**English:** Through training-data curation and guardrail models that detect and filter unwanted content.

</details>

**4. Mit kell tenni a hallucináció kockázatának csökkentéséhez?** \
*What should be done to reduce the risk of hallucinations?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A felhasználókat tájékoztatni kell az ellenőrzés szükségességéről, a fontos állításokat független forrásból
kell igazolni, az ellenőrizetlen tartalmat pedig jelölni kell.

**English:** Users should be taught to verify outputs, important claims should be checked against independent sources,
and unverified content should be labeled.

</details>

**5. Milyen módszereket említ a lecke a szellemi tulajdon védelmére?** \
*Which methods does the lesson mention for protecting intellectual property?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A modellből való eltávolítást, a differenciális adatvédelmet, a részekre osztást és a kimeneti szűrést.

**English:** Model disgorgement, differential privacy, sharding, and output filtering.

</details>

**6. Melyik nyolc terület alkotja a felelős [AI] keretét?** \
*Which eight dimensions make up the responsible [AI] framework?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Méltányosság, megmagyarázhatóság, adatvédelem és biztonság, robusztusság, irányítás, átláthatóság,
biztonságosság és szabályozhatóság.

**English:** Fairness, explainability, privacy and security, robustness, governance, transparency, safety, and
controllability.

</details>

**7. Ki felel a generatív [AI] kimenetéért?** \
*Who is accountable for generative [AI] output?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Az [AI]-t a működésébe beépítő szervezet és a fejlesztésben, illetve használatban részt vevő csapatok.

**English:** The organization integrating [AI] into its operations and the teams involved in its development and use.

</details>

## Kapcsolódó anyag

- [Amazon Science-cikk](https://www.amazon.science/blog/responsible-ai-in-the-generative-era): *Responsible [AI] in the
  Generative Era*

[AWS]: ../roviditesek.md#aws "Amazon Web Services"
[AI]: ../roviditesek.md#ai "Artificial intelligence"
[FM]: ../roviditesek.md#fm "Foundation model"
[LLM]: ../roviditesek.md#llm "Large language model"
