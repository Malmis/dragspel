# Dragspel

Ett webbaserat verktyg som spelar upp melodier, basgångar och trummor utifrån noter som du skriver in i en textruta. Allt ljud syntetiseras i webbläsaren med Web Audio API, så inga ljudfiler behövs och ingen installation krävs.

Språk: svenska och English (väljs i rullistan högst upp på sidan).

🇬🇧 Read this in English: [README.en.md](README.en.md)

---

## Komma igång

1. Spara koden som `dragspel.html`.
2. Dubbelklicka på filen så att den öppnas i en webbläsare (Chrome, Edge, Firefox eller Safari).
3. Klicka på **Spela**. Standardmelodin, ett riff i E-moll, spelas direkt.

Ljudet startar först när du klickar på en knapp. Det är en säkerhetsregel i webbläsare, så om du inte hör något, klicka på **Spela** en gång till.

---

## Sidans delar

| Del | Vad den gör |
|---|---|
| **Språkväxlare** | Byter mellan Svenska och English. Alla texter, instrument och felmeddelanden byts. |
| **Textrutan** | Här skriver du noterna, en rad per takt. |
| **Melodi** | Instrument för den övre stämman: Dragspel, Trumpet, Munspel eller Saxofon. |
| **Bas** | Instrument för den undre stämman, med samma val. |
| **Trummor** | Av, Rock 4/4, Polka eller Swing. |
| **Volym melodi / bas / trummor** | Reglage för att balansera mixen (0 till 1,5). |
| **Tempo (BPM)** | Slag per minut. Standard är 180. |
| **Balgens tremolo** | Hur mycket volymen pulserar när instrumentet är Dragspel. Påverkar inte de andra instrumenten. |
| **Antal varv** | Hur många gånger melodin spelas. Sätt 0 för att loopa tills du stoppar. |
| **Paus mellan varv** | Vilopaus i taktslag mellan varven. 0 ger en sömlös loop. |
| **Spela / Stoppa** | Startar och avbryter uppspelningen. |
| **Statusrad** | Visar varv, takt och ackord för takten som hörs just nu. |

---

## Så skriver du noter

### Grundformat

Varje rad är en takt, uppdelad i kolumnerna:

```
Takt | Ackord | Melodi | Bas
```

Exempel:

```
1 | C | C4 1 E4 1 G4 1 C5 1 | C3 1 G2 1 C3 1 G2 1
```

- **Takt** är takt­numret. Det används bara för läsbarhet och för felmeddelanden.
- **Ackord** visas i statusraden under uppspelningen. Det spelas inte upp.
- **Melodi** är den övre stämman.
- **Bas** är den undre stämman.

Kolumnerna kan separeras med `|` eller med tabb. Du kan klistra in direkt från ett kalkylblad.

### Noter och längder

En not skrivs som **tonnamn följt av oktav**, sedan **längd i taktslag**:

- `C4 1` betyder C i oktav 4, en taktslag lång.
- `F#3 0.5` betyder F# i oktav 3, en halv taktslag lång.
- `Bb4 2` betyder B-platt i oktav 4, två taktslag lång.

Längderna är i taktslag, där 1 är en kvartsnot i 4/4:

| Längd | Notvärde (i 4/4) |
|---|---|
| `4` | helnot |
| `2` | halvnot |
| `1` | kvartsnot |
| `0.5` | åttondelsnot |
| `1.5` | punkterad kvart |

Paus skrivs som `R` följt av längden, till exempel `R 1` för en kvarts paus.

Halvtoner skrivs med `#` (höjt) eller `b` (sänkt). Oktaven styr vilken C som menas. Mellan-C är `C4`.

### Regler som måste följas

1. **Melodi och bas på samma rad måste summera till samma antal taktslag.** Annars visas ett felmeddelande, till exempel "Takt 3: melodin har 3 taktslag men basen 4".
2. **Varje not behöver en längd.** `C4 E4` är fel, `C4 1 E4 1` är rätt.
3. **I 4/4-takt** ska varje rad summera till 4. Tre taktslag är ok om du vill skriva i 3/4, då ska båda stämmorna summera till 3.
4. **Rader utan siffror hoppas över.** Du kan skriva rubriker som `Takt | Ackord | Melodi | Bas` utan att det stör.

### Tips för att få loopen att låta bra

- Låt den sista takten sluta på den tonika som första takten börjar på, till exempel C i en låt i C-dur.
- Om melodin slutar för tidigt eller för sent, lägg till en paus med `R` eller justera längden på sista noten.
- Behöver du en paus mellan varven, använd fältet **Paus mellan varv** i stället för att lägga in pauser i noterna.

