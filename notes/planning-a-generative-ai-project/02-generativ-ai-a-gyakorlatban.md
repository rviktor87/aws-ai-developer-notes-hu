# Generatív [AI] a gyakorlatban

> Kurzus: *Planning a Generative [AI] Project* \
> Lecke: *Generative [AI] in Practice* \
> Forrás: [AWS] [Skill Builder - kurzusadatlap](https://skillbuilder.aws/learn/HU1FQRGDDZ/planning-a-generative-ai-project/SYR3SCPSHC) \
> Jegyzet készült: 2026. szeptember 12. \
> Rövidítések: [rövidítésszótár](../roviditesek.md)

## A mondatkiegészítési példa

A lecke azt mutatja be, hogyan egészít ki egy transzformermodell (transformer model) egy mondatot a következő szó
előrejelzésével (next-word prediction). A bemenet egy angol nyelvű analógia:

> A puppy is to dog as kitten is to ...

A várt folytatás a `cat`, mert a `puppy` és a `dog` közötti kapcsolat megfelel a `kitten` és a `cat` közötti
kapcsolatnak.

A feldolgozás fő lépései:

1. bemenet
2. tokenizálás és kódolás
3. szóbeágyazás
4. dekódolás
5. kimenet

## 1. Bemenet

A bemenet (input) a modellnek átadott adat vagy utasítás. Ebben a példában a felhasználó egy hiányos mondatot ad meg,
és azt várja, hogy a generatív [AI] következtessen a hiányzó szóra.

## 2. Tokenizálás és kódolás

A tokenizálás (tokenization) során a modell kisebb egységekre, tokenekre (tokens) bontja a bemenetet. Egy token lehet
teljes szó, szórész (subword), kifejezés vagy akár egy írásjel. A tokenizálás egységesebb formát ad a bemenetnek, így azt
a modell fel tudja dolgozni.

A példamondat lehetséges tokenjei:

`A`, `puppy`, `is`, `to`, `dog`, `as`, `kitten`, `is`, `to`

A kódolás (encoding) minden tokenhez numerikus reprezentációt rendel. A leckében látható tokenazonosítók egy
szemléltető tokenizálási eredmény részei. Más tokenizáló (tokenizer) vagy szókészlet használatakor eltérő felbontás és
azonosítók készülhetnek.

### A tokenek költséghatása

A feldolgozott tokenek száma összefügg a modell számítási igényével. Emiatt a tokenmennyiség pénzügyi szempont is lehet
az előtanítás és a modellhasználat tervezésekor. A pontos elszámolás a választott szolgáltatástól és modelltől függ.

## 3. Szóbeágyazás

A szóbeágyazás (word embedding) a tokeneket többdimenziós numerikus vektorokká alakítja. A vektor (vector) egy szó vagy
token matematikai reprezentációja egy n dimenziós térben.

A hasonló jelentésű szavak reprezentációi jellemzően közelebb kerülnek egymáshoz a vektortérben (vector space). A lecke
ezt térképi koordinátákhoz hasonlítja. A `cat` és a `feline` várhatóan közelebb helyezkedik el egymáshoz, mint a `dog`
és a `kitten`.

A beágyazások alapján a modell már nem pusztán szöveges elemeket lát. Numerikus formában tudja vizsgálni a jelentésbeli
kapcsolatokat és a bemeneti sorozat kontextusát.

## 4. Dekódolás

A dekódoló (decoder) a vektorreprezentációk alapján becsüli meg a kívánt kimenetet. Beépített figyelmi mechanizmusok
(attention mechanisms) segítségével a bemenet különböző részeire összpontosít, majd matematikai módszerekkel értékeli a
lehetséges folytatásokat.

A példában a modell felismeri a következő kapcsolatot:

`puppy : dog = kitten : ?`

A lecke a `cat`, `bird`, `bear` és `human` szavakat mutatja lehetséges jelöltként. A `cat` kapja a legmagasabb értéket,
ezért ezt választja a modell. A megjelenített számok csak szemléltető értékek, nem egy megnevezett modell tényleges
valószínűségei.

## 5. Kimenet

A kimenet (output) a kiválasztott következő szóval kiegészített mondat:

> A puppy is to dog as kitten is to cat.

A folyamat szöveggeneráláskor ismétlődik. A modell minden lépésben a rendelkezésre álló kontextus alapján választja ki
a következő tokent.

## Miért alkalmas erre a transzformer?

A transzformerek a tanítás során a bemenet elemeit párhuzamosan tudják feldolgozni. Ez eltér a korábbi visszacsatolt
neurális hálózatoktól (recurrent neural networks), amelyek sorban haladnak végig a szekvencia elemein. A párhuzamos
feldolgozás jól méretezhető tanítást tesz lehetővé.

Az alapmodellek (foundation models, [FM]) hosszú tanítása és finomhangolása (fine-tuning) miatt sokféle bemenetre tudnak
hihető választ adni. A hihető megfogalmazás azonban nem jelenti automatikusan, hogy a válasz helyes.

## Vizsgára érdemes megjegyezni

| Magyar | English |
|---|---|
| A mondatkiegészítés lépései: bemenet, tokenizálás és kódolás, szóbeágyazás, dekódolás, majd kimenet. | The sentence completion process consists of input, tokenization and encoding, word embedding, decoding, and output. |
| A token lehet szó, szórész, kifejezés vagy írásjel. | A token can be a word, subword, phrase, or punctuation mark. |
| A kódolás numerikus azonosítót vagy reprezentációt rendel a tokenekhez. | Encoding assigns a numerical identifier or representation to tokens. |
| A többdimenziós beágyazásokban a hasonló jelentésű elemek jellemzően közelebb helyezkednek el egymáshoz. | In multidimensional embeddings, items with similar meanings are generally located closer together. |
| A dekódoló a bemenet reprezentációiból értékeli a lehetséges folytatásokat, és kiválaszt egy következő tokent. | The decoder evaluates possible continuations from the input representations and selects a next token. |
| A tokenek száma hatással van a számítási igényre, ezért költségtervezési szempont is. | Token count affects computational demand and is therefore a cost-planning consideration. |
| A transzformerek párhuzamos feldolgozhatósága támogatja a nagy léptékű tanítást. | The parallel processing capability of transformers supports large-scale training. |

## Gyors önellenőrzés

**1. Milyen feldolgozási lépéseken halad át a bemeneti mondat?** \
*Which processing steps does the input sentence pass through?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Bemenet, tokenizálás és kódolás, szóbeágyazás, dekódolás, majd kimenet.

**English:** Input, tokenization and encoding, word embedding, decoding, and output.

</details>

**2. Mi lehet token?** \
*What can be a token?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Teljes szó, szórész, kifejezés vagy akár egy írásjel.

**English:** A complete word, a subword, a phrase, or even a punctuation mark.

</details>

**3. Miért alakítja a modell numerikus vektorokká a tokeneket?** \
*Why does the model turn tokens into numerical vectors?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Így matematikai formában tudja feldolgozni a jelentésbeli kapcsolatokat és a szövegkörnyezetet.

**English:** This lets it process semantic relationships and textual context in a mathematical form.

</details>

**4. Mit jelent a vektortérben lévő közelség?** \
*What does proximity in vector space represent?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A közel elhelyezkedő vektorokhoz tartozó szavak vagy tokenek jellemzően hasonló jelentésűek.

**English:** Words or tokens represented by nearby vectors generally have similar meanings.

</details>

**5. Hogyan választja ki a dekódoló a következő szót?** \
*How does the decoder select the next word?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A bemenet vektorreprezentációi és a kontextus alapján értékeli a lehetséges folytatásokat, majd kiválasztja
a legmagasabbra értékelt jelöltet.

**English:** It evaluates possible continuations from the vector representations and context, then selects the
highest-ranked candidate.

</details>

**6. Miért számít költségtervezési tényezőnek a tokenek száma?** \
*Why is token count a cost-planning factor?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** Mert a feldolgozott tokenek mennyisége összefügg a modell számítási igényével.

**English:** The number of processed tokens is related to the model's computational requirements.

</details>

**7. Miért nem szabad a hihető választ automatikusan helyesnek tekinteni?** \
*Why should a plausible answer not automatically be considered correct?*

<details>
<summary>Válasz (Answer)</summary>

**Magyar:** A modell valószínű folytatást állít elő a tanult minták alapján, ezért tényszerűen hibás válasz is hangozhat
meggyőzően.

**English:** The model produces a likely continuation from learned patterns, so a factually incorrect answer can still
sound convincing.

</details>

[AWS]: ../roviditesek.md#aws "Amazon Web Services"
[AI]: ../roviditesek.md#ai "Artificial intelligence"
[FM]: ../roviditesek.md#fm "Foundation model"
