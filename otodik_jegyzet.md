Intel’s Core-based client processors - Jegyzet

Szerző: Dezső Sima
Verzió: 8.0
Dátum: 2026. február

---

1. Bevezetés és áttekintés

- Kliens processzorok: Asztali számítógépeket (DT) és laptopokat (notebookokat) kiszolgáló
  processzorok.
- Összehasonlítás a mobil processzorokkal:
  - Kliens: x86 ISA architektúra, általában nem érintőképernyős kijelzőkhöz.
  - Mobil (táblagépek, okostelefonok): Elsődlegesen ARM ISA architektúra, érintőképernyős
    kijelzőkhöz.
- Főbb kategóriák az Intel Core családban:
  - Server: Xeon E7/E5/E3 Platinum/Gold stb. (akár 144 mag).
  - Workstation: Xeon W7/W5/W3 (akár 60 mag).
  - HEDT (High-End Desktop): Core i7/i9 Extreme Edition vagy X modellek (akár 32 mag).
  - Client: Core i9/i7/i5/i3 (akár 8+16 mag + grafika).
  - Mobile: Atom vonalak, LP Core modellek (akár 10 mag + grafika).

Intel útja a Core családig (Mérföldkövek)

- 1971: 4004 (4-bit)
- 1972: 8008 (8-bit)
- 1974: 8080 (8-bit)
- 1978: 8086 (16-bit, x86 ISA bevezetése)
- 1979: 8088 (8-bit busz)
- 1981: Az eredeti IBM PC megjelenése (8088 processzorral).
- 1982: 80186, 80286
- 1985: 80386DX (32-bit korszak kezdete)
- 1989: 80486
- 1993: Pentium (64-bit busz)
- 1995: Pentium Pro
- 1997: Pentium II
- 1999: Pentium III
- 2000: Pentium 4 (Willamette)
- 2004: 64-bit korszak (Prescott F Pentium 4 modell).
- 2006: A Core család elindítása (64-bit dual-core, maximális teljesítmény/Watt fókusz).

Generációs áttekintés (Főbb jellemzők)

- 1.  gen: Core 2 (65 nm, 2006. 06.), Penryn (45 nm, 2007. 11. - Tick), Nehalem (45 nm, 2008. 11. -
      Tock).
- 2.  gen: Sandy Bridge (32 nm, 2011. 01. - Tock).
- 3.  gen: Ivy Bridge (22 nm, 2012. 04. - Tick).
- 4.  gen: Haswell (22 nm, 2013. 06. - Tock).
- 5.  gen: Broadwell (14 nm, 2014. 09. - Tick).
- 6.  gen: Skylake (14 nm, 2015. 10. - Tock).
- 7.  gen: Kaby Lake (14 nm, 2016. 08. - Tock).
- 8.  gen: Kaby Lake R/G, Coffee Lake, Amber Lake-Y, Whiskey Lake-U, Cannon Lake (10 nm)
      (2017-2018).
- 9.  gen: Coffee Lake R (14 nm, 2018. 10.).
- 10. gen: Comet Lake (14 nm, 2019. 08.), Ice Lake (10 nm, 2019. 07. - Tock).
- 11. gen: Tiger Lake (10 nm, 2020. 09.), Rocket Lake (14 nm, 2021. 03. - Backporting).
- 12. gen: Alder Lake (Intel 7 / 10 nm, 2021. 11. - Új hibrid architektúra).
- 13. gen: Raptor Lake (Intel 7 / 10 nm, 2022. 10.).
- 14. gen: Raptor Lake Refresh (Intel 7, 2023. 10.), Meteor Lake (Intel 4 / 7 nm, 2023. 12.).

Core Ultra sorozatok (CUS)

- CUS 1: Meteor Lake (Series 1, 2023. 12.).
- CUS 2: Lunar Lake (Series 2, 2024. 09.), Arrow Lake (Series 2, 2024. 10.).
- CUS 3: Panther Lake (Series 3, 2026. 01.).

---

2. Elnevezési konvenciók
   Az Intel két elkülönülő elnevezési rendszert alkalmaz:

a) Eredeti rendszer (1-14. generációig, 2011-2023)

- Márkanév: Intel Core
- Márka módosító: i3, i5, i7, i9
- Generáció azonosító: 1 vagy 2 számjegy (pl. 7, 10, 14)
- SKU szám: 3 számjegy
- Termékvonal utótag (Suffix):
  - Mobil: Y (ultra-low power, 4.5-13 W), U (low power, 15-28 W), H (high-performance, 35-45 W).
  - Asztali: T (power-optimized, 35-45 W), S (performance-optimized, 65 W), K (unlocked, 60-95
    W).

b) Új rendszer (Core Ultra sorozat, 2023-tól)

- Márkanév: Intel Core (főáram) vagy Intel Core Ultra (prémium).
- Márka szint (Brand Level): 3, 5, 7, 9 (az "i" betű elhagyásával).
- Processzor szám: Sorozat azonosító (Meteor Lake = Series 1) + SKU (2 számjegy) + Utótag.
- Új TDP értékek: HX és K/KF utótagok akár 125 W felett is lehetnek.

