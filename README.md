# Korszerű számítógép-architektúrák összefoglaló

## 1. Az Intel szerepe és a félvezetőipar fejlődése

### 1.1. Alapítás és a kezeti sikerek
*   **Alapítás:** 1968, Robert Noyce és Gordon Moore.
*   **Kulcsszereplők:** Andy Grove (Gróf András) és Leslie Vadasz (Vadász László).
*   **Első sikerek:** 1103 DRAM (1970), 4004 mikroprocesszor (1971).

### 1.2. Moore törvénye és a Pentium 4 tanulságai
*   **Moore törvénye:** A tranzisztorszám 2 évente duplázódik.
*   **A Pentium 4 kudarc (2000-2004):** A 10 GHz-es cél elmaradt aPrescott mag túlzott hőtermelése miatt.
*   **Tanulságok:** Átállás a **teljesítmény/Watt (GFLOPS/W)** szemléletre és a **Tick-Tock** modellre.

### 1.3. Fejlesztési modellek
*   **Tick-Tock:** Tick (technológia váltás), Tock (új architektúra).
*   **Backporting:** Új architektúra régebbi technológián (pl. Rocket Lake 14nm-en).
*   **Single-phase:** Új technológia és architektúra egyszerre (Core Ultra széria).

### 1.4. Az x86 ISA és a SIMD fejlődése
*   **SSE (1999):** 128 bites FP, dedikált regiszterek.
*   **AVX (2011):** 256 bites FP, 16 regiszter (YMM).
*   **AVX-512 (2017):** 512 bites, 32 regiszter (ZMM).
*   **Aliasing:** Regiszter-átfedés (XMM0 ⊂ YMM0 ⊂ ZMM0).

### 1.5. Gyártástechnológia és a TSMC szerepe
*   **20A törlése:** Az Intel a 18A-ra fókuszál.
*   **Outsourcing:** A **Lunar Lake** és **Arrow Lake** számítási lapkáit a **TSMC (N3)** gyártja.
*   **18A mérföldkő:** A **Panther Lake** (2026) és a **Clearwater Forest** már saját 18A technológiával készül.

---

## 2. Kliens processzorok (Desktop és Laptop)

### 2.1. Névkonvenciók
*   **Core Ultra (Prémium):** Nincs "i", Series identifier (1, 2, 3) + SKU + Suffix (pl. 185H).
*   **Core (Mainstream):** Core 3/5/7 (pl. 150U).

### 2.2. Core Width (Szélesség)
*   Az utasítás-dekódolók száma.
*   **Panther Lake:** 8-wide Cougar Cove (P) és 3x3-wide Darkmont (E) magok.

### 2.3. Thread Director (TD)
*   Hardveres ütemezés támogatás. Panther Lake-ben **TD v2** (LP-E, E és P osztályok kezelése).

### 2.4. Tokozás (Packaging)
*   **EMIB:** 2.5D, Si-hidak a hordozóban.
*   **Foveros:** 3D rétegzés.
*   **Foveros Direct 3D:** Cu-Cu hybrid bonding (Clearwater Forest).

### 2.5. Esettanulmány: Lunar Lake (2024)
*   4P + 4LP-E mag, **nincs Hyper-Threading**, on-package LPDDR5x, NPU 4 (48 TOPS).

---

## 3. Szerver processzorok (2S / Dual-Socket)

### 3.1. Memóriahozzáférés: UMA vs. NUMA
*   **UMA (Uniform Memory Access):** Régebbi rendszerek (MCH-n keresztül), minden processzor azonos sebességgel éri el a memóriát.
*   **NUMA (Non-Uniform Memory Access):** Nehalem óta. Helyi memória elérése gyorsabb (~65ns), távolié lassabb (~106ns). A különbség az inter-processor access penalty (~41ns).

### 3.2. Belső összeköttetések (Interconnects)
*   **Ring Bus:** Sandy Bridge-től, kb. 15 magig hatékony.
*   **2D Mesh:** Skylake-SP óta. 2D grid struktúra routerekkel. Előnye a kisebb késleltetés és nagyobb sávszélesség magas magszámnál.

### 3.3. Xeon 6 generáció (2024-2025)
*   **Sierra Forest (Xeon 6E):** Csak E-magok (Crestmont), nagy sűrűség (akár 288 mag), hatékonyságra optimalizálva.
*   **Granite Rapids (Xeon 6P):** P-magok (Redwood Cove), SMT támogatás, teljesítményre optimalizálva (akár 128 mag).
*   **MRDIMM:** Multiplexed Rank DIMM, 30-40%-os sávszélesség növekedés.

### 3.4. Jövőkép: Clearwater Forest (2026)
*   Intel **18A** technológia, akár 288 **Darkmont** E-mag, **Foveros Direct 3D** tokozás.

---

## 4. Lehetséges ZH kérdések és válaszok

*   **K: Hogyan értelmezzük a CPU magok szélességét?**
    *   **V:** Az utasítás-dekódolók számával.
*   **K: Mely két előnnyel rendelkezik a memória direkt csatolása a lapkára?**
    *   **V:** Csökkenti a memória elérési idejét és növeli a sávszélességet multiprocesszoros szerverekben.
*   **K: Mely két előnnyel rendelkeznek az LPDDRx memóriák az LPDDR-rel szemben?**
    *   **V:** Nagyobb sebességet biztosítanak és kisebb a fogyasztásuk.
*   **K: Milyen előnyökkel járnak a szimmetrikus többmagos processzorok?**
    *   **V:** Egyszerűsítik a magok ütemezését és a disszipáció kezelését.
*   **K: Milyen céllal vezette be az Intel a big.LITTLE architektúrát?**
    *   **V:** A fogyasztás csökkentése céljából.
*   **K: Miért vezette be az Intel a heterogén több-lapkás (multi-die) kialakítást?**
    *   **V:** A gyártási költségek csökkentése érdekében.
