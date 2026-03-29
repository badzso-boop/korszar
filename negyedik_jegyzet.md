Intel’s Core family – a brief introduction

- Szerző: Dezső Sima
- Verzió: Vers. 8.0
- Dátum: Febr. 2026
- Copyright: © Dezső Sima 2026

---

Tartalomjegyzék

1.  Lessons learned from the preceding Pentium 4 family
2.  Intel's key design decisions made for the Core family
3.  Evolution of the x86 ISA
4.  Overview of the Core family
5.  References

---

1. Tanulságok a Pentium 4 családból

- Pentium 4 család indítása: 11/2000.
- Generációk (Tick-Tock 2 éves ciklusokban):
  - Pentium 4 / Willamette: 180nm, 11/2000.
  - Pentium 4 / Northwood: 130nm, 01/2002. (Hyperthreading bevezetése 2002-ben).
  - Pentium 4 / Prescott: 90nm, 02/2004. (64-bit ISA és mikroarchitektúra 2004-ben, Dual-core
    2005-ben).
  - Pentium 4 (Cedar Mill SC) / Pentium D (Presler DC): 65nm, 01/2006.
  - Core 2: 07/2006.

- Főbb innovációk:
  - Hyperthreading (HT): 2002 (Northwood).
  - 64-bit ISA: 2004 (Prescott).
  - Dual-core (DC): 2005 (Prescott), pl. Pentium D (Smithfield) (05/2005).
  - Új mikroarchitektúra: Netburst (11/2000).

- A "Pentium 4 kudarc":
  - Az Intel 10 GHz-es órajelet ígért 2005-re.
  - Valóság: Greg Barrett (akkori CEO) 10/2004-ben elismerte, hogy a 4 GHz-et sem érik el.
  - Ok: A mikroarchitektúra a maximális órajelet prioritizálta a fogyasztás és hőtermelés kárára.

- Váltás a fókuszban:
  - Régi: Legmagasabb teljesítmény (pl. GFLOPS).
  - Új: Legmagasabb teljesítmény wattonként (GFLOPS/Watt).

- Fejlesztési modellek:
  - Single-phase (Pentium 4): Egyszerre váltottak IC technológiát és mikroarchitektúrát.
    Kockázatos és hibaérzékeny.
  - Two-phase (Core 2-től):
    - Phase 1: Új mikroarchitektúra meglévő technológián.
    - Phase 2: Új technológia a már bizonyított mikroarchitektúrán.

---

2. Kulcsfontosságú tervezési döntések a Core családnál

- Tick-Tock modell (kétfázisú):
  - Tick: Gyártástechnológia zsugorítása (pl. 65nm -> 45nm).
  - Tock: Új mikroarchitektúra.
- Timothy Wilson (Vice President, Design Engineering Group): A kétfázisú modellel csökkentik a
  kockázatot.
- Multithreading: Az első Core vonalaknál (Core 2, Penryn) kihagyták a gyorsabb piacra lépés
  érdekében. A Nehalem-nél tért vissza.

- Kezdeti generációk:
  1.  Core 2 (2006): 65nm, Tock.
  2.  Penryn (2007): 45nm, Tick.
  3.  Nehalem (2008): 45nm, Tock.
  4.  Westmere (2010): 32nm, Tick.
  5.  Sandy Bridge (2011): 32nm, Tock.
  6.  Ivy Bridge (2012): 22nm, Tick.
  7.  Haswell (2013): 22nm, Tock.
  8.  Broadwell (2014): 14nm, Tick.

- Moore törvénye: A 0.7-es szorzóval való méretcsökkentés lehetővé teszi a tranzisztorszám
  duplázását azonos lapkaméret mellett 2 évente.

- Névadási anomáliák:
  - Core 2 = 1. generáció.
  - Sandy Bridge = 2. generáció.
  - Nehalem és Westmere nem kaptak generációs azonosítót.
  - Tervezőközpontok: Haifa (Core 2, Sandy Bridge), Oregon (Nehalem, Westmere).
  - 2023-as váltás: Elhagyták a generációs számozást, bevezették a "Core Ultra Series x" nevet
    (Series 1 = Meteor Lake).

