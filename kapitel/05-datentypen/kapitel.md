---
# bibliography: references.bib

execute: 
  echo: false
---

# Datentypen {#sec-datentypen}

## Die fundamentalen Datentypen

Datentypen helfen uns Werte zu organisieren. Wir haben bereits drei wichtige Datentypen kennengelernt. Damit kennen wir bereits den Grossteil der wichtigsten Datentypen für einzelne Werte. Die vollständige Auflistung besteht aus fünf Datentypen:

1. Zahlen (engl. *numerics*)
2. Wahrheitswerte (engl. *booleans*)
3. Zeichenketten (engl. *strings*)
4. Fehlerwerte (engl. *error values*)
5. Undefinierte Werte (engl. *undefined values*). 

Diese Datentypen beschreiben jeweils einzelne Werte. 

::: {#def-fundamentale-datentypen}
**Fundamentale Datentypen** heissen Datentypen, die Eigenschaften für einzelne Werte festlegen.
:::

Die fundamentalen Datentypen legen die allgemeinen Wertebereiche fest, auf welchen die speziellen Wertebereiche der Datenschemata aufbauen.

### Undefinierte Werte

Gelegentlich fehlen Werte in den Daten oder wurden bei der Datenverarbeitung (noch) nicht zugewiesen. In diesen Fällen werden die "fehlenden" Werte nicht ignoriert, sondern als **undefinierte Werte** festgehalten.

::: {#def-undefinierte-werte}
Als **undefinierte Werte**  die keine Werte repräsentieren.
:::

In den meisten Programmiersprachen kennen für undefinierte Werte eine konstanten Wert. Dieser Wert ist in der Regel vom beliebigen Datentyp. 

### Zahlen

::: {#def-zahlenwerte}
Als **Zahlenwerte** werden nummerische Werte bezeichnet.
:::

Zahlenwerte können verschiedene Darstellungen haben, ohne dass sich der *Wert* der Zahl verändert (s. @sec-daten-kodieren).

Zahlenwerte können in zwei Klassen unterteilt werden:

- *Ganze Zahlen*
- *Reelle Zahlen*

Daneben unterstützen die meisten Programmiersprachen für die Datenanalyse auch *komplexe Zahlen*. Diese werden jedoch selten direkt eingegeben, sondern sind in der Regel Teil von Berechnungen.

::: {.callout-warning}
Ein Teil der reellen Zahlen sind die *Gleitkommazahlen*. Gleitkommazahlen arbeiten wie die wissenschaftliche Schreibweise von Zahlen (s. [Abschnitt @sec-wissenschaftliche-schreibweise]) mit einer Basis und einer Potenz, durch welche die Grössenordnung einer Zahl definiert ist. 

Alle reellen Zahlen werden in Computern grundsätzlich als Gleitkommazahlen abgebildet. Dadurch wird der mögliche Zahlenraum prinzipiell erweitert. Zahlen lassen sich so nicht mehr mit beliebiger Genauigkeit behandeln. Deshalb kann mit Gleitkommazahlen nicht immer exakt gerechnet werden. Das ist immer dann der Fall, wenn sehr kleine und sehr grosse Zahlen miteinander verrechnet werden. In solchen Fällen kann es zu unerwarteten Rundungsfehlern kommen.

Falls sehr genaue Berechnungen notwendig sind, dann müssen spezielle Bibliotheken verwendet werden, die mit der entsprechenden Genauigkeit umgehen können.
:::

### Wahrheitswerte

::: {#def-wahrheitswerte}
Als **Wahrheitswerte** werden die Werte `Wahr` (`True`) und `Falsch` (`False`) bezeichnet.
:::

Weil es nur zwei Wahrheitswerte gibt, werden sind Wahrheitswerte ein **binärer Datentyp**.

In den meisten Programmiersprachen lassen sich Zahlenwerte als Wahrheitswerte verwenden. Dabei wird die Zahl `0` als `Falsch` und alle anderen Zahlen als `Wahr` interpretiert.

Wahrheitswerte werden meistens zur Steuerung der Programmlogik verwendet (s. @sec-boolesche-operationen).

### Zeichenketten

::: {#def-zeichenketten}
Als **Zeichenketten** werden Werte bezeichnet, die aus einer Zeichenfolge bestehen. Dazu gehören Buchstaben, Ziffern, sowie Leer-, Satz- und Sonderzeichen.
:::

Zeichenketten setzen sich aus Symbolen zusammen, weshalb Zeichenketten eine *Länge* haben. Die Länge einer Zeichenkette entspricht der Anzahl ihrer Symbole. Entsprechend hat jedes Symbol eine eindeutige *Position* in der Zeichenkette.

Zeichenketten werden für alle Werte verwendet, die nicht als Zahlenwerte oder Wahrheitswerte dargestellt werden können. Gelegentlich müssen Zahlen als Zeichenketten dargestellt werden, um sie in einem bestimmten Format auszugeben oder für mathematische Operationen zu sperren.

In den meisen Programmiersprachen müssen Zeichenketten besonders markiert werden, damit sie von anderen Datentypen und Bezeichnern unterschieden werden können (s. @sec-variablen-fkts-ops). Die Markierung erfolgt meistens durch Anführungszeichen.

::: {.callout-note}
Programmiersprachen wie bspw. C, C++, C# oder Java verwenden für Zeichenketten den fundamentalen Datentyp des *Symbols* (oder *Character*). In diesen Programmiersprachen werden Zeichenketten als Liste von Symbolen behandelt. 

Diese Unterscheidung ist für die Programmiersprachen der Datenwissenschaften nur insofern von Bedeutung, als dass eine Zeichenkette eine Länge hat und jedes Symbol in einer Zeichenkette über dessen Position abgefragt werden kann.
:::

### Fehlerwerte

::: {#def-Fehlerwerte}
Als **Fehlerwerte** werden Werte bezeichnet, die Fehler repräsentieren.
:::

Fehlerwerte unterscheiden sich von den anderen Datentypen. Mit ihnen eine Programmierumgebung oder eine Programmiersprache an, dass ein Fehler aufgetreten ist oder eine unzulässige Operation ausgeführt wurde. Für die meisten Programmiersprachen sind die möglichen Fehler von Operationen und Funktionen dokumentiert.

Fehlerwerte können nicht mit anderen Datentypen verknüpft werden. Wird ein Fehlerwert mit einem anderen Datentyp verknüpft, dann wird der Fehlerwert als Ergebnis zurückgegeben.

Fehlerwerte geben an, welche Art von Fehler aufgetreten ist. Dadurch können regelmässig auftretende Fehler automatisch behandelt werden. Hierzu stellen alle Programmiersprachen spezielle Funktionen zur *Fehlerbehandlung* bereit.

::: {.callout-tip}
## Praxis

Ein besonderer Fehlerwert in der Datenanalyse ist der **fehlende Wert**. Er wird verwendet, wenn ein Wert nicht vorhanden ist oder nicht zugewiesen wurde. Dieser Wert ist notwendig, weil fehlende Werte (normalerweise) nicht durch den Wert `0` ersetzt werden dürfen. Er ist dem Datentyp *undefinierter Wert* vorzuziehen, weil dieser Fehlerwert einen fehlenden Wert *explizit* kennzeichnet und diesen Wert für normale Operationen sperrt, was bei undefinierten Werten nicht immer der Fall ist.
:::

## Klassen von Datentypen {#sec-skalenniveaus}

Es werden zwei Klassen von Datentypen unterschieden: 

1. Diskrete Daten 
2. Kontinuierliche Daten

::: {.callout-note}
In der Statistik heissen die folgenden Wertebereichklassen **Skalenniveaus**.
::: 

### Diskrete Daten

::: {#def-diskrete-daten}
Wenn ein Wertebereich nur eindeutige Werte enthält, dann heisst der Wertebereich *diskret*. 
:::

Ganze Zahlen, Wahrheitswerte, Zeichenketten und Fehlerwerte haben immer diskrete Wertebereiche. Undefinierte Werte umfassen nur einen einzigen Wert und können je nach Kontext diskret oder kontinuierlich sein.

Es werden drei Arten von diskreten Daten unterschieden: 

- Nominale Daten
- Ordinale Daten
- Intervallskalierte Daten

Zusätzlich erfahren *binäre Wertebereiche* oft eine besondere Behandlung in der Literatur. 

#### Nominalskalierte Daten

::: {#def-nominalskaliert}

Lassen sich alle Werte in einem Wertebereich eindeutig voneinander unterscheiden, dann liegt ein **nominalskalierter Wertebereich** vor. 

:::

*Nominalskalierte Daten* können nur durch Gleichheit oder Ungleichheit voneinander unterschieden werden. Nominalskalierte Daten können nur über Häufigkeiten zusammengefasst werden.

#### Ordinalskalierte Daten

::: {#def-ordinalskaliert}

Lassen sich alle Werte eines nominalskalierten Wertebereichs in eine eindeutige Reihenfolge sortieren, dann liegt ein **ordinalskalierter Wertebereich** vor. 

::: 

Ordinale Daten sind eine Untermenge der nominalen Daten, bei der sich die Werte im Wertebereich *sortieren* lassen. Dadurch kann jedem Wert ein *eindeutiger Rang* zugewiesen werden. Der Rang markiert die *Position* eines Werts im *sortierten Wertebereich*.

::: {.callout-note} 
Eine Reihenfolge bedeutet *nicht*, dass auch die *Abstände* zwischen allen Werten gleich sind. 
::: 

#### Binäre Daten

::: {#def-binaere-daten}
Hat ein Wertebereich genau zwei Werte, dann liegt ein **binärer Wertebereich** vor.
::: 

Binäre Wertebereiche sind ein Sonderfall unter den diskreten Daten, denn sie können entweder nominal- oder ordinalskaliert sein. 

Ein binärer Wertebereich ist ordinalskaliert, wenn die zulässigen Werte sortierbar sind. Ein häufiger Fall eines ordinalen binären Wertebereichs sind *vorher-nachher*-Markierungen.

::: {.callout-note}
## Merke
Alle binären Daten können als Wahrheitswerte dargestellt werden.
:::

Mehrere binäre Wertebereiche können durch die Verknüpfung von Zweier-Potenzen zu einem **nominalskalierten** Wertebereich zusammengefasst werden. 

#### Intervallskalierte Daten

::: {#def-invervalskalierte-daten}
Haben alle Werte in einem Wertebereich die gleichen Abstände, ist der Wertebereich **intervallskaliert**.
:::

Intervallskalierte Daten sind über die *Differenz* definiert: Werden zwei beliebige benachbarte Wertepaare ausgewählt, dann muss die Differenz zwischen Paaren, zwischen den beiden kleineren Werten und zwischen den beiden grösseren Werten jeweils zueinander gleich sein. Benachbarte Werte unterscheiden sich im Rang um $1$. 

> ::: {#exm-intervallskaliert}
> Aus dem ordinalskalierten Wertebereich der ganzen Zahlen $\mathbb{I}$ werden die Werte `1`, `2`, `5` und `6` gewählt. Die Wertepaare `1` und `2` sowie `5` und `6` sind benachbart.
> 
> Wenn der Wertebereich intervallskaliert ist, dann müssen beide Gleichungen in @eq-intervallskaliert gelten.
>
> $$
> 2 - 1 = 6 - 5 \Leftrightarrow 1 = 1 \\ und \\
> 6 - 2 = 5 - 1 \Leftrightarrow 4 = 4
> $$ {#eq-intervallskaliert}
> 
> Beide Gleichungen müssen für alle Wertepaare im Wertebereich gültig sein, was bei den ganzen Zahlen der Fall ist. Deshalb ist $\mathbb{I}$ intervallskaliert.
> :::

::: {.callout-warning}
## Wichtig
Die Abstände zwischen den einzelnen Werten lassen sich nicht für alle ordinalen Wertebereiche feststellen. *Solche Wertebereiche sind **nie** intervallskaliert*.
:::

### Kontinuierliche Daten

Lässt ein Wertebereich beliebige Abstufungen zwischen Werten zu, dann heisst dieser Wertebereich *kontinuierlich*. 

::: {#def-kontinuierliche-daten}
**Kontinuierliche Daten** liegen vor, wenn alle Werte im Wertebereich *sortierbar* sind, die *gleichen Abstände* haben und die Verhältnisse von Werten ebenfalls im Wertebereich liegen. 
:::

::: {.callout-note} 
*Kontinierliche Daten* werden auch als *metrische Daten*, *varianzskalierte Daten* oder *kardinale Skalenniveaus* bezeichnet. 
::: 

@def-kontinuierliche-daten verweist auf die Verhältnisse zwischen zwei Werten. Das Verhältnis ist das Gleiche wie ein Bruch bzw. die Division. Bei diskreten Daten können die Verhältnisse zwischen beliebigen Wertepaaren nicht so gebildet werden, dass auch alle Verhältnisse im gleichen diskreten Wertebereich liegen.


> ::: {#exm-kont-daten}
> Gegeben sind die Werte `1`, `2`, `3` und `4` aus dem *intervallskalierten* Wertebereich der ganzen Zahlen $\mathbb{I}$. 
> 
> Die Verhältnisse zwischen diesen Werten sind 
> $\frac{1}{2}$, $\frac{1}{3}$, $\frac{1}{4}$, $\frac{2}{1}$, $\frac{2}{3}$, $\frac{2}{4}$, $\frac{3}{1}$, $\frac{3}{2}$, $\frac{3}{4}$, $\frac{4}{1}$, $\frac{4}{2}$ und $\frac{4}{3}$. Nur die Verhältnisse $\frac{2}{1}$, $\frac{3}{1}$, $\frac{4}{1}$ und $\frac{4}{2}$ sind wieder ganze Zahlen und würden zum Wertebereich gehören.
> 
> Wäre der Wertebereich mit $\mathbb{R}$ festgelegt worden, dann liegen alle Verhältnisse ebenfalls im Wertebereich von $\mathbb{R}$. Daraus folgt, dass $\mathbb{R}$ ein *kontinuierlicher Wertebereich* ist.
>
> :::

Alle kontinuierlichen Daten lassen sich auf reelle Zahlen abbilden.

::: {.callout-tip}
## Praxis
Häufig stellt sich bei der Analyse der Daten heraus, dass die Werte eines eigentlich kontinuierlichen Wertebereichs nur (wenige) diskrete Werte annehmen. In diesem Fall **muss** der Wertebereich als *diskret* behandelt werden.
:::
