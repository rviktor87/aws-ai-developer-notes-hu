# A generatív [AI] etikai kérdései

> Kurzus: *Introduction to Generative [AI] - Art of the Possible* \
> Lecke: *Ethical Considerations of Generative [AI]* (8/10) \
> Forrás: [AWS] [Skill Builder - kurzusadatlap](https://skillbuilder.aws/learn/ZEVZZ1D4AS/introduction-to-generative-ai--art-of-the-possible/Y7MTGJCW1U) \
> Jegyzet készült: 2026. szeptember 12. \
> Rövidítések: [rövidítésszótár](../roviditesek.md)

## Felelős [AI]

A felelős mesterséges intelligencia (responsible artificial intelligence) olyan gyakorlatokat és elveket jelent,
amelyek átlátható és megbízható [AI]-rendszerek készítését, valamint a lehetséges károk mérséklését segítik.

Ezeket nem elég az elkészült rendszer végén ellenőrizni. Az alkalmazás teljes életciklusa (application lifecycle) alatt
figyelembe kell venni őket:

1. tervezés
2. fejlesztés
3. telepítés
4. megfigyelés
5. értékelés

## A generatív [AI] fő kihívásai

### Toxikus tartalom

A toxicitás (toxicity) sértő, felkavaró vagy más módon nem megfelelő tartalom előállításának lehetősége.

### Hallucináció

A hallucináció (hallucination) hihetően hangzó, de tényszerűen hibás állítás vagy következtetés. A magabiztos
megfogalmazás nem bizonyítja a válasz helyességét.

### Szellemi tulajdon

A nagy nyelvi modellek (large language models, [LLM]) a tanítóadatokra erősen hasonlító szöveget vagy kódot is
létrehozhatnak. Ez szerzői jogi, üzletititok-védelmi és más szellemi tulajdonnal (intellectual property) kapcsolatos
kockázatot jelenthet.

### Plágium és csalás

A generatív [AI] alkotóképessége felhasználható művek jogosulatlan másolására, plágiumra (plagiarism), illetve tanulmányi
vagy más jellegű csalásra (cheating).

### Elfogultság felerősítése

Ha a tanítóadatok elfogult mintákat tartalmaznak, azok bekerülhetnek a modell kimenetébe, és az automatizálás miatt
nagyobb léptékben is megjelenhetnek.

### Adatvédelmi kockázat

A modellnek átadott bemenet személyes vagy bizalmas adatot tartalmazhat. Ez sértheti a szervezet adatkezelési szabályait
vagy az alkalmazandó adatvédelmi előírásokat.

## Elfogultság a generatív [AI]-ban

Az elfogultság (bias) bizonyos jellemzők előnyben vagy hátrányban részesítésére való hajlam. Torz kimenethez és káros
következményekhez vezethet. Származhat a tanítóadatokból, a rendszer tervezéséből, az algoritmusból és a felhasználás
módjából is.

A nyilvánosan hozzáférhető adatok társadalmi előítéleteket hordozhatnak. Egy automatizált rendszer ezeket emberi
mérlegelés nélkül ismételheti vagy erősítheti fel.

### Az elfogultság típusai

| Típus | Mit jelent a leckében? |
|---|---|
| Kognitív elfogultság (cognitive bias) | Emberi döntések befolyásolják, milyen adat kerül a rendszerbe, hogyan használják az [AI]-t, és kik férhetnek hozzá. |
| Megerősítési torzítás (confirmation bias) | A rendszer a felhasználó által várt nézeteket adja vissza, és ezzel hibás elképzeléseket erősíthet meg. |
| Kulturális elfogultság (cultural bias) | Az adathalmazok és a tanítás társadalmi előítéleteket vagy sztereotípiákat tartalmaznak. |
| Adathalmaz-elfogultság (dataset bias) | A könnyen elérhető adat használata előnyt élvezhet egy jobban reprezentáló, de nehezebben beszerezhető adathalmazzal szemben. |
| Demográfiai elfogultság (demographic bias) | Egyes faji, nemi, etnikai vagy társadalmi csoportok túl- vagy alulreprezentáltak lehetnek. |
| Politikai elfogultság (political bias) | A kimenet tükrözheti a tanítóanyag politikai vagy ideológiai nézőpontját. |
| Nyelvi elfogultság (language bias) | Az interneten nagy mennyiségben jelen lévő nyelvek, különösen az angol, erősebben képviseltetik magukat a modellekben. |
| Statisztikai elfogultság (statistical bias) | A tervezői feltételezések befolyásolják, hogy kit és mit vesznek figyelembe a rendszerben. |
| Rendszerszintű elfogultság (systems bias) | A rendszerbe épített meglévő eljárások és gyakorlatok egyes csoportokat előnyben, másokat hátrányban részesíthetnek. |
| Időbeli elfogultság (time-related bias) | A modell meghatározott időszakból származó adatokon tanult, ezért korábbi vagy későbbi információkat nem feltétlenül ismer. |

## Az elfogult kimenetek következményei

### Társadalmi előítéletek megerősítése

Az elfogult kimenetek diszkriminatív élményeket és sztereotip ábrázolásokat hozhatnak létre. A lecke példája szerint egy
tartalomgeneráló rendszer következetesen férfiként ábrázolhatja az orvosokat, nőként az ápolókat, fiatalnak pedig a
technológiai dolgozókat. Sok kimenet együtt a társadalmi észlelést is alakíthatja.

### Nagy kockázatú alkalmazások

A következmények különösen súlyosak, ha az [AI] döntéseket befolyásol:

- a munkaerő-felvételben nemileg elfogult álláshirdetést készíthet
- az egészségügyben figyelmen kívül hagyhat demográfiai különbségeket
- a pénzügyi szolgáltatásokban torzíthatja a hitelbírálatot vagy a befektetési javaslatot

### Visszacsatolási hurkok

Visszacsatolási hurok (feedback loop) jöhet létre, ha egy elfogult [AI]-kimenetet más modellek tanítóadataként használnak.
Az új rendszer továbbviheti és felerősítheti az eredeti torzítást. A széles körben terjesztett elfogult tartalom emellett
a közbeszédet is befolyásolhatja.

### A technológiába vetett bizalom csökkenése

Ha egyes csoportok rendszeresen pontatlanabb vagy kevésbé megfelelő választ kapnak, elveszíthetik az [AI]-rendszerekbe
vetett bizalmukat. Emiatt akkor sem használják őket, amikor azok valóban segíthetnének. Ez részvételi szakadékhoz
(participation gap) és a digitális egyenlőtlenségek növekedéséhez vezethet.

## A felelős [AI] területei

A lecke nyolc, egymással összefüggő területet sorol fel:

1. méltányosság (fairness)
2. megmagyarázhatóság (explainability)
3. adatvédelem és biztonság (privacy and security)
4. robusztusság (robustness)
5. irányítás (governance)
6. átláthatóság (transparency)
7. biztonságosság (safety)
8. szabályozhatóság (controllability)

Egyik terület sem kezelhető önmagában. A lecke a méltányosságot és az átláthatóságot különösen fontosnak nevezi a
generatív [AI] esetében.

### Méltányosság

A méltányos [AI]-rendszer támogatja a befogadást, csökkenti a diszkrimináció kockázatát, megfelel a felelős működés
elveinek és a jogi normáknak, valamint erősíti a társadalmi bizalmat.

### Átláthatóság

Az átláthatóság információt ad a rendszer fejlesztési folyamatáról, képességeiről és korlátairól. Ennek alapján az
érintettek megalapozottabban dönthetnek a használatról, és értékelhetik a rendszer méltányosságát, robusztusságát és
megmagyarázhatóságát.

## Felelősség a kimenetekért

Az [AI] működésbe illesztéséért és megfelelő használatáért a szervezet felel. Ez megosztott felelősség a részt vevő
csapatok között, nem ruházható át a modellre.

A torzítás csökkentését segítheti:

- sokféle hátterű fejlesztőcsapat
- alapos tesztelési keretrendszer
- átlátható jelentési folyamat
- folyamatos megfigyelés és értékelés

A modellbe küldött információt előzetesen át kell vizsgálni. Ezzel csökkenthető a bizalmas adatok, a személyes adatok,
a biztonsági előírások és a szellemi tulajdon megsértésének kockázata.

## Vizsgára érdemes megjegyezni

| Magyar | English |
|---|---|
| A felelős [AI] elveit a tervezéstől az értékelésig a teljes alkalmazás-életciklusban figyelembe kell venni. | Responsible [AI] principles must be considered throughout the application lifecycle, from design to evaluation. |
| A fő kihívások a toxikus tartalom, a hallucináció, a szellemi tulajdon, a plágium és csalás, az elfogultság, valamint az adatvédelem. | The main challenges are toxicity, hallucinations, intellectual property, plagiarism and cheating, bias, and privacy. |
| A hallucináció hihetően hangzó, de tényszerűen hibás állítás. | A hallucination is a plausible-sounding but factually incorrect assertion. |
| Az elfogultság származhat az adatokból, az algoritmusból, a tervezői döntésekből és a felhasználás módjából. | Bias can come from data, algorithms, design decisions, and how the system is used. |
| Az elfogult kimenet társadalmi előítéletet erősíthet, nagy kockázatú döntést torzíthat, visszacsatolási hurkot hozhat létre és rombolhatja a bizalmat. | Biased output can reinforce social prejudice, distort high-stakes decisions, create feedback loops, and erode trust. |
| A felelős [AI] nyolc területe közül a lecke a méltányosságot és az átláthatóságot különösen fontosnak nevezi a generatív [AI] számára. | Of the eight dimensions of responsible [AI], the lesson identifies fairness and transparency as especially important for generative [AI]. |
| A generatív [AI] kimenetéért és megfelelő használatáért a szervezet és az érintett csapatok felelnek. | The organization and its teams are accountable for generative [AI] outputs and their appropriate use. |

## Gyors önellenőrzés

**1. Mit jelent a felelős mesterséges intelligencia?** \
*What does responsible artificial intelligence mean?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Olyan gyakorlatokat és elveket, amelyek átlátható, megbízható [AI]-rendszerek készítését és a lehetséges
károk mérséklését segítik.

**English:** Practices and principles that help create transparent and trustworthy [AI] systems while mitigating
potential harm.

</details>

**2. Melyik öt életciklusszakaszban kell alkalmazni a felelős [AI] elveit?** \
*During which five lifecycle phases should responsible [AI] principles be applied?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A tervezés, a fejlesztés, a telepítés, a megfigyelés és az értékelés során.

**English:** During design, development, deployment, monitoring, and evaluation.

</details>

**3. Mi a hallucináció?** \
*What is a hallucination?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Hihetően hangzó, de tényszerűen hibás állítás vagy következtetés.

**English:** An assertion or conclusion that sounds plausible but is factually incorrect.

</details>

**4. Hogyan keletkezhet visszacsatolási hurok az [AI]-rendszerek között?** \
*How can a feedback loop form between [AI] systems?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Ha egy elfogult rendszer kimenetét egy másik modell tanítóadataként használják, az új modell továbbviheti és
felerősítheti a torzítást.

**English:** When biased output from one system is used as training data for another model, the new model can carry
forward and amplify the bias.

</details>

**5. Miért veszélyesebb az elfogultság a nagy kockázatú alkalmazásokban?** \
*Why is bias more dangerous in high-stakes applications?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Mert munkaerő-felvételi, egészségügyi vagy pénzügyi döntéseket torzíthat, és ezzel emberek lehetőségeire,
ellátására vagy anyagi helyzetére hathat.

**English:** It can distort recruitment, healthcare, or financial decisions and affect people's opportunities, care,
or financial situation.

</details>

**6. Melyik nyolc terület alkotja a felelős [AI] keretét a leckében?** \
*Which eight dimensions make up the responsible [AI] framework in the lesson?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Méltányosság, megmagyarázhatóság, adatvédelem és biztonság, robusztusság, irányítás, átláthatóság,
biztonságosság és szabályozhatóság.

**English:** Fairness, explainability, privacy and security, robustness, governance, transparency, safety, and
controllability.

</details>

**7. Mit kell átgondolni, mielőtt egy csapat adatot küld egy generatív [AI]-rendszernek?** \
*What should a team consider before sending data to a generative [AI] system?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Meg kell vizsgálni, hogy az adat tartalmaz-e bizalmas vagy személyes információt, sért-e biztonsági vagy
adatvédelmi előírást, illetve veszélyeztet-e szellemi tulajdont.

**English:** The team should check whether the data contains confidential or personal information, violates security
or privacy requirements, or puts intellectual property at risk.

</details>

[AWS]: ../roviditesek.md#aws "Amazon Web Services"
[AI]: ../roviditesek.md#ai "Artificial intelligence"
[LLM]: ../roviditesek.md#llm "Large language model"
