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

George Boole hat mit seiner Arbeit "The Mathematical Analysis of Logic" (1847) die Grundlagen für die moderne Informatik gelegt. Er hat die Grundlagen für die Boole'sche Algebra gelegt, die die Grundlage für die moderne Informatik ist. Seine Überlegungen standen im Kontext der industriellen Revolution und der damit verbundenen Entwicklung von Maschinen, die mit Hilfe von mathematischen Gleichungen gesteuert werden. Er erkannte, dass die Sprache und damit die Philosophie der Logik genau wie die Mathematik auf Grundlage von Symbolen basierte. Er fragte sich, ob Sprache und Logik einer mathematischen Analyse unterzogen werden können. Speziell interessierte ihn für seine Analyse der Zweig des *Syllogismus* in der Logik, der sich mit dem deduktiven Schlussfolgern aus Argumenten beschäftigt. 

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

> Logische Ausdrücken haben in der Programmierpraxis eine grosse Bedeutung. Aus diesem Grund verfügen alle Programmiersprachen die Möglichkeit *beliebige* Zahlen als Wahrheitswerte zu behandeln. **Dabei gilt die Konvention, dass die Zahl `0` als `FALSCH` und alle anderen Zahlen als `WAHR` interpretiert werden.**

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

Für die Arbeit mit Vektoren ist zusätzlich der Vergleich der **Existenz** wichtig. Dabei wird der Vergleich `WAHR` zurückgegeben, wenn der linke Operand ein Element des rechten Operanden ist. In diesem Fall wird der Vergleich formal als $a \in B$ geschrieben, wobei $B$ eine Menge bzw. ein Vektor von Werten ist.
