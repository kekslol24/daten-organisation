---
# bibliography: references.bib

title: Vektor-Operationen

abstract: ""

execute: 
  echo: false
---

## Sequenzen und zwei besondere Vektoren

Eine besondere Gruppe von Vektoren sind Sequenzen. 

>**Definition:** Als **Sequenz** werden Vektoren bezeichnet, bei denen die Werte aufeinanderfolgender Indizes immer den gleichen Abstand haben. 

> **Konvention:** Der *Abstand einer Sequenz* wird als **Schrittweite** bezeichnet. Wird keine Schrittweite für eine Sequenz angegeben, wird die Schrittweite 1 angenommen. 


Implizit setzt diese Definition einen Anfangswert oder einen Endwert voraus. Per Konvention wird üblicherweise der Anfangswert einer Sequenz angegeben. Wird kein Anfangswert für eine Sequenz angegeben, dann wird ebenfalls per Konvention der Wert 1 angenommen. 

> **Begriffe:** Der **Anfangswert** einer Sequenz wird auch  **Startwert** oder **Initialwert** genannt.


> **Beispiel 1:** Eine Sequenz mit der Länge 5 entspricht dem Vektor `{1,2,3,4,5}`.


> **Beispiel 2:** Eine Sequenz mit der Schrittweite 3 und der Länge 4 entspricht dem Vektor `{1,4,7,10}`.


> **Beispiel 3:** Eine Sequenz mit dem Startwert 3 und der Länge 6 entspricht dem Vektor `{3,4,5,6,7,8}`.


> **Beispiel 4:** Eine Sequenz mit dem Startwert 3, der Schrittweite 3 und der Länge 10 entspricht dem Vektor `{3,6,9,12,15,18,21,24,27,30}`.


Wir erkennen, dass eine Sequenz mit gleichem Anfangswert und Schrittweite der jeweiligen Multiplikationsreihe entspricht. Der Startwert und die Indizes der Sequenz entsprechen den Multiplikatoren. 

### Die Sequenzfunktion 

Mit der Sequenzfunktion können Sequenzen von beliebiger Länge erzeugt werden. In Excel kann die Sequenzfunktion Zeilenvektoren, Spaltenvektoren oder Matrizen erzeugen und hat den bezeichnenden Namen `SEQUENZ()`. In R erzeugt die Sequenzfunktion immer Spaltenvektoren und hat den Namen `seq()`. 

Um eine Sequenz der Länge 5 zu erzeugen, geben wir in Excel die Formel `= SEQUENZ(5)` ein. Diese Formel erzeugt einen Spaltenvektor, mit der entsprechenden Sequenz. Diese Formel entspricht in R der Operation `seq(5)`. 

Um in Excel eine Sequenz als Zeilenvektor zu erzeugen, verwenden wir die Operation `= SEQUENZ(1; 5)`, wobei der zweite Parameter der Funktion die Länge des Zeilenvektors angibt.

Der Anfangswert einer Sequenz wird in Excel als dritter Parameter der `SEQUENZ()`-Funktion übergeben. Die Operation `= SEQUENZ(6;1;3)` entspricht dem Beispiel 3. 

Wenn wir in R einen Startwert festlegen, dann müssen wir die Länge explizit markieren. Das Beispiel 3 erhalten wir also über die folgende Operation: `seq(length = 6, from = 3)`. In R können wir alternativ auch den Endwert der Sequenz übergeben. Wir könnten Beispiel 3 auch über die Operation `seq(length = 6, to = 8)` erzeugen. 


> **Merke:** In R übergeben wir den Endwert für eine Sequenz, wenn wir eine Sequenz mit einem bekannten Endwert erzeugen müssen. 


> **Beispiel** Wir möchten in R die letzten vier Werte aus Vektor der Länge 10 extrahieren. 


```
vektor = seq(length = 10, from = 7, by = 13)

vektor[ seq(length = 4, to = 10) ] # ergibt (85, 98, 111, 124)
```

Die zweite Operation können wir verallgemeinern, sodass wir die letzten vier Werte aus Vektoren mit beliebiger Länge extrahieren können: 

```
vektor[ seq(length = 4, to = length(vektor)) ] # ergibt (85, 98, 111, 124)
```

Im vorangegangenen Beispiel wird der Parameter `by` verwendet, um die Schrittweite der ersten Sequenz festzulegen. Mit diesem Parameter können wir Beispiel 2 wie folgt erzeugen: `seq(length = 4, by = 3)`. In Excel verwenden wir dazu den vierten Parameter der Funktion `SEQUENZ()`, um das gleiche Ergebnis zu erhalten: `= SEQUENZ(4; 1; 1; 3)`. 

Wir benötigen alle Parameter für Beispiel 4: 

Für Excel: 

```
= SEQUENZ(10; 1; 3; 3)
```

Für R:

```
seq(length = 10, from = 3, by = 3)
```

## Besondere Vektoren

> **Definition:** Ein Vektor mit beliebiger Länge wird als **Nullvektor** bezeichnet, wenn an allen Indizes der Wert `0` steht. 


