# Intel’s Core-based client processors - Jegyzet

**Forrás:** Dezső Sima, Vers. 8.0, 2026. február
**Copyright:** © Dezső Sima 2026

## 1. Bevezetés és áttekintés
*   **Fókusz:** Desktop (DT) és laptop kliens processzorok.
*   **Terminológia:** A "processor family", "processor line" és "processor series" szinonimák.
*   **Kategóriák az Intel Core családban:**
    *   **Server:** Xeon E7/E5/E3, Platinum/Gold stb. (akár 144 mag).
    *   **Workstation:** Xeon W7/W5/W3 (akár 60 mag).
    *   **HEDT (High-End Desktop):** Core i7/i9 Extreme Edition vagy X modellek (akár 32 mag).
    *   **Client (Asztali/Laptop):** Core i9/i7/i5/i3 (Basic architektúrák, akár 8+16 mag + Grafika).
    *   **Mobile (Tablet/Okostelefon):** Atom vonalak, LP Core modellek (akár 10 mag + Grafika).
*   **ISA különbség:** A kliens processzorok jellemzően x86 ISA-t használnak, míg a mobilok (tabletek, okostelefonok) elsősorban ARM ISA-t. Ez a határvonal mára elmosódott.

### Intel útja a Core családig (Évszámok és mérföldkövek):
*   **1971:** 4004 (4-bit)
*   **1972:** 8008 (8-bit)
*   **1974:** 8080 (8-bit)
*   **1978:** 8086 (16-bit, x86 ISA kezdete)
*   **1979:** 8088 (8-bit busz)
*   **1981:** IBM PC megjelenése (8088-as processzorral)
*   **1982:** 80186, 80286 (16-bit), 8087/80287 FP koprocesszorok.
*   **1985:** 80386DX (32-bit), 80387 on-die FP.
*   **1989:** 80486.
*   **1993:** Pentium (64-bit busz).
*   **1995:** Pentium Pro.
*   **1997:** Pentium II (Klamath, Dixon).
*   **1999:** Pentium III (MMX, SSE).
*   **2000:** Pentium 4 (Willamette, SSE2).
*   **2004:** 64-bit éra kezdete a Prescott F Pentium 4 modellel.
*   **2006:** Az első 64-bit dual-core processzorcsalád: **Core family** (fókusz: teljesítmény per Watt).

### Core generációk és technológiák (Slide 9-11):
1.  **Core 2 (2006. 06.):** 65 nm, 2 mag, LGA 775.
2.  **Nehalem (Lynnfield) (2009. 09.):** 45 nm, 4 mag, LGA 1156.
3.  **Sandy Bridge (2011. 01.):** 32 nm, 2C/4C+G, Ring bus, LGA 1155.
4.  **Ivy Bridge (2012. 04.):** 22 nm, 4C+G.
5.  **Haswell (2013. 06.):** 22 nm, 4C+G, FIVR (integrált feszültségszabályozó).
6.  **Broadwell (2014. 09.):** 14 nm, 4C+G.
7.  **Skylake (2015. 10.):** 14 nm, 4C+G.
8.  **Kaby Lake (2016. 08.):** 14 nm, 4C+G.
9.  **Coffee Lake (2017. 10.):** 14 nm, 6C+G.
10. **Comet Lake (2019. 08.):** 14 nm, 10C+G.
11. **Rocket Lake (2021. 03.):** 14 nm, 8C+G (Backporting).
12. **Ice Lake (2019. 07.):** 10 nm, 4C+G.
13. **Tiger Lake (2020. 09.):** 10 nm, 4C/8C+G.
14. **Alder Lake (2021. 11.):** Intel 7 (10 nm), 8+8C+G (Hybrid architektúra).
15. **Raptor Lake (2022. 10.):** Intel 7, 8+16C+G.
16. **Meteor Lake (Core Ultra Series 1) (2023. 12.):** Intel 4 / TSMC N5/N6, 6+8+2C+G+NPU. Multi-die (4 tile).
17. **Lunar Lake (Core Ultra Series 2) (2024. 09.):** TSMC N3B/N6, 4+4C+G+NPU (nincs hyperthreading). On-package memória.
18. **Arrow Lake (Core Ultra Series 2) (2024. 10.):** TSMC N3B/N5P/N6, 8+16C+G (nincs hyperthreading).
19. **Panther Lake (Core Ultra Series 3) (2026. 01.):** Intel 18A / TSMC N3E/N6, 4+8+4 mag.

