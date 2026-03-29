# Intel Core-alapú kliens processzorok - Jegyzet

**Szerző:** Dezső Sima
**Verzió:** 8.0 (2026. február)

## 1. Bevezetés és áttekintés

- **Kliens processzorok:** Asztali számítógépeket (DT) és laptopokat kiszolgáló egységek.
- **Terminológia:** Az Intel és az AMD a laptopprocesszorokat "mobil processzornak" is nevezi.
- **ISA:** A kliens processzorok jellemzően x86 alapúak, míg a tabletek/okostelefonok ARM
  alapúak.
- **Kategóriák az Intel Core családban:**
  - **Szerver:** Xeon E7/E5/E3, Platinum/Gold (akár 144 mag).
  - **Munkaállomás:** Xeon W7/W5/W3 (akár 60 mag).
  - **HEDT (High-End Desktop):** Core i7/i9 Extreme Edition vagy X modellek (akár 32 mag).
  - **Kliens:** Core i9/i7/i5/i3 (akár 8+16 mag + grafika).
  - **Mobil (tablet/okostelefon):** Atom vonalak, LP Core modellek (akár 10 mag + grafika).

### Az Intel útja a Core családig

- 1971: 4004 (4-bit)
- 1972: 8008 (8-bit)
- 1974: 8080
- 1978: 8086 (16-bit, x86 ISA kezdete)
- 1979: 8088 (8-bit busz, az eredeti IBM PC-be (1981) ezt választották)
- 1982: 80186, 80286, 80188
- 1985: 80386DX (32-bit)
- 1989: 80486 (on-die lebegőpontos egység - 80387)
- 1993: Pentium (64-bit busz)
- 1995: Pentium Pro (off-die L2 cache)
- 1997: Pentium II (Klamath)
- 1999: Pentium III (MMX -> SSE)
- 2000: Pentium 4
- 2004: 64-bit éra (Prescott F Pentium 4)
- 2006: Core család megjelenése (64-bit dual-core, hatékonyság fókuszú)

## 2. Elnevezési konvenciók

- **Standard branding (2011, Sandy Bridge óta):** Core i3/i5/i7/i9.
- **Váltás (14. generáció, Meteor Lake óta):** "Core Ultra" és "Core" (az "i" betű elhagyásával).

### Eredeti séma (1-14. generáció, 2011-2023)

- **Részei:** Márkanév (Intel Core) + Módosító (i3/i5/i7/i9) + Generáció (1-2 számjegy) + SKU (3
  számjegy) + Suffix (1-2 betű).
- **Gyakori Suffixek:**
  - **Mobil:** Y (ultra-low power, 4.5-13W), U (low power, 15-28W), H (high perf, 35-45W).
  - **Asztali:** T (power-optimized, 35-45W), S (perf-optimized, 65W), K (unlocked, 60-95W).

### Új séma (Core Ultra, 2023-tól)

- **Szintek:** Core Ultra 5/7/9 (prémium) és Core 3/5/7 (mainstream).
- **Sorozat azonosító:** Meteor Lake = Series 1.
- **Suffixek (új):**
  - V: low-power (17/30W).
  - HX: extreme performance (65W).
  - KF: unlocked, GPU nélkül (125W).

## 3. Kulcsfontosságú fejlesztések

### Mikroarchitektúra

- **Mag szélesség (Decoderek száma):** 2 (Pentium, 1993) -> 4 (Core 2, 2006) -> 6 (Alder Lake,

2021. -> 8 (Lunar Lake, 2024) -> 9 (Lunar Lake E-magok).

- **SIMD szélesség:** 128-bit -> 256-bit (AVX/AVX2) -> 512-bit (AVX-512, Cannon Lake 2018).
- **Gyorsítótár:** Privát L2, megosztott L3 (monolitikus vagy szegmentált).

### Evolúciós lépések

1.  **Szimmetrikus többmagos (2006-2021):** Minden mag egyforma. Cél: teljesítmény növelése
    parallelizmussal.
2.  **Single-die big.LITTLE (2021, Alder Lake):** P (Performance) és E (Efficiency) magok egy
    lapkán. Cél: fogyasztás csökkentése.
3.  **Heterogén multi-die (2023, Meteor Lake):** Különböző gyártástechnológiájú lapkák (tiles)
    összekapcsolása. Cél: gyártási költség csökkentése.

### Gyártástechnológia (Tiles)

- **Meteor Lake:** CPU (Intel 4), GPU (TSMC N5), SOC (TSMC N6), IOE (Intel 22FFL).
- **Lunar Lake:** Compute (TSMC N3B), Platform (TSMC N6).
- **Panther Lake (2026):** Compute (Intel 18A - az első ilyen termék), GPU (Intel 3), SOC (TSMC
  N6).

### Csomagolási technológiák

- **EMIB (2.5D):** Beágyazott hidak az organikus hordozóban. (2017, Stratix 10).
- **Foveros (2.5D):** Lapkák egymásra helyezése Si-interposerrel és micro-bumpokkal. (2019,
  Lakefield).
- **Foveros Direct 3D:** Közvetlen Cu-to-Cu kötés (<10 um osztásköz). (2026, Clearwater Forest).

### Memória alrendszer

- **Váltás:** Északi hídból (NB) közvetlenül a processzorba integrált memóriavezérlő (MC). Intel
  Nehalem (2009) óta.
- **Típusok:**
  - **LPDDR5X-8533:** Lunar Lake-nél a csomagon belülre integrálva (2x8GB vagy 2x16GB).
  - **LPCAMM2:** Cserélhető, de kompakt modulok (2024, Lenovo ThinkPad P1 Gen 7).
  - **CUDIMM:** Clock Driverrel (CKD) ellátott modulok, akár DDR5-9600 sebességig.

### Ütemezés (Thread Director - TD)

- Hardware-támogatott OS ütemezés (Windows 11 21H2 óta).
- **Panther Lake (TD v2, 2026):** Három osztály (CL0: LP-E, CL1: E, CL2: P magok). 8-bites
  képességértékek (0-255).

## 4. Esettanulmányok

### 4.1 Lunar Lake (2024)

- Qualcomm Snapdragon X ellenfele.
- 4 P-mag (Lion Cove, 8-wide), 4 LPE-mag (Skymont, 3x3 wide). **Nincs multithreading.**
- NPU 4 (48 TOPS). Xe2 GPU (8 mag).
- **Akkumulátor:** 17 óra 7 perc (Procyon teszt), lekörözve az AMD-t és az Apple-t.

### 4.2 Panther Lake (2026)

- Akár 16 mag (P, E és LPE típusok).
- Cougar Cove P-magok (8-wide).
- NPU 5 (50 TOPS). Xe3 GPU (akár 12 mag).
- Gyártás: Ocatillo Campus, Arizona (Intel 18A technológia).

## 5. Piaci és gazdasági adatok

- **Vulnerabilitás:** 2023. novemberében a Google súlyos hibát jelentett (Ice Lake, Alder Lake,
  Raptor Lake), amit mikrokód-foltokkal javítottak. Ez piaci részesedés-csökkenést okozott.
- **Intel bevételek:** 2021-ben csúcs (79,02 mrd USD), 2024-re 53,1 mrd USD-re csökkent.
- **Részvényárfolyam (2025-2026):**
  - 2025. szeptember: 10 mrd USD állami támogatás.
  - 2025. október: Az NVIDIA 5 mrd USD értékben Intel részvényt vásárolt.
  - 2026. január: Panther Lake indítása után az árfolyam ~20 USD-ről ~50 USD-re emelkedett.
