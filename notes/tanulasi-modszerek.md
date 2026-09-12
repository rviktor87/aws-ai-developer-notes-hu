# Tanulási módszerek

A jegyzetek akkor segítenek a legtöbbet, ha az olvasás mellett rendszeresen elő is kell hívni és alkalmazni kell a tanultakat. Az alábbi módszerek erre adnak használható keretet.

## 1. Aktív felidézés (retrieval practice)

Az önellenőrző kérdésekre először emlékezetből válaszolj. Csak ezután nyisd ki a rejtett megoldást és hasonlítsd össze a saját válaszoddal.

Az újraolvasás rövid távon könnyebbnek tűnhet, de az emlékezetből történő felidézés jobban támogathatja a tartós megjegyzést. Ezt mutatta ki Roediger és Karpicke tanulási kísérlete is: [Test-Enhanced Learning: Taking Memory Tests Improves Long-Term Retention](https://doi.org/10.1111/j.1467-9280.2006.01693.x).

## 2. Időben elosztott ismétlés (spaced practice)

Egy lehetséges ismétlési ütemezés:

| Ismétlés | Időpont |
|---:|---|
| 1. | a tanulás után 1 nappal |
| 2. | 3 nappal később |
| 3. | 7 nappal később |
| 4. | 14 nappal később |
| 5. | 30 nappal később |

Az időközöket a teljesítményhez érdemes igazítani. A nehezen felidézett anyag hamarabb, a biztosan tudott anyag később kerüljön elő. Az elosztott gyakorlás eredményeit Cepeda és munkatársai több kutatás alapján elemezték: [Distributed practice in verbal recall tasks](https://pubmed.ncbi.nlm.nih.gov/16719566/).

## 3. Bizonyossági értékelés

Minden önellenőrző válasz előtt becsüld meg, mennyire vagy biztos benne:

| Érték | Jelentés |
|---:|---|
| 0 | Nem tudom. |
| 1 | Bizonytalan vagyok. |
| 2 | Nagyjából tudom. |
| 3 | Biztosan tudom. |

A válasz ellenőrzése után jegyezd fel azt is, hogy helyes volt-e. A magas bizonyosság mellett adott hibás válasz külön figyelmet érdemel, mert valószínűleg tévesen rögzült tudás áll mögötte.

## 4. Hibanapló

A hibanaplóban minden fontosabb tévedéshez érdemes rögzíteni:

- a kérdést vagy feladatot;
- a hibás választ;
- a helyes választ;
- a tévedés okát;
- az összekevert fogalmakat;
- a következő ellenőrzés időpontját.

A cél nem minden apró hiba dokumentálása. Azokat a tévedéseket érdemes felvenni, amelyek fogalmi hiányosságot vagy visszatérő félreértést mutatnak.

## 5. Összehasonlító kérdések

A hasonló fogalmakat ne csak külön-külön tanuld meg. Hasonlítsd össze őket ugyanazon szempontok szerint, majd gyakorold annak eldöntését, hogy egy adott helyzetben melyik használható.

Példák:

- alapmodell (foundation model) és nagy nyelvi modell (large language model);
- tanítás (training), finomhangolás (fine-tuning) és következtetés (inference);
- Amazon Bedrock és Amazon SageMaker;
- tudásbázis (knowledge base) és vektoradatbázis (vector database).

Az összehasonlításban szerepelhet a cél, a bemenet, a kimenet, a szükséges adatok, a költség, a biztonság és egy jellemző használati eset.

## 6. Váltakozó gyakorlás (interleaving)

Egy gyakorlás során keverd össze az egymáshoz kapcsolódó, könnyen összetéveszthető témákat. Egy heti tesztben például több korábbi lecke kérdései is szerepelhetnek.

Nem érdemes teljesen független témákat véletlenszerűen összekeverni. A módszer elsősorban akkor hasznos, amikor hasonló fogalmak vagy megoldások közül kell választani. A kutatási eredmények területenként eltérnek: [A systematic review of interleaving as a concept learning strategy](https://strathprints.strath.ac.uk/75711/7/Firth_etal_RE_2021_A_systematic_review_of_interleaving.pdf).

## 7. Gyakorlati laborok (hands-on labs)

Minden fontosabb témához készülhet egy rövid gyakorlati feladat az alábbi felépítéssel:

1. cél;
2. szükséges [AWS]-szolgáltatások;
3. előfeltételek;
4. megvalósítási lépések;
5. elvárt eredmény;
6. ellenőrző kérdések;
7. a létrehozott erőforrások törlése.

Az erőforrások törlése kerüljön minden labor végére, hogy ne maradjanak szükségtelenül futó, költséget termelő szolgáltatások.

Az [AWS] Generative [AI] for Developers Professional Certificate gyakorlati feladatokat is használ az Amazon Bedrock alkalmazásprogramozási felületeinek (application programming interfaces) és az Amazon Q Developer használatának gyakorlására: [képzési leírás](https://aws.amazon.com/blogs/training-and-certification/aws-generative-ai-for-developers-professional-certificate/).

## 8. Saját magyarázat és architektúrarajz

Egy lecke befejezése után csukd be a tananyagot, majd emlékezetből:

1. foglald össze a témát 4-5 mondatban;
2. rajzold le a fontos összetevőket és kapcsolataikat;
3. írj egy konkrét használati példát;
4. hasonlítsd össze az eredményt a tananyaggal;
5. jelöld meg a hiányzó vagy pontatlan részeket.

Az architektúrarajznál ne a szép megjelenés legyen az elsődleges. Az a fontos, hogy kiderüljön, melyik komponens mit kap bemenetként, mit ad tovább, és hol történik adatkezelés vagy jogosultság-ellenőrzés (authorization check).

## Javasolt használat egy leckénél

1. Olvasd végig a leckét, és készíts jegyzetet.
2. Válaszolj az önellenőrző kérdésekre segítség nélkül.
3. Értékeld a bizonyosságodat 0 és 3 között.
4. Ellenőrizd a rejtett válaszokat.
5. Vedd fel a fontos tévedéseket a hibanaplóba.
6. Készíts egy rövid gyakorlati feladatot vagy architektúrarajzot.
7. Ütemezd be a következő ismétlést.

[AWS]: roviditesek.md#aws "Amazon Web Services"
[AI]: roviditesek.md#ai "Artificial intelligence"
