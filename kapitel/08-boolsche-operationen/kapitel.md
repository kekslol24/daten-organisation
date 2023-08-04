---
# bibliography: references.bib

title: Bool'sche Operationen

abstract: ""

execute: 
  echo: false
---

Bool'sche Operationen sind für das Programmieren von zentraler Bedeutung, weil mit ihnen regelbasierte Entscheidungen möglich sind.

> Als *Logischer Ausdruck* werden alle Funktionsketten bezeichnet, die einen Wahrheitswert als Ergebnis haben.

Die klassische Aussagenlogik ist seit der Antike Teil der Rethorik und der Philosophie. Sie wurde von Aristoteles in seiner Schrift "Peri hermeneias" (Über die Interpretation) beschrieben. Das Ziel der Aussagenlogik ist es, die Struktur von Argumenten zu analysieren und zu bewerten. 

Ein wesentliche Aufgabe der Aussagenlogik ist die Analyse von Argumenten, um sinnvolle und nicht-sinnvolle Aussagen zu unterscheiden. Dazu werden die Argumente in Voraussetzungen (*Prämissen*) und Schlussfolgerungen (*Konklusionen*) unterteilt. Die Prämissen sind die Voraussetzungen, die für die Konklusion erfüllt sein müssen. 

Die klassische Aussagenlogik ist eine *zweiwertige* Logik. Das bedeutet, dass die Aussagen entweder *wahr* oder *falsch* sein können. Es gibt keine Zwischenwerte.

Die klassische Aussagenlogik beschäftigte sich mit der Verknüpfung von Argumenten zu *Aussagen*. Dabei werden drei Arten von Aussagen unterschieden: 

- Die Tautologie bezeichnet Aussagen, die immer wahr sind.
- Die Kontradiktion bezeichnet Aussagen, die immer falsch sind.
- Die Kontingenz ist eine Aussage, die weder eine Tautologie noch eine Kontradiktion ist.

Aussagen sind also *Konklusionen*, die sich aus der Verknüpfung von Argumenten (*Prämissen*) ergeben. Die klassische Aussagenlogik untersucht, wie sich die Wahrheitswerte der Prämissen auf die Wahrheitswerte der Konklusion auswirken. Es handelt sich dabei also um die
Analyse der Verknüpfung von Argumenten zu Aussagen in Form von Wenn-Dann-Beziehungen.

Klassisch werden die folgenden Beziehungen unterschieden:

- Die Negation (NICHT) kehrt den Wahrheitswert einer Aussage um. Eine wahre Aussage wird falsch und eine falsche Aussage wird wahr.
- Die Konjunktion (UND) ist nur dann wahr, wenn beide Aussagen wahr sind.
- Die Nihilition ist nur dann wahr, wenn beide Aussagen falsch sind.
- Die Inversion ist wahr, wenn die erste Aussage wahr ist oder die zweite Aussage falsch ist.
- Die Äquivalenz ist wahr, wenn beide Aussagen den gleichen Wahrheitswert haben.
- Die Antivalenz (entweder-oder) ist wahr, wenn die beiden Aussagen unterschiedliche Wahrheitswerte haben.
- Die Disjunktion (ODER) ist wahr, wenn mindestens eine der beiden Aussagen wahr ist.
- Die Unverträglichkeit ist wahr, wenn mindestens eine der beiden Aussagen falsch ist.
- Die Implikation ist wahr, wenn die erste Aussage falsch ist oder die zweite Aussage wahr ist.

Bereits den antiken Philosophen war bekannt, dass die Negation, die Konjunktion und die Disjunktion die Grundlage für die Aussagenlogik bilden. Die anderen Beziehungen lassen sich aus diesen drei Beziehungen ableiten.

## Mathematische Operationalisierung der Aussagenlogik

George Boole hat mit seiner Arbeit "The Mathematical Analysis of Logic" (1847) die Grundlagen für die moderne Informatik gelegt. Er hat die Grundlagen für die Boole'sche Algebra gelegt, die die Grundlage sowohl für die moderne Kommunikationstechnologie als auch für die Informatik ist. Seine Überlegungen standen im Kontext der industriellen Revolution und der damit verbundenen Entwicklung von Maschinen, die mit Hilfe von mathematischen Gleichungen gesteuert werden. Er erkannte, dass die Sprache und damit die Philosophie der Logik genau wie die Mathematik auf Grundlage von Symbolen basierte. Er fragte sich, ob Sprache und Logik einer mathematischen Analyse unterzogen werden können. Speziell interessierte ihn für seine Analyse der Zweig des *Syllogismus* in der Logik, der sich mit dem deduktiven Schlussfolgern aus Argumenten beschäftigt. 