## 2. Elnevezési konvenciók (Naming)
*   **2011 (Sandy Bridge) óta:** Standard branding (i3/i5/i7/i9).
*   **Két megközelítés:**
    1.  **Eredeti (1-14. generációig):** Brand (Intel Core) + Brand Modifier (i3-i9) + Gen. Identifier (pl. 7500) + SKU numeric digits + Product Line Suffix (pl. U).
    2.  **Új (2023, Meteor Lake óta - Core Ultra):** Brand Name (Intel Core Ultra) + Brand Level (5/7/9) + Processor Number (Series identifier + SKU# + Suffix, pl. 185H).

### Suffixok és TDP értékek:
*   **Laptop:**
    *   **Y:** ultra-low-power (4.5/5 W vagy 11.5/13 W).
    *   **U:** low power (tipikusan 15/28 W).
    *   **V:** low-power (17/30 W).
    *   **H:** high-performance laptop (35/45 W).
    *   **HX:** extreme performance (akár 55/65 W).
*   **Desktop:**
    *   **T:** power-optimized (35 W).
    *   **S:** performance-optimized (65 W).
    *   **K:** unlocked (60-95 W vagy akár 125 W).
    *   **KF:** unlocked, GPU nélkül (125 W).

## 3. Kulcsfontosságú fejlesztések
*   **CPU mag szélessége (Core width):** 4-ről 9-re nőtt az utasítás dekódolók száma.
*   **Cache:** Megjelent a privát L2 és a megosztott L3 cache (monolitikus, majd szegmentált).
*   **SIMD:** 128-bit -> 256-bit (AVX/AVX2) -> 512-bit (AVX-512).
*   **Magok száma:** 2-től (2006) akár 24-ig (laptop/DT).
*   **Architektúra fejlődése:**
    *   **Symmetrical multicore (2006-2021):** Minden mag egyforma.
    *   **Single-die big.LITTLE (2021, Alder Lake):** P-magok (Performance) és E-magok (Efficiency) egy lapkán.
    *   **Heterogeneous multi-die big.LITTLE (2023, Meteor Lake):** Több különálló lapka (tiles) összekapcsolva.

### Csomagolási technológiák (Packaging):
*   **EMIB (2.5D):** Beágyazott hidak a szubsztrátumban (2017, Stratix 10).
*   **Foveros (2.5D):** Lapkák egymásra pakolása forrasztott micro-bumpokkal (2019, Lakefield).
*   **Foveros Direct 3D:** Közvetlen Cu-to-Cu hybrid bonding (<10 µm osztásköz, 2026, Clearwater Forest).

### Memória alrendszer:
*   **Kapcsolódás:** FSB (Northbridge-en keresztül, 2008-ig) -> Közvetlen kapcsolódás (Nehalem óta).
*   **Típusok:** DDR2 -> DDR3 -> DDR4 -> DDR5.
*   **Laptop specifikus:** LPDDR4x, LPDDR5x, **LPCAMM2** (cserélhető, tömörítéses érintkezők), **CUDIMM** (Clocked Unbuffered DIMM, integrált órajel-meghajtóval).
*   **Lunar Lake innováció:** 16 vagy 32 GB LPDDR5x-8533 memória integrálva közvetlenül a processzor tokba (on-package).

### Grafika és 3D feldolgozás:
*   **Alapegység:** Háromszögek halmaza (Triangle mesh), FP32 adatokkal.
*   **Shaderek:** Vertex, Pixel (Fragment), Geometry shaderek.
*   **Nyelvek:** HLSL (Microsoft), GLSL (Khronos Group), Cg (NVIDIA).
*   **Unified Design (2006 óta):** Minden shader ugyanazon a hardveren (GPU magokon) fut.

## 4. Esettanulmányok
### 4.1 Lunar Lake (Core Ultra Series 2, 2024):
*   **Cél:** Verseny a Qualcomm ARM-alapú Snapdragon X processzoraival.
*   **Felépítés:** 2-die design (Compute és Platform controller tile).
*   **Magok:** 4 P-core (Lion Cove) + 4 LPE-core (Skymont). Nincs hyperthreading.
*   **NPU 4:** Akár 48 TOPS AI teljesítmény.
*   **GPU:** Xe2 (8 mag, 8 MB L2).
*   **Akkumulátor élettartam:** 17 óra 7 perc (UL Procyon teszten), megelőzve a versenytársakat.

### 4.2 Panther Lake (Core Ultra Series 3, 2026):
*   **Technológia:** Intel 18A (első ilyen termék).
*   **Magok:** Akár 16 mag (P: Cougar Cove, E: Darkmont, LPE: Darkmont).
*   **NPU 5:** 50 TOPS.
*   **Tile-ok:** Compute tile (Intel 18A), Graphics tile (Intel 3 / TSMC N3E), SOC tile (TSMC N6). Foveros 2.5D csomagolás.

## 5. Piaci adatok és események
*   **Intel bevétele:** 1999-ben 29.4 milliárd USD, csúcs 2021-ben (79.02 mrd USD), 2024-ben 53.1 mrd USD.
*   **Piaci részesedés (Laptop):** Intel dominancia (80-90%), de az AMD (Ryzen) folyamatosan növekszik (akár 22.3% 2024 végére).
*   **Sérülékenység:** 2023. novemberében a Google jelentett komoly biztonsági hibát (Ice Lake, Alder Lake, Raptor Lake vonalaknál), amit microcode patchekkel javítottak.
*   **Részvényárfolyam:** Jelentős növekedés 2025 végétől 2026 elejéig, amit az amerikai kormány 10 milliárd USD támogatása, az NVIDIA 5 milliárd USD-s Intel részvényvásárlása és a Panther Lake sikeres startja hajtott.

---
*Jegyzet vége.*
