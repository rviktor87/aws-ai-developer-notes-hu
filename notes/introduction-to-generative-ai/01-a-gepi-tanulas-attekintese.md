# A gépi tanulás áttekintése

> Kurzus: *Introduction to Generative [AI] - Art of the Possible* \
> Lecke: *Overview of [ML]* (2/10) \
> Forrás: [AWS] [Skill Builder - kurzusadatlap](https://skillbuilder.aws/learn/ZEVZZ1D4AS/introduction-to-generative-ai--art-of-the-possible/Y7MTGJCW1U) \
> Jegyzet készült: 2026. szeptember 12.
> Rövidítések: [rövidítésszótár](../roviditesek.md)

## Röviden

A generatív [AI] a gépi tanulás (machine learning, [ML]) egyik ága. Felhasználói bemenet alapján új tartalmat, például szöveget, képet, programkódot, hangot vagy videót képes létrehozni. A hagyományos [ML]-megoldások jellemzően egy konkrét feladatra készülnek, míg a nagy mennyiségű adaton előtanított alapmodellek (foundation models, [FMs]) több különböző feladathoz is adaptálhatók, gyakran természetes nyelvű utasításokkal.

## Hogyan működik a gépi tanulás?

A gépi tanulás (machine learning, [ML]) múltbeli adatok mintázatait tanulja meg, majd ezek alapján korábban nem látott adatokra ad előrejelzést. Az eredmény üzleti döntések vagy műveletek alapja lehet.

A leegyszerűsített folyamat:

1. Összeállítunk egy tanító adathalmazt (training dataset).
2. Az adathalmaz **jellemzőket (features)** és **címkéket (labels)** tartalmaz.
3. A modell összefüggést tanul a bemeneti jellemzők és az elvárt kimenetek között.
4. Új adaton felismeri a megtanult mintázatokat.
5. A tanult összefüggés alapján előrejelzést készít.

```text
adathalmaz -> mintázatok megtanulása -> előrejelzés új adatra -> üzleti művelet
```

## [AI], [ML], deep learning és generatív [AI]

A fogalmak egymásba ágyazódnak:

1. mesterséges intelligencia (artificial intelligence, [AI])
2. gépi tanulás (machine learning, [ML])
3. mélytanulás (deep learning, [DL])
4. generatív [AI]

- **[AI]:** a legtágabb terület; intelligens viselkedést megvalósító rendszerek gyűjtőfogalma.
- **[ML]:** adatokból tanul mintázatokat, amelyekkel előrejelzéseket készít.
- **Mélytanulás (deep learning, [DL]):** neuronok és szinapszisok működéséhez lazán hasonló, többrétegű neurális hálózatokra (neural networks) épül.
- **Generatív [AI]:** a deep learningre építve új tartalmat hoz létre.

Példák az [AWS] világából:

- Az **Amazon Rekognition** deep learning segítségével képeket, valamint tárolt és streamelt videókat elemez.
- Az **Amazon Q Developer** generatív [AI] használatával, megjegyzésekből és a meglévő kódból kiindulva valós időben ad kódjavaslatokat.

## Alapmodellek és nagy nyelvi modellek

Az **alapmodell (foundation model, [FM])** internetes léptékű adatmennyiségen előtanított, nagy méretű modell. Nem feltétlenül egyetlen feladatra készül: ugyanaz a modell több célra is adaptálható.

Az [FM]-ek többféle modalitással (modality) dolgozhatnak:

- szöveg,
- kép,
- programkód,
- hang.

A **nagy nyelvi modell (large language model, [LLM])** az [FM]-ek egyik típusa. A mondat szavainak helyét és szövegkörnyezetét figyelembe véve a következő szót, pontosabban tokent jelzi előre. Ennek ismétlésével hoz létre új tartalmat.

### Hagyományos [ML] és [FM]-ek összevetése

| Szempont | Hagyományos [ML] | [FM]-re épülő generatív [AI] |
|---|---|---|
| Tipikus cél | Egy jól körülhatárolt feladat | Többféle feladat |
| Tanítás | Feladatspecifikus, gyakran címkézett adat | Nagy adatmennyiségen végzett előtanítás, majd adaptálás |
| Új feladat | Gyakran új modell vagy újratanítás kell | Sokszor prompttal vagy további finomhangolással (fine-tuning) megoldható |
| Kimenet | Előrejelzés, osztályozás | Új szöveg, kép, kód, hang stb. |

## Az [ML] szerepe az Amazonnál

Az Amazon több mint húsz éve használ [AI]- és [ML]-megoldásokat. A leckében szereplő példák:

- személyre szabott termékajánlások az Amazon webáruházban;
- robotok árumozgatási útvonalainak optimalizálása a logisztikai központokban;
- ellátási lánc (supply chain), kereslet-előrejelzés (demand forecasting) és kapacitástervezés (capacity planning);
- deep learning az Amazon Prime Air drónos kézbesítésében;
- számítógépes látás (computer vision) az Amazon Go üzletek pénztár nélküli működésében;
- több mint harminc [ML]-rendszer együttműködése az Alexában.

### Fontosabb mérföldkövek

| Év | Esemény |
|---:|---|
| 2001 | Elindulnak az Amazon személyre szabott ajánlásai. |
| 2005 | Elindul az Amazon Prime. |
| 2012 | Az Amazon robotokat kezd használni a logisztikai központokban. |
| 2014 | Elindul az Amazon Alexa és az Amazon Prime Now. |
| 2016 | Az Amazon Prime Air végrehajtja első kézbesítését. |
| 2018 | Elindul az Amazon Go. |
| 2020 | Az Amazon leányvállalata, a Zoox bemutatja autonóm robotaxiját. |
| 2023 | Elindul az Amazon CodeWhisperer, és bejelentik az Amazon Bedrockot. |
| 2024 | Megjelennek a generatív [AI]-ra épülő Amazon Q asszisztensek, köztük az Amazon Q Developer és az Amazon Q Business. |

## Miért éppen most tört előre a generatív [AI]?

Nem egyetlen ok, hanem több tényező együttes hatása tette lehetővé a gyors fejlődést:

- A 2017-ben bemutatott **Transformer architektúra (Transformer architecture)** hatékonyabbá tette a nagyon nagy modellek tanítását.
- Jelentősen nőtt a számítási erőforrásokba (compute resources) és infrastruktúrába fektetett tőke.
- Nagyobb, specializált kutatói és mérnöki csapatok jöttek létre.
- A szervezetek hajlandóvá váltak nagyszabású, kockázatosabb kutatási ötleteket finanszírozni.

## Vizsgára érdemes megjegyezni

| Magyar | English |
|---|---|
| A generatív [AI] az [AI], az [ML] és a mélytanulás (deep learning, [DL]) hierarchiáján belül helyezkedik el. | Generative [AI] sits within the hierarchy of [AI], [ML], and deep learning. |
| A hagyományos [ML] fő célja jellemzően a mintafelismerés (pattern recognition) és az előrejelzés (prediction). A generatív [AI] új tartalmat hoz létre (content generation). | Traditional [ML] typically focuses on pattern recognition and prediction. Generative [AI] creates new content. |
| Az [FM]-ek nagy adatmennyiségen előtanított, több célra adaptálható modellek. | [FM]s are pretrained on large amounts of data and can be adapted to multiple tasks. |
| Az [LLM] az [FM]-ek egyik típusa, és a két fogalom jelentése nem azonos. | An [LLM] is a type of [FM], and the two terms do not mean the same thing. |
| A Transformer architektúra (Transformer architecture), a számítási erőforrások, a szakértői csapatok és a kutatási beruházások együtt gyorsították fel a generatív [AI] fejlődését. | The Transformer architecture, compute resources, specialized teams, and research investment accelerated the development of generative [AI]. |

## Gyors önellenőrzés

**1. Mi a jellemzők és a címkék szerepe egy tanító adathalmazban?** \
*What are the roles of features and labels in a training dataset?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A jellemzők (features) a modell bemeneti adatai. A címkék (labels) az elvárt kimenetek, amelyek alapján a modell megtanulja a bemenet és a kívánt eredmény közötti kapcsolatot.

**English:** Features are the model inputs. Labels are the expected outputs that allow the model to learn the relationship between an input and the desired result.

</details>

**2. Hogyan viszonyul egymáshoz az [AI], az [ML], a mélytanulás (deep learning, [DL]) és a generatív [AI]?** \
*How are [AI], [ML], deep learning, and generative [AI] related?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Az [AI] a legtágabb terület. Ezen belül helyezkedik el az [ML], azon belül pedig a [DL]. A generatív [AI] általában [DL]-architektúrákra és alapmodellekre épül.

**English:** [AI] is the broadest field. [ML] is a subset of [AI], and deep learning is a subset of [ML]. Generative [AI] usually relies on deep learning architectures and foundation models.

</details>

**3. Miben tér el egy alapmodell (foundation model, [FM]) a hagyományos, egyetlen feladatra tanított modelltől?** \
*How does an [FM] differ from a traditional model trained for a single task?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A hagyományos modell általában egy konkrét feladatra készül, és gyakran feladatspecifikus, címkézett adatokat igényel. Az [FM] nagy adatmennyiségen végzett előtanítás után több feladatra is használható, például promptolással vagy finomhangolással (fine-tuning).

**English:** A traditional model is usually built for one task and often requires task-specific labeled data. An [FM] is pretrained on a large amount of data and can be used for multiple tasks through prompting or fine-tuning.

</details>

**4. Miért nevezhető az [LLM] alapmodellnek (foundation model), és hogyan állít elő szöveget?** \
*Why is an [LLM] considered an [FM], and how does it generate text?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Az [LLM] nagy mennyiségű nyelvi adaton előtanított, többféle nyelvi feladatra használható modell, ezért az [FM]-ek egyik típusa. A szöveget a következő token környezet alapján történő előrejelzésével, majd a folyamat ismétlésével állítja elő.

**English:** An [LLM] is pretrained on large amounts of language data and can perform different language tasks, making it a type of [FM]. It generates text by repeatedly predicting the next token from the available context.

</details>

**5. Mely tényezők tették lehetővé a generatív [AI] közelmúltbeli gyors fejlődését?** \
*Which factors enabled the recent rapid development of generative [AI]?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A 2017-ben bemutatott Transformer architektúra, a nagyobb számítási kapacitás, a specializált kutatói és mérnöki csapatok, valamint a nagyszabású kutatások finanszírozása együtt gyorsította fel a fejlődést.

**English:** The Transformer architecture introduced in 2017, greater compute capacity, specialized research and engineering teams, and funding for ambitious research collectively accelerated development.

</details>

[AWS]: ../roviditesek.md#aws "Amazon Web Services"
[AI]: ../roviditesek.md#ai "Artificial intelligence"
[ML]: ../roviditesek.md#ml "Machine learning"
[DL]: ../roviditesek.md#dl "Deep learning"
[FM]: ../roviditesek.md#fm "Foundation model"
[FMs]: ../roviditesek.md#fm "Foundation models"
[LLM]: ../roviditesek.md#llm "Large language model"