- A 10nm-es technológia nehézségei:
  - 2011-es terv: 10nm 2015-re.
  - Valóság: Csak 2018-ban indult a pilot (Cannon Lake), 2019-ben a tömegtermelés. ~3.5 év késés.
  - Új modell (a késés miatt): "Optimization" fázisok bevezetése a Tock után (PAO modell:
    Process-Architecture-Optimization).
  - Példa: 14nm-en maradt a 7. gen (Kaby Lake), 8. gen (Coffee Lake stb.), 9. gen (Coffee Lake
    R), 10. gen (Comet Lake).

- Backporting: Fejlett mikroarchitektúra megvalósítása régebbi technológián (pl. 11. gen Rocket
  Lake: 14nm-en).
- Symmetrical multicores: A 11. generációig minden mag azonos képességű volt.
- big.LITTLE: A 12. generációtól (Alder Lake, 2021) hibrid architektúra (erős és alacsony
  fogyasztású magok).

- Heterogeneous multi-die: Több különálló lapkából (die) álló processzor (pl. Compute die, Graphics
  die).
  - Core Ultra Series 1 (Meteor Lake, 2023): Intel 4 / TSMC N5/N6.
  - Core Ultra Series 2 (Lunar Lake, 2024): TSMC N3/N6.
  - Core Ultra Series 3 (Panther Lake, 2026): Intel 1.8A / TSMC N3/N6.

---

3. Az x86 ISA evolúciója

- Kezdet: 1978.
- SIMD (Single Instruction Multiple Data): Párhuzamos adatfeldolgozás.
- MMX (1997): 64-bit FX, multimedia (2D) támogatás, 32-bit Pentium-MMX.
- SSE (1999): 128-bit FP, 3D támogatás, 8x128-bit regiszter, Pentium III.
- Regiszter bővülések:
  - SSE3 (2004): 16x128-bit (64-bit módban).
  - AVX (2011): 16x256-bit (YMM regiszterek).
  - AVX-512 (2017/2018): 32x512-bit (ZMM regiszterek).
- Aliasing (Azonosítás): A rövidebb regiszterek a hosszabbak alsó részei (pl. XMM a YMM része).

- Integrált grafika lépcsőfokai:
  1.  North Bridge-be integrálva (GMCH): 1999-2009.
  2.  On-package (MCP - egy tokban, de külön lapkán): 01/2010 (Westmere).
  3.  On-die (egy lapkán a CPU-val): 01/2011 (Sandy Bridge).

---

4. A Core család áttekintése

- Kategóriák:
  - Szerver: Xeon E7/E5/E3 Platinum/Gold (akár 144 mag).
  - Workstation: Xeon W7/W5/W3 (akár 60 mag).
  - HEDT (High-End Desktop): Core i7/i9 Extreme/X (akár 32 mag).
  - Client (Desktop/Laptop): Core i9/i7/i5/i3 (akár 8+16 mag + grafika).
  - Mobile (Tablet/Smartphone): Atom vonalak (akár 10 mag + grafika).

- TDP (Thermal Design Power): A processzor maximális fogyasztása realisztikus alkalmazások alatt
  (Wattban).
  - Szerver: ~200-400 W.
  - HEDT: ~100-150 W (X tag).
  - Desktop High perf: ~70-125 W (K tag).
  - Notebook Ultra-thin: ~15 W (U tag).
  - Tablet: ~5 W (Y/m tag).
  - Tjmax: Junction temperature limit, pl. 90°C.

- IPC (Instructions Per Cycle):
  - Több mint kétszeres növekedés 15 év alatt (2004-2019).
  - Referenciapont: Pentium M (Dothan, 2004).

- Lapkaméretek (Die size):
  - Client (Broadwell 2C): 82 mm² - 133 mm².
  - Server (Skylake-SP 28C): ~680 mm².
