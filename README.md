# Projekty NGS — Bioinformatyka

Repozytorium zawiera raporty i prezentacje z projektów bioinformatycznych realizowanych w ramach zajęć z sekwencjonowania nowej generacji (NGS).

---

## 1. Analiza metylacji CpG Nanopore — żubr europejski

**Plik:** `Projekt-analizy-metylacji-CpG.pdf`

Raport z analizy metylacji DNA w dinukleotydach CpG u dwóch osobników żubra europejskiego (*Bison bonasus*) z wykorzystaniem sekwencjonowania długich odczytów Oxford Nanopore Technology (ONT). Odczyty mapowano do genomu referencyjnego bydła (*Bos taurus*, assembly ARS-UCD2.0), wykrywając modyfikacje 5mC i 5hmC przy użyciu narzędzia `modkit`.

**Kluczowe wyniki:**
- Próbka A (tryb SIMPLEX, ~3,76 mln odczytów) wykazuje średnią metylację autosomów ~89,8%, próbka B (tryb DUPLEX, ~2,37 mln odczytów) — ~79,5%.
- Różnica ~10 punktów procentowych utrzymuje się równomiernie na wszystkich chromosomach, co wskazuje na globalną różnicę epigenomiczną między osobnikami.
- Zidentyfikowano kandydujące regiony różnicowo zmetylowane (DMR) w oknach 500 kb.
- Niski poziom mapowania próbki A (44,5%) wynika prawdopodobnie z niższej jakości basecallingu (simplex vs duplex) i dywergencji sekwencji między gatunkami.

---

## 2. Analiza epigenomu *Monascus purpureus*

**Plik:** `Projekt-epigenomu-Monascus.pdf`

Sprawozdanie z integracyjnej analizy metylacji DNA (ćwiczenie 2) przeprowadzonej na grzybie *Monascus purpureus* KUPM5. Porównano szczep matczyny i potomny (po mutagenezie) przy użyciu sekwencjonowania ONT (R10.4.1 e8.2 400 bps SUP) z wykrywaniem modyfikacji 5mC, 5hmC oraz 6mA.

**Kluczowe wyniki:**
- Poziomy metylacji CpG są bardzo niskie (~0,1–0,2%), co jest typowe dla grzybów.
- Szczep potomny wykazuje konsekwentnie wyższe wartości metylacji we wszystkich 10 kontigach genomu (delta +0,006 do +0,033 p.p.).
- Zidentyfikowano 16 miejsc CpG o różnicy ≥20 p.p. (9 hypermetylowanych, 7 hypometylowanych w szczepu potomnym).
- Wyniki mają charakter eksploracyjny — brak replik biologicznych uniemożliwia wnioskowanie statystyczne.

---

## 3. Dysgeneza hybrydowa kury i przepiórki — analiza transkryptomu

**Plik:** `Projekt-hybryda-kury-i-przepiórki.pdf`

Prezentacja projektu analizującego wczesną dysgenezę hybrydową u międzygatunkowych mieszańców kury (*Gallus gallus*) i przepiórki japońskiej (*Coturnix japonica*) w stadium blastoderm EGK X. Projekt realizowany przez Wiktorię Humienną i Oliwię Grochowską.

Pipeline: pobieranie danych z ENA → kontrola jakości (FastQC/MultiQC) → przycinanie adapterów (Trimmomatic) → kwantyfikacja ekspresji (Salmon) → import danych (tximport) → analiza ekspresji różnicowej (DESeq2).

**Kluczowe wyniki:**
- Zidentyfikowano 4284 istotnie różnicowo eksprymowanych genów (padj < 0,05).
- PCA wykazała bardzo silną separację grup — PC1 wyjaśnia 89,7% wariancji, co potwierdza dominujący wpływ hybrydyzacji na profil transkryptomu.
- U hybryd wyciszone są geny rozwojowe i mitochondrialne (synteza ATP), a aktywowane — szlaki detoksykacji (cytochromy P450, transferaza S-glutationowa), co sugeruje wewnętrzny stres metaboliczny i autotoksyczność komórkową.
- Wyniki wpisują się w regułę Haldane'a dotyczącą obniżonej żywotności płci heterogametycznej u hybryd.

**Literatura:** Ishishita et al., *PLoS ONE*, DOI: 10.1371/journal.pone.0240183