---

## Instrument och trummor

- **Dragspel:** Två något stämda sågvågor med balgtremolo. Basen låter mörkare och mjukare.
- **Trumpet:** Ljus klang med vibrato och ett filter som öppnar sig i början av tonen.
- **Munspel:** Skarp, nasal klang, lite vibrato.
- **Saxofon:** Varm klang med långsam attack och vibrato.
- **Trummor:** Rock 4/4, Polka och Swing består av syntetiserad bastrumma, virveltrumma och hi-hat. Av stänger av trummorna.

Ljuden är syntetiska approximationer. De går att känna igen som respektive instrument men är inga inspelningar.

---

## Exempelmelodier

Alla exempel nedan är gemensam egendom eller egna kompositioner. De är skrivna från minnet och kan behöva justeras mot ett notblad. Kopiera hela blocket till textrutan och klicka på **Spela**.

### 1. Frère Jacques (fransk folkvisa, C-dur, 8 takter)

Passar bra för att testa instrumenten. Tempo 100 till 120 BPM. Melodi på Dragspel eller Trumpet, bas på Dragspel, trummor på Polka eller Av.

```
1 | C | C4 1 D4 1 E4 1 C4 1 | C3 1 C3 1 C3 1 C3 1
2 | C | C4 1 D4 1 E4 1 C4 1 | C3 1 C3 1 C3 1 C3 1
3 | G | E4 1 F4 1 G4 2 | G2 1 B2 1 G2 2
4 | G | E4 1 F4 1 G4 2 | G2 1 B2 1 G2 2
5 | C | G4 0.5 A4 0.5 G4 0.5 F4 0.5 E4 1 C4 1 | C3 1 E3 1 G3 1 C3 1
6 | C | G4 0.5 A4 0.5 G4 0.5 F4 0.5 E4 1 C4 1 | C3 1 E3 1 G3 1 C3 1
7 | C | C4 1 G3 1 C4 2 | C3 1 G2 1 C3 2
8 | C | C4 1 G3 1 C4 2 | C3 1 G2 1 C3 2
```

### 2. Blinka lilla stjärna (fransk folkvisa, C-dur, 4 takter)

Enkel och lugn. Tempo 100 till 110 BPM. Bra med Saxofon eller Munspel på melodin och Swing som trumstil.

```
1 | C | C4 1 C4 1 G4 1 G4 1 | C3 1 C3 1 C3 1 C3 1
2 | F | A4 1 A4 1 G4 2 | F2 1 A2 1 C3 1 A2 1
3 | G | F4 1 F4 1 E4 1 E4 1 | G2 1 B2 1 D3 1 B2 1
4 | C | D4 1 D4 1 C4 2 | C3 1 E3 1 G3 2
```

### 3. Standardriffet (egen komposition, E-moll, 16 takter)

Det här är riffet som ligger förinställt på sidan. Det är skrivet för snabbt pop-punk-tempo, 150 till 180 BPM, med Saxofon på melodin och Polka eller Rock 4/4 på trummorna. Kopiera det från standardinnehållet i textrutan i `dragspel.html` om du vill ha det som utgångspunkt för egna ändringar.

---

## Felsökning

| Problem | Lösning |
|---|---|
| Inget ljud | Klicka på **Spela** en gång till. Kontrollera att volymen på datorn är påslagen och att volymreglagen inte står på 0. |
| "Takt N: melodin har X taktslag men basen Y" | Summan av längderna skiljer sig mellan stämmorna på rad N. Justera längderna så att de blir lika. |
| "Takt N: ogiltig not ..." | Kontrollera stavningen. Tonnamn ska vara A till G, följt av oktav. Exempel: `F#4`, `Bb3`. |
| "Takt N: varje not behöver en längd" | Det finns ett jämnt antal ord, men en not saknar längd. Kontrollera att varje tonnamn följs av en siffra. |
| Loopen hackar eller glider | Stoppa och starta om. Sänk tempot om datorn är långsam eller har många flikar öppna. |
| Låten slutar efter ett varv | Sätt **Antal varv** till 0 för oändligt, eller till ett högre tal. |

---

## Begränsningar

- Verktyget läser inte in noter från filer eller nothäften. Du skriver in dem manuellt.
- Ljuden är syntetiska och låter inte som verkliga inspelningar.
- Ackorden visas bara i statusraden och spelas inte upp.
- Verktyget kräver en modern webbläsare med stöd för Web Audio API.

---

## Filer

- `dragspel.html` är hela verktyget. Den innehåller HTML, CSS och JavaScript i en enda fil.
- `README.md` är den här filen.

---

Created with Claude by Malmis