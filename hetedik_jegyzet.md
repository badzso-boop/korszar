# Intel’s Core-based client processors - Jegyzet

**Szerző:** Dezső Sima
**Verzió:** 8.0
**Dátum:** 2026. február
**Copyright:** © Dezső Sima 2026

---

## 1. Bevezetés és áttekintés

### Alapfogalmak
- **Kliens processzorok (client processors):** Asztali számítógépeket (DT - desktops) és laptopokat kiszolgáló processzorok.
- **Terminológia:** A "processor family", "processor line" és "processor series" kifejezések szinonimák.
- **ISA (Instruction Set Architecture):** 
  - Kliens processzorok (DT és laptop): x86 ISA.
  - Mobil processzorok (tabletek, okostelefonok): Elsődlegesen ARM ISA.
- **Megjegyzés:** Az Intel és az AMD a laptop processzorokat gyakran "mobile processors"-ként említi.

### Intel processzor kategóriák (piaci cél szerint)
- **Szerver (Server):** Xeon E7/E5/E3 Platinum/Gold stb. Akár 144 mag (144 C).
- **Munkaállomás (Workstation):** Xeon W7/W5/W3. Akár 60 mag (60 C).
- **HEDT (High-End Desktops):** Core i7/i9 (Extreme Edition vagy X modellek). Akár 32 mag (32 C).
- **Kliens (Client):** Core i9/i7/i5/i3. Akár (8 + 16) mag + Grafika (G).
- **Mobil (Mobile - tabletek, telefonok):** Atom vonalak (+ LP Core modellek). Akár 10 mag + G.

---

## 2. Az Intel útja a Core családig

### Idővonal (Pre-Core korszak)
- **1971:** 4004 (4-bit)
- **1972:** 8008 (8-bit)
- **1974:** 8080
- **1978:** 8086 (16-bit, x86 ISA bevezetése)
- **1979:** 8088 (8-bit busz) - Az IBM PC-be ezt választották 1981-ben a költséghatékonyság miatt.
- **1982:** 80186, 80286, 80188
- **1985:** 80386DX (32-bit), 80386SX (16-bit busz)
- **1989:** 80486
- **1993:** Pentium (64-bit busz)
- **1995:** Pentium Pro
- **1997:** Pentium II (Klamath), Pentium II (Dixon) MMX
- **1999:** Pentium III
- **2000:** Pentium 4 (Willamette)
- **2004:** Prescott F Pentium 4 (64-bit korszak kezdete).
- **2006:** Első 64 bites dual-core sorozat: a **Core család**. Cél: maximális teljesítmény/Watt.

### Technológiai váltások
- **FP co-processzorok:** 8087, 80287, 80387 (on-die FP a 486-tól).
- **L2 Cache:** Off-die-ból On-die-ba került.
- **Utasításkészlet:** MMX -> SSE -> SSE 2.

---

## 3. Intel Core-alapú kliens processzor vonalak (Gen 1-11)

| Gen | Processzor / Architektúra | Technológia | Bevezetés | Max magszám | Memória | Foglalat (Socket) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1. | Core 2 | 65 nm | 6/2006 | 2C | DDR2-800 | LGA 775 |
| | Core 2 Quad | 65 nm | 6/2007 | 2x2C | DDR3-1067 | LGA 775 |
| | Penryn | 45 nm | 6/2008 | 2x2C | DDR3-1067 | LGA 775 |
| | Nehalem (Lynnfield) | 45 nm | 9/2009 | 4C | DDR3-1333 | LGA 1156 |
| | Westmere (Arrandale/Clarkdale) | 32 nm | 1/2010 | 2C+G | DDR3-1333 | BGA 1288/LGA 1156 |
| 2. | Sandy Bridge | 32 nm | 1/2011 | 2C/4C+G | DDR3-1333 | PGA 988/LGA 1155 |
| 3. | Ivy Bridge | 22 nm | 4/2012 | 4C+G | DDR3-1600 | PGA 988/LGA 1155 |
| 4. | Haswell / Haswell Refr. | 22 nm | 2013/14 | 4C+G | DDR3-1600/1666 | BGA 1168/LGA 1150 |
| 5. | Broadwell | 14 nm | 9/2014 | 4C+G | DDR3-1866 | - |
| 6. | Skylake | 14 nm | 10/2015 | 4C+G | DDR4-2133 | BGA 1356/LGA 1151 |
| 7. | Kaby Lake | 14 nm | 8/2016 | 4C+G | DDR4-2400 | - |
| 8. | Coffee Lake / Amber Lake / Whiskey Lake | 14 nm | 2017/18 | 6C+G / 2C+G / 4C+G | DDR4-2666 / LPDDR3-2133 | BGA 1440/1515/1528 |
| 8. | Cannon Lake | 10 nm | 5/2018 | 2C | DDR4-2400 | BGA 1440 |
| 9. | Coffee Lake Refresh | 14 nm | 10/2018 | 8C+G | DDR4-2666 | LGA 1151 |
| 10. | Comet Lake | 14 nm | 8/2019 | 10C+G | DDR4-2666 | BGA 1528/LGA 1200 |
| 10. | Ice Lake | 10 nm | 7/2019 | 4C+G | DDR4-3200/LPDDR4-3733 | BGA 1526 |
| 11. | Tiger Lake | 10 nm | 2020/21 | 4C+G / 8C+G | LPDDR4x-4267/DDR4-3200 | BGA 1449/1787/LGA 1700 |
| 11. | Rocket Lake | 14 nm | 3/2021 | 8C+G | DDR4-3200 | LGA 1200 |