---

3. Mikroarchitekturális fejlesztések

Evolúciós lépések

1.  Szimmetrikus multicore (2006-2021): Minden mag azonos (Core 2-től a 11. generációig). Cél:
    teljesítmény növelése párhuzamosítással.
2.  Single-die big.LITTLE (2021): Egy lapkán belül P-magok (teljesítmény) és E-magok (hatékonyság).
    Először az Alder Lake-nél (12. gen). Cél: fogyasztás csökkentése.
3.  Heterogén multi-die big.LITTLE (2023): Több különböző gyártástechnológiájú lapka (tiles)
    összekapcsolva. Először a Meteor Lake-nél (14. gen). Cél: gyártási költség csökkentése és
    rugalmasság.

Fontosabb technológiák

- Mag szélesség (Core width): Az utasítás-dekódolók száma. Core 2-nél 4-wide, Meteor Lake P-core
  6-wide, Lunar Lake P-core 8-wide.
- Visszaportolás (Backporting): Egy modernebb architektúra megvalósítása régebbi
  gyártástechnológiával (pl. Rocket Lake: 10 nm-es tervezés 14 nm-en).
- Tokozás (Packaging):
  - EMIB 2.5D: Beágyazott hidak a szubsztrátumban (2017).
  - Foveros 2.5D: Lapkák egymásra pakolása forrasztott mikro-gömbökkel (2019, Lakefield).
  - Foveros Direct 3D: Közvetlen réz-réz (Cu-to-Cu) hibrid kötés, forrasztás nélkül (<10 μm
    osztásköz, 2026, Panther Lake).

Memória alrendszer

- Váltás direkt kapcsolatra: Korábban az északi hídon (NB) keresztül, a Nehalem-től (2008/2009)
  kezdve a memóriavezérlő (MC) a processzorba integrált.
- Sebesség növekedés: DDR3/4 sebessége kb. 8 évente duplázódik, DDR5/LPDDRx sebessége kb. 4 évente.
- Új memóriatípusok:
  - LPCAMM2: Alacsony fogyasztású, cserélhető modul (2024, Lenovo ThinkPad P1 Gen 7).
  - CUDIMM: Órajel-vezérelt (Clocked) pufferelt DDR5 (2024 végétől).
  - On-package memória: A processzor tokján belül elhelyezett memória (Lunar Lake: 16/32 GB
    LPDDR5x-8533).

3D Grafika és Shadel-ek

- Vertex, Pixel, Geometry shader-ek.
- Unified Design: 2006 óta (Shader model 4.0) minden shader ugyanazon a hardveren (GPU magokon)
  fut.
- FP32 erőforrások: Az NVIDIA GeForce RTX 5090 például 21760 FP32 MAC műveletet tud ciklusonként
  (összesen 43520 művelet/ciklus).

---

4. Esettanulmányok

4.1 Intel Core Ultra Series 2 (Lunar Lake, 2024)

- Cél: Verseny a Qualcomm Snapdragon X (ARM) processzorokkal.
- Felépítés: 2-die heterogén design.
  - 4 P-core (Lion Cove, 8-wide).
  - 4 LPE-core (Skymont, 3x3-wide).
  - Nincs Hyper-threading.
- Memória: 16 vagy 32 GB LPDDR5x-8522 a tokozáson belül.
- AI: NPU 4 (akár 48 TOPS).
- GPU: Xe2 (8 mag).
- TDP: 17-30 W.
- Akkumulátor élettartam: 17 óra 7 perc (Procyon teszt), megelőzve a Qualcommot és az AMD-t.

4.2 Intel Core Ultra Series 3 (Panther Lake, 2026)

- Gyártástechnológia: Intel 18A (az első termék ezen a csomóponton).
- Felépítés: Akár 16 mag (P, E és LPE keveréke).
  - Compute tile (Intel 18A).
  - Graphics tile (Intel 3 / TSMC N3E).
  - SOC tile (TSMC N6).
- P-mag: Cougar Cove (8-wide decode).
- E-mag: Darkmont (3x3-wide decode).
- AI: NPU 5 (50 TOPS).
- Konfigurációk: 8 magostól a 16 magos (12 Xe magos GPU-val szerelt) változatig.
- Piac: Megjelenés 2026. H1 (első félév).

---

Piaci és pénzügyi adatok

- Biztonság: 2023. 11-ben a Google súlyos sebezhetőséget tárt fel (10-13. generációs
  processzoroknál), amit mikrokód foltokkal javítottak. Ez piaci részesedés vesztéshez vezetett.
- Piaci események (2025-2026):
  - Az amerikai kormány 10 milliárd USD támogatást adott az Intelnek.
  - Az NVIDIA 5 milliárd USD értékben vásárolt Intel részvényeket.
  - Az Intel részvényárfolyama jelentősen emelkedett a Panther Lake bejelentése után (kb. 20
    USD-ről 55 USD fölé 2026 februárjára).
- Bevételek: 2021-ben 79,02 milliárd USD, 2024-ben 53,1 milliárd USD.
