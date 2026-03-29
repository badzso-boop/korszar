# Intel’s Core family - a brief introduction

**Szerző:** Dezső Sima
**Verzió:** 8.0
**Dátum:** 2026. február
**Copyright:** © Dezső Sima 2026

---

## 1. Lessons learned from the preceding Pentium 4 family (Tanulságok a Pentium 4 családból)

### A Pentium 4 család generációi (Indítás: 2000. november)

- **Willamette:** 180nm, 2000/11 (Tick-Tock modell szerint: Tick)
- **Northwood:** 130nm, 2002/01 (Tick)
- **Prescott:** 90nm, 2004/02 (Tick)
- **Cedar Mill (SC) / Pentium D (Presler DC):** 65nm, 2006/01 (Tick)
- **Core 2:** 2006/07 (Tock)

### Kulcsfontosságú innovációk a Pentium 4 családban

1. **Hyperthreading (HT):** 2002-ben vezették be a Northwood maggal.
2. **64-bit ISA és mikroarchitektúra:** 2004-ben a Prescott maggal.
3. **Dual-core (kétmagos) processzorok:** 2005-ben a Prescott maggal (Pentium D Smithfield, 2005/05).

### A Pentium 4 kudarc ("The Pentium 4 debacle")

- Az Intel eredetileg azt állította, hogy a Pentium 4 eléri a **10 GHz**-es órajelet 2005-re.
- 2004 októberében Greg Barrett (akkori CEO) elismerte, hogy a család még a **4 GHz**-et sem fogja elérni.

### Két fontos tanulság:

1. **Lesson One (Fókuszváltás):** Az órajel-hajszolás helyett a **Teljesítmény/Watt (Performance per Watt)** maximalizálása lett a cél (pl. GFLOPS/Watt).
2. **Lesson Two (Fejlesztési modell):** Az "egyfázisú" modellről (technológia és architektúra egyszerre vált) áttértek a **kétfázisú fejlesztési modellre** a megbízhatóság és egyszerűbb validáció érdekében.
   - **1. fázis:** Új mikroarchitektúra meglévő technológiával.
   - **2. fázis:** Új technológia bizonyított mikroarchitektúrával.

---

## 2. Intel’s key design decisions for the Core family (Kulcsfontosságú tervezési döntések)

### Tervezési irányelvek:

- **Teljesítmény/Watt** alapú megközelítés.
- **Tick-Tock modell** bevezetése:
  - **Tick fázis:** Gyártástechnológia zsugorítása (pl. 65nm -> 45nm).
  - **Tock fázis:** Új mikroarchitektúra bevezetése a már kiforrott gyártástechnológián.
- **Multithreading (Hyperthreading) mellőzése:** Az első Core vonalaknál (Core 2, Penryn) elhagyták a gyorsabb piacra kerülés érdekében. A HT a **Nehalem** architektúrával tért vissza.

### Tick-Tock generációk:

- **1. gen:** Core 2 (Tock, 65nm, 2006), Penryn (Tick, 45nm, 2007)
- **2. gen:** Nehalem (Tock, 45nm, 2008), Westmere (Tick, 32nm, 2010)
- **3. gen:** Sandy Bridge (Tock, 32nm, 2011), Ivy Bridge (Tick, 22nm, 2012)
- **4. gen:** Haswell (Tock, 22nm, 2013)
- **5. gen:** Broadwell (Tick, 14nm, 2014)

### Technológiai zsugorodás:

- A Moore-törvénnyel összhangban a méretcsökkenési ráta **0.7-szeres** (ezzel a tranzisztorszám megduplázható azonos területen).

### Névadási anomáliák:

- **Core 2:** 1. generáció.
- **Sandy Bridge:** 2. generáció.
- A **Nehalem** és **Westmere** nem kaptak hivatalos generációs azonosítót.
- **2023:** Az Intel elhagyta a hagyományos generációs számozást a Meteor Lake-től kezdve, bevezetve a **Core Ultra Series x** megjelölést.

### A 10nm-es technológia nehézségei:

- 2011-es terv: 10nm bevezetése 2015-re.
- Valóság: Jelentős késés, kísérleti gyártás (pilot) csak 2018-ban (**Cannon Lake**), tömeggyártás 2019-ben.

### Optimalizációs fázisok (A 6. generáció után):

A Tick-Tock modell kiegészült egy harmadik fázissal: **Tick-Tock-Optimization**.

