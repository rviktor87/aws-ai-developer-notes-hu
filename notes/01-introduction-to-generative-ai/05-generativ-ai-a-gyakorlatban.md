# Generatív [AI] a gyakorlatban

> Kurzus: *Introduction to Generative [AI] - Art of the Possible* \
> Lecke: *Generative [AI] in Practice* (6/10) \
> Forrás: [AWS] [Skill Builder - kurzusadatlap](https://skillbuilder.aws/learn/ZEVZZ1D4AS/introduction-to-generative-ai--art-of-the-possible/Y7MTGJCW1U) \
> Jegyzet készült: 2026. szeptember 12. \
> Rövidítések: [rövidítésszótár](../roviditesek.md)

## A lecke helyzete

Az AnyCompany nevű, kitalált cipőmárka új városi sétacipőt készül piacra vinni. A lecke ezen a termékbevezetésen
keresztül mutatja be, hogyan használhatók az alapmodellek (foundation models, [FM]) a termék teljes életciklusa alatt.

A négy bemutatott feladattípus:

1. tartalomösszegzés (content summarization)
2. tartalomgenerálás (content generation)
3. kódgenerálás (code generation)
4. kérdés-válasz (question and answer)

## 1. Piackutatás összegzése

A termékcsapat részletes piackutatást készített. A vezetőségnek szánt bemutatóhoz nincs szükség a teljes anyagra, ezért
egy [FM]-t kérnek meg magas szintű összefoglaló és piacelemzés készítésére.

A prompt három lényeges részt tartalmaz:

- a feladatot: összegzés és elemzés
- a bemenetet: a részletes piackutatási jelentést
- a célt és a közönséget: vezetőknek készülő prezentáció

A modell kimenete kiemeli a jelentés fontos megállapításait, így a csapat rövidebb anyagból készülhet a vezetőségi
egyeztetésre.

### A példakimenet számai

A bemutatott modellválasz 12 százalékos piaci növekedést és egy 63 százalékos fogyasztói arányt említ. Ezek a lecke
szemléltető modellkimenetének részei. A kurzus nem ad hozzájuk ellenőrizhető kutatási forrást, ezért nem szabad őket
valós piaci adatként használni.

## 2. Tartalomgenerálás

Miután a termék megkapta a jóváhagyást, a csapat többféle marketinganyagot készít ugyanabból a termékleírásból.

### Weboldal szövege

A prompt felsorolja a cipő használati helyét és jellemzőit: londoni séta, kényelem, tartósság, hálós anyag, gumitalp és
fényvisszaverő biztonsági elem. A modell ezekből weboldalon használható termékleírást készít. A kimenet gyors
kiindulópont, amelyet a csapat szükség esetén szerkeszthet.

### Közösségimédia-bejegyzés

A következő prompt az előző válasz adataira hivatkozik, és közösségi médiára szánt termékbejelentést kér. A modell az
adott beszélgetés korábbi információit használja, ezért nem kell minden termékjellemzőt újra megadni.

Ez a példa a beszélgetési kontextus (conversation context) használatát mutatja. A kontextus elérhetősége az alkalmazás
és a modell beállításaitól függ, nem korlátlan emlékezetet jelent.

### Termékkép

A csapatnak nincs ideje és költségkerete londoni fotózásra. Egy meglévő stúdiófotót csatolnak, majd azt kérik a
képgeneráló [AI]-tól, hogy londoni hátterű termékfotóként stilizálja.

Itt a prompt mellett egy kép is bemenetként szolgál. A feladat nem teljesen új kép létrehozása, hanem a csatolt kép
átalakítása a kívánt vizuális környezethez.

## 3. Kódgenerálás

A termék megjelenése után a csapat a közösségi médiából származó hangulatelemzési adatokat (sentiment data) egy Amazon
Simple Storage Service ([S3]) tárolóba szeretné feltölteni. Az Amazon Q Developer egy rövid utasítás alapján Python-kódot
generál a fájlfeltöltéshez.

A bemutatott kód a `boto3` könyvtárral hoz létre [S3]-ügyfelet, majd az `upload_file` művelettel feltölt egy helyi
fájlt egy megadott tárolóba és objektumkulcsra.

A példakód csak a művelet alapját szemlélteti. Éles használatnál külön kell kezelni többek között a hitelesítést, a
jogosultságokat, a konfigurációt és a hibákat.

## 4. Kérdés-válasz

A vállalat egy [AI]-alapú chatbotot helyez el a weboldalán. A lecke szerint a modellt a termékvonalak és az
ügyféladatbázis adataival finomhangolták (fine-tuning). A példában a vásárló a legutóbbi rendelése nyomkövetési számát
kéri, a chatbot pedig személyre szabott rendelési adatokat ad vissza.

A bemutató nem részletezi, hogyan kapcsolódik a modell az aktuális ügyféladatokhoz. Valós rendszerben a hozzáférést,
az adatok naprakész lekérését, valamint az azonosítási és jogosultsági ellenőrzéseket külön meg kell tervezni. A
finomhangolás önmagában nem helyettesíti ezeket.

## Mit mutat meg együtt a példa?

Ugyanaz a generatív [AI]-megoldás több csapat munkáját is támogathatja:

- a termékcsapat összefoglalót készít
- a marketingcsapat szöveget és képet hoz létre
- a fejlesztők kódot generálnak
- az ügyfélszolgálat személyre szabott választ ad

A jó prompt megnevezi a feladatot, megadja a szükséges hátteret és leírja a kívánt kimenetet. A létrehozott tartalmat
ettől függetlenül ellenőrizni és a felhasználási helyzethez igazítani kell.

## Vizsgára érdemes megjegyezni

| Magyar | English |
|---|---|
| A lecke négy feladattípust mutat be: tartalomösszegzés, tartalomgenerálás, kódgenerálás és kérdés-válasz. | The lesson presents four task types: content summarization, content generation, code generation, and question and answer. |
| A tartalomösszegzés hosszú piackutatási jelentésből vezetői összefoglalót készít. | Content summarization turns a long market research report into an executive summary. |
| Egy beszélgetés következő promptja hivatkozhat a korábbi válaszban szereplő adatokra, ha az alkalmazás megőrzi a kontextust. | A later prompt in a conversation can refer to information in an earlier response when the application preserves the context. |
| A képgenerálási példában egy csatolt stúdiófotót alakítanak át londoni hátterű termékképpé. | In the image generation example, an attached studio photo is transformed into a product image with a London background. |
| Az Amazon Q Developer Python-kódot generál fájlok [S3]-ba történő feltöltéséhez. | Amazon Q Developer generates Python code for uploading files to [S3]. |
| A kérdés-válasz példa személyre szabott rendelési adatot ad vissza, de a lecke nem részletezi az adatkapcsolat megvalósítását. | The question-and-answer example returns personalized order information, but the lesson does not describe how the data connection is implemented. |
| A modell által előállított számokat és állításokat felhasználás előtt ellenőrizni kell. | Numbers and claims produced by the model must be verified before use. |

## Gyors önellenőrzés

**1. Melyik négy generatív [AI]-feladatot mutatja be a lecke?** \
*Which four generative [AI] tasks does the lesson present?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Tartalomösszegzést, tartalomgenerálást, kódgenerálást és kérdés-válasz feladatot.

**English:** Content summarization, content generation, code generation, and question and answer.

</details>

**2. Miért szerepel a vezetőség a tartalomösszegző promptban?** \
*Why are executives mentioned in the content summarization prompt?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Meghatározza a kimenet közönségét és célját, így a modell magas szintű, prezentációhoz használható
összefoglalót készíthet.

**English:** It defines the audience and purpose of the output, helping the model produce a high-level summary suitable
for a presentation.

</details>

**3. Mit szemléltet a közösségimédia-bejegyzés promptja?** \
*What does the social media post prompt demonstrate?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Azt, hogy a modell ugyanazon beszélgetés korábbi termékadatait is felhasználhatja, ha azok a kontextusban
maradnak.

**English:** It shows that the model can use product information from earlier in the same conversation when it remains
in the context.

</details>

**4. Miben különbözik a termékképes példa a teljesen új kép létrehozásától?** \
*How does the product image example differ from creating an entirely new image?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A modell egy csatolt stúdiófotót alakít át, és ahhoz készít londoni hátteret.

**English:** The model transforms an attached studio photo and adds a London background to it.

</details>

**5. Mit tesz az Amazon Q Developer által generált Python-kód?** \
*What does the Python code generated by Amazon Q Developer do?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** `boto3` segítségével [S3]-ügyfelet hoz létre, majd feltölt egy helyi fájlt egy [S3]-tárolóba.

**English:** It uses `boto3` to create an [S3] client and then uploads a local file to an [S3] bucket.

</details>

**6. Mi hiányzik a chatbotpélda technikai leírásából?** \
*What is missing from the technical description of the chatbot example?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Nem derül ki, hogyan éri el a modell az aktuális ügyfél- és rendelési adatokat, illetve hogyan történik az
azonosítás és a jogosultságok ellenőrzése.

**English:** It does not explain how the model accesses current customer and order data or how authentication and
authorization are enforced.

</details>

**7. Miért nem kezelhetők valós piaci adatként a példakimenet százalékai?** \
*Why should the percentages in the example output not be treated as real market data?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Mert egy szemléltető modellválasz részei, és a kurzus nem ad hozzájuk ellenőrizhető kutatási forrást.

**English:** They are part of an illustrative model response, and the course does not provide a verifiable research
source for them.

</details>

[AWS]: ../roviditesek.md#aws "Amazon Web Services"
[AI]: ../roviditesek.md#ai "Artificial intelligence"
[FM]: ../roviditesek.md#fm "Foundation model"
[S3]: ../roviditesek.md#s3 "Amazon Simple Storage Service"
