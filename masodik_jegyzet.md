# Intel – és szerepe a félvezetőiparban

**Szerző:** Dezső Sima
**Verzió:** 8.0 (2026. febr.)
**Dátum:** 2026. március 29. (Jegyzet készült)

## Előző vizsgák tanulsága

### ZH eredmények 2024

- Az összpontszám alapján a legtöbb hallgató (11 fő) alacsony pontszámot ért el.
- A görbe több csúcsot mutat (multimodális eloszlás).

## 1. Hogyan vált az Intel dominánssá a processzorpiacon?

### Történelmi mérföldkövek (Idővonal)

- **1947:** Bardeen, Brattain és Shockley feltalálják a pontkontaktusos Ge (germánium) tranzisztort a Bell Laboratories-nál.
- **1955:** Shockley Semiconductor Laboratory (SSL) alapítása.
- **1957:** A "Hűtlen Nyolcak" (Traitorous Eight) elhagyják az SSL-t és megalapítják a **Fairchild Semiconductor**-t William Shockley autoriter vezetése miatt. Köztük volt Gordon Moore és Robert Noyce is.
- **1959:** Jack Kilby (Texas Instruments) elkészíti az első működő integrált áramkört (IC).
- **1960:** Robert Noyce (Fairchild) kifejleszti az első kereskedelmileg életképes IC-t.
- **1965:** Gordon Moore megfogalmazza első előrejelzését a Fairchild-nél dolgozva.
- **1967:** Intel alapítása (egyes táblázatok szerint, de a hivatalos alapítás 1968).
- **1968:** Robert Noyce és Gordon Moore megalapítják az **Intel**-t. Noyce lett a CEO, Moore az elnök.

### A Moore-törvény evolúciója

- **1965 (Eredeti):** A tranzisztorszám az IC-ken évente nagyjából megduplázódik.
- **1975 (Módosított):** Az IC technológia fejlődése lassult; 1980-tól kezdve a tranzisztorszám megduplázódása kb. kétévente várható.
- **2003:** Az adatok igazolták a módosított előrejelzést.
- **2000-es évek eleje:** A CPU órajelek növekedése stagnálni kezdett 3-4 GHz körül a termikus és teljesítménysűrűségi korlátok miatt.

### A "Fairchild gyermekei" (Vállalatok, amiket volt Fairchild alkalmazottak alapítottak)

- **AMD:** 1968-ban alapítva (túlélt).
- **Intel:** 1967/68-ban alapítva (túlélt).
- **National Semiconductor:** 1967-ben alapítva, 2011-ben a TI felvásárolta.
- **Signetics:** 1961-ben alapítva, 1975-ben a Philips (ma NXP) felvásárolta.
- **Csak az AMD és az Intel maradt talpon független szereplőként.**

### Kulcsszemélyiségek

- **Robert Noyce (1927-1990):** Társalapító, az IC egyik feltalálója.
- **Gordon Moore (1936-2023):** Társalapító, a Moore-törvény megalkotója.
- **Andy Grove (Gróf András) (1936-2016):** Az Intel 3. alkalmazottja, 1987-1998 között CEO. A Time magazin 1997-ben az "Év emberének" választotta. 1956-ban, 20 évesen hagyta el Magyarországot.
- **Leslie Vadász (Vadász László) (1936-):** Az Intel 4. alkalmazottja. Vezette az Intel 1103 (1 Kb DRAM) tervezőcsapatát. 1956-ban hagyta el Magyarországot.

### Korai termékek és piaci váltások

- **Intel 1103 DRAM (1970. 10.):** Az első sikeres DRAM chip, kiváltotta a mágnesmagos memóriát. >3000 tranzisztor.
- **Intel 4004 (1971. 11.):** A világ első mikroprocesszora (4-bit). 2300 tranzisztor.
- **Intel 8080 (1974):** Az első széles körben elterjedt 8-bites mikroprocesszor.
- **1985. 10.:** Kilépés a DRAM üzletágból a japán verseny (NEC, Toshiba stb.) miatt.

### Az x86 architektúra felemelkedése

- **Intel 8086 (1978):** 16-bites processzor, az x86 ISA alapköve.
- **IBM PC döntés (1981):** Az IBM az Intel 8088-at választotta (költségcsökkentés miatt 8-bites busszal). Ez tette az Intel-t dominánssá.
- **Apple döntés:** Az Apple I (1976) a MOS Technology 6502-esét használta, mert olcsóbb volt, mint az Intel 8080.

---

## 2. Versenyfutás a dominanciáért a processzorpiacon