---

## 4. Intel Core-alapú kliens processzor vonalak (Gen 12-14)

| Gen | Processzor | Technológia | Bevezetés | Max magszám | Memória |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 12. | Alder Lake | Intel 7 | 11/2021 | 8+8C+G / 6+8C+G | DDR5-4800 / LPDDR5-5200 |
| 13. | Raptor Lake | Intel 7 | 10/2022 | 8+16C+G | DDR5-5600 |
| 14. | Raptor Lake Refresh | Intel 7 | 10/2023 | 8+16C+G | DDR5-5600 |

### Core Ultra Sorozat (Series 1-3)
| Sorozat | Processzor | Technológia (CPU/GPU/SOC) | Dátum | Magok | Memória | TDP |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Series 1 | Meteor Lake | Intel 4 / N5 / N6 | 12/2023 | 6+8+2C+G | DDR5-5600/LP5X-7467 | 9-45W |
| Series 2 | Lunar Lake | TSMC N3B / N6 | 09/2024 | 4+4C+G+NPU | LPDDR5x-8533 (on-pkg) | 17/30W |
| Series 2 | Arrow Lake | TSMC N3B / N5 / N6 | 10/2024 | 8+16C+G+NPU | DDR5-5600 / LP5X-8400 | 28-125W |
| Series 3 | Panther Lake | Intel 18A / N3E / N6 | 01/2026 | 4+8+4+G | DDR5-7200 / LP5X-9600 | 25W |

---

## 5. Elnevezési konvenciók

### Eredeti rendszer (Sandy Bridge - 13. generáció)
- **Brand name:** "Intel Core"
- **Brand modifier:** i3, i5, i7, i9.
- **Generation identifier:** 1 vagy 2 számjegy (pl. 7 a 7500U-ban).
- **SKU (Stock Keeping Unit):** 3 számjegy.
- **Product line suffix:** pl. U, H, K.

### Új rendszer (Meteor Lake-től, 2023-)
- **Brand name:** "Intel Core" (mainstream) vagy "Intel Core Ultra" (premium).
- **Brand level:** 3, 5, 7, 9 (az "i" betű elmarad).
- **Processor number:** Series identifier (pl. 1), SKU (2 számjegy), Suffix.
  - Példa: Intel Core Ultra 9 processor 185H (1-es széria, 85-ös SKU, H-suffix).

### Suffixek és TDP értékek
- **Mobil:**
  - **Y:** Ultra-low-power (9-13 W).
  - **U:** Low power (15/28 W).
  - **V:** Low power (17/30 W - Lunar Lake).
  - **H:** High-performance laptop (28/45 W).
  - **HX:** Extreme performance (65 W).
- **Desktop:**
  - **T:** Power-optimized (35 W).
  - **S:** Performance-optimized (65 W).
  - **K:** Unlocked (125 W).
  - **KF:** Unlocked GPU nélkül (125 W).

---

## 6. Mikroarchitekturális fejlesztések

### Hallgatói teszteredmények (Tudásellenőrzés)
- **Kérdés 1:** Milyen előnyökkel járnak a szimmetrikus többmagos processzorok?
  - **Válasz:** Egyszerűsítik a magok ütemezését [1/2 pont] és a disszipáció kezelését [1/2 pont].
  - **Eredmények:** 88 hallgató (0.0 pont), 41 hallgató (0.5 pont), 10 hallgató (1.0 pont).
- **Kérdés 2:** Milyen céllal vezette be az Intel a big.little architektúrát?
  - **Válasz:** Fogyasztás csökkentése céljából [1 pont].
  - **Eredmények:** 45 hallgató (0.0 pont), 94 hallgató (1.0 pont).
- **Kérdés 3:** Mi a célja a heterogén többlapkás kialakításnak?
  - **Válasz:** Gyártási költségek csökkentése [1 pont].
  - **Eredmények:** 94 hallgató (0.0 pont), 45 hallgató (1.0 pont).
