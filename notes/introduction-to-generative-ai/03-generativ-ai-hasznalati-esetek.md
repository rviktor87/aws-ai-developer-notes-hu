# Generatív [AI] használati esetek

> Kurzus: *Introduction to Generative [AI] - Art of the Possible* \
> Lecke: *Generative [AI] use cases* (4/10) \
>
Forrás: [AWS] [Skill Builder - kurzusadatlap](https://skillbuilder.aws/learn/ZEVZZ1D4AS/introduction-to-generative-ai--art-of-the-possible/Y7MTGJCW1U) \
> Jegyzet készült: 2026. szeptember 12. \
> Rövidítések: [rövidítésszótár](../roviditesek.md)

## Gazdasági hatás

A lecke szerint a generatív [AI] jelentős változásokat hozhat a világgazdaságban. A Goldman Sachs becslése alapján az
Egyesült Államok foglalkozásainak körülbelül kétharmadát egészítheti ki valamilyen [AI]-megoldás. A technológia meglévő
munkaköröket alakíthat át, és új feladatkörök megjelenéséhez is vezethet.

Ezek előrejelzések, ezért nem biztos eredményként kell kezelni őket. A következő időszakban várhatóan sok új
modellarchitektúrát és üzleti alkalmazást próbálnak majd ki.

## Üzleti használati esetek

### 1. Egészségügy

- Az [AWS] HealthScribe a beteg és az egészségügyi szakember beszélgetésének elemzésével segíthet klinikai jegyzeteket
  készíteni.
- A személyre szabott orvoslás (personalized medicine) a genetikai jellemzők, az életmód és a betegség alakulása alapján
  támogathatja a kezelési tervek létrehozását.
- Az [AI] javíthat, rekonstruálhat vagy előállíthat orvosi képeket, például röntgenfelvételeket, [MRI]-képeket és [CT]
  -felvételeket. Ezek segíthetik a diagnózist.

### 2. Élettudományok

- A gyógyszerkutatásban (drug discovery) új molekulaszerkezetek hozhatók létre, ami gyorsíthatja a lehetséges
  gyógyszerjelöltek keresését.
- A fehérjehajtogatás előrejelzése (protein folding prediction) az aminosavsorrend alapján becsüli meg a fehérjék
  háromdimenziós szerkezetét. Ez fontos lehet a betegségek megértésében és új terápiák fejlesztésében.
- A szintetikus biológia (synthetic biology) területén mesterséges biológiai rendszerek, például módosított élőlények
  vagy biológiai áramkörök tervei készíthetők.

### 3. Pénzügyi szolgáltatások

- A csalásfelderítés (fraud detection) szintetikus adathalmazokkal modellezhet különböző pénzmosási mintákat, így
  javíthatja az [AI]- és [ML]-rendszerek tanítását.
- A portfóliókezelésben (portfolio management) különböző piaci forgatókönyvek szimulálhatók, amelyek segíthetik a
  befektetési portfóliók kialakítását és kezelését.
- A követeléskezelésben (debt collection) kommunikációs és tárgyalási stratégiák készíthetők.

A leckében idézett 2023-as McKinsey-becslés szerint a felsorolt megoldások teljes körű bevezetése évente 200-340
milliárd dollárnyi értéket teremthetne a banki szektorban. Ez feltételes becslés, nem ténylegesen elért eredmény.

### 4. Gyártás

- A terméktervezésben (product design) megadott paraméterek és korlátozások alapján több tervváltozat készíthető. A
  változatok költség, anyaghasználat és teljesítmény szerint optimalizálhatók.
- A folyamatoptimalizálás (process optimization) eltérő gyártási forgatókönyveket modellezhet, majd költség, idő és
  erőforrás-felhasználás alapján kereshet hatékonyabb megoldást.
- A megelőző karbantartás (preventive maintenance) korábbi gyártási adatokból becsülheti meg a karbantartások megfelelő
  időpontját, így csökkentheti az állásidőt.
- Az anyagtudományban (materials science) kívánt tulajdonságokkal rendelkező új anyagösszetételek tervezhetők.

### 5. Kiskereskedelem

- Az ároptimalizálás (pricing optimization) különböző árképzési forgatókönyveket modellezhet.
- A virtuális termékpróba (virtual try-on) digitális vásárlói modellekkel javíthatja az online vásárlási élményt.
- Az üzletelrendezés optimalizálása (store layout optimization) segíthet hatékonyabb üzlettér kialakításában.
- A termékértékelések összegzése (product review summarization) gyorsabban áttekinthetővé teheti a vásárlói
  véleményeket.

A leckében idézett 2023-as McKinsey-becslés a generatív [AI] lehetséges éves hatását 400-660 milliárd dollárra teszi a
kiskereskedelmi és fogyasztási cikkeket gyártó ágazatokban. Ez szintén becslés.

### 6. Média és szórakoztatás

- A tartalomgenerálás (content generation) forgatókönyvek, párbeszédek és teljes történetek létrehozásában segíthet
  filmekhez, televíziós műsorokhoz és játékokhoz.
- A virtuális valóságban (virtual reality) interaktív környezetek készíthetők játékokhoz és szimulációkhoz.
- A hírgenerálás (news generation) nyers adatokból vagy eseményleírásokból hozhat létre hírcikkeket és összefoglalókat.

## Példa: Create With Alexa

A Create With Alexa funkcióval a felhasználók történeteket készíthetnek narratív ívvel, képekkel és háttérzenével. Az
animált történetek Amazon Echo Show eszközökön jelennek meg.

A rendszer több tartalomgenerátort és feldolgozási lépést kapcsol össze.

### 1. Történet létrehozása

A történetgenerátor két, előtanított nyelvi modellre épül:

1. A tervezőmodell (planner model) megkapja a felhasználó által kiválasztott promptokat, majd további kulcsszavakat
   készít és jelenetekhez rendeli őket. Ezek együtt alkotják a történet tervét.
2. A szöveggenerátor (text generator) megkapja a történet tervét, és elkészíti a történet szövegét. A tanításban témák
   szerint címkézett, emberek által írt történeteket használnak.

### 2. Jelenetek létrehozása

A szöveget két természetesnyelv-feldolgozó (natural language processing, [NLP]) modul dolgozza fel. Ezek feloldják a
névmási és más szöveges hivatkozásokat. Ha például a második jelenetben a "sellő" helyett csak az "ő" névmás szerepel, a
modul visszaírhatja a konkrét szereplőt. Ez egyértelműbb bemenetet ad a jelenetgenerátornak.

### 3. Zene létrehozása

- A rendszer hangszeres részletek nagy könyvtárából állít össze témát és zenei motívumot az egyes szereplőkhöz.
- Egy [AI]-alapú zenei hangszerelő rendszer (musical arrangement system) az akkordmenet, a ritmus és a hangszertípus
  alapján illeszti össze a részleteket.
- Egy szövegfelolvasó modell (text-to-speech model) megbecsüli a szöveg felolvasási idejét. Ez segít meghatározni a
  háttérzene hosszát és jellegét.
- Egy paralingvisztikai elemzőmodell (paralinguistic analysis model) több skálán értékeli a szöveget, például nyugodt
  vagy izgalmas, illetve szomorú vagy vidám jelleg szerint.

A lépések eredménye egy összehangolt történet, amelyben a szöveg, a jelenetek és a zene egymáshoz igazodik.

## Vizsgára érdemes megjegyezni

| Magyar                                                                                                                                                    | English                                                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| A lecke hat iparági területet mutat be: egészségügy, élettudományok, pénzügyi szolgáltatások, gyártás, kiskereskedelem, valamint média és szórakoztatás.  | The lesson presents six industry areas: healthcare, life sciences, financial services, manufacturing, retail, and media and entertainment. |
| A generatív [AI] szintetikus adatokat, terveket, szöveget, képet, zenét és szimulációkat is létrehozhat.                                                  | Generative [AI] can create synthetic data, designs, text, images, music, and simulations.                                                  |
| Az egészségügyben a klinikai dokumentáció, a személyre szabott kezelési tervek és az orvosi képalkotás a fő példák.                                       | Healthcare examples include clinical documentation, personalized treatment plans, and medical imaging.                                     |
| A gyártási példák a terméktervezésre, a folyamatoptimalizálásra, a megelőző karbantartásra és az anyagtudományra terjednek ki.                            | Manufacturing examples cover product design, process optimization, preventive maintenance, and materials science.                          |
| A Create With Alexa külön modelleket használ a történet megtervezéséhez, a szöveg létrehozásához, a jelenetek feldolgozásához és a zene összeállításához. | Create With Alexa uses separate models for story planning, text generation, scene processing, and music composition.                       |
| Az [NLP]-modulok a névmási és más szöveges hivatkozások feloldásával teszik egyértelműbbé a jelenetgenerátor bemenetét.                                   | The [NLP] modules resolve pronouns and other textual references to make the scene generator input clearer.                                 |
| A gazdasági adatok előrejelzések, amelyek a használati esetek széles körű bevezetését feltételezik.                                                       | The economic figures are forecasts that assume broad implementation of the use cases.                                                      |

## Gyors önellenőrzés

**1. Melyik hat iparági területet mutatja be a lecke?** \
*Which six industry areas does the lesson present?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Egészségügy, élettudományok, pénzügyi szolgáltatások, gyártás, kiskereskedelem, valamint média és
szórakoztatás.

**English:** Healthcare, life sciences, financial services, manufacturing, retail, and media and entertainment.

</details>

**2. Hogyan használható a generatív [AI] az egészségügyben?** \
*How can generative [AI] be used in healthcare?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Segíthet klinikai jegyzeteket készíteni, személyre szabott kezelési terveket létrehozni, valamint orvosi
képeket javítani, rekonstruálni vagy előállítani.

**English:** It can help create clinical notes and personalized treatment plans, as well as enhance, reconstruct, or
generate medical images.

</details>

**3. Mire használható a szintetikus adat a pénzügyi szolgáltatásokban?** \
*How can synthetic data be used in financial services?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Különböző pénzmosási minták szimulálására és a csalásfelderítő [AI]- és [ML]-rendszerek fejlesztésére.

**English:** It can simulate different money-laundering patterns and improve [AI] and [ML] fraud detection systems.

</details>

**4. Milyen kiskereskedelmi használati eseteket sorol fel a lecke?** \
*Which retail use cases does the lesson list?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Ároptimalizálást, virtuális termékpróbát, üzletelrendezés-optimalizálást és termékértékelések összegzését.

**English:** Pricing optimization, virtual try-ons, store layout optimization, and product review summarization.

</details>

**5. Mi történik a Create With Alexa történetkészítési lépésében?** \
*What happens during the story generation step in Create With Alexa?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A tervezőmodell a felhasználói promptokból jelenetekhez rendelt kulcsszavakat és történettervet készít. A
szöveggenerátor ebből hozza létre a történet szövegét.

**English:** The planner model turns the user prompts into scene-specific keywords and a story plan. The text generator
uses that plan to produce the story text.

</details>

**6. Hogyan igazítja a rendszer a zenét a történethez?** \
*How does the system adapt the music to the story?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A hangszerelő rendszer zenei részleteket kombinál, a szövegfelolvasó modell meghatározza a szükséges
időtartamot, a paralingvisztikai elemzés pedig a szöveg hangulata alapján segít kiválasztani a zene jellegét.

**English:** The arrangement system combines musical parts, the text-to-speech model determines the required duration,
and paralinguistic analysis helps select the character of the music from the tone of the text.

</details>

## Kapcsolódó anyagok

- [Generative AI customer stories on AWS](https://aws.amazon.com/ai/generative-ai/customers/)
- [The economic potential of generative AI](https://www.mckinsey.com/capabilities/mckinsey-digital/our-insights/the-economic-potential-of-generative-AI-the-next-productivity-frontier)
- [The science behind Alexa's interactive story-creation experience](https://www.amazon.science/blog/the-science-behind-alexas-new-interactive-story-creation-experience)

[AWS]: ../roviditesek.md#aws "Amazon Web Services"
[AI]: ../roviditesek.md#ai "Artificial intelligence"
[ML]: ../roviditesek.md#ml "Machine learning"
[NLP]: ../roviditesek.md#nlp "Natural language processing"
[MRI]: ../roviditesek.md#mri "Magnetic resonance imaging"
[CT]: ../roviditesek.md#ct "Computed tomography"