Boole wurde durch die Arbeiten von Leibniz beeinflusst, die sich mit der Formalisierung von Argumenten beschäftigten. Leibniz hatte die Idee, dass Argumente in Form von mathematischen Gleichungen dargestellt werden können. Boole hat diese Idee aufgegriffen und weiterentwickelt. 

Boole versuchte, die klassische Aussagenlogik mathematisch zu formalisieren, indem er jeder Aussage einen Wahrheitswert in Form von `0` für falsch und `1` für wahr zuordnete. Auf dieser Grundlage untersuchte er, welche mathematischen Operationen zu den bekannten Ergebnissen der klassischen Aussagenlogik führen. 

Ausgehend von den Beziehungsarten der klassischen Aussagenlogik stellte er die *Belegungen* für die möglichen Kombinationen von Wahrheitswerten in der jeweiligen Beziehung auf. D.h. er stellte die möglichen Kombinationen von Wahrheitswerten der Prämissen den Wahrheitswerten der Konklusion gegenüber. Für jede dieser Belegungen suchte Boole anschliessend nach einer arithmetischen Operation, die alle Belegungen einer Beziheung erzeugt.

### Belegungstafeln oder Wahrheitstafeln

Eine Wahrheitstafel oder Wahrheitstabelle ist eine Tabelle, die alle möglichen Kombinationen von Wahrheitswerten für einen logischen Ausdruck enthält. Weil die klassische Aussagenlogik nur zwei Wahrheitswerte kennt, müssen nur alle Kombinationen dieser beiden Werte für einen logischen Ausdruck gefunden werden.

Die Wahrheitstafel für die Negation `NICHT` sieht wie folgt aus:

| a | NICHT a |
|---|:---:|
| 0 | 1       |
| 1 | 0       |

Die in den Wahrheitstafeln aufgeführten Ergebniswerte werden auch als *Belegungen* bezeichnet. Für die logischen Basisoperationen werden diese Belegungen als *Grundbelegung* bezeichnet.

Die Grundbelegungen sind die Basis für die Bool'sche Algebra und Arithmetik. 

Die Wahrheitstafel für die Konjunktion `UND` sieht wie folgt aus:

| a | b | a UND b |
|---|---|:---:|
| 0 | 0 | 0       |
| 0 | 1 | 0       |
| 1 | 0 | 0       |
| 1 | 1 | 1       |

Für Wahrheitstafeln ist auch die Matrix-Schreibweise üblich. Dabei werden die Wahrheitswerte als Spaltenvektoren geschrieben. Die Wahrheitstafel für die Konjunktion `UND` sieht wie folgt aus:

| b \| a -> | 0 | 1 |
|---|---|---|
| 0 | 0 | 0 |
| 1 | 0 | 1 |

Verkürzt werden die Spalten und Zeilenüberschriften weggelassen und können die Belegung als Matrix schreiben:

$$
\begin{matrix}
0 & 0 \\
0 & 1
\end{matrix}
$$

Die Wahrheitstafel für die Disjunktion `ODER` sieht wie folgt aus:

| a | b | a ODER b |
|---|---|:---:|
| 0 | 0 | 0        |
| 0 | 1 | 1        |
| 1 | 0 | 1        |
| 1 | 1 | 1        |

Oder in der Matrix-Schreibweise:

$$
\begin{matrix}
0 & 1 \\
1 & 1
\end{matrix}
$$


Die Wahrheitstafel für die Exklusiv-Oder `XODER` sieht wie folgt aus:

| a | b | a XODER b |
|---|---|:---:|
| 0 | 0 | 0         |
| 0 | 1 | 1         |
| 1 | 0 | 1         |
| 1 | 1 | 0         |

Die entsprechende Belegung sieht als Matrix wie folgt aus:

$$
\begin{matrix}
0 & 1 \\
1 & 0
\end{matrix}
$$


