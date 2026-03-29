# Jegyzet: Intel Core-alapú 2S szerver processzorok

**Forrás:** nyolcadik.pdf
**Szerző:** Dezső Sima
**Dátum:** 2026. február
**Verzió:** 10.0

## 1. Bevezetés és kategóriák

- **Intel processzor kategóriák:**
  - **Szerver:** Xeon E7/E5/E3, Platinum/Gold. Konfiguráció: akár 144 mag (C).
  - **Munkaállomás (Workstation):** Xeon W7/W5/W3. Akár 60 mag.
  - **HEDT (High-End Desktop):** Core i7/i9 (Extreme Edition vagy X modellek). Akár 32 mag.
  - **Kliens (Asztali/Laptop):** Core i9/i7/i5/i3. Akár (8+16) mag + G.
  - **Mobil (Tablet/Okostelefon):** Atom vonalak (+ LP Core modellek). Akár 10 mag + G.
- **Szerver platformok osztályozása foglalatok (socket) szerint:**
  _ **UP (Uniprocessor):** 1-utas szerver platform.
  _ **MP (Multiprocessor):** Többprocesszoros platformok.
  _ **2S (DP - Dual Processor):** 2-utas platformok (ez uralja a piacot, 2016-ban a
  szállítások ~80%-a).
  _ **4S/8S (MP):** 4/8-utas platformok. \* **8+ foglalat:** Harmadik féltől származó node-kontrollert igényelnek.

## 2. Architektúrális evolúció (64-bit multicore)

Az evolúció három szakaszra osztható:

### 1. szakasz (2004 – 2007)

- **Jellemzők:** Dedikált tervek minden foglalatszámhoz. Csak "mainstream" megoldások.
- **Memória:** Az MCH-n (Memory Control Hub) keresztül csatlakozik.
- **Processzorok:** Pentium 4-től Penryn-alapúig.
- **Platform típus:** UMA (Uniform Memory Access) – minden processzor azonos késleltetéssel éri
  el a memóriát.

### 2. szakasz (2010 – 2016)

- **Jellemzők:** Dedikált tervek teljesítmény-szegmensenként (Expandable - EX, Efficient
  Performance - EP, Entry-Level - EN).
- **Memória:** Közvetlenül a processzorhoz kapcsolódik (integrált memóriavezérlő).
- **Platform típus:** NUMA (Non-Uniform Memory Access).
  - **Helyi memória elérés (Nehalem):** 65,1 ns (190 ciklus).
  - **Távoli memória elérés (Nehalem):** 106 ns (~310 ciklus).
  - **Büntetés (penalty):** 41 ns.
- **Processzorok:** Nehalem-től Broadwell-alapúig.

### 3. szakasz (2017 – napjainkig)

- **Jellemzők:** Egységesített tervek minden foglalatszámhoz és szegmenshez.
- **Elnevezés:** Scalable (Skálázható) szerver processzorok.
- **Processzorok:** Skylake-SP-től kezdődően.

## 3. Skálázható (Scalable) generációk (1-5. gen)

| Platform         | Generáció            | Technológia | Megjelenés | Magok (max) | Memória       | TDP (W) | Foglalat |
| :--------------- | :------------------- | :---------- | :--------- | :---------- | :------------ | :------ | :------- |
| **Purley**       | 1. (Skylake-SP)      | 14 nm       | 2017/07    | 28C         | 6x DDR4-2400  | 205     | LGA 3647 |
|                  | 2. (Cascade Lake-SP) | 14 nm       | 2019/04    | 28C         | 6x DDR4-2400  | 205     | LGA 3647 |
|                  | (Cascade Lake-AP)    | 14 nm       | 2019/04    | 2x28C       | 12x DDR4-2933 | 400     | BGA 5903 |
|                  | (Cascade Lake R-SP)  | 14 nm       | 2020/02    | 28C         | 6x DDR4-2933  | 165/205 | LGA 3647 |
| **Whitley**      | 3. (Ice Lake-SP)     | 10 nm       | 2021/04    | 40C         | 8x DDR4-3200  | 270     | LGA 4189 |
| **Eagle Stream** | 4. (Sapphire Rapids) | Intel 7\*   | 2023/01    | 60C         | 8x DDR5-4800  | 350     | LGA 4677 |
|                  | 5. (Emerald Rapids)  | Intel 7\*   | 2023/12    | 64C         | 8x DDR5-4800  | 330     | LGA 4677 |

_\*Az Intel 7 valójában 10 nm-es technológia._

### Naming (Elnevezési konvenció 1-5. gen):

