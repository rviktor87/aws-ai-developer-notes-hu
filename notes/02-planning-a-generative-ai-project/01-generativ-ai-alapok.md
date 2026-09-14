# Generatív [AI] alapok

> Kurzus: *Planning a Generative [AI] Project* \
> Lecke: *Generative [AI] Fundamentals* \
> Forrás: [AWS] [Skill Builder - kurzusadatlap](https://skillbuilder.aws/learn/HU1FQRGDDZ/planning-a-generative-ai-project/SYR3SCPSHC) \
> Jegyzet készült: 2026. szeptember 12. \
> Rövidítések: [rövidítésszótár](../roviditesek.md)

## Alapmodellek

Az alapmodell (foundation model, [FM]) nagy mennyiségű adaton előre betanított gépi tanulási (machine learning, [ML])
modell. Nem egyetlen feladatra készül: különböző további feladatokhoz igazítható.

### Az adatoktól a feladatokig

A lecke öt lépésben mutatja be az [FM] működésének alapját:

1. **Címkézetlen adat (unlabeled data):** nyers kép, szöveg vagy videó, amelyhez nem tartozik a tartalmát magyarázó
   címke.
2. **Előtanítás (pretraining):** a modellt nagy mennyiségű adaton tanítják, hogy használható tudásreprezentációt
   alakítson ki.
3. **Alapmodell:** az eredmény egy nagy mennyiségű, általános témájú adaton tanított [FM].
4. **Adaptálás (adaptation):** a modell promptok segítségével egy adott feladathoz igazítható.
5. **Általános feladatok:** az [FM] többek között összegzésre, tartalom- és kódgenerálásra, valamint kérdések
   megválaszolására használható.

## Az alapmodellek képességkategóriái

### Kódgenerálás

Egy [FM] programkódot is létrehozhat. A lecke az Amazon Kiro fejlesztői eszközt említi példaként, amely az integrált
fejlesztői környezetben (integrated development environment, [IDE]) használható. Más modellek az [IDE]-n kívül is
képesek kódot generálni.

### Tartalomgenerálás

Ez a kategória szöveges és vizuális tartalmak széles körét foglalja magában. Ide tartozhat blogbejegyzés,
közösségimédia-frissítés, e-mailes hírlevél, kép, illusztráció, embléma vagy más grafikai terv.

### Tartalomösszegzés

Az [FM] jelentési adatokból, megbeszélések jegyzőkönyvéből vagy hosszabb cikkekből rövidebb összefoglalót készíthet.
Ez időt takaríthat meg, de az összegzés pontosságát továbbra is ellenőrizni kell.

### Kérdés-válasz

Ebbe a kategóriába tartoznak például a chatbotok. Egy vállalkozás az ügyfélút egyszerűsítésére és a működési költségek
csökkentésére használhat ilyen megoldást.

## Előtanítás

Az előtanítás során terabájtnyi címkézetlen szöveges vagy multimodális adattal (multimodal data) tanítják a modellt. A
multimodális adatok között kép, hang és videó is lehet. Az adat származhat nyilvánosan bejárható internetes forrásból
vagy hozzáférhető saját adatból.

A címkézetlen adatok nagy mennyiségben könnyebben beszerezhetők, mint a címkézettek. Egy címkézett képadatbázisnál
embereknek kell például minden kutyát ábrázoló képhez hozzáadniuk a megfelelő címkét. Ez idő- és munkaigényes.

Az előtanítás alatt a modell a szekvenciális adatok összefüggéseit tanulja. Szövegnél figyelembe veszi a szavak
helyzetét és környezetét, majd ezek alapján tanulja meg a következő szó előrejelzését.

### A modellméret szerepe

Egy több milliárd paraméteres modell a lecke szerint gazdagabb és mélyebb kontextust tud tárolni, mint egy kisebb
adathalmazon tanított, kisebb modell. Egy ilyen modell előtanításához két alapvető feltétel szükséges:

1. elegendő mennyiségű és megfelelő minőségű tanítóadat, a releváns adatok összegyűjtésével, feldolgozásával és a
   duplikátumok eltávolításával
2. nagy léptékű tanítási infrastruktúra (large-scale training infrastructure)

A több paraméter önmagában nem biztosít jobb eredményt. Az adatminőség és a feladathoz való illeszkedés is számít.

## Transzformerarchitektúra

A transzformerarchitektúra (transformer architecture) olyan neurális hálózati felépítés, amely jól méretezhető,
párhuzamosítható, és képes a bemeneti, illetve kimeneti adatok közötti összefüggések modellezésére.

### Párhuzamos tanítás

A transzformer nem feltétlenül dolgozza fel a szavakat egyenként, szigorúan egymás után. A tanítás során a teljes
bemenetet egyszerre kezelheti, ezért a számítás több grafikus feldolgozóegységen (graphics processing unit, [GPU])
párhuzamosítható. Ez rövidebb tanítási időt és nagy adatmennyiségnél jobb méretezhetőséget tesz lehetővé.

### Jelentés és pozíció

A pozícióinformáció megmutatja, hol található egy szó a bemeneti sorozatban. A modell ennek segítségével a szavak
fontosságát és egymáshoz való viszonyát is figyelembe veheti.

A pozíciókódolás (positional encoding) segít elkülöníteni az azonos alakú, de eltérő jelentésű szavakat. A lecke angol
példájában a `bank` egyszer pénzintézetet, egyszer folyópartot jelent. A környező szavak és a mondatbeli helyzet alapján
a modell különbséget tud tenni a két jelentés között.

### Megjegyzés a lecke harmadik lenyitható részéhez

A rész címe egyszerre több dologra irányuló figyelmet említ, a hozzá tartozó magyarázat azonban ismét a
pozíciókódolást és a `bank` szó eltérő jelentéseit mutatja be. A lecke ezen a ponton nem fejti ki külön a többfejes
figyelem (multi-head attention) működését.

## Vizsgára érdemes megjegyezni

| Magyar | English |
|---|---|
| Az [FM] nagy mennyiségű adaton előre betanított [ML]-modell, amely sokféle további feladathoz igazítható. | An [FM] is an [ML] model pretrained on a large amount of data and adaptable to many downstream tasks. |
| A folyamat fő lépései: címkézetlen adat, előtanítás, alapmodell, adaptálás és a modell alkalmazása különböző feladatokra. | The main flow is unlabeled data, pretraining, a foundation model, adaptation, and application to different tasks. |
| A négy képességkategória a kódgenerálás, a tartalomgenerálás, a tartalomösszegzés és a kérdés-válasz. | The four capability categories are code generation, content generation, content summarization, and question and answer. |
| Az előtanítás nagy mennyiségű címkézetlen szöveget vagy multimodális adatot használ. | Pretraining uses large amounts of unlabeled text or multimodal data. |
| Nagy modellek tanításához megfelelő mennyiségű és minőségű adat, valamint nagy léptékű infrastruktúra szükséges. | Training large models requires sufficient high-quality data and large-scale infrastructure. |
| A transzformerek tanítása jól párhuzamosítható, ezért nagy adatmennyiségnél hatékonyan méretezhetők. | Transformer training is highly parallelizable, so it can scale efficiently to large amounts of data. |
| A pozícióinformáció és a szövegkörnyezet segít a szavak közötti kapcsolatok és az eltérő jelentések felismerésében. | Positional information and context help identify relationships between words and distinguish different meanings. |

## Gyors önellenőrzés

**1. Mi az alapmodell?** \
*What is a foundation model?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Nagy mennyiségű adaton előre betanított [ML]-modell, amely különböző további feladatokhoz igazítható.

**English:** An [ML] model pretrained on a large amount of data that can be adapted to different downstream tasks.

</details>

**2. Melyik öt lépés vezet a címkézetlen adattól az általános feladatokig?** \
*Which five steps lead from unlabeled data to general tasks?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Címkézetlen adat, előtanítás, alapmodell, adaptálás és a modell használata különböző általános feladatokra.

**English:** Unlabeled data, pretraining, a foundation model, adaptation, and use of the model for different general
tasks.

</details>

**3. Melyik négy alapmodell-képességet emeli ki a lecke?** \
*Which four foundation model capabilities does the lesson highlight?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Kódgenerálást, tartalomgenerálást, tartalomösszegzést és kérdés-válasz feladatokat.

**English:** Code generation, content generation, content summarization, and question and answer.

</details>

**4. Miért használnak nagy mennyiségű címkézetlen adatot az előtanításhoz?** \
*Why is a large amount of unlabeled data used for pretraining?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Mert nagy mennyiségben egyszerűbben beszerezhető, míg a címkézett adatok elkészítéséhez jelentős emberi
munka szükséges.

**English:** It is easier to obtain at scale, whereas creating labeled data requires substantial human effort.

</details>

**5. Mi kell egy több milliárd paraméteres modell előtanításához?** \
*What is required to pretrain a model with billions of parameters?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Elegendő mennyiségű, megfelelő minőségű és feldolgozott tanítóadat, valamint nagy léptékű tanítási
infrastruktúra.

**English:** A sufficient quantity of high-quality, processed training data and large-scale training infrastructure.

</details>

**6. Miért taníthatók hatékonyan párhuzamosan a transzformerek?** \
*Why can transformers be trained efficiently in parallel?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Mert a bemenetet nem kizárólag elemenként, szigorúan egymás után dolgozzák fel, így a számítás több [GPU]-n
is végezhető.

**English:** They do not process the input only one element at a time in strict sequence, so computation can run across
multiple [GPU]s.

</details>

**7. Mire szolgál a pozíciókódolás?** \
*What is positional encoding used for?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Információt ad az elemek sorozatbeli helyéről, és segít a szövegkörnyezet, a szókapcsolatok, valamint az
eltérő jelentések felismerésében.

**English:** It provides information about the position of elements in a sequence and helps identify context,
relationships between words, and different meanings.

</details>

## Kapcsolódó anyag

- [What are Foundation Models?](https://aws.amazon.com/what-is/foundation-models/)

[AWS]: ../roviditesek.md#aws "Amazon Web Services"
[AI]: ../roviditesek.md#ai "Artificial intelligence"
[ML]: ../roviditesek.md#ml "Machine learning"
[FM]: ../roviditesek.md#fm "Foundation model"
[IDE]: ../roviditesek.md#ide "Integrated development environment"
[GPU]: ../roviditesek.md#gpu "Graphics processing unit"