- **Összesített eredmények (3 kérdés):** Pontszámok eloszlása: 0.0 (30 fő), 0.5 (3 fő), 1.0 (43 fő), 1.5 (24 fő), 2.0 (21 fő), 2.5 (14 fő), 3.0 (4 fő).

### Fejlődési lépések (CPU konfiguráció)
1. **Szimmetrikus többmagos (Symmetrical multicore):** Minden mag egyenrangú. Cél: teljesítménynövelés párhuzamos feldolgozással. (2006-2021).
2. **Single-die big.little:** P (Performance) és E (Efficiency) magok keveréke egy lapkán. Cél: fogyasztáscsökkentés. (Alder Lake, 2021).
3. **Heterogén multi-die big.little:** Több különböző gyártástechnológiájú lapka (tiles) egy tokban. Cél: gyártási költségek csökkentése. (Meteor Lake, 2023).

### Fontosabb újítások
- **Mag szélesség (Core width):** Az utasítás-dekódolók száma.
  - Pentium: 2-wide.
  - Core 2 - Broadwell: 4-wide.
  - Alder Lake: 6-wide (P-core).
  - Lunar Lake: 8-wide (P-core), 3x3-wide (E-core).
- **SIMD szélesség:** 128-bit -> 256-bit (AVX/AVX2) -> 512-bit (AVX 512 - Cannon Lake).
- **Backporting:** Egy mikroarchitektúra megvalósítása régebbi gyártástechnológián (pl. Rocket Lake: Ice Lake architektúra 14 nm-en).
- **Thread Director (TD):** Hardveres segítség az OS-nek a szálak ütemezéséhez hibrid architektúráknál. (Alder Lake-től, Windows 11 21H2-vel).

---

## 7. Csomagolási technológiák (Packaging)

- **MCM (Multi-Chip Package):** Forrasztott, alacsony csatlakozási sűrűség.
- **EMIB (Embedded Multi-die Interconnect Bridge):** Szilícium hidak a hordozóba ágyazva. (Stratix 10 - 2017).
- **Foveros 2.5D:** Lapkák forrasztása egy passzív alaplapkára (Si-interposer). (Lakefield - 2019).
- **Foveros Direct 3D:** Közvetlen réz-réz (Cu-to-Cu) kötés, forrasztás nélkül. Pitch < 10 µm. (Clearwater Forest - 2026).

---

## 8. Memória alrendszer

- **Váltás:** MC (Memory Controller) a North Bridge-ből a processzor lapkára került (Nehalem, 2009).
- **Memória típusok:**
  - **LPDDR (Low Power DDR):** Kisebb feszültség, alaplapra forrasztva (BGA).
  - **LPCAMM2 (Low-Power Compression Attached Memory Module):** Cserélhető, tömörítéssel érintkező modul (2024).
  - **CUDIMM (Clocked Unbuffered DIMM):** Órajel-meghajtó (CKD) a modulon, jobb jelintegritás (2024).
- **Sebesség duplázódás:**
  - DDR3/DDR4: kb. 8 évente.
  - DDR5/LPDDRx: kb. 4 évente.

---

## 9. Esettanulmányok

### Lunar Lake (Core Ultra 200V, 2024)
- **Cél:** Verseny a Qualcomm Snapdragon X-szel.
- **Felépítés:** 2 tiles (Compute N3B, Platform N6). 4 P + 4 LPE mag.
- **Memória:** 16 vagy 32 GB LPDDR5x-8522 a tokba integrálva.
- **NPU 4:** 48 TOPS.
- **Grafika:** Xe2 GPU (8 core).
- **Akkuidő:** 17 óra 7 perc (Procyon teszt).

### Panther Lake (Core Ultra Series 3, 2026)
- **Felépítés:** 3 tiles. Magok: Cougar Cove (P), Darkmont (E/LPE). Akár 16 mag.
- **NPU 5:** 50 TOPS.
- **Gyártás:** Intel 18A (Compute tile). Ocatillo Campus, Arizona.
- **TDP:** 25 W bázis.

---

## 10. Piaci adatok és események

- **Vulnerabilitás:** 2023. novemberében a Google súlyos sebezhetőséget tárt fel (Ice, Alder, Raptor Lake), amit mikrokód javításokkal orvosoltak.
- **Piaci részesedés (Mobile x86 CPU):** 
  - Intel: 2018 Q2: 91.2% -> 2024 Q3: 77.7%.
  - AMD: 2018 Q2: 8.8% -> 2024 Q3: 22.3%.
- **Intel Bevétel (2021-2024):** 
  - 2021: 79.02 Mrd USD.
  - 2024: 53.1 Mrd USD.
- **Tőzsde:** 2025 szeptembere és 2026 februárja között az Intel részvényára ~20$-ról ~50$-ra emelkedett (kormányzati támogatás, NVIDIA befektetés és a Panther Lake startja miatt).
