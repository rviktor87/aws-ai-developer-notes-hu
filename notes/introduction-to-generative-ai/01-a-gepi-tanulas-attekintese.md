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

- A generatív [AI] az [AI], az [ML] és a deep learning hierarchiáján belül helyezkedik el.
- A hagyományos [ML] fő célja tipikusan a **mintafelismerés (pattern recognition) és előrejelzés (prediction)**; a generatív [AI]-é az **új tartalom létrehozása (content generation)**.
- Az [FM]-ek nagy adatmennyiségen előtanított, több célra adaptálható modellek.
- Az [LLM] az [FM]-ek egyik típusa, nem az [FM] szinonimája.
- A Transformer architecture áttörése, a számítási erőforrások, a szakértői csapatok és a beruházási hajlandóság együtt gyorsították fel a generatív [AI] fejlődését.

## Gyors önellenőrzés

**1. Mi a jellemzők és a címkék szerepe egy tanító adathalmazban?**

<details>
<summary>Válasz</summary>

A jellemzők (features) a modell bemeneti adatai. A címkék (labels) az elvárt kimenetek, amelyek alapján a modell megtanulja a bemenet és a kívánt eredmény közötti kapcsolatot.

</details>

**2. Hogyan viszonyul egymáshoz az [AI], az [ML], a deep learning és a generatív [AI]?**

<details>
<summary>Válasz</summary>

Az [AI] a legtágabb terület. Ezen belül helyezkedik el az [ML], azon belül pedig a mélytanulás (deep learning, [DL]). A generatív [AI] általában [DL]-architektúrákra és alapmodellekre épül.

</details>

**3. Miben tér el egy alapmodell a hagyományos, egyetlen feladatra tanított modelltől?**

<details>
<summary>Válasz</summary>

A hagyományos modell általában egy konkrét feladatra készül, és gyakran feladatspecifikus, címkézett adatokat igényel. Az alapmodell (foundation model, [FM]) nagy adatmennyiségen végzett előtanítás után több feladatra is használható, például promptolással vagy finomhangolással (fine-tuning).

</details>

**4. Miért nevezhető az [LLM] alapmodellnek, és hogyan állít elő szöveget?**

<details>
<summary>Válasz</summary>

Az [LLM] nagy mennyiségű nyelvi adaton előtanított, többféle nyelvi feladatra használható modell, ezért az [FM]-ek egyik típusa. A szöveget a következő token környezet alapján történő előrejelzésével, majd a folyamat ismétlésével állítja elő.

</details>

**5. Mely tényezők tették lehetővé a generatív [AI] közelmúltbeli gyors fejlődését?**

<details>
<summary>Válasz</summary>

A 2017-ben bemutatott Transformer architektúra, a nagyobb számítási kapacitás, a specializált kutatói és mérnöki csapatok, valamint a nagyszabású kutatások finanszírozása együtt gyorsította fel a fejlődést.

</details>

[AWS]: ../roviditesek.md#aws "Amazon Web Services"
[AI]: ../roviditesek.md#ai "Artificial intelligence"
[ML]: ../roviditesek.md#ml "Machine learning"
[DL]: ../roviditesek.md#dl "Deep learning"
[FM]: ../roviditesek.md#fm "Foundation model"
[FMs]: ../roviditesek.md#fm "Foundation models"
[LLM]: ../roviditesek.md#llm "Large language model"