### Boole'sche Arithmetik

Obwohl die Arbeit von Geoge Boole wegweisend für die Logik als mathematische Disziplin war, konzentrierte sich seine Arbeit auf der Übersetzung von logischen Aussagen in *arithmetische* Ausdrücke. Die Boole'sche Arithmetik ist eine Erweiterung der Arithmetik. Dabei werden logische Ausdrücke mithilfe der Grundrechenarten in berechenbare Ausdrücke übersetzt. 

Die Boole'schen Arithmetik im engeren Sinn basiert auf der Übersetzung von Wahrheitswerten in Zahlen. Dabei wird `WAHR` als `1` und `FALSCH` als `0`. 

Logische Operation | Arithmetische Operation
:---: | :---:
`NICHT` | $1 - a$
`UND` | $a \cdot b$
`ODER` | $a + b - ab$
`Entweder-Oder` (`XODER`)| $a + b - 2ab$ oder $(a-b)^2$

Weil Wahrheitswerte immer `0` oder `1` sein müssen, stellen diese Operationen sicher, dass die  Ergebnisse logischer Ausdrücke ebenfalls immer `0` oder `1` sind. Das ist vor allem für die beiden Oder-Operationen wichtig, weil die arithmetische Addition einen Wert ausserhalb der erlaubten Werte liefert, wenn beide Operanden `Wahr` bzw. `1` sind.

Boole konnte zeigen, dass die arithmetischen Operationen die gleichen Ergebnisse liefern wie die logischen Operationen der klassischen Aussagenlogik. Ausgehend von den Wahrheitstafeln zeigte Boole auch, dass die Begrenzung aus Wahrheitswerte `0` und `1` bei Additionen eine Ausgleichsoperation erfordert, damit das Ergebnis in den gleichen Wertebereich fällt.



## Boole'sche Algebra

Die Bool'sche Arithmetik ist für regelmässige Aufgaben etwas unhantlich, weil die beiden Operationen `ODER` und `Entweder-Oder` sich nicht mit einer arithmetischen Operation ausdrücken lassen. Weil die logischen Operationen einen besonderen Fall der Mengenlehre darstellen, wurden die Symbole für die Konjunktion und Disjunktion der Symbolik der Mengenlehre entlehnt.

| Logische Operation | logischer Operator | Mengenoperator | Mengenoperation |
| --- | :---: | :---: | --- |
| Negation | $\neg$ | $\notin$ | Negation |
| Konjunktion (UND) | $\land$ | $\cap$ | Schnittmenge |
| Disjunktion (ODER) | $\lor$ | $\cup$ | Vereinigung |
| Antivalenz (XODER) | $\oplus$ | $\triangle$ | Symmetrische Differenz |

Die Antivalenz kann durch die anderen drei Operationen ausgedrückt werden, weshalb sie seltener in logischen Ausdrücken verwendet wird.

### Grundregeln der Boole'sche Algebra   

Grundsätzlich gelten für die Boole'sche Algebra die gleichen Regeln wie für die Arithmetik. D.h. zuerst wird die Negation berechnet, dann `UND` abschliessend `ODER`. Diese Reihenfolge ist damit begründet, dass die `UND`-Operation der Multiplikation und die `ODER`-Operation der Addition entsprecht. Um die Reihenfolge zu ändern, werden wie üblich Klammern verwendet.

Logische Ausdrücke werden schnell komplex und unübersichtlich. Die Boole'sche Algebra definiert Regeln, die die Umformung von logischen Ausdrücken vereinfachen. Die wichtigsten Regeln sind in der folgenden Tabelle aufgelistet.

| Name | Gleichung |
| --- | :---: |
| Idempotenzgesetz | $a \land a = a$ |
| | $a \lor a = a$ |
| Tautologie | $a \lor \neg a$ = 1 | 
| Kontradiktion | $a \land \neg a$ = 0 |
| Kommutativgesetz | $a \land b = b \land a$ | 
| | $a \lor b =b \lor a$ |
| Assoziativgesetz | $(a \land b) \land c = a \land (b \land c)$ | 
| | $(a \lor b) \lor c = a \lor (b \lor c)$ |
| Distributivgesetz | $a \land (b \lor c) = a \land b \lor a \land c$ |
| |  $a \lor b \land c = (a \lor b) \land (a \lor c)$ |
| Absorptionsgesetz | $a \land (a \lor b) = a$ |
| | $a \lor a \land b = a$ |
| De Morgan'sche Regeln | $\neg (a \land b) = \neg a \lor \neg b$ |
||  $\neg (a \lor b) = \neg a \land \neg b$ |

