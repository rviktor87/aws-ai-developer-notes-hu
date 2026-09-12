# A generatív [AI]-projekt tervezésének lépései

> Kurzus: *Planning a Generative [AI] Project* \
> Lecke: *Steps in Planning a Generative [AI] Project* \
> Forrás: [AWS] [Skill Builder - kurzusadatlap](https://skillbuilder.aws/learn/HU1FQRGDDZ/planning-a-generative-ai-project/SYR3SCPSHC) \
> Jegyzet készült: 2026. szeptember 12. \
> Rövidítések: [rövidítésszótár](../roviditesek.md)

## A tervezési folyamat

A lecke négy fő lépésre bontja a generatív [AI]-projekt tervezését:

1. a hatókör meghatározása
2. a modell kiválasztása
3. a modell adaptálása
4. a modell használata és követése

A folyamat az üzleti problémából indul. Ezután lehet eldönteni, hogy elegendő-e egy előtanított modell promptokkal és
további kontextussal, vagy finomhangolásra is szükség van. Az elkészült megoldást végül be kell építeni az alkalmazásba,
majd használat közben is figyelni kell.

## 1. A hatókör meghatározása

A hatókör (scope) kijelöli, milyen problémát old meg a projekt, kiknek készül, és mit tekint a szervezet sikernek. A jól
meghatározott hatókör segít abban, hogy a projekt fókuszált, releváns és megvalósítható maradjon.

A lecke a kiinduló szempontokat három csoportba rendezi:

- ügyfél
- bevétel
- költség

### Akarják ezt az ügyfelek?

Az ügyfél nézőpontjából ezekre a kérdésekre kell válaszolni:

- Milyen problémát próbálunk megoldani?
- Milyen eredményt szeretnénk elérni az ügyfél számára?
- Kik a megoldás célzott ügyfelei?

### Képes erre a szervezet?

Ez a megvalósítás nehézségét, időigényét és erőforrásigényét vizsgálja:

- Milyen belső irányítási vagy szabályzati akadályok vannak?
- Honnan származik a projekt finanszírozása?
- Melyek a legnagyobb technikai vagy mérnöki kihívások?

### Érdemes ezt megvalósítani?

Itt az üzleti életképesség (business viability) kerül előtérbe:

- Miért használnák az ügyfelek ismételten a megoldást?
- Kik a legfontosabb versenytársak?
- Miért ajánlanák az ügyfelek másoknak a szolgáltatást?

E kérdések alapján ellenőrizhető, hogy a projekt üzleti szempontból is indokolható-e, és lehet-e belőle fenntartható
bevételi forrás.

### Rövid és hosszú távú hatás

Nem minden megoldás azonos idő alatt hoz eredményt. A lecke két példát állít egymás mellé:

- **Gyorsabban bevezethető megoldás:** az Amazon Kiro programozási segéd néhány lépésben beépíthető a fejlesztői
  munkafolyamatba, így hamar javíthatja a termelékenységet.
- **Összetettebb megoldás:** egy testreszabott [AI]-asszisztens több időt és pénzt igényelhet, különösen további tanítás
  vagy finomhangolás esetén, de a jobb ügyfélélményen keresztül bevételi hatása is lehet.

A bemutatott helyzetben a lecke a két munka párhuzamos végzését javasolja: a fejlesztők gyors eredményt kapnak a Kiro
használatával, miközben a gépi tanulási (machine learning, [ML]) csapat megtervezi az ügyfélélményt javító megoldást.

## 2. A modell kiválasztása

A fő döntés az egyszerű használat és a testreszabhatóság közötti kompromisszum (trade-off).

| Megközelítés | Mikor lehet megfelelő? | Hátrány vagy költség |
|---|---|---|
| Előtanított modell változtatás nélkül | Általános feladathoz, kevés testreszabási igénynél, amikor fontos a gyors bevezetés | Kevésbé igazodik a szervezet egyedi feladatához |
| Meglévő modell finomhangolása | Speciális feladathoz és erősen testreszabott kimenethez | Több számítási kapacitást, szakértelmet, időt és jó minőségű adatot igényel |

A döntést a kívánt ügyfélmegoldásból visszafelé érdemes felépíteni. Először azt kell tisztázni, milyen kérdésekre
válaszoljon az [AI]-asszisztens, majd azt, honnan származik a szükséges adat.

### Visszakereséssel kiegészített generálás

A visszakereséssel kiegészített generálás (Retrieval-Augmented Generation, [RAG]) során egy előtanított modell a kéréshez
kapcsolódó külső dokumentumokat kap további kontextusként. A lecke példájában ezek a szervezet saját dokumentumai. Így a
modell szervezetspecifikus információ alapján válaszolhat anélkül, hogy feltétlenül módosítani kellene a paramétereit.

## 3. A modell adaptálása

A modellkimenet két fő módon szabható a feladathoz.

### Prompttervezés

A prompttervezés (prompt engineering) a modellnek adott utasítások és bemenetek megtervezése, kipróbálása és finomítása.
Már kisebb nyelvi változtatás is jelentősen módosíthatja a kimenet minőségét.

Ez illik a lecke [AI]-asszisztens példájához: a megoldás előtanított modellt, utasítást adó promptokat és [RAG]-gel
betöltött saját adatokat használ.

### Finomhangolás

A finomhangolás (fine-tuning) az előtanítás folytatása. A folyamat módosítja a modell paramétereit, és egy adott
megoldáshoz igazított, új modellváltozatot hoz létre. Jó minőségű, címkézett és használatieset-specifikus adatra van
szüksége.

Nagy modell esetén a finomhangolás jelentős költséggel járhat. Emellett szabályozni kell a tanítóadatok minőségének
fenntartását is.

## 4. A modell használata

A telepítés után a projekt nem tekinthető lezártnak. A lecke négy működtetési kérdést emel ki:

1. Kezeltük a felelős [AI]-val kapcsolatos kockázatokat?
2. Van tervünk a felhasználói visszajelzések gyűjtésére és feldolgozására?
3. Hogyan követjük az [FM] teljesítményét időben?
4. Hogyan követjük az alapul szolgáló előtanított modell változásait, és mikor tanítjuk újra a finomhangolt modellt?

Ezek a kérdések a folyamatos modellfelügyelet (model monitoring), a visszajelzési folyamat és a verziókövetés
szükségességére mutatnak rá.

## Döntési összefoglaló

| Igény | Valószínű megközelítés |
|---|---|
| Általános feladat, gyors bevezetés | Előtanított modell változtatás nélkül |
| Jobb utasításkövetés vagy pontosabb formátum | Prompttervezés |
| Saját, naprakész dokumentumok használata | Előtanított modell és [RAG] |
| Erősen speciális viselkedés, amely paramétermódosítást igényel | Finomhangolás |

Ez iránymutatás, nem automatikus döntési szabály. A végső választást a minőségi elvárás, az adatok, a költség, a
határidő és a csapat szakértelme együtt határozza meg.

## Vizsgára érdemes megjegyezni

| Magyar | English |
|---|---|
| A tervezés négy lépése a hatókör meghatározása, a modell kiválasztása, az adaptálás, majd a modell használata és követése. | The four planning steps are defining the scope, selecting a model, adapting it, and then using and monitoring the model. |
| A hatókör vizsgálja az ügyféligényt, a szervezet megvalósítási képességét és az üzleti életképességet. | Scoping examines customer demand, the organization's ability to implement the solution, and business viability. |
| Az előtanított modell gyors és általános megoldás, a finomhangolás nagyobb rugalmasságot ad több erőforrásért cserébe. | A pretrained model is a fast, general solution, while fine-tuning offers more flexibility at the cost of additional resources. |
| A [RAG] saját dokumentumokat adhat kontextusként az előtanított modellnek a paraméterek módosítása nélkül. | [RAG] can provide proprietary documents as context to a pretrained model without changing its parameters. |
| A prompttervezés a bemenet megfogalmazásának módosításával javítja a kimenetet. | Prompt engineering improves output by changing how the input is written. |
| A finomhangolás módosítja a modell paramétereit, és jó minőségű, címkézett adatot igényel. | Fine-tuning changes model parameters and requires high-quality labeled data. |
| Telepítés után kezelni kell a felelős [AI] kérdéseit, a visszajelzéseket, a teljesítménykövetést és a modellváltozásokat. | After deployment, responsible [AI], feedback, performance monitoring, and model changes must be managed. |

## Gyors önellenőrzés

**1. Melyik négy fő lépésből áll a generatív [AI]-projekt tervezése?** \
*What are the four main steps in planning a generative [AI] project?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A hatókör meghatározása, a modell kiválasztása, a modell adaptálása, majd a használat és a folyamatos
követés.

**English:** Define the scope, select the model, adapt the model, and then use and continuously monitor it.

</details>

**2. Milyen három nézőpontból kell vizsgálni a projekt hatókörét?** \
*From which three perspectives should the project scope be examined?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Az ügyféligény, a szervezet megvalósítási képessége és az üzleti életképesség szempontjából.

**English:** Customer demand, the organization's implementation capability, and business viability.

</details>

**3. Mikor lehet megfelelő egy előtanított modell változtatás nélküli használata?** \
*When can using a pretrained model as is be appropriate?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Általános feladatnál, kevés testreszabási igénynél, amikor fontos a gyors bevezetés.

**English:** For a general task with minimal customization needs when rapid implementation is important.

</details>

**4. Mi a különbség a [RAG] és a finomhangolás között?** \
*What is the difference between [RAG] and fine-tuning?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A [RAG] külső adatot ad kontextusként a modellnek, míg a finomhangolás tanítással módosítja a modell
paramétereit.

**English:** [RAG] provides external data to the model as context, while fine-tuning changes the model's parameters
through training.

</details>

**5. Mit jelent a prompttervezés?** \
*What is prompt engineering?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A modellnek adott utasítások és bemenetek megtervezését, kipróbálását és finomítását a kívánt kimenet
eléréséhez.

**English:** Designing, testing, and refining model instructions and inputs to achieve the desired output.

</details>

**6. Milyen adat szükséges a finomhangoláshoz a lecke szerint?** \
*What data does fine-tuning require according to the lesson?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Jó minőségű, címkézett és az adott használati esethez kapcsolódó adat.

**English:** High-quality, labeled data related to the specific use case.

</details>

**7. Milyen kérdéseket kell feltenni a modell használatba vétele után?** \
*Which questions should be asked after putting the model into use?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Kezeltük-e a felelős [AI] kockázatait, hogyan gyűjtjük a visszajelzést, miként követjük az [FM]
teljesítményét, és hogyan kezeljük az alapmodell változásait, illetve az újratanítást?

**English:** Have responsible [AI] risks been addressed, how will feedback be collected, how will [FM] performance be
tracked, and how will base-model changes and retraining be managed?

</details>

[AWS]: ../roviditesek.md#aws "Amazon Web Services"
[AI]: ../roviditesek.md#ai "Artificial intelligence"
[ML]: ../roviditesek.md#ml "Machine learning"
[FM]: ../roviditesek.md#fm "Foundation model"
[RAG]: ../roviditesek.md#rag "Retrieval-Augmented Generation"