- **1. számjegy (szint):** 8 (Platinum), 6/5 (Gold), 4 (Silver), 3 (Bronze).
- **2. számjegy (generáció):** pl. 1 = Skylake-SP.
- **Utolsó két betű (speciális):** pl. P (Cloud-IaaS), V (Cloud-SaaS), Q (Folyadékhűtés).

## 4. 6. generációs Xeon (Xeon 6)

- **Változások:** Elhagyták a "Scalable" kifejezést. Két osztály:
  - **P-cores (Performance):** Teljesítményre optimalizált (Granite Rapids).
  - **E-cores (Efficiency):** Hatékonyságra optimalizált (Sierra Forest).
- **Modellek:**
  - **6780E (Sierra Forest-SP):** Intel 3, 2024/06, 144 mag, 330W, LGA 4710.
  - **6780P (Granite Rapids-SP):** Intel 3, 2024/09, 86 mag, 350W, LGA 4710.
  - **6980E (Sierra Forest-AP):** Intel 3, 2025/02, 288 mag, 500W, LGA 7529.
  - **6980P (Granite Rapids-AP):** Intel 3, 2024/09, 128 mag, 500W, LGA 7529.

## 5. Fizikai felépítés és gyártás

- **Lapka (Die) evolúció:** Dual-die (2005) -> Single-die (2006-2021) -> Multi-die (2023-tól).
- **Die méret korlát:** ~800 mm².
  - **Maximális expozíciós terület:** 26 x 33 mm = 858 mm².
  - **Wafer átmérő:** jellemzően 300 mm (12").
- **Összeköttetés:**
  _ **EMIB (Embedded Multi-die Interconnect Bridge):** 2.5D technológia (2017-ben vezették be a
  Stratix 10-nél).
  _ **Foveros Direct 3D:** Közvetlen Cu-to-Cu kötés, 9µm bump pitch.
- **Tranzisztor számok:**
  - Nehalem-EX (2010): 2,3 milliárd.
  - Haswell-EX (2014): 5,69 milliárd.
  - Skylake-SP (2017): ~8 milliárd.
  - Sapphire Rapids MCC (becsült): ~140 milliárd (Intel 7 sűrűség: ~180M tranzisztor/mm²).

## 6. Teljesítmény trendek

- **Tranzisztor szám duplázódás:** Az L3 gyorsítótárak megjelenése után Moore törvényétől eltérve
  ~4 évente duplázódik (nem 2).
- **Magok száma:**
  - 2006-2010: ~2 évente duplázódott.
  - 2010 után: ~4 évente duplázódott a teljesítmény-sűrűség korlátok miatt.
- **Memória sebesség:**
  - DDR/DDR2: ~4 évente duplázódott.
  - DDR3/DDR4: Lelassult, ~8 évente duplázódott.
  - DDR5: Ismét gyorsult, ~4 éves duplázódás várható (DDR5-8000 2026-ban).

## 7. Belső összeköttetések (On-die interconnects)

1.  **Crossbar switch:** Korai többmagosok (2-4 mag).
2.  **Ring bus (Gyűrű):** Sandy Bridge-től (2011). Sandy Bridge-EP (2012): két 32-bites ellentétes
    irányú út.
3.  **Dual ring bus:** Haswell-EP-től (2014), ha a magszám >= 10.
4.  **2D Mesh (Háló):** Skylake-SP-től (2017). Skálázhatóbb magas magszám esetén.

## 8. Tokozás és érintkezők

- **Típusok:** LGA (Land Grid Array), PGA (Pin Grid Array), BGA (Ball Grid Array).
- **Érintkezők száma:**
  - Korai (LGA 771): 3 memória csatorna, 48 PCIe sáv.
  - Legújabb (LGA 9729-ig): akár 12 memória csatorna és 96 PCIe sáv.

## 9. Kilátások: Clearwater Forest (6+ gen)

- **Megjelenés:** 2026 első fele.
- **Technológia:** Intel 18A (back-side power delivery, RibbonFET/GAA).
- **Felépítés:** Akár 288 E-mag (Darkmont).
  - 12 CPU chiplet (Intel 18A).
  - 3 Base chiplet (Intel 3).
  - 2 IO chiplet (Intel 7).
- **Darkmont mag:** 3x3-wide decode (szemben a Sierra Forest 2x3-asával). 17%-kal magasabb IPC.
- **Paraméterek:** 12 csatornás DDR5-8000, 96 sáv PCIe 5.0, 64 sáv CXL 2.0. TDP: 300-500W.

## 10. Piaci adatok

- **AMD részesedés:** 2017-ben közel 0%, 2024 Q4-re 24,2%.
- **Nvidia-Intel együttműködés:** 2025. szept. 18-án bejelentve. Nvidia 5 milliárd dollárt fektet
  be. Intel egyedi CPU-kat tervez NVLink támogatással.
  EOF
