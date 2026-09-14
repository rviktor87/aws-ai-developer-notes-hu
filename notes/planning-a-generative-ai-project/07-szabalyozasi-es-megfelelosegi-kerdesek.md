# Szabályozási és megfelelőségi kérdések

> Kurzus: *Planning a Generative [AI] Project* \
> Lecke: *Regulatory and Compliance Issues* \
> Forrás: [AWS] [Skill Builder - kurzusadatlap](https://skillbuilder.aws/learn/HU1FQRGDDZ/planning-a-generative-ai-project/SYR3SCPSHC) \
> Jegyzet készült: 2026. szeptember 14. \
> Rövidítések: [rövidítésszótár](../roviditesek.md)

## Miért része a megfelelés a projekttervezésnek?

A generatív [AI]-projektet nem lehet a jogi és iparági környezettől függetlenül megtervezni. Egy chatbot, egy
tartalomgeneráló eszköz vagy egy adatelemző rendszer más adatokat kezelhet, más emberekre lehet hatással, és eltérő
előírások alá eshet.

A megfelelés (compliance) azért fontos, mert:

- csökkenti a jogsértés és a szankció kockázatát
- védi a felhasználók személyes adatait
- segít fenntartani az ügyfelek és más érintettek bizalmát
- dokumentálhatóbbá és ellenőrizhetőbbé teszi a rendszer működését

Nincs egyetlen, az egész világon egységes [AI]-szabályozás. A szervezetnek a működési helye, az érintett felhasználók,
az adatok és az iparág alapján kell meghatároznia az alkalmazandó követelményeket.

## Gyorsan változó szabályozási környezet

A lecke kiemeli, hogy a kormányok és más szervezetek folyamatosan alakítják az [AI] fejlesztésére és használatára
vonatkozó kereteket. Az Európai Unió (European Union) külön [AI]-szabályozást dolgozott ki, máshol pedig meglévő
adatvédelmi, fogyasztóvédelmi vagy ágazati jogszabályok vonatkozhatnak az algoritmikus döntésekre.

A jogszabályok követése nem egyszeri feladat. A projektnek kezelnie kell a későbbi szabályváltozásokat, az új
hatósági értelmezéseket és az iparági előírások módosulását is.

## Adatvédelmi követelmények

A generatív [AI] tervezésekor át kell gondolni az adatok teljes útját:

1. honnan származik az adat
2. milyen jogalappal gyűjtik és használják
3. hol és meddig tárolják
4. ki férhet hozzá
5. milyen feldolgozási műveleteket végeznek rajta
6. hogyan teljesítik az érintetti kérelmeket

A tanítóadat forrását és feldolgozását dokumentálni kell. A rendszer tervezésének része az adatvédelem beépítése
(privacy by design), valamint annak átlátható közlése, hogyan használja az [AI] a személyes információt.

### Általános adatvédelmi rendelet (General Data Protection Regulation, [GDPR])

[GDPR] az Európai Gazdasági Térségben (European Economic Area, [EEA]) élő természetes személyek adatainak kezelésére
állapít meg követelményeket. A lecke az alábbi
érintetti jogokat emeli ki:

- hozzáférés
- helyesbítés
- törlés

A szervezetekre adatkezelési alapelvek, elszámoltathatósági és átláthatósági kötelezettségek is vonatkoznak. A rendelet
pontos hatályát mindig az adott adatkezelésre kell megvizsgálni.

### Kaliforniai fogyasztói adatvédelmi törvény (California Consumer Privacy Act, [CCPA])

[CCPA] a hatálya alá tartozó vállalkozások adatgyűjtésére, adatfelhasználására,
értékesítésére és megosztására vonatkozó szabályokat tartalmaz. A leckében szereplő fő követelmények:

- egyértelmű adatvédelmi tájékoztató
- hozzáférési és törlési kérelmek teljesítése
- lehetőség az adatok értékesítésének vagy megosztásának letiltására

A kurzus az automatizált döntéshozatali technológiával (Automated Decisionmaking Technology, [ADMT]) és a
kiberbiztonsági kockázatértékeléssel kapcsolatos újabb szabályokat is megemlíti.

## Iparágspecifikus előírások

Az általános [AI]- és adatvédelmi szabályok mellett az adott ágazat saját követelményeit is alkalmazni kell.

### Egészségügy

Az Egyesült Államokban a Health Insurance Portability and Accountability Act ([HIPAA]) szabályai vonatkozhatnak a
védett egészségügyi adatok kezelésére. Egy egészségügyi [AI]-rendszernél betegbizalmasságra, erős biztonsági védelemre
és pontos orvosi információra van szükség.

### Pénzügy

A Fair Credit Reporting Act ([FCRA]) és az azt végrehajtó Regulation V követelményei érinthetik a fogyasztói
hitelinformációt használó rendszereket. Egy hiteldöntést támogató [AI]-nál meg kell előzni a diszkriminatív működést,
folyamatos megfigyelést kell kialakítani, és meg kell őrizni az auditnyomot (audit trail).

## Megfelelési gyakorlatok

A lecke hat alapvető lépést sorol fel:

1. A bevezetés előtt készüljön részletes adatvédelmi hatásvizsgálat (privacy impact assessment).
2. Minden adatforrást és feldolgozási tevékenységet dokumentáljanak.
3. Vezessenek be erős adatbiztonsági intézkedéseket.
4. Készüljön egyértelmű szabályzat a modell tanítására és telepítésére.
5. Az [AI]-rendszert rendszeresen auditálják és figyeljék.
6. A végfelhasználók kapjanak átlátható tájékoztatást az [AI] használatáról.

Ezt támogathatja megfelelőségkezelő szoftver (compliance management software), rendszeres munkatársi képzés és [AI]
szabályozásában jártas jogi szakértő. Az iparági szövetségek és hatóságok közleményeit is követni kell.

## A lecke esettanulmányai

### Tanítóadat helytelen kezelése

A kurzus szerint 2023-ban több vállalat kapott jelentős bírságot [AI]-tanítóadatok szabálytalan kezelése miatt. A
bemutatott példában egy egészségügyi startup nem védte megfelelően a modellhez használt betegadatot, ami többmilliós
bírsághoz és hírnévromláshoz vezetett.

A lecke nem nevezi meg a vállalatot és nem ad ellenőrizhető forrást az esethez. Emiatt ezt szemléltető példaként, nem
azonosított jogesetként érdemes kezelni.

### Sikeres bevezetés

Egy pénzügyi szolgáltató generatív [AI]-chatbotot vezetett be. A szabályozási követelményeket már a tervezés kezdetén
figyelembe vette, erős adatvédelmi intézkedéseket alkalmazott, és egyértelmű dokumentációt vezetett a megfelelési
tevékenységekről.

A két példa közös tanulsága, hogy a megfelelés nem a telepítés előtti utolsó ellenőrzés. A projekt teljes életciklusában
tervezni, dokumentálni és felülvizsgálni kell.

## Aktualitási megjegyzés, 2026. szeptember 14.

Ez a rész a kurzus tartalmán túlmutató, hivatalos forrásokkal ellenőrzött kiegészítés.

- Az uniós mesterségesintelligencia-rendelet 2024. augusztus 1-jén lépett hatályba, és főszabály szerint 2026. augusztus
  2-től alkalmazandó. Egyes rendelkezések korábban, a nagy kockázatú rendszerek bizonyos szabályai pedig későbbi
  időpontban alkalmazandók. A határidőt az adott rendszer besorolása alapján kell ellenőrizni.
- A kaliforniai [ADMT]-, kockázatértékelési és kiberbiztonsági előírásokat tartalmazó szabálycsomag 2026. január 1-jén
  lépett hatályba. Egyes kötelezettségekhez későbbi teljesítési határidő tartozik, az [ADMT]-re vonatkozó követelményeket
  pedig az érintett vállalkozásoknak 2027. január 1-jétől kell alkalmazniuk.
- A Regulation V jelenlegi változata 2026. január 1-jei módosításokat is tartalmaz, ezért pénzügyi projektben mindig az
  aktuális szöveget kell ellenőrizni.

Ez a jegyzet tanulási segédlet, nem jogi tanács. Egy valós projektben jogi szakértőnek kell meghatároznia a rendszerre
vonatkozó szabályokat és határidőket.

## Vizsgára érdemes megjegyezni

| Magyar | English |
|---|---|
| Nincs egyetlen globális [AI]-szabályozás, ezért a működési hely, az adatok, a felhasználók és az iparág alapján kell meghatározni a követelményeket. | There is no single global [AI] regulation, so requirements must be identified from the operating location, data, users, and industry. |
| Az adatvédelem kiterjed az adatgyűjtésre, a források dokumentálására, a tárolásra, a felhasználásra és az érintetti kérelmekre. | Data privacy covers data collection, source documentation, storage, use, and data-subject requests. |
| A [GDPR] hozzáférési, helyesbítési és törlési jogokat biztosít, valamint elszámoltathatóságot és átláthatóságot követel meg. | The [GDPR] provides rights of access, correction, and erasure and requires accountability and transparency. |
| A [CCPA] többek között hozzáférési, törlési és bizonyos adatértékesítési vagy adatmegosztási letiltási jogokat biztosít. | The [CCPA] provides rights including access, deletion, and certain opt-outs from data sale or sharing. |
| Az egészségügyi és pénzügyi projektekre az általános szabályok mellett ágazati előírások, például a [HIPAA] és az [FCRA] is vonatkozhatnak. | Healthcare and financial projects may also be subject to sector rules such as [HIPAA] and [FCRA]. |
| A megfeleléshez hatásvizsgálat, dokumentáció, adatbiztonság, egyértelmű szabályzat, rendszeres audit és felhasználói átláthatóság szükséges. | Compliance requires impact assessment, documentation, data security, clear policies, regular audits, and transparency to users. |
| A szabályozási megfelelést a projekt teljes életciklusában kezelni kell. | Regulatory compliance must be managed throughout the project lifecycle. |

## Gyors önellenőrzés

**1. Miért nincs egyetlen megfelelési ellenőrzőlista minden generatív [AI]-projekthez?** \
*Why is there no single compliance checklist for every generative [AI] project?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Mert az alkalmazandó szabályok a működési helytől, az érintett személyektől, az adatoktól, az iparágtól és
a rendszer használati módjától függenek.

**English:** Applicable rules depend on the operating location, affected people, data, industry, and how the system is
used.

</details>

**2. Mit kell dokumentálni a tanítóadatokkal kapcsolatban?** \
*What should be documented about training data?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Az adatok forrását, gyűjtésének és használatának jogalapját, tárolását, hozzáférését és minden feldolgozási
tevékenységet.

**English:** Data sources, the legal basis for collection and use, storage, access, and all processing activities.

</details>

**3. Melyik három érintetti jogot emeli ki a lecke a [GDPR] kapcsán?** \
*Which three data-subject rights does the lesson highlight under the [GDPR]?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A hozzáférés, a helyesbítés és a törlés jogát.

**English:** The rights of access, correction, and erasure.

</details>

**4. Milyen alapvető jogokat emel ki a lecke a [CCPA] kapcsán?** \
*Which basic rights does the lesson highlight under the [CCPA]?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A személyes adatokhoz való hozzáférést, az adatok törlését, valamint az értékesítés vagy megosztás bizonyos
eseteinek letiltását.

**English:** Access to personal data, deletion, and certain opt-outs from the sale or sharing of data.

</details>

**5. Melyik két iparágspecifikus amerikai törvényt említi a lecke?** \
*Which two industry-specific United States laws does the lesson mention?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Az egészségügyben a [HIPAA] szabályait, a pénzügyben pedig az [FCRA] követelményeit.

**English:** [HIPAA] in healthcare and [FCRA] in finance.

</details>

**6. Melyik hat megfelelési gyakorlatot sorolja fel a lecke?** \
*Which six compliance practices does the lesson list?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Adatvédelmi hatásvizsgálat, adatforrások és feldolgozás dokumentálása, erős adatbiztonság, tanítási és
telepítési szabályzat, rendszeres audit és megfigyelés, valamint átlátható felhasználói tájékoztatás.

**English:** Privacy impact assessment, documentation of data sources and processing, strong data security, training
and deployment policies, regular auditing and monitoring, and transparent user communication.

</details>

**7. Mi a két esettanulmány közös tanulsága?** \
*What is the shared lesson from the two case studies?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A szabályozási és adatvédelmi követelményeket a projekt kezdetétől figyelembe kell venni, majd a döntéseket
és intézkedéseket végig dokumentálni kell.

**English:** Regulatory and privacy requirements must be considered from the start of the project, and decisions and
controls must be documented throughout.

</details>

## Hivatalos források

- [Az általános adatvédelmi rendelet szövege](https://eur-lex.europa.eu/eli/reg/2016/679/oj)
- [Az uniós mesterségesintelligencia-rendelet és alkalmazási idővonala](https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai)
- [California Consumer Privacy Act](https://oag.ca.gov/privacy/ccpa)
- [Kaliforniai szabálycsomag](https://cppa.ca.gov/regulations/ccpa_updates.html): [ADMT], kockázatértékelés és kiberbiztonsági audit
- [HHS információs oldal](https://www.hhs.gov/hipaa/index.html) a [HIPAA] szabályairól
- [Fair Credit Reporting, Regulation V](https://www.consumerfinance.gov/rules-policy/regulations/1022/)

[AWS]: ../roviditesek.md#aws "Amazon Web Services"
[AI]: ../roviditesek.md#ai "Artificial intelligence"
[GDPR]: ../roviditesek.md#gdpr "General Data Protection Regulation"
[EEA]: ../roviditesek.md#eea "European Economic Area"
[CCPA]: ../roviditesek.md#ccpa "California Consumer Privacy Act"
[ADMT]: ../roviditesek.md#admt "Automated Decisionmaking Technology"
[HIPAA]: ../roviditesek.md#hipaa "Health Insurance Portability and Accountability Act"
[FCRA]: ../roviditesek.md#fcra "Fair Credit Reporting Act"
