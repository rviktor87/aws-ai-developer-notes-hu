# Generatív [AI] az [AWS]-en

> Kurzus: *Introduction to Generative [AI] - Art of the Possible* \
> Lecke: *Generative [AI] on [AWS]* (5/10) \
> Forrás: [AWS] [Skill Builder - kurzusadatlap](https://skillbuilder.aws/learn/ZEVZZ1D4AS/introduction-to-generative-ai--art-of-the-possible/Y7MTGJCW1U) \
> Jegyzet készült: 2026. szeptember 12. \
> Rövidítések: [rövidítésszótár](../roviditesek.md)

## Az [AWS] generatív [AI]-szolgáltatásai

Az [AWS] gépi tanulási modelleket, adatfeldolgozási lehetőségeket és biztonságos infrastruktúrát ad generatív
[AI]-megoldások készítéséhez. A lecke három nagy rétegre bontja a kínálatot:

1. számítási kapacitás (compute)
2. saját modellek készítése (build your own models)
3. alapmodellek szolgáltatásként (foundation models as a service)

### 1. Számítási kapacitás

A nagy nyelvi modellek (large language models, [LLM]) tanítása és futtatása jelentős számítási kapacitást igényel. Az
[AWS] két, erre a célra tervezett gépi tanulási gyorsítóval (machine learning accelerator) támogatja ezeket a
feladatokat:

- Az [AWS] Inferentia első generációját kisebb modellek költséghatékony telepítésére tervezték.
- Az [AWS] Trainium és az [AWS] Inferentia2 több százmilliárd paraméteres generatív [AI]-modellek tanítására és
  telepítésére is használható.

### 2. Saját modellek készítése

Az Amazon SageMaker JumpStart kétféle utat kínál:

- Saját [LLM] tanítható az Amazon SageMaker és az [AWS] Trainium használatával.
- A SageMaker JumpStart kínálatából kiválasztott nyelvi modell saját adatokkal újratanítható.

A második megoldásnál egy már elérhető modell adja a kiindulópontot, ezért nem kell minden esetben teljesen új modellt
készíteni.

### 3. Alapmodellek szolgáltatásként

Az alapmodellek (foundation models, [FM]) előtanítása sok időt és erőforrást igényel, különösen több milliárd paraméter
esetén. Az Amazon Bedrock teljesen felügyelt szolgáltatás (fully managed service), amely az Amazon és vezető
[AI]-vállalatok modelljeit alkalmazásprogramozási felületen (application programming interface, [API]) teszi
elérhetővé. Ide tartoznak az Amazon Titan modellek is.

Az ügyfél több [FM] közül választhatja ki a használati esetéhez megfelelő modellt. A Bedrock célja, hogy egyszerűbbé
tegye az [FM]-ekre épülő generatív [AI]-alkalmazások elkészítését és méretezését.

## Kódgenerálás Amazon Q Developerrel

Az Amazon Q Developer egy [AI]-alapú programozási segéd (coding companion), amely kódot generál, és valós idejű
javaslatokat ad. A fejlesztő a kód vagy a megjegyzések írása közben, az integrált fejlesztői környezetben (integrated
development environment, [IDE]) kaphat segítséget. Így kevesebbszer kell megszakítania a munkát internetes keresés
vagy egy kolléga megkérdezése miatt.

Az Accenture a leckében felsorolt példák szerint többek között ezekre használja:

- új fejlesztők betanítása
- ismétlődő alapkód (boilerplate code) írása
- ismeretlen programozási nyelvek használata
- biztonsági sérülékenységek felismerése

## A leckében szereplő eredmények

Az Amazon Q Developer előzetes verziója alatt végzett Amazon produktivitási felmérésben a megoldást használó résztvevők
27 százalékkal nagyobb valószínűséggel fejezték be sikeresen a feladatokat, és átlagosan 57 százalékkal gyorsabbak
voltak a megoldást nem használóknál.

Az Accenture beszámolója szerint az Amazon Q Developer egyes esetekben akár 30 százalékkal csökkentette a fejlesztési
ráfordítást. A felszabaduló figyelmet a biztonság, a minőség és a teljesítmény javítására fordították.

Mindkét adat egy meghatározott mérésből vagy ügyfélbeszámolóból származik. Nem általános teljesítménygarancia.

## Vizsgára érdemes megjegyezni

| Magyar | English |
|---|---|
| Az [AWS] három nagy generatív [AI]-réteget különít el: számítási kapacitás, saját modellek készítése és alapmodellek szolgáltatásként. | [AWS] distinguishes three broad generative [AI] layers: compute, building your own models, and foundation models as a service. |
| Az [AWS] Inferentia és az [AWS] Trainium kifejezetten gépi tanulási feladatokra készült gyorsítók. | [AWS] Inferentia and [AWS] Trainium are purpose-built accelerators for machine learning workloads. |
| Az Amazon SageMaker JumpStart segítségével saját [LLM] tanítható, vagy egy elérhető nyelvi modell saját adatokkal újratanítható. | Amazon SageMaker JumpStart can be used to train a custom [LLM] or retrain an available language model with your own data. |
| Az Amazon Bedrock teljesen felügyelt szolgáltatás, amely több szolgáltató [FM]-jeit [API]-n keresztül teszi elérhetővé. | Amazon Bedrock is a fully managed service that provides access to [FM]s from multiple providers through an [API]. |
| Az Amazon Q Developer az [IDE]-n belül ad valós idejű programozási javaslatokat és generál kódot. | Amazon Q Developer provides real-time coding recommendations and generates code inside the [IDE]. |
| A leckében szereplő százalékos eredmények egy Amazon felmérésből és egy Accenture-beszámolóból származnak, ezért nem általános garanciák. | The percentages in the lesson come from an Amazon study and an Accenture report, so they are not general guarantees. |

## Gyors önellenőrzés

**1. Melyik három rétegre bontja a lecke az [AWS] generatív [AI]-kínálatát?** \
*Which three layers does the lesson use to describe the [AWS] generative [AI] offering?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Számítási kapacitás, saját modellek készítése és alapmodellek szolgáltatásként.

**English:** Compute, building your own models, and foundation models as a service.

</details>

**2. Mire szolgál az [AWS] Inferentia és az [AWS] Trainium?** \
*What are [AWS] Inferentia and [AWS] Trainium used for?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Gépi tanulási modellek futtatását, tanítását és telepítését gyorsítják. Az egyes chipgenerációk eltérő
modellméretekhez és feladatokhoz készültek.

**English:** They accelerate the running, training, and deployment of machine learning models. Different chip
generations are designed for different model sizes and tasks.

</details>

**3. Milyen két lehetőséget mutat be a SageMaker JumpStart?** \
*Which two options does the lesson present for SageMaker JumpStart?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Saját [LLM] tanítható SageMaker és Trainium használatával, vagy egy elérhető nyelvi modell újratanítható
saját adatokkal.

**English:** You can train your own [LLM] with SageMaker and Trainium, or retrain an available language model with your
own data.

</details>

**4. Mit biztosít az Amazon Bedrock?** \
*What does Amazon Bedrock provide?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Teljesen felügyelt hozzáférést biztosít az Amazon és más vezető [AI]-vállalatok [FM]-jeihez [API]-n
keresztül.

**English:** It provides fully managed access through an [API] to [FM]s from Amazon and other leading [AI] companies.

</details>

**5. Hogyan illeszkedik az Amazon Q Developer a fejlesztő munkafolyamatába?** \
*How does Amazon Q Developer fit into a developer's workflow?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Az [IDE]-n belül, kód vagy megjegyzések írása közben ad valós idejű javaslatokat és generál kódot.

**English:** It provides real-time recommendations and generates code inside the [IDE] while the developer writes code
or comments.

</details>

**6. Miért kell óvatosan értelmezni a leckében szereplő százalékos eredményeket?** \
*Why should the percentage results in the lesson be interpreted carefully?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Mert egy előzetes verzióhoz kapcsolódó Amazon felmérésből, illetve egy Accenture-beszámolóból származnak.
Nem minden fejlesztőre és feladatra érvényes teljesítménygaranciák.

**English:** They come from an Amazon study tied to a preview and from an Accenture report. They are not performance
guarantees for every developer and task.

</details>

## Kapcsolódó anyagok

- [Generative AI on AWS](https://aws.amazon.com/ai/generative-ai/)
- [AWS Generative AI Innovation Center](https://aws.amazon.com/ai/generative-ai/innovation-center/)
- [Generative AI services on AWS](https://aws.amazon.com/ai/generative-ai/services/?sec=aiapps&pos=0)
- [Amazon Q Developer](https://aws.amazon.com/q/developer/)
- [Amazon Q Developer customer stories](https://aws.amazon.com/q/customers/#Amazon_Q_Developer_customers)

[AWS]: ../roviditesek.md#aws "Amazon Web Services"
[AI]: ../roviditesek.md#ai "Artificial intelligence"
[LLM]: ../roviditesek.md#llm "Large language model"
[FM]: ../roviditesek.md#fm "Foundation model"
[API]: ../roviditesek.md#api "Application programming interface"
[IDE]: ../roviditesek.md#ide "Integrated development environment"
