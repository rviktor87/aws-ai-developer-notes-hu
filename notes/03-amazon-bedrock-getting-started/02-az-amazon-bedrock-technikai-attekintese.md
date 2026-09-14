# Az Amazon Bedrock technikai áttekintése

> Kurzus: *Amazon Bedrock Getting Started* \
> Lecke: *Technical Overview for Amazon Bedrock* \
> Forrás: [AWS] [Skill Builder - kurzusadatlap](https://skillbuilder.aws/learn/63KTRM86DQ/amazon-bedrock-getting-started/SC2Y3HMAUE) \
> Jegyzet készült: 2026. szeptember 14. \
> Rövidítések: [rövidítésszótár](../roviditesek.md)

## A lecke céljai

A lecke két kérdésre összpontosít:

1. Mely elemek alkotják az Amazon Bedrock szolgáltatásarchitektúráját (service architecture)?
2. Mely [AWS]-szolgáltatásokkal integrálható az Amazon Bedrock, és mi ezek szerepe?

## Az Amazon Bedrock architektúrája

Az Amazon Bedrock teljesen felügyelt, kiszolgáló nélküli keretrendszer (fully managed, serverless framework), amely
egységes felületen kapcsolódik az alapmodellekhez (foundation models, [FM]). A keretrendszer [FM]-eket, ügynököket,
tudásbázisokat és értékelési eszközöket fog össze.

A lecke architektúra-ábrája egy vállalati adatokat használó, visszakereséssel kiegészített generálási
(Retrieval-Augmented Generation, [RAG]) folyamatot mutat be az Amazon Lex, az [AWS] Lambda, az Amazon Simple Storage
Service ([S3]) és az Amazon Bedrock közreműködésével.

### A kérdéstől a válaszig

1. **Felhasználói kérdés (user query):** a felhasználó természetes nyelven kérdez az Amazon Lex felhasználói
   felületén. Az Amazon Lex felismeri és értelmezi a természetes nyelvű bemenetet.
2. **Számítás és üzleti logika (compute and business logic):** az [AWS] Lambda feldolgozza a kérdést, majd az üzleti
   logika alapján továbbítja és összehangolja a kéréseket, illetve válaszokat az érintett szolgáltatások között.
3. **Releváns adatok (relevant data):** a különböző forrásokból érkező vállalati adatokat [S3]-ban tárolják, majd
   szinkronizálják az Amazon Bedrock Knowledge Bases szolgáltatásával. Így a [RAG] a szervezetre jellemző információval
   javíthatja a válasz pontosságát és kontextusát.
4. **Amazon Bedrock Knowledge Bases:** a tudásbázis feldolgozza és indexeli az [S3]-ból szinkronizált vállalati
   tartalmat. A visszakeresett információ releváns kontextust biztosít az [FM] számára.
5. **Generatív [AI]-válasz (generative [AI] response):** az Amazon Bedrock egy [FM] segítségével előállítja a választ,
   majd további feldolgozásra visszaküldi az [AWS] Lambdának. A kapcsolódó fejlesztői környezet támogatja a modellek
   felderítését, tesztelését és az alkalmazások elemzőeszközökkel segített fejlesztését.
6. **Válasz a felhasználónak (response to user):** a kész, természetes nyelvű válasz visszakerül az Amazon Lex
   felhasználói felületére.

Az architektúra lényeges eleme az [AWS] Lambda: ez futtatja az Amazon Bedrock és a többi szolgáltatás közötti
interakciókat összehangoló kódot. Ez szerepel helyes válaszként a lecke első ellenőrző kérdésében is.

## Szolgáltatásintegrációk

Az Amazon Bedrock a meglévő [AWS]-infrastruktúrához kapcsolva egyesítheti az adatokat, a számítási erőforrásokat és az
alkalmazáslogikát. A lecke nyolc fontos integrációt mutat be.

### Amazon SageMaker [AI]

Az Amazon SageMaker [AI] az Amazon Bedrock mellett a teljes gépi tanulási (machine learning, [ML]) életciklust
támogatja. Míg az Amazon Bedrock egyszerűsített felületen ad hozzáférést az [FM]-ekhez, a SageMaker [AI] egyéni modellek
fejlesztéséhez és üzembe helyezéséhez kínál kiegészítő képességeket.

Egy közös munkafolyamatban az adattudósok a SageMaker [AI]-t adatelőkészítésre és jellemzőtervezésre (feature
engineering), az Amazon Bedrockot pedig generatív feladatokra használhatják. Ez egyszerre támogatja az [FM]-eket és a
saját [ML]-modelleket alkalmazó stratégiát.

### Amazon Kendra

Az Amazon Kendra vállalati kereséssel (enterprise search) egészíti ki az Amazon Bedrock [RAG]-képességeit. Webhelyek,
fájlrendszerek, adatbázisok és más adattárak információit kapcsolhatja az [FM]-ekhez.

A Kendra szemantikus keresése (semantic search) a kérdés mögötti szándékot is figyelembe veszi, majd releváns
információt keres vissza. Ez pontosabbá és relevánsabbá teheti a vállalati tudásra támaszkodó generatív
[AI]-alkalmazásokat. A lecke második ellenőrző kérdésének helyes válasza is az Amazon Kendra integrációja.

### [AWS] Lambda

Az [AWS] Lambda futtatja az Amazon Bedrock és más szolgáltatások közötti kapcsolatot összehangoló kódot. Feladata lehet
a bemenet előfeldolgozása, a válasz formázása és az üzleti logika megvalósítása.

A Lambda eseményvezérelt architektúrát (event-driven architecture) tesz lehetővé: más [AWS]-szolgáltatások eseményei
Lambda-függvényeket indíthatnak, amelyek [FM]-eket hívnak meg. A szolgáltatás automatikusan méreteződik, ezért a
munkafolyamat kiszolgáló nélküli működési modellben maradhat.

### Amazon [S3]

Az Amazon [S3] méretezhető objektumtárolást biztosít az Amazon Bedrock által használt adatokhoz. Tárolhatók benne
[RAG]-hoz szükséges dokumentumok és finehangolási (fine-tuning) adatkészletek is.

Az Amazon Bedrock közvetlenül elérheti az [S3]-tárolók tartalmát. Ez egyszerűsíti a szervezeti információforrások és az
[FM]-ek összekapcsolását, miközben az [S3] tartóssági és biztonsági képességei is használhatók.

### Amazon OpenSearch Service

Az Amazon OpenSearch Service dokumentumokat és más tartalmakat indexel a hatékony [RAG] és szemantikus keresés
érdekében. Felhasználói kérdés érkezésekor a rendszer előbb releváns információt kereshet az OpenSearch-indexekben,
majd az eredményt átadhatja az Amazon Bedrocknak. Így a modell válasza a szervezet konkrét és pontos adataira
támaszkodhat.

### [AWS] Identity and Access Management

Az [AWS] Identity and Access Management ([IAM]) szabályozza az Amazon Bedrock és a kapcsolódó szolgáltatások elérését.
A részletes jogosultságok meghatározzák, mely felhasználók és alkalmazások érhetnek el egy adott [FM]-et vagy
szolgáltatási képességet.

Az [IAM]-szabályzatoknak a legkisebb jogosultság elvét (principle of least privilege) kell követniük: minden identitás
csak a feladatához szükséges engedélyeket kapja meg. Ez védi az érzékeny adatokat és csökkenti a jogosulatlan
modell-hozzáférés kockázatát.

### Amazon CloudWatch

Az Amazon CloudWatch az Amazon Bedrock-alkalmazások teljesítményét és állapotát figyeli. Mérőszámokat, naplókat és
eseményeket gyűjt például a válaszidőről, a hibaarányról és a használati mintákról.

A CloudWatch irányítópultjai (dashboards) segítenek a problémák felismerésében és a teljesítmény optimalizálásában. A
riasztások értesíthetnek, ha egy mérőszám átlép egy meghatározott küszöbértéket.

### Amazon EventBridge

Az Amazon EventBridge eseményvezérelt architektúrába illeszti az Amazon Bedrock képességeit. Egy szolgáltatás eseménye
automatikusan elindíthat egy [FM]-műveletet.

A lecke példájában egy új dokumentum kerül egy [S3]-tárolóba. Ez aktivál egy EventBridge-szabályt, amely egy generatív
[AI]-alkalmazáson keresztül meghívja az Amazon Bedrock alkalmazásprogramozási felületét (application programming
interface, [API]), majd összefoglalót készít a dokumentumról. A minta az adat beérkezésekor, emberi beavatkozás nélkül
indítja el a feldolgozást.

## Integrációs tervezési szempontok

### Biztonság és megfelelőség

Az integrációknak megfelelő titkosítást, hozzáférés-szabályozást és megfelelőségi intézkedéseket kell alkalmazniuk az
adatvédelem és az irányítás biztosításához.

### Teljesítményoptimalizálás

A modellválasztást és a konfigurációs beállításokat úgy kell kiegyensúlyozni, hogy az alkalmazás teljesítményigényei
teljesüljenek, miközben a költségek kezelhetők maradnak.

### Méretezhetőség tervezése

Az integrációt változó terhelésre kell méretezni. Figyelembe kell venni a párhuzamos kérések számát, a válaszidőt és
az erőforrás-kihasználást.

## Vizsgára érdemes megjegyezni

| Magyar | English |
|---|---|
| Az Amazon Bedrock teljesen felügyelt, kiszolgáló nélküli keretrendszer, amely [FM]-eket, ügynököket, tudásbázisokat és értékelési eszközöket fog össze. | Amazon Bedrock is a fully managed, serverless framework that combines [FM]s, agents, knowledge bases, and evaluation tools. |
| Az Amazon Lex fogadja a természetes nyelvű kérdést és jeleníti meg a választ, az [AWS] Lambda pedig az üzleti logika alapján összehangolja a szolgáltatások közötti kéréseket és válaszokat. | Amazon Lex receives the natural-language query and presents the response, while [AWS] Lambda orchestrates requests and responses between services according to the business logic. |
| A vállalati adatokat [S3]-ban tárolják és az Amazon Bedrock Knowledge Bases szolgáltatással szinkronizálják, amely feldolgozza és indexeli a tartalmat a [RAG] számára. | Enterprise data is stored in [S3] and synchronized with Amazon Bedrock Knowledge Bases, which processes and indexes the content for [RAG]. |
| A SageMaker [AI] egyéni [ML]-modellek fejlesztésével és üzembe helyezésével egészíti ki az Amazon Bedrock [FM]-hozzáférését. | SageMaker [AI] complements Amazon Bedrock's [FM] access with custom [ML] model development and deployment. |
| Az Amazon Kendra több vállalati adattárra kiterjedő szemantikus kereséssel javítja az Amazon Bedrock [RAG]-képességeit. | Amazon Kendra enhances Amazon Bedrock [RAG] with semantic search across multiple enterprise repositories. |
| Az [S3] dokumentumokat és finehangolási adatkészleteket tárolhat, az OpenSearch pedig a releváns információ szemantikus visszakeresését segítő indexeket biztosít. | [S3] can store documents and fine-tuning datasets, while OpenSearch provides indexes for semantic retrieval of relevant information. |
| Az [IAM] a legkisebb jogosultság elvével szabályozza a modellek és képességek elérését. | [IAM] controls access to models and features according to the principle of least privilege. |
| A CloudWatch mérőszámokkal, naplókkal, irányítópultokkal és riasztásokkal figyeli az alkalmazást. | CloudWatch monitors the application through metrics, logs, dashboards, and alarms. |
| Az EventBridge események alapján automatikusan indíthat Amazon Bedrock-műveleteket, például egy [S3]-ba feltöltött dokumentum összegzését. | EventBridge can automatically trigger Amazon Bedrock operations from events, such as summarizing a document uploaded to [S3]. |
| Az integráció tervezésekor a biztonság és megfelelőség, a teljesítmény és költség egyensúlya, valamint a változó terhelésre való méretezés egyaránt fontos. | Integration design must account for security and compliance, the balance between performance and cost, and scaling for variable workloads. |
| Az ellenőrző kérdések helyes válaszai: az [AWS] Lambda összehangolja az Amazon Bedrock és más szolgáltatások közötti interakciókat, az Amazon Kendra pedig vállalati kereséssel javítja a [RAG]-ot. | The knowledge-check answers are that [AWS] Lambda orchestrates interactions between Amazon Bedrock and other services, and Amazon Kendra enhances [RAG] with enterprise search. |

## Gyors önellenőrzés

**1. Mely fő elemeket fogja össze az Amazon Bedrock keretrendszere?** \
*Which main elements does the Amazon Bedrock framework combine?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** [FM]-eket, ügynököket, tudásbázisokat és értékelési eszközöket.

**English:** [FM]s, agents, knowledge bases, and evaluation tools.

</details>

**2. Mi az Amazon Lex és az [AWS] Lambda szerepe az architektúra-folyamatban?** \
*What are the roles of Amazon Lex and [AWS] Lambda in the architecture flow?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Az Amazon Lex fogadja a természetes nyelvű kérdést és megjeleníti a választ. Az [AWS] Lambda az üzleti
logika alapján feldolgozza és összehangolja a szolgáltatások közötti kéréseket és válaszokat.

**English:** Amazon Lex receives the natural-language query and presents the response. [AWS] Lambda processes and
orchestrates requests and responses between services according to the business logic.

</details>

**3. Hogyan jut el a vállalati adat az [FM] kontextusába?** \
*How does enterprise data reach the [FM]'s context?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Az adatot [S3]-ban tárolják, majd az Amazon Bedrock Knowledge Bases szolgáltatással szinkronizálják. A
tudásbázis feldolgozza és indexeli a tartalmat, a [RAG] pedig a kérdéshez kapcsolódó részeket adja az [FM]
kontextusához.

**English:** The data is stored in [S3] and synchronized with Amazon Bedrock Knowledge Bases. The knowledge base
processes and indexes the content, and [RAG] adds the parts relevant to the query to the [FM]'s context.

</details>

**4. Hogyan egészíti ki egymást a SageMaker [AI] és az Amazon Bedrock?** \
*How do SageMaker [AI] and Amazon Bedrock complement each other?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A SageMaker [AI] az egyéni [ML]-modellek fejlesztését és üzembe helyezését, az Amazon Bedrock pedig az
[FM]-ek egyszerű elérését és a generatív feladatokat támogatja.

**English:** SageMaker [AI] supports custom [ML] model development and deployment, while Amazon Bedrock provides
simplified [FM] access and supports generative tasks.

</details>

**5. Miért hasznos az Amazon Kendra az Amazon Bedrock mellett?** \
*Why is Amazon Kendra useful alongside Amazon Bedrock?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Mert több vállalati adattárban képes a kérdés szándékát figyelembe vevő szemantikus keresésre, és ezzel
pontosabbá, relevánsabbá teszi a [RAG]-alapú válaszokat.

**English:** It provides intent-aware semantic search across multiple enterprise repositories, making [RAG]-based
responses more accurate and relevant.

</details>

**6. Mit figyel az Amazon CloudWatch egy Amazon Bedrock-alkalmazásnál?** \
*What does Amazon CloudWatch monitor in an Amazon Bedrock application?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Többek között a válaszidőt, a hibaarányt és a használati mintákat. Ezekhez mérőszámokat, naplókat,
irányítópultokat és riasztásokat biztosít.

**English:** It monitors response times, error rates, and usage patterns, among other signals, using metrics, logs,
dashboards, and alarms.

</details>

**7. Hogyan működik a lecke EventBridge-példája?** \
*How does the lesson's EventBridge example work?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Egy [S3]-ba feltöltött új dokumentum eseménye aktivál egy EventBridge-szabályt, amely egy generatív
[AI]-alkalmazáson keresztül meghívja az Amazon Bedrock [API]-ját, és elindítja a dokumentum összegzését.

**English:** An event from a newly uploaded [S3] document activates an EventBridge rule, which invokes the Amazon
Bedrock [API] through a generative [AI] application and starts document summarization.

</details>

**8. Mely három szempontot kell mérlegelni az integráció tervezésekor?** \
*Which three considerations should be evaluated when designing an integration?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A biztonságot és megfelelőséget, a teljesítmény és költség egyensúlyát, valamint a változó terhelésre való
méretezhetőséget.

**English:** Security and compliance, the balance between performance and cost, and scalability for variable
workloads.

</details>

[AWS]: ../roviditesek.md#aws "Amazon Web Services"
[AI]: ../roviditesek.md#ai "Artificial intelligence"
[ML]: ../roviditesek.md#ml "Machine learning"
[FM]: ../roviditesek.md#fm "Foundation model"
[API]: ../roviditesek.md#api "Application programming interface"
[S3]: ../roviditesek.md#s3 "Amazon Simple Storage Service"
[RAG]: ../roviditesek.md#rag "Retrieval-Augmented Generation"
[IAM]: ../roviditesek.md#iam "Identity and Access Management"