Viele Programmiersprachen werten logische Ausdrücke von links nach rechts aus und brechen die Auswertung ab, sobald das Ergebnis feststeht. Das ist bei der Boole'schen Algebra eigentlich nicht möglich, weil die Reihenfolge der Auswertung nicht festgelegt ist. Um die Auswertung logischer Ausdrücke in Programmiersprachen zu unterstützen, sollten die Teilaussagen in ihrer Wichtigkeit und Komplexität absteigend angeordnet werden.

> Logische Ausdrücke haben in der Programmierpraxis eine grosse Bedeutung. Aus diesem Grund verfügen alle Programmiersprachen die Möglichkeit *beliebige* Zahlen als Wahrheitswerte zu behandeln. **Dabei gilt die Konvention, dass die Zahl `0` als `FALSCH` und alle anderen Zahlen als `WAHR` interpretiert werden.**

## Vergleiche

Die Vergleichsoperatoren sind in der Programmierung sehr wichtig, weil sie die Grundlage für die Kontrollstrukturen bilden. Die Vergleichsoperatoren sind in der Regel binäre Operatoren, die zwei Operanden miteinander vergleichen. Das Ergebnis ist immer ein Wahrheitswert.

Der zentrale Vergleich ist die Gleichheit. Die Gleichheit ist gegeben, wenn beide Operanden des Vergleichs gleich sind. In diesem Fall gibt dieser Vergleich `WAHR` zurück. 

Für Zahlenwerte und andere sortierbare Werte sind die Vergleiche kleiner als (`<`) und grösser als (`>`) definiert. Dabei wird der Vergleich `WAHR` zurückgegeben, wenn der linke Operand kleiner bzw. grösser als der rechte Operand ist.

Zusätzlich sind die kombinierten Vergleiche wichtig: 


|Operation|  Symbol | Alternative Schreibweise |
|---|:---:|:---:|
| ungleich| $a \neq b$ 	| $\neg(a = b)$ | 
| kleiner oder gleich | $a \leq b$ | $(a < b) \lor (a = b)$| 
| grösser oder gleich | $a \geq b$ | $(a > b) \lor (a = b)$ |

Für die Arbeit mit Vektoren ist zusätzlich der Vergleich der **Existenz** wichtig. Dabei wird der Wert `WAHR` zurückgegeben, wenn der linke Operand ein Element des rechten Operanden ist. In diesem Fall wird der Vergleich formal als $a \in B$ geschrieben, wobei $B$ eine Menge bzw. ein Vektor von Werten ist. Dieser Vergleich entspricht einer `ODER`-Operation, mit der die Elemente des Vektors $B$ einzelnt mit dem Wert $a$ auf Gleichheit geprüft werden, wie im folgenden Beispiel gezeigt wird.

$$
a \in \{ 1, 2, 3, 4, 5 \} \Leftrightarrow (a = 1) \lor (a = 2) \lor (a = 3) \lor (a = 4) \lor (a = 5)
$$

> Die expliziten Vergleiche sind nicht immer für logische Ausdrücke geeignet. In vielen Fällen sind die zu prüfenden Elemente in $B$ nicht vorab bekannt oder die Anzahl der Elemente variiert. In diesem Fall ist eine explizite `ODER`-Operation nicht möglich. Auch in weniger komplexen Fällen, empfielt es sich, die `ODER`-Operation zu vermeiden und die Existenzprüfung vorzuziehen, weil sie die Lesbarkeit eines logischen Ausdrucks erhöht. 

## Logische Ausdrücke

ogische Ausdrücke basieren auf der Verknüpfung von **Wahrheitswerten**.

> **Definition:** Ein **logischer Ausdruck** ist eine Verknüpfung von Operationen, die einen Wahrheitswert als Ergebnis haben.

> **Definition:** Als **Wahrheitswerte** werden die Werte `WAHR` (`TRUE`) und `FALSCH` (`FALSE`) bezeichnet. 

