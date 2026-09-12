# Generatív [AI] kontextus

> Kurzus: *Planning a Generative [AI] Project* \
> Lecke: *Generative [AI] Context* \
> Forrás: [AWS] [Skill Builder - kurzusadatlap](https://skillbuilder.aws/learn/HU1FQRGDDZ/planning-a-generative-ai-project/SYR3SCPSHC) \
> Jegyzet készült: 2026. szeptember 12. \
> Rövidítések: [rövidítésszótár](../roviditesek.md)

## Mi a kontextus?

A kontextus (context) az az információ, amelyet a modell az aktuális munkamenetben egy válasz elkészítéséhez figyelembe
tud venni. Ide tartozik a felhasználó mostani kérése, a beszélgetés korábbi fordulói és minden további háttéradat,
amelyet az alkalmazás a modellnek átad.

A releváns kontextus pontosabb kimenetet eredményezhet. Különösen hasznos lehet:

- vállalatspecifikus adatok használatakor
- tartalomgenerálásnál
- virtuális asszisztenseknél
- kreatív tervezésnél

Ezekben a feladatokban a rövid vagy általános utasítás gyakran nem tartalmaz elég részletet a kívánt válaszhoz.

## A kontextus korlátai

A lecke a kontextust a modellel folytatott egyedi munkamenetként írja le. Két fontos korlátot emel ki:

1. **Nem marad meg automatikusan új beszélgetésben.** Az új munkamenet alaphelyzetből indul, ezért a korábban megadott
   információra nem lehet automatikusan hivatkozni.
2. **Véges a befogadható tokenek száma.** A kontextusablak (context window) csak meghatározott mennyiségű tokent tud
   kezelni. Hosszú beszélgetésben a korai információ kikerülhet a modell számára elérhető tartományból.

Az alkalmazás külön tárolhat korábbi adatokat, majd egy új kérésnél ismét átadhatja őket a modellnek. Ez azonban az
alkalmazás által kialakított állapotkezelés, nem a modell korlátlan vagy automatikus emlékezete.

## Állásinterjús hasonlat

A lecke egy állásinterjúhoz hasonlítja a munkamenetet. Az interjú ideje véges, és minden új interjúztatónak újra el kell
mondani a szükséges hátteret. A következő interjúztató nem ismeri az előző beszélgetésben elhangzott példákat.

Ugyanez történik egy új modellmunkamenet kezdetén. Ha az alkalmazás nem adja át újra a korábbi információt, a modell nem
tud arra építeni.

## Hogyan használja a modell a beszélgetés előzményeit?

A lecke Seattle-ről szóló, kétfordulós beszélgetést mutat be.

### Első forduló

A felhasználó Seattle legjobb meglátogatandó helyéről kérdez. A modell a Columbia Centert ajánlja, és megemlíti a városi
kilátást.

### Második forduló

A felhasználó ezt kérdezi:

> Will this be fun for children?

A `this` szó önmagában nem nevezi meg a helyet. A modellnek a korábbi válasz alapján kell felismernie, hogy a Columbia
Centerre utal.

Ez a hivatkozásfeloldás (coreference resolution) egyszerű példája. A transzformermodell (transformer model) a szavak
jelentését, helyzetét és a beszélgetés korábbi részeit együtt vizsgálja. Ennek alapján kapcsolja a névmást vagy mutató
szót egy korábban említett elemhez.

## Miért hibázhat a modell?

A kontextus használata természetesebb párbeszédet tesz lehetővé, mert nem kell minden mondatban megismételni az összes
előzményt. A feloldás azonban nem mindig egyértelmű. A modell téves elemhez kötheti a hivatkozást, ha:

- több lehetséges előzmény szerepel a beszélgetésben
- a kérdés túl általános
- a fontos részlet már nincs a kontextusablakban
- az utalás nyelvileg vagy tartalmilag kétértelmű

Ilyenkor pontosabb megnevezéssel vagy a szükséges háttér megismétlésével csökkenthető a félreértés esélye.

## Gyakorlati következmények projekttervezésnél

A kontextus kezelését már a generatív [AI]-projekt tervezésekor át kell gondolni:

- milyen háttéradat szükséges a válaszhoz
- mely korábbi üzenetek maradjanak a kérésben
- hogyan fér el a szükséges információ a kontextusablakban
- mit kell összefoglalni vagy ismét betölteni
- hogyan választja szét az alkalmazás a különböző felhasználók beszélgetéseit
- milyen bizalmas vagy személyes adat kerülhet a kontextusba

A több háttéradat nem automatikusan jelent jobb eredményt. A modell számára releváns, pontos és jól rendezett
információt érdemes átadni.

## Vizsgára érdemes megjegyezni

| Magyar | English |
|---|---|
| A kontextus az aktuális válaszhoz elérhető utasításokat, beszélgetési előzményeket és háttéradatokat jelenti. | Context consists of the instructions, conversation history, and background information available for the current response. |
| A releváns, vállalatspecifikus kontextus pontosabb modellkimenetet eredményezhet. | Relevant, business-specific context can produce more precise model output. |
| A korábbi beszélgetés tartalma nem marad meg automatikusan egy új munkamenetben. | Content from a previous conversation does not automatically persist into a new session. |
| A kontextusablakban tárolható tokenek száma véges, ezért a modell elveszítheti a korán megadott információt. | The context window has a finite token limit, so the model can lose information provided early in the conversation. |
| A modell a szavak jelentése, helyzete és az előzmények alapján oldhatja fel az olyan hivatkozásokat, mint a `this`. | The model can resolve references such as `this` by using word meaning, position, and conversation history. |
| A túl általános vagy kétértelmű kérdés hibás hivatkozásfeloldáshoz vezethet. | A vague or ambiguous question can lead to incorrect reference resolution. |

## Gyors önellenőrzés

**1. Mit jelent a kontextus egy generatív [AI]-beszélgetésben?** \
*What does context mean in a generative [AI] conversation?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Az aktuális válaszhoz elérhető kérést, beszélgetési előzményeket és további háttéradatokat.

**English:** The current request, conversation history, and additional background information available for the
response.

</details>

**2. Mi történik a kontextussal egy új munkamenet kezdetén?** \
*What happens to context when a new session starts?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Nem kerül át automatikusan az új munkamenetbe. A szükséges információt az alkalmazásnak vagy a
felhasználónak ismét meg kell adnia.

**English:** It is not transferred automatically to the new session. The application or user must provide the required
information again.

</details>

**3. Mi a kontextusablak?** \
*What is a context window?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Az a véges tartomány, amely meghatározza, hogy a modell egyszerre mennyi tokennyi információt tud figyelembe
venni.

**English:** The finite range that determines how many tokens of information the model can consider at one time.

</details>

**4. Mire utal a `this` szó a Seattle-példában?** \
*What does the word `this` refer to in the Seattle example?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A korábbi válaszban ajánlott Columbia Centerre.

**English:** The Columbia Center recommended in the previous response.

</details>

**5. Milyen információ alapján oldja fel a modell a `this` hivatkozást?** \
*What information does the model use to resolve the reference `this`?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A szavak jelentése, mondatbeli helyzete és az aktuális beszélgetés korábbi tartalma alapján.

**English:** Word meaning, position in the sentence, and the earlier content of the current conversation.

</details>

**6. Hogyan csökkenthető a kétértelmű hivatkozásokból eredő hiba?** \
*How can errors caused by ambiguous references be reduced?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A hivatkozott elem pontos megnevezésével vagy a szükséges háttér rövid megismétlésével.

**English:** By naming the referenced item explicitly or briefly repeating the necessary background.

</details>

[AWS]: ../roviditesek.md#aws "Amazon Web Services"
[AI]: ../roviditesek.md#ai "Artificial intelligence"