### Három fő "csatatér"

1.  **IC technológia** (gyártástechnológia).
2.  **Teljesítmény-vezetés** (nyers sebesség).
3.  **Processzor hatékonyság** (GFLOPS/W) – a 2000-es évek közepe óta alapvető paradigma.

### Gyártástechnológiai verseny (2000-2018)

- Az Intel 2014-ig vezetett (Broadwell, 14 nm).
- **10 nm-es kudarc:** A 14 nm-ről a 10 nm-re való átállás közel 4 évig tartott (Broadwell 2014 -> Cannon Lake 2018).
- Ekkor a TSMC és a Samsung beérte és megelőzte az Intelt.
- **Transzisztorsűrűség (100 millió transzisztor/mm²):**
  - Intel 10 nm: 106.
  - TSMC 7 nm: 97.
  - Samsung 7 nm: 95.

### Új elnevezési séma (2021. 07.)

Az Intel elhagyta a "nm" jelölést a félreértések elkerülése végett:

- **Intel 7:** Korábban 10 nm Enhanced Superfin.
- **Intel 4:** Korábban 7 nm, EUV litográfia teljes használata.
- **Intel 3:** További optimalizációk.
- **Intel 20A / 18A:** Az "Angström korszak", RibbonFET és PowerVia technológiákkal.

### "5 csomópont 4 év alatt" (Roadmap)

- **Intel 7:** Sorozatgyártásban.
- **Intel 4:** Gyártás alatt.
- **Intel 3:** Gyártásra kész (2023 H2). Sierra Forest (2024. 06.).
- **Intel 20A:** Törölve (2024. 09.).
- **Intel 18A:** Késleltetve 2025-re. 2024 végén a kihozatali arány (yield) < 10% volt.

### Teljesítmény verseny: Intel vs. AMD

- **2003-2005:** Az AMD megelőzte az Intelt (Opteron, 64-bit, integrált memóriavezérlő).
- **2006:** Intel Core 2 (Conroe) visszavette a vezetést (65 nm vs 90 nm, 4-wide vs 3-wide core).
- **2017:** AMD Zen architektúra (52%-kal jobb teljesítmény a Bulldozerhez képest).
- **2020. 11.:** Zen 3 (Ryzen 9 5900X) legyőzte az Intel 10. generációját (Comet Lake).
- **2021-2023:** Váltakozó vezetés az Alder Lake (12. gen), Raptor Lake (13. gen) és Zen 4/5 között.

### Laptop processzorok és hatékonyság (2024-2026)

- **2024. 06.:** Qualcomm Snapdragon X Elite/Plus belépése a Windows piacra (ARM architektúra).
- **2026. 01.:** Intel **Panther Lake** (Core Ultra Series 3) megjelenése 1.8A technológiával.
- **Benchmarks (Cinebench 2024):**
  - **Single Core:** Apple M5 (200), Snapdragon X2 Elite (146), Panther Lake CU7 (~131).
  - **Multi Core:** Snapdragon X2 Elite (1432), Panther Lake CU7 (~1210), Apple M5 (1153).
- **Hatékonyság (Points/Watt):** Apple M3 vezet (28.3), utána Snapdragon X Elite (22.6), az Intel Core Ultra 7 155H jóval lemaradva (14.5).

---

## 3. Mi az Intel jelenlegi piaci helyzete?

### Pénzügyi adatok és válság

- **2021-2023:** A bevételek minden szegmensben csökkentek.
- **Részvényárfolyam:** A 2021-es >$60-ról ~$20-ra esett 2025 közepére (2025. jún. 6.: 20.06 USD).
- **Létszámleépítés (2024. 08.):** ~15 000 munkahely megszüntetése (a munkaerő 15%-a), cél 10 milliárd dollár megtakarítás.

### Vezetésváltás

- **Pat Gelsinger:** 2024. augusztusában bejelentette lemondását, 2024. decemberében távozott.
- **Lip-Bu Tan:** 2025. márciusában nevezték ki az új CEO-nak (korábban a Cadence CEO-ja volt).

### Mentőövek és kilátások (2025-2026)

- **2025. 08.:** Az USA kormánya 8.9 milliárd (más forrás szerint 10 milliárd) dolláros befektetést eszközölt az Intel részvényeibe.
- **2025. 09.:** Az NVIDIA ~5 milliárd dollárért vásárolt Intel részvényeket.
- **2026. 01.:** A Panther Lake elindítása és az 1.8A folyamat tömeggyártása pozitív hatással volt a részvényárfolyamra, ami 2026 februárjára ~$50-re emelkedett.