Der *Nullvektor* ist damit eine besondere Sequenz, bei der die Schrittweite immer `0` ist.

Ein zweiter Vektor mit der Schrittweite `0` ist der *Einsvektor*. 

> **Definition:** Der **Einsvektor** ist ein Vektor mit beliebiger Länge mit dem Wert `1` bei jedem Index. 


In der mathematischen Literatur wird der *Einsvektor* oft nicht benannt. Wegen der besonderen Bedeutung dieses Vektors für verschiedene Operationen, benennen wir den Vektor hier.

> **ACHTUNG** Der **Einsvektor** darf nicht mit dem **Einheitsvektor** verwechselt werden. Im Gegensatz zum Einsvektor hat der Einheitsvektor die geometrische Länge 1. Der Einsvektor der Länge 3 hat wegen dem Satz des Pythagoras die geometrische Länge von $\sqrt{3} \approx 1.7321$

Der *Nullvektor* und der *Einsvektor* werden durch die Sequenzfunktion erzeugt, wenn die Schrittweite auf 0 festgelegt wird. 

Nullvektor mit der Länge 5 in Excel: 

```
= SEQUENZ(5; 1; 0; 0)
```

Einsvektor mit der Länge 5 in Excel: 

```
= SEQUENZ(5; 1; 1; 0)
```

Die beiden Vektoren können in R durch die folgende Sequenzfunktion erzeugt werden. 

```
seq(length = 5, from = 0, by = 0) # Nullvektor
seq(length = 5, from = 1, by = 0) # Einsvektor
```

Eleganter erreicht man dieses Ziel in R mit der Funktion `rep()`. Diese Funktion wiederholt (engl. *repeat*) einen Wert für die angegebene Länge. 

```
rep(0, 5) # Nullvektor der Länge 5
rep(1, 5) # Einsvektor der Länge 5
```

Leider gibt es für diese Funktion keine Entsprechung in Excel.

## Zählen

> **Definition:** Als **Umfang** bezeichnen wir die Anzahl der Elemente eines Vektors.


> **Definition:** Als **Grösse** bezeichnen wir den Raum, den ein oder mehrere Objekte  einnehmen. Objekte können Werte, Vektoren oder Stichproben sein.


> **Definition:** Als **Zählen** bezeichnen wir das Bestimmen der Anzahl von Elementen eines Objekts. Wir sprechen vom **Abzählen**, wenn wir zum Zählen eine **Summe über die zählbaren Einheiten** bilden. 


> Beachten Sie, dass es in der Mathematik (Mengenlehre) ein Konzept der **Abzählbarkeit** gibt. Dieses Konzept wird auf *beliebige* und insbesondere unendliche Mengen angewandt, um deren abstrakte Umfänge zu vergleichen. 
>
> Beim Rechnen und Problemlösen mit Computern haben wir es **immer** mit **speziellen, endlichen** Objekten zu tun. Wir beantworten damit immer die Frage nach dem *konkreten Umfang* der vorliegenden Objekte.


> **Definition:** Eine **zählbare Einheit** bezeichnet ein Objekt, das gezählt werden muss. Eine **nicht zählbare Einheit** bezeichnet ein Objekt, das zwar vorhanden ist, aber nicht gezählt werden darf. 


- Eine **zählbare Einheit** wird durch den Wert `1` (oder `WAHR`) repräsentiert.
- Eine **nicht zählbare Einheit** wird durch den Wert `0` (oder `FALSCH`) repräsentiert.

Eine zählbare Einheit kann mehrere Teilobjekte umfassen. Daraus ergibt sich, dass der Umfang einer endlichen Menge von Objekten gleich der Summe zählbaren Einheiten dieser Menge entspricht. Es gilt also die folgende Formel für das *Abzählen*: 

$$
\sum{zählbar(objekt)}
$$ 

Wobei die Funktion $zählbar(objekt)$ das Ergebnis 1 (oder WAHR) für eine zählbare und 0 (oder FALSCH) für eine nicht zählbare Einheit liefert. 

> In der Praxis werden wir selten die Funktion $zählbar()$ explizit definieren, sondern mit einer alternativen Funktion oder einem *logischen Ausdruck* substituieren. 

> **Merke:** Wenn wir die zählbaren Einheiten durchnummerieren, dann entspricht der Umfang dieser Einheiten der grössten Nummerierung.

## Filtern

Neben den Verzweigungen gibt es eine zweite wichtige Operation, die logische Ausdrücke verwendet: Die *Filter-Operation*. Die Filter-Operation verwendet einen logischen Ausdruck, um Datensätze gezielt aus einer Stichprobe auszuwählen. Der logische Ausdruck kann dabei beliebig komplex sein. Mit Hilfe von Filtern können wir unsere Analysen fokussieren und Fragestellungen für Teilmengen beantworten.

> **Definition:** Als Filter wird eine Funktion bezeichnet, die Datensätze mittels logischer Ausdrücke auswählt. Dabei enthält das Ergebnis nur die Datensätze, für die der jeweilige logische Ausdruck Wahr ergibt. 
