# Bevezetés az Amazon Bedrockba

> Kurzus: *Amazon Bedrock Getting Started* \
> Lecke: *Introduction to Amazon Bedrock* \
> Forrás: [AWS] [Skill Builder - kurzusadatlap](https://skillbuilder.aws/learn/63KTRM86DQ/amazon-bedrock-getting-started/SC2Y3HMAUE) \
> Jegyzet készült: 2026. szeptember 14. \
> Rövidítések: [rövidítésszótár](../roviditesek.md)

## Mi az Amazon Bedrock?

Az Amazon Bedrock teljesen felügyelt szolgáltatás (fully managed service), amely vezető [AI]-szolgáltatók
alapmodelljeit (foundation model, [FM]) egységes alkalmazásprogramozási felületen (application programming interface,
[API]) teszi elérhetővé. Generatív [AI]-alkalmazások építhetők és méretezhetők vele anélkül, hogy az alapul szolgáló
infrastruktúrát vagy saját nagy nyelvi modellt (large language model, [LLM]) kellene fejleszteni és üzemeltetni.

A fejlesztő több különböző képességű, sebességű és költségű modell közül választhat. Az Amazon Bedrock kezeli a
modellkövetkeztetéshez (model inference) szükséges infrastruktúrát és automatikusan igazodik a terheléshez.

### Adatvédelem és testreszabás

A szolgáltatás biztonságos környezetet biztosít, és a lecke szerint a felhasználó bemeneteit, kimeneteit és saját
adatait nem használja az igénybe vett modellek tanítására.

A modellek két kiemelt módon igazíthatók a szervezet igényeihez:

- **Finehangolás (fine-tuning):** saját példák segítségével a modell stílusa, szóhasználata és szakterületi tudása
  módosítható.
- **Visszakereséssel kiegészített generálás (Retrieval-Augmented Generation, [RAG]):** a modell újratanítása nélkül
  kapcsolható saját, naprakész tudásforrásokhoz.

Az Amazon Bedrock más [AWS]-szolgáltatásokkal is együttműködik, továbbá tartalomszűrést, modellértékelést és más, a
felelős [AI]-használatot segítő eszközöket kínál.

## Alapvető működés

### [AWS]-modellek

Az Amazon Nova modellek eltérő modalitásokra és felhasználási helyzetekre készültek:

| Modell | Modalitás és fő felhasználás |
|---|---|
| **Nova Micro** | Csak szöveges, nagyon alacsony költségű és a Nova családon belül a legkisebb késleltetésű modell gyors szövegfeldolgozáshoz. |
| **Nova Lite** | Költséghatékony multimodális modell kép-, videó- és szövegbemenethez, interaktív és nagy volumenű alkalmazásokhoz. |
| **Nova Pro** | Nagy képességű multimodális modell, amely a pontosságot, a sebességet és a költséget egyensúlyozza ki, például videó-összegzéshez és szoftverfejlesztéshez. |
| **Nova Premier** | A legösszetettebb feladatokra szánt, legfejlettebb multimodális Nova modell. Modelldesztillációval (model distillation) más Nova modellek specializált változatainak létrehozását is támogatja. |
| **Nova Canvas** | Szöveges vagy képi promptból professzionális képeket előállító modell, beépített szerkesztési és biztonsági funkciókkal. |
| **Nova Reel** | Szövegből és képből jó minőségű videót készít, a vizuális stílus, a tempó és a kameramozgás szabályozásával. |
| **Nova Sonic** | Valós idejű, kis késleltetésű és természetes hangalapú beszélgetésekre készült beszédmodell, kifejező hangok támogatásával. |

Az Amazon Titan [FM]-család szintén elérhető. Ezeket a modelleket az [AWS] által válogatott adatkészleteken tanították.

### További modellszolgáltatók

Az Amazon Bedrock a lecke szerint többek között az Anthropic, az AI21 Labs, a Cohere, a Meta és a Stability [AI]
modelljeihez ad hozzáférést. A modellek a konzolon kipróbálhatók, majd ugyanazon Amazon Bedrock [API]-n keresztül
illeszthetők az alkalmazásokba. Így nem kell szolgáltatónként külön felületet megtanulni vagy külön infrastruktúrát
üzemeltetni.

## Technikai fogalmak

### Alapmodellek és modalitások

Az [FM] nagy mennyiségű adaton tanított, sokféle feladathoz adaptálható [AI]-modell. A hagyományos, egyetlen feladatra
tanított gépi tanulási (machine learning, [ML]) modellektől a léptéke és az általánosíthatósága különbözteti meg.

Az Amazon Bedrock leckében szereplő modalitások (modalities):

- **Szöveg:** szöveg létrehozása, megértése, feldolgozása, összegzése és kérdések megválaszolása.
- **Kép:** vizuális tartalom létrehozása, feldolgozása és értelmezése.
- **Beágyazás (embedding):** a bemenet, jellemzően szöveg, szemantikai jelentést hordozó numerikus vektorrá alakítása.
  Tudásbázisokhoz, szemantikus kereséshez (semantic search) és tartalmak kapcsolatainak felismeréséhez használható.

### Tokenek és tokenkorlátok

A token a modell által feldolgozott alapegység, amely lehet egy szó vagy annak egy része. Minden modell korlátozza a
bemenet és a kimenet együttes tokenmennyiségét. Ezt a promptok tervezésekor és a költségek becslésekor is figyelembe
kell venni, mert az árazás gyakran a tokenhasználaton alapul.

### Prompttervezés

A prompttervezés (prompt engineering) a kívánt eredményhez vezető utasítások megfogalmazása és szerkezeti kialakítása.
A válasz minőségét javíthatja példák megadása, a kimeneti formátum rögzítése, valamint az összetett feladat kisebb
lépésekre bontása.

### Következtetési paraméterek

A következtetési paraméterek (inference parameters) szabályozzák a válaszgenerálást:

- a **temperature** a véletlenszerűség mértékét befolyásolja; alacsonyabb értéknél kiszámíthatóbb, magasabbnál
  változatosabb válasz várható
- a **top-p** a következő token kiválasztását a nagyobb összesített valószínűségű tokenek körére szűkíti
- a **maximum token count** a válasz maximális hosszát korlátozza

### [RAG]

A [RAG] külső tudásforrásból származó információval egészíti ki az [FM] kontextusát. Tipikus folyamata:

1. tudásbázis létrehozása a szervezet adataiból
2. a felhasználói kérdéshez kapcsolódó információ visszakeresése
3. a találatok hozzáadása az [FM]-nek átadott kontextushoz
4. a válasz előállítása a kérdés és a visszakeresett információ alapján

Ez a megközelítés újratanítás nélkül javíthatja a szakterületi válaszok pontosságát és aktualitását.

### Modellértékelés

A modellértékelés (model evaluation) az [FM] teljesítményének módszeres vizsgálata például pontosság, relevancia és
biztonság szerint. Az Amazon Bedrock eszközei modellek összehasonlítását és a testreszabás hatásának időbeli követését
is segítik. A megfelelő mérőszámokat az alkalmazás követelményeihez és az üzleti célokhoz kell igazítani.

### Flows

Az Amazon Bedrock Flows vizuális, kódolás nélküli (no-code) eszköz összetett [AI]-munkafolyamatok összeállításához.
Fogd és vidd (drag-and-drop) felületen kapcsolhatók össze modellek, tudásbázisok, adatforrások, logikai műveletek és
egyéni függvények. Egy folyamat például dokumentumból adatot nyerhet ki, összefoglalhatja, majd az összegzés alapján
választ generálhat. Szükség esetén egyéni kód is beilleszthető.

### Agents

Az Amazon Bedrock Agents [FM]-eket, egyéni műveleteket és tudásbázisokat kapcsol össze feladatorientált
[AI]-asszisztensek létrehozásához. Az ügynök értelmezi a kérést, kijelölt adatforrásokat ér el, előre meghatározott
függvényeket futtat, több lépésen keresztül gondolkodik, és megőrzi a beszélgetés kontextusát.

A lecke példájában egy webáruházi ügyfélszolgálati ügynök hozzáfér a termékkatalógushoz, követi a csomagokat,
megválaszolja a szabályzati kérdéseket, és a vásárlási előzmények ellenőrzése után elindíthatja a visszaküldést.

## Biztonság, irányítás és felelős [AI]

Az Amazon Bedrock vállalati biztonsági képességei:

- finomhangolt hozzáférés-szabályozás az [AWS] Identity and Access Management ([IAM]) segítségével
- titkosítás nyugalmi állapotban és átvitel közben
- privát hálózati kapcsolat virtuális magánfelhőn (virtual private cloud, [VPC]) és [AWS] PrivateLinken keresztül
- kulcskezelés az [AWS] Key Management Service ([KMS]) használatával
- [API]-tevékenységek részletes naplózása az [AWS] CloudTrailben, auditálási célra
- megfelelőségi állapot követése az [AWS] Artifactban

Az irányítás (governance) az [AI]-használat, az adatkezelés és a megfelelőség szervezeti szabályozását jelenti. A
védőkorlátok (guardrails) modell-hozzáférési korlátozásokat, promptellenőrzést és válaszszűrést valósíthatnak meg.
Az [AWS] CloudWatch mérőszámai és a CloudTrail naplói a használat megfigyelését és az auditálást támogatják.

Egy pénzügyi ügyfélszolgálati asszisztensnél a védőkorlátok például megakadályozhatják nem engedélyezett pénzügyi
termékek tárgyalását és kiszűrhetik az érzékeny adatokat. A kvóták részlegenként korlátozhatják az [API]-hívásokat, a
promptsablonok pedig egységesíthetik az ügyfél-interakciókat.

## Fő képességek

- **Többmodell-hozzáférés (multi-model access):** különböző szolgáltatók modelljei egy egységes [API]-n keresztül
  érhetők el, így feladatonként választható a megfelelő modell.
- **Modelltestreszabás (model customization):** a finehangolás saját példák alapján módosítja a modell paramétereit, a
  [RAG] pedig újratanítás nélkül kapcsolja a modellt saját adatokhoz.
- **Ügynök-keretrendszer (agents framework):** tudásbázisokat és külső rendszerekhez vezető [API]-kapcsolatokat fog
  össze több lépéses feladatok végrehajtásához.
- **Vállalati biztonság (enterprise security):** az adatvédelem, a jogosultságkezelés, a privát végpontok, a titkosítás
  és az auditnaplók vállalati és szabályozói követelményeket támogatnak.
- **Kiszolgáló nélküli architektúra (serverless architecture):** nincs szükség kapacitástervezésre vagy
  fürtüzemeltetésre, mert a szolgáltatás automatikusan méreteződik. A használatalapú árazás (pay-as-you-go pricing) a
  tényleges fogyasztáshoz igazítja a költséget.
- **Felelős [AI]-eszközök (responsible AI tools):** tartalomszűrés, testreszabható védőkorlátok és modellértékelés
  segíti a biztonsági és szervezeti elvárások érvényesítését.

## Gyakorlati üzleti alkalmazások

1. **Tartalomgenerálás:** marketinges szövegvázlatok, blogbejegyzések, közösségimédia-tartalmak, termékleírások és
   kampányképek gyorsabb elkészítése, következetesebb üzenetekkel.
2. **Ügyfélszolgálat:** összetett kérdéseket értelmező, kontextusfüggő válaszokat adó asszisztensek, amelyek saját
   tudásbázisból termékekről, eljárásokról és szabályzatokról is válaszolhatnak.
3. **Adatelemzés és következtetések:** szerződések, kutatási cikkek és műszaki dokumentációk összegzése, mintázatok
   felismerése és kérdések megválaszolása. Ez gyorsíthatja például a szerződés- és szakirodalom-elemzést.
4. **Termékfejlesztés támogatása:** kód- és dokumentációgenerálás, műszaki problémamegoldás, valamint nagy
   mennyiségű ügyfél-visszajelzés elemzése a termékdöntésekhez.
5. **Vállalati tudásmenedzsment:** különböző adattárak tudásának természetes nyelvű elérése. A [RAG] révén a válaszok
   a vállalati adatbázisok és dokumentumok pontos, naprakész információira támaszkodhatnak.

## Vizsgára érdemes megjegyezni

| Magyar | English |
|---|---|
| Az Amazon Bedrock teljesen felügyelt szolgáltatás, amely több vezető szolgáltató [FM]-jeit egységes [API]-n keresztül teszi elérhetővé. | Amazon Bedrock is a fully managed service that provides access to [FM]s from multiple leading providers through a unified [API]. |
| Az Amazon Bedrock kezeli és automatikusan méretezi a következtetési infrastruktúrát. | Amazon Bedrock manages and automatically scales the inference infrastructure. |
| A bemeneteket, kimeneteket és saját adatokat nem használják az igénybe vett modellek tanítására. | Inputs, outputs, and proprietary data are not used to train the models being used. |
| A finehangolás saját példákkal módosítja a modellt, míg a [RAG] újratanítás nélkül kapcsolja külső tudásforrásokhoz. | Fine-tuning adapts a model with proprietary examples, while [RAG] connects it to external knowledge sources without retraining. |
| A lecke három modalitása a szöveg, a kép és a beágyazás. | The three modalities in the lesson are text, image, and embeddings. |
| A tokenkorlát a bemenet és a kimenet együttes hosszát szabályozza, a tokenhasználat pedig a költséget is befolyásolhatja. | The token limit constrains the combined input and output length, and token usage can also affect cost. |
| Az alacsonyabb temperature kiszámíthatóbb, a magasabb temperature változatosabb válaszokat eredményez. | A lower temperature produces more predictable responses, while a higher temperature produces more varied responses. |
| A modellértékeléshez az alkalmazás céljaihoz igazított pontossági, relevancia- és biztonsági mérőszámok szükségesek. | Model evaluation requires accuracy, relevance, and safety metrics aligned with the application's objectives. |
| A Flows vizuálisan szervez több lépéses munkafolyamatokat, az Agents pedig modelleket, tudásbázisokat és műveleteket kapcsol össze feladatorientált asszisztensekké. | Flows visually orchestrate multi-step workflows, while Agents combine models, knowledge bases, and actions into task-oriented assistants. |
| Az [IAM], a titkosítás, a [VPC]-végpontok, a [KMS], a CloudTrail és a védőkorlátok együtt támogatják a vállalati biztonságot és irányítást. | [IAM], encryption, [VPC] endpoints, [KMS], CloudTrail, and guardrails jointly support enterprise security and governance. |
| A négy ellenőrző kérdés helyes válaszai: egységes hozzáférés vezető szolgáltatók [FM]-jeihez, prompttervezés, saját vagy friss adatokkal való modelltestreszabás, valamint nagy léptékű tartalom- és műszaki dokumentációgenerálás. | The four knowledge-check answers are unified access to leading providers' [FM]s, prompt engineering, model customization with proprietary or updated data, and content and technical documentation generation at scale. |

## Gyors önellenőrzés

**1. Mi az Amazon Bedrock alapvető feladata?** \
*What is the core function of Amazon Bedrock?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Több vezető [AI]-szolgáltató [FM]-jeihez ad egységes [API]-hozzáférést, miközben kezeli a szükséges
infrastruktúrát.

**English:** It provides unified [API] access to [FM]s from multiple leading [AI] providers while managing the
required infrastructure.

</details>

**2. Miben különbözik a finehangolás és a [RAG]?** \
*How do fine-tuning and [RAG] differ?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A finehangolás saját példákkal módosítja a modell paramétereit. A [RAG] nem tanítja újra a modellt, hanem
visszakeresett külső információt ad a kontextusához.

**English:** Fine-tuning changes model parameters using proprietary examples. [RAG] does not retrain the model; it
adds retrieved external information to the model's context.

</details>

**3. Melyik három modalitást sorolja fel a lecke?** \
*Which three modalities does the lesson list?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A szöveget, a képet és a beágyazást.

**English:** Text, image, and embeddings.

</details>

**4. Miért fontos ismerni a tokenkorlátot?** \
*Why is it important to understand the token limit?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Mert korlátozza a bemenet és a kimenet együttes hosszát, továbbá a tokenhasználat a költséget is
meghatározhatja.

**English:** It constrains the combined input and output length, and token usage can also determine cost.

</details>

**5. Hogyan hat a temperature a modell válaszára?** \
*How does temperature affect a model's response?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Alacsonyabb értéknél kiszámíthatóbb, magasabb értéknél változatosabb és esetleg kreatívabb a válasz.

**English:** A lower value makes the response more predictable; a higher value makes it more varied and potentially
more creative.

</details>

**6. Mi a különbség a Flows és az Agents szerepe között?** \
*What is the difference between the roles of Flows and Agents?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A Flows vizuálisan szervez modellekből, adatforrásokból és logikából álló munkafolyamatot. Az Agents
modelleket, tudásbázisokat és műveleteket kapcsol össze olyan asszisztenssé, amely kéréseket értelmez és feladatokat
hajt végre.

**English:** Flows visually orchestrate a workflow of models, data sources, and logic. Agents combine models,
knowledge bases, and actions into assistants that interpret requests and perform tasks.

</details>

**7. Mely biztonsági szolgáltatásokat és mechanizmusokat emeli ki a lecke?** \
*Which security services and mechanisms does the lesson highlight?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Az [IAM]-szabályzatokat, a nyugalmi és átvitel közbeni titkosítást, a [VPC]-végpontokat, az [AWS]
PrivateLinket, a [KMS]-t, a CloudTrail-naplózást és a védőkorlátokat.

**English:** [IAM] policies, encryption at rest and in transit, [VPC] endpoints, [AWS] PrivateLink, [KMS], CloudTrail
logging, and guardrails.

</details>

**8. Melyik öt üzleti alkalmazást mutatja be a lecke?** \
*Which five business applications does the lesson present?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Tartalomgenerálást, ügyfélszolgálatot, adatelemzést és következtetések kinyerését, termékfejlesztési
támogatást, valamint vállalati tudásmenedzsmentet.

**English:** Content generation, customer service, data analysis and insights, product development assistance, and
enterprise knowledge management.

</details>

## Kapcsolódó anyag

- [Amazon Bedrock](https://aws.amazon.com/bedrock/)

[AWS]: ../roviditesek.md#aws "Amazon Web Services"
[AI]: ../roviditesek.md#ai "Artificial intelligence"
[ML]: ../roviditesek.md#ml "Machine learning"
[FM]: ../roviditesek.md#fm "Foundation model"
[LLM]: ../roviditesek.md#llm "Large language model"
[API]: ../roviditesek.md#api "Application programming interface"
[RAG]: ../roviditesek.md#rag "Retrieval-Augmented Generation"
[IAM]: ../roviditesek.md#iam "Identity and Access Management"
[VPC]: ../roviditesek.md#vpc "Virtual private cloud"
[KMS]: ../roviditesek.md#kms "Key Management Service"