Aus diesen Definitionen folgt direkt, dass die beiden einfachsten logischen Ausdrücke die Wahrheitswerte sind.

Wahrheitswerte *können* als Zahlen geschrieben werden. Gängig ist dabei für `FALSCH` der Wert `0` und für `WAHR` der Wert `1`. Diese Unterscheidung ist unvollständig, denn die meisten Programmiersprachen interpretieren ausserdem `0` für `FALSCH` und **ungleich** `0` für `WAHR`. Diese unterschiedliche Behandlung bei der Umwandlung von Wahrheitswerten in Zahlen macht deutlich, dass Wahrheitswerte **keine** Zahlen sind, sondern ein separater **Datentyp**. 

Gelegentlich werden Zahlen als *logische Ausdrücke* verwendet. In diesem Fall wird ***implizit*** die Zahl mit dem Wert `0` verglichen. In solchen Fällen müssen wir uns diesen zusätzlichen Vergleich dazu denken. In **Excel** ist dieser gedachte Vergleich `ZAHL <> 0`, wobei `ZAHL` der jeweilige Wert einer Zahl ist. Z.B. `= 123174 <> 0`  oder `= 0 <> 0` oder `= SUMME(AQ16:BC18) <> 0`.  In **R** ist der gedachte Vergleich `ZAHL != 0`, wobei `ZAHL` eine beliebige Variable sein kann, die einen Vektor enthält. Mit diesem impliziten Vergleich erzwingen die beiden Umgebungen einen geforderten Wahrheitswert, falls dieser nicht explizit aus einer Operation folgt. 

## Vergleiche


> **Wichtig:** Sie müssen alle Vergleichsoperatoren auswendig und jederzeit korrekt anwenden können!

Neben den logischen Operationen sind Vergleiche ein wichtiges Konzept, das wir in logischen Ausdrücken regelmässig anwenden. 

Es gibt genau sechs (6) Vergleichsoperatoren für die atomaren Datentypen:

* Gleich (Excel: `=`; R: `==`)
* Ungleich (Excel: `<>`; R: `!=`)
* Grösser als (`>`)
* Grösser gleich (`>=`)
* Kleiner als (`<`)
* Kleiner gleich (`<=`)

> Bei Vergleichen müssen Sie sich sicher sein, dass Sie Werte vom gleichen Typ vergleichen.


Bei Zeichenketten werten Excel und R die alphabetische Reihenfolge der Symbole vom Beginn einer Zeichenkette aus, um grösser oder kleiner Vergleiche durchzuführen.

Für die tägliche Arbeit ist ein weiterer Vergleichsoperator wichtig: Der $\in$-Operator ist ein spezieller Vergleichsoperator, der die Existenz eines Wertes in einem Vektor bzw. einer Liste prüft.

Der folgende Ausdruck zeigt die Anwendung des $\in$-Operators:

$$
    7 \in \{ 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 \}
$$

### Sortieren

> **Definition:** Als **Sortieren** bezeichnen wir die Anordnung von Werten in einem Vektor in der Reihenfolge der Werte. 

Grundsätzlich werden 2 Sortierreihenfolgen unterschieden. Diese sind für Zahlen, Zeichenketten und Wahrheitswerte definiert: 

1. Aufsteigende Sortierung (engl. ascending)
2. Absteigende Sortierung (engl. descending)

Die Sortierrichtung basiert auf zwei paarweisen Vergleichen: 

- Die aufsteigende Sortierung beginnt mit dem kleinsten Wert des Sortierkriteriums und endet mit dem grössten Wert der Sortierung. Dabei gilt für alle Werte des sortierten Vektors  die folgende Ungleichung: 

$$
v_{Vorgänger} \le v_{Nachfolger}
$$

- Die absteigende Sortierung arbeitet genau entgegengesetzt vom grössten Wert des Sortierkriteriums zum kleinsten Wert. Entsprechend gilt für diese Reihenfolge die Ungleichung: 

$$
v_{Vorgänger} \ge v_{Nachfolger}
$$


