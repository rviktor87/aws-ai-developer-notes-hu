# A gépi tanulás áttekintése

> Kurzus: *Introduction to Generative <abbr title="Artificial intelligence">AI</abbr> - Art of the Possible*  
> Lecke: *Overview of <abbr title="Machine learning">ML</abbr>* (2/10)  
> Forrás: [<abbr title="Amazon Web Services">AWS</abbr> Skill Builder - kurzusadatlap](https://skillbuilder.aws/learn/ZEVZZ1D4AS/introduction-to-generative-ai--art-of-the-possible/Y7MTGJCW1U)  
> Jegyzet készült: 2026. szeptember 12.
> Rövidítések: [rövidítésszótár](../roviditesek.md)

## Röviden

A generatív <abbr title="Artificial intelligence">AI</abbr> a gépi tanulás (machine learning, <abbr title="Machine learning">ML</abbr>) egyik ága. Felhasználói bemenet alapján új tartalmat, például szöveget, képet, programkódot, hangot vagy videót képes létrehozni. A hagyományos <abbr title="Machine learning">ML</abbr>-megoldások jellemzően egy konkrét feladatra készülnek, míg a nagy mennyiségű adaton előtanított alapmodellek (foundation models, <abbr title="Foundation models">FMs</abbr>) több különböző feladathoz is adaptálhatók, gyakran természetes nyelvű utasításokkal.

## Hogyan működik a gépi tanulás?

A gépi tanulás (machine learning, <abbr title="Machine learning">ML</abbr>) múltbeli adatok mintázatait tanulja meg, majd ezek alapján korábban nem látott adatokra ad előrejelzést. Az eredmény üzleti döntések vagy műveletek alapja lehet.

A leegyszerűsített folyamat:

1. Összeállítunk egy tanító adathalmazt (training dataset).
2. Az adathalmaz **jellemzőket (features)** és **címkéket (labels)** tartalmaz.
3. A modell összefüggést tanul a bemeneti jellemzők és az elvárt kimenetek között.
4. Új adaton felismeri a megtanult mintázatokat.
5. A tanult összefüggés alapján előrejelzést készít.

```text
adathalmaz -> mintázatok megtanulása -> előrejelzés új adatra -> üzleti művelet
```

## <abbr title="Artificial intelligence">AI</abbr>, <abbr title="Machine learning">ML</abbr>, deep learning és generatív <abbr title="Artificial intelligence">AI</abbr>

A fogalmak egymásba ágyazódnak:

1. mesterséges intelligencia (artificial intelligence, <abbr title="Artificial intelligence">AI</abbr>)
2. gépi tanulás (machine learning, <abbr title="Machine learning">ML</abbr>)
3. mélytanulás (deep learning, <abbr title="Deep learning">DL</abbr>)
4. generatív <abbr title="Artificial intelligence">AI</abbr>

- **<abbr title="Artificial intelligence">AI</abbr>:** a legtágabb terület; intelligens viselkedést megvalósító rendszerek gyűjtőfogalma.
- **<abbr title="Machine learning">ML</abbr>:** adatokból tanul mintázatokat, amelyekkel előrejelzéseket készít.
- **Mélytanulás (deep learning, <abbr title="Deep learning">DL</abbr>):** neuronok és szinapszisok működéséhez lazán hasonló, többrétegű neurális hálózatokra (neural networks) épül.
- **Generatív <abbr title="Artificial intelligence">AI</abbr>:** a deep learningre építve új tartalmat hoz létre.

Példák az <abbr title="Amazon Web Services">AWS</abbr> világából:

- Az **Amazon Rekognition** deep learning segítségével képeket, valamint tárolt és streamelt videókat elemez.
- Az **Amazon Q Developer** generatív <abbr title="Artificial intelligence">AI</abbr> használatával, megjegyzésekből és a meglévő kódból kiindulva valós időben ad kódjavaslatokat.

## Alapmodellek és nagy nyelvi modellek

Az **alapmodell (foundation model, <abbr title="Foundation model">FM</abbr>)** internetes léptékű adatmennyiségen előtanított, nagy méretű modell. Nem feltétlenül egyetlen feladatra készül: ugyanaz a modell több célra is adaptálható.

Az <abbr title="Foundation model">FM</abbr>-ek többféle modalitással (modality) dolgozhatnak:

- szöveg,
- kép,
- programkód,
- hang.

A **nagy nyelvi modell (large language model, <abbr title="Large language model">LLM</abbr>)** az <abbr title="Foundation model">FM</abbr>-ek egyik típusa. A mondat szavainak helyét és szövegkörnyezetét figyelembe véve a következő szót, pontosabban tokent jelzi előre. Ennek ismétlésével hoz létre új tartalmat.

### Hagyományos <abbr title="Machine learning">ML</abbr> és <abbr title="Foundation model">FM</abbr>-ek összevetése

| Szempont | Hagyományos <abbr title="Machine learning">ML</abbr> | <abbr title="Foundation model">FM</abbr>-re épülő generatív <abbr title="Artificial intelligence">AI</abbr> |
|---|---|---|
| Tipikus cél | Egy jól körülhatárolt feladat | Többféle feladat |
| Tanítás | Feladatspecifikus, gyakran címkézett adat | Nagy adatmennyiségen végzett előtanítás, majd adaptálás |
| Új feladat | Gyakran új modell vagy újratanítás kell | Sokszor prompttal vagy további finomhangolással (fine-tuning) megoldható |
| Kimenet | Előrejelzés, osztályozás | Új szöveg, kép, kód, hang stb. |

## Az <abbr title="Machine learning">ML</abbr> szerepe az Amazonnál

Az Amazon több mint húsz éve használ <abbr title="Artificial intelligence">AI</abbr>- és <abbr title="Machine learning">ML</abbr>-megoldásokat. A leckében szereplő példák:

- személyre szabott termékajánlások az Amazon webáruházban;
- robotok árumozgatási útvonalainak optimalizálása a logisztikai központokban;
- ellátási lánc (supply chain), kereslet-előrejelzés (demand forecasting) és kapacitástervezés (capacity planning);
- deep learning az Amazon Prime Air drónos kézbesítésében;
- számítógépes látás (computer vision) az Amazon Go üzletek pénztár nélküli működésében;
- több mint harminc <abbr title="Machine learning">ML</abbr>-rendszer együttműködése az Alexában.

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
| 2024 | Megjelennek a generatív <abbr title="Artificial intelligence">AI</abbr>-ra épülő Amazon Q asszisztensek, köztük az Amazon Q Developer és az Amazon Q Business. |

## Miért éppen most tört előre a generatív <abbr title="Artificial intelligence">AI</abbr>?

Nem egyetlen ok, hanem több tényező együttes hatása tette lehetővé a gyors fejlődést:

- A 2017-ben bemutatott **Transformer architektúra (Transformer architecture)** hatékonyabbá tette a nagyon nagy modellek tanítását.
- Jelentősen nőtt a számítási erőforrásokba (compute resources) és infrastruktúrába fektetett tőke.
- Nagyobb, specializált kutatói és mérnöki csapatok jöttek létre.
- A szervezetek hajlandóvá váltak nagyszabású, kockázatosabb kutatási ötleteket finanszírozni.

## Vizsgára érdemes megjegyezni

- A generatív <abbr title="Artificial intelligence">AI</abbr> az <abbr title="Artificial intelligence">AI</abbr>, az <abbr title="Machine learning">ML</abbr> és a deep learning hierarchiáján belül helyezkedik el.
- A hagyományos <abbr title="Machine learning">ML</abbr> fő célja tipikusan a **mintafelismerés (pattern recognition) és előrejelzés (prediction)**; a generatív <abbr title="Artificial intelligence">AI</abbr>-é az **új tartalom létrehozása (content generation)**.
- Az <abbr title="Foundation model">FM</abbr>-ek nagy adatmennyiségen előtanított, több célra adaptálható modellek.
- Az <abbr title="Large language model">LLM</abbr> az <abbr title="Foundation model">FM</abbr>-ek egyik típusa, nem az <abbr title="Foundation model">FM</abbr> szinonimája.
- A Transformer áttörése, a számítási erőforrások, a szakértői csapatok és a beruházási hajlandóság együtt gyorsították fel a generatív <abbr title="Artificial intelligence">AI</abbr> fejlődését.

## Gyors önellenőrzés

1. Mi a jellemzők és a címkék szerepe egy tanító adathalmazban?
2. Hogyan viszonyul egymáshoz az <abbr title="Artificial intelligence">AI</abbr>, az <abbr title="Machine learning">ML</abbr>, a deep learning és a generatív <abbr title="Artificial intelligence">AI</abbr>?
3. Miben tér el egy alapmodell a hagyományos, egyetlen feladatra tanított modelltől?
4. Miért nevezhető az <abbr title="Large language model">LLM</abbr> alapmodellnek, és hogyan állít elő szöveget?
5. Mely tényezők tették lehetővé a generatív <abbr title="Artificial intelligence">AI</abbr> közelmúltbeli gyors fejlődését?