- **6. gen:** Skylake (Tock, 14nm, 2015)
- **7. gen:** Kaby Lake (Optimization, 14nm, 2016)
- **8. gen:** Kaby Lake R, Coffee Lake, Whiskey Lake, Cannon Lake (10nm) (Optimization, 2017/18)
- **9. gen:** Coffee Lake R (Optimization, 2018)
- **10. gen:** Comet Lake (Optimization, 2019)

### Backporting (Visszaportolás):

- **11. gen Rocket Lake (2021):** Fejlett mikroarchitektúra megvalósítása régebbi, 14nm-es technológián.

### Újabb architektúrák (Core Ultra):

- **12. gen:** Alder Lake (Új design, big.LITTLE architektúra, 10nm, 2021)
- **13. gen:** Raptor Lake (Optimization, 10nm, 2022)
- **14. gen:** Raptor Lake Refresh (Optimization, 10nm, 2023)
- **Core Ultra Series 1:** Meteor Lake (Multi-die, 2023)
- **Core Ultra Series 2:** Lunar Lake, Arrow Lake (TSMC N3/N6/N5 technológia használata, 2024)
- **Core Ultra Series 3:** Panther Lake (Intel 1.8A, 2026)

---

## 3. Evolution of the x86 ISA (Az x86 ISA fejlődése)

### Kezdetek és SIMD:

- **1978:** x86 ISA megszületése.
- **SIMD (Single Instruction Multiple Data):** Vektoros kiterjesztések a párhuzamos adatfeldolgozáshoz.

### SIMD történeti mérföldkövek:

- **1990-es évek közepe:** Multimedia igények (2D grafika, RGB, FX8/FX32 adatok).
- **1997:** **MMX** (Multi-Media Extension), 32-bit Pentium-MMX. 64-bites regiszterek (8 db).
- **1999:** **SSE** (Streaming SIMD Extensions), Pentium III. 128-bites FP SIMD, 8 db 128-bites dedikált regiszter (XMM0-XMM7).
- **2004:** **SSE3** (64-bit mód), 16 db 128-bites regiszter (XMM0-XMM15).
- **2011:** **AVX** (Advanced Vector Extensions), 16 db 256-bites regiszter (YMM0-YMM15).
- **2017/18:** **AVX-512**, 32 db 512-bites regiszter (ZMM0-ZMM31).

### Integrált grafika (három lépésben):

1. **NB-be integrált GPU:** Pentium III - Nehalem (1999-2009).
2. **On-package GPU (MCP):** CPU és GPU külön lapkán, de egy tokban (Westmere, 2010/01).
3. **On-die GPU:** CPU és GPU ugyanazon a lapkán (Pineview 2011/01, Sandy Bridge 2011/01).

---

## 4. Overview of the Core family (A Core család áttekintése)

### Processzor kategóriák és konfigurációk:

- **Server:** Xeon E7/E5/E3 Platinum/Gold. Akár **144 mag**.
- **Workstation:** Xeon W7/W5/W3. Akár **60 mag**.
- **HEDT (High-End Desktop):** Core i7/i9 (Extreme/X). Akár **32 mag**.
- **Client (Desktop/Laptop):** Core i9/i7/i5/i3. Akár **(8+16) mag + Grafika**.
- **Mobile (Tablets/Smartphones):** Atom vonal (+LP Core). Akár **10 mag + Grafika**.

### TDP (Thermal Design Power - Tervezési hőérték):

- Maximális teljesítményfelvétel valós alkalmazások futtatásakor (Wattban megadva).
- Meghatározza a hűtési rendszer igényét.
- **Tjmax (Junction Temperature):** kb. 90°C.

### Jellemző TDP értékek:

- **Szerverek:** ~200-400 W
- **HEDT:** ~100-150 W (Jelölés: X)
- **Asztali (High perf):** ~70-125 W (Jelölés: K)
- **Asztali (Mainstream):** ~50-65 W (Jelölés: S)
- **Asztali (Low power):** ~35-45 W (Jelölés: T)
- **Notebook (High perf):** ~45 W (Jelölés: H/HQ)
- **Notebook (Mainstream/Ultra-thin):** ~15-35 W (Jelölés: U)
- **Tabletek:** ~5 W (Jelölés: Y/m)

### IPC (Instructions Per Cycle) fejlődés:

- Több mint **kétszeres** IPC növekedés a Core vonalon 15 év alatt (2004-2019).
- Referenciapont: Dothan (2004).

### Lapkaméretek (Példák):

- **Kliens:** Broadwell (2 mag, 5500 GPU): **82 mm²**.
- **Szerver:** Skylake-SP (28 mag): **~680 mm²**.