Die Basisfunktionen für das Sortieren sind die Funktionen `sort()` (R) und `SORTIEREN()` (Excel). Diese Funktionen bringen einen Vektor in die gewünschte Reihenfolge.  Beide Funktionen können nur nach einem Vektor sortieren. Deshalb eignen sie sich  nur für einfache Sortierungen. 

> **Excels `SORTIEREN()`-Funktion** kann einen Bereich zeilen- oder spaltenweise sortieren. Diese Funktion hat vier Parameter: 

-  `Matrix` - der zu sortierende Bereich, der *keine* Matrix sein muss.
- `Sortierindex` - die Spalten- oder Zeilennummer, nach der sortiert werden soll. Standardmässig wird die erste Spalte bzw. die erste Zeile angenommen. 
- `Sortierreihenfolge` - legt die Sortierreihenfolge fest. `1`, um aufsteigend und `-1`, um absteigend zu sortieren.
- `nach_Spalte` - Ein Wahrheitswert, ob die Spalten oder die Zeilen sortiert werden sollen. `WAHR` bedeutet, dass die Spalten (horizontal) sortiert werden sollen. `FALSCH` bedeutet, dass die Zeilen (vertikal) sortiert werden sollen. Standardmässig wird zeilenweise sortiert. 


#### Die Funktionen `arrange()` und `SORTIERENNACH()`

Für allgemeine Sortierungen nach mehreren Vektoren stellen Excel und R eigene Funktionen bereit. Zwei dieser Funktionen heben sich wegen ihrer Flexibilität besonders ab. Ihnen liegt der gleiche Denkprozess zu Grunde. Diese beiden Funktionen sind:

- Die R-Funktion `arrange()` und 
- die Excel-Funktion `SORTIERENNACH()`.

Beide Funktionen ermöglichen uns, mehrere Vektoren auf einmal nach **mehreren** gemeinsamen Kriterien zu sortieren. Dazu müssen wir zuerst die Sortierkriterien identifizieren. 

#### Schritt 1: Sortierkriterien festlegen. 

Die Sortierkriterien sind durch die Werte in Vektoren festgelegt, nach denen sortiert werden soll. Wir können dazu mehrere Vektoren festlegen, deren Werte nacheinander zum Sortieren unserer Daten verwendet werden. In R legen wir die Suchkriterien über die entsprechenden *Vektornamen* und in Excel über entsprechende Vektoren oder Bereiche fest. 

- In R müssen die Vektoren mit den Suchkriterien im Stichprobenobjekt vorhanden sein.  
- In Excel können die Vektoren mit den Suchkriterien an einer beliebigen Position in einer Arbeitsmappe liegen. Dabei müssen zwei Bedingungen erfüllt sein: 
  1. Die Vektoren müssen die gleiche Länge haben. 
  2. Die Vektoren müssen die gleiche Orientierung haben. 

Sowohl in Excel als auch in R können mehrere Sortierkriterien festgelegt werden. In beiden Umgebungen werden die Suchkriterien von links nach rechts berücksichtigt. Die jeweils rechtere Bedingung kommt zum Einsatz, wenn die linkere Bedingung mehrmals den gleichen Wert nacheinander sortiert. 

#### Schritt 2: 

Im zweiten Schritt werden die zu sortierenden Vektoren ausgewählt.

In R wird dieser zweite Schritt automatisch auf die vorgegebene Stichprobe angewandt. In Excel können wir zusammenhängende Vektoren als "Matrix" an die `SORTIERENNACH()`-Funktion übergeben. Hängen die Vektoren nicht direkt zusammen, dann müssen mehrere Sortieroperationen mit den gleichen Referenzen auf die Sortierreferenzen durchgeführt werden. 

### Sortierreihenfolge

In Excel wird die Sortierrichtung als `Sortierreihenfolge` bezeichnet und als separater Parameter für das jeweilige Sortierkriterium angegeben. Dabei steht `1` für die aufsteigende Sortierung und `-1` für die absteigende Sortierung. 

In R wird grundsätzlich von einer aufsteigenden Sortierung ausgegangen. Um eine absteigende Sortierung zu erreichen, verwenden wir die Hilfsfunktion `desc()` (für engl. *descending* ~ *absteigend*). 

Das folgende R-Beispiel zeigt, wie die Daten im Stichprobenobjekt, zu erst absteigend nach dem `natel`-Vektor und anschliessend nach dem `geschlecht`-Vektor sortiert werden. 

```
daten %>% 
    arrange(
         desc(natel), # Sortierkriterium absteigend sortiert
         geschlecht   # Sortierkriterium aufsteigend sortiert
    )
```

## Entscheidungen

> **Definition:** Eine **Entscheidung** beschreibt eine Funktion, die mit Hilfe eines *logischen Ausdrucks* (oder mehr Ausdrücken) aus zwei (oder mehr) alternativen Ergebnissen *auswählt*. Eine Entscheidung ist eine besondere Transformationsfunktion zum *Umwandeln* von Daten.

### Einfache Verzweigungen

Excels Entscheidungsfunktion ist die `WENN()`-Funktion. Diese Funktion hat drei Parameter: 

1. Einen logischen Ausdruck - dieser Parameter wird als Wahrheitswert interpretiert. 
2. `WAHR`-Ergebnis - dieser Parameter wird als Ergebnis zurückgegeben, wenn der erste Parameter `WAHR` ist.
3. `FALSCH`-Ergebnis - dieser Parameter wird als Ergebnis zurückgegeben, wenn der erste Parameter `FALSCH` ist. 

Diese Funktion entscheidet mit Hilfe des logischen Ausdrucks, welcher der beiden anderen Parameter zurückgegeben werden muss. 

In R heisst diese Funktion `ifelse()` und hat genau die gleichen Parameter. 

Häufig finden wir Formeln, in denen einfach ein Wert als erster Parameter an die `WENN()`-Funktion übergeben wird. Dieser Wert wird als logischer Ausdruck interpretiert. Dabei wird der Wert `0` mit dem Wahrheitswert `FALSCH` gleichgesetzt und Werte ungleich `0` werden  als `WAHR` interpretiert.

### Abbruchbedingungen 

> **Definition:** Eine **Abbruchbedingung** ist eine spezielle Entscheidung, die einen Algorithmus beendet. Dabei wird zwischen einem *konstanten* Wert und einem *dynamischen* Wert entschieden.

Mit Hilfe von Abbruchbedingungen "schützen" wir unsere Programmlogik vor unerwünschten oder fehlerhaften Werten. 

> Genau genommen bricht dieses Konzept nicht ab, sondern verwendet  die dynamischen Werte des Vektors nicht mehr. Stattdessen werden konstante Werte zurückgegeben. Für diese Werte müssen wir einen Wert wählen, der den logischen Ausdruck der Abbruchbedingung weiterhin so erfüllt, dass der Algorithmus diese Werte ignoriert. 

### Komplexe Entscheidungen

Komplexe Entscheidungen können wir uns als eine Folge einfacher Entscheidungen vorstellen. Weil solche Entscheidungen sehr unübersichtlich sein können, bieten Excel und R Kurzformen an, mit denen wir solche Folgen einfacher schreiben können.

> **Definition:** Eine Verkettung von Entscheidungen wird als **Entscheidungsbaum** bezeichnet.

> **Definition:** Ein *Entscheidungsbaum*, der nur für einen  logischen Ausdruck genau eine Entscheidung vorsieht, heisst **linearer Entscheidungsbaum**.

### Excels WENNS

Die `WENNS()`-Funktion erlaubt es uns, verschiedene Entscheidungen zusammenzufassen. Dabei gibt es immer Paare von logischen Ausdrücken und Ergebniswerten. Die `WENNS()`-Funktion prüft nacheinander die logischen Ausdrücke und liefert als Ergebnis den Wert, der zum ersten logischen Ausdruck gehört, der WAHR ergibt. 

**Beispiel A: linearer Entscheidungsbaum**

```
=WENNS( A1 > 5; "Sehr gut"; A1 > 4; "Gut"; A1 > 3; "Genügend"; A1 <= 3; "Ungenügend")
```

Beachten Sie, dass im Beispiel der zweite logische Ausdruck auch für die Werte des ersten logischen Ausdrucks WAHR ergeben würde. Weil aber diese Fälle bereits durch den ersten logischen Ausdruck abgefangen werden, kommen diese gar nicht mehr zum zweiten logischen Ausdruck. Entsprechend müssen Sie aufpassen, dass die logischen Ausdrücke sich nicht überschneiden. 

**Beispiel B: nicht erreichbare Entscheidungen**

```
=WENNS( A1 > 5; "Sehr gut"; A1 > 3; "Genügend"; A1 > 4; "Gut"; A1 <= 3; "Ungenügend")
```

In Beispiel B kann nie das Ergebnis "Gut" angezeigt werden, weil der zweite logische Ausdruck (A1 > 3) alle Werte "maskiert", die durch den dritten logischen Ausdruck (A1 > 4) als "Gut" markiert werden müssten. "Ungenügend" würde trotzdem angezeigt werden, wenn der Wert in A1 entweder 1, 2 oder 3 ist.

In diesem Beispiel kann die Entscheidung `A1 > 4` nicht erreicht werden, weil das vorherige und allgemeinere Kriterium `A1 > 3` für die gleichen Werte zutrifft.  

> **Merke:** Es müssen also immer die spezielleren Kriterien vor den allgemeineren Kriterien geprüft werden.


Es ist guter Stil, das letzte Parameterpaar immer für den gültigen logischen Ausdruck `WAHR` zu reservieren. Damit stellen Sie sicher, dass für jeden möglichen Eingabewert ein gültiges Ergebnis zurückgegeben wird. Dieser Schritt ist notwendig, weil `WENNS()` keine Alternativausgabe hat.

**Beispiel C: Abschliessender Standardwert mit `WAHR`**

```
=WENNS( A1 > 5; "Sehr gut"; A1 > 4; "Gut"; A1 > 3; "Genügend"; UND(A1 <= 3; A1 > 0); "Ungenügend"; WAHR; "Nicht angetreten")
```
### R's `case_when()` Funktion

Die Funktion `case_when()` ist die Entsprechung für `WENNS()` in Excel. Allerdings ist die Schreibweise für die Fälle etwas anders. 

**Beispiel D: `case_when()`  Entscheidungsbaum.**

```R
data = c(1,2,3,4,5,6,0,4)

case_when(
    data <= 3 ~ "ungenügend",
    data > 5 ~ "Sehr gut",
    data > 4 ~ "gut",
    data > 3 ~ "ausreichend"
)
```

Für jeden Fall können wir einen logischen Ausdruck angeben. Dieser logische Ausdruck wird vom Tilde-Symbol (`~`) gefolgt. Dabei handelt es sich um den *"aus `a` folgt `b`"-Operator*. Die rechte Seite dieses Operators  zeigt an, welcher Wert aus dem logischen Ausdruck folgt.

> Den Parameter `data <= 3 ~ "ungenügend"` wird wie folgt gelesen: "Aus den Werten in `data`, die kleiner oder gleich `3` sind, folgt die Zeichenkette `ungenügend`. 


Wie in Excel müssen auch bei dieser Funktion die spezifischeren logischen Ausdrücke vor den unspezifischeren Ausdrücken im Entscheidungsbaum angegeben werden. 

Es ist üblich, ebenfalls eine immer zutreffende allgemeine Bedingung als letzten Parameter zu übergeben. 

**Beispiel E: abschliessende allgemeine Bedingung.**

```R
data = c(1,2,3,4,5,6,0,4)

case_when(
    data <= 3 & data > 0 ~ "ungenügend",
    data > 5 ~ "Sehr gut",
    data > 4 ~ "gut",
    data > 3 ~ "ausreichend",
    TRUE ~ "nicht angetreten"
)
```

### Sonstige Entscheidungen in Excel

In Excel gibt es zusätzlich die beiden Funktionen `WENNFEHLER()` und deren spezialisierte Form `WENNNV()`. Diese Funktionen erlauben eine kompaktere Schreibweise der typischen Fehlerbehandlung: Wenn kein Fehler erzeugt wird, dann wird das Ergebnis der Formel des ersten Parameters als Ergebnis geliefert. Wird ein Fehler erzeugt, dann wird der 2. Parameter als Rückfallwert  zurückgegeben. 

Wir sparen uns mit diesen beiden Funktionen die Schreibweise: 

```
=WENN(ISTFEHLER(A1); "Rückfallwert", A1)
```

Stattdessen schreiben wir:

```
=WENNFEHLER(A1, "Rückfallwert")
```

Das ist leichter verständlich, als die ausführliche Variante mit `WENN()`.
