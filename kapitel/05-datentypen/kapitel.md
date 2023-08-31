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

> **Definition:** **Atomare Datentypen** heissen Datentypen, die Eigenschaften für einzelne Werte festlegen.

### Undefinierte Werte

Gelegentlich fehlen Werte in den Daten oder wurden bei der Datenverarbeitung (noch) nicht zugewiesen. In diesen Fällen werden die "fehlenden" Werte nicht ignoriert, sondern als **undefinierte Werte** festgehalten.

> **Definition:** Als **undefinierte Werte**  die keine Werte repräsentieren.

In den meisten Programmiersprachen kennen für undefinierte Werte eine konstanten Wert. Dieser Wert ist in der Regel vom beliebigen Datentyp. 

### Zahlen

> **Definition:** Als **Zahlenwerte** werden nummerische Werte bezeichnet.

Zahlenwerte können verschiedene Darstellungen haben, ohne dass sich der *Wert* der Zahl verändert. 

### Wahrheitswerte

> **Definition:** Als **Wahrheitswerte** werden die Werte `WAHR` (`TRUE`) und `FALSCH` (`FALSE`) bezeichnet. 

Weil es nur zwei Wahrheitswerte gibt, werden Wahrheitswerte auch als **binärer Datentyp** bezeichnet.

In den meisten Programmiersprachen lassen sich Zahlenwerte als Wahrheitswerte verwenden. Dabei wird die Zahl `0` als `FALSCH` und alle anderen Zahlen als `WAHR` interpretiert.

### Zeichenketten

> **Definition:** Als **Zeichenketten** werden Werte bezeichnet, die aus einer Folge von Zeichen bestehen. Dazu gehören Buchstaben, Ziffern, sowie Leer-, Satz- und Sonderzeichen.

### Fehlerwerte

> **Definition:** Als **Fehlerwerte** werden Werte bezeichnet, die Fehler repräsentieren.

## Klassen von Datentypen {#sec-skalenniveaus}

Es werden zwei Klassen von Datentypen unterschieden: 

1. Diskrete Daten 
2. Kontinuierliche Daten

::: {.remark}
In der Statistik heissen die folgenden Wertebereichklassen **Skalenniveaus**.
::: 

### Diskrete Daten

::: {#def-diskrete-daten}

Wenn ein Wertebereich nur eindeutige Werte enthält, dann heisst der Wertebereich *diskret*. 

:::

Wahrheitswerte, Zeichenketten und Fehlerwerte haben immer diskrete Wertebereiche.

Es werden drei Arten von diskreten Daten unterschieden: 

- Nominale Daten
- Ordinale Daten
- Intervallskalierte Daten

Zusätzlich erfahren *binäre Wertebereiche* oft eine besondere Behandlung in der Literatur. 

#### Nominalskalierte Daten

::: {#def-nominalskaliert}

Lassen sich alle Werte in einem Wertebereich eindeutig voneinander unterscheiden, dann liegt ein **nominalskalierter Wertebereich** vor. 

:::

**Nominalskalierte Daten** können nur durch Gleichheit oder Ungleichheit voneinander unterschieden werden. Nominalskalierte Daten können nur über Häufigkeiten zusammengefasst werden.

#### Ordinalskalierte Daten

::: {#def-ordinalskaliert}

Lassen sich alle Werte eines nominalskalierten Wertebereichs in eine eindeutige Reihenfolge sortieren, dann liegt ein **ordinalskalierter Wertebereich** vor. 

::: 

Ordinale Daten sind eine Untermenge der nominalen Daten, bei der sich die Werte im Wertebereich *sortieren* lassen. Dadurch kann jedem Wert ein *eindeutiger Rang* zugewiesen werden. Der Rang markiert die *Position* eines Werts im *sortierten Wertebereich*.

> ::: {.remark} 
> Eine Reihenfolge bedeutet *nicht*, dass auch die *Abstände* zwischen allen Werten gleich sind. 
> ::: 

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

Intervallskalierte Daten sind über die *Differenz* definiert: Werden zwei beliebige benachbarte Wertepaare ausgewählt, dann muss die Differenz zwischen Paaren, zwischen den beiden kleineren Werten und den beiden grösseren Werten jeweils zueinander gleich sein. Benachbarte Werte unterscheiden sich im Rang um $1$. 

> ::: {#exm-intervallskaliert}
> Gegeben sind die Wertepaare `1`, `2`, `5` und `6`. Die Wertepaare `1` und `2` sowie `5` und `6` sind benachbart.  aus dem ordinalskalierten Wertebereich der ganzen Zahlen $\mathbb{I}$.
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

### Kontinuierliche Daten

Lässt ein Wertebereich beliebige Abstufungen zwischen Werten zu, dann heisst dieser Wertebereich *kontinuierlich*. 

::: {#def-kontinuierliche-daten}

**Kontinuierliche Daten** liegen vor, wenn alle Werte im Wertebereich *sortierbar* sind, die *gleichen Abstände* haben und die Verhältnisse von Werten ebenfalls im Wertebereich liegen. 

:::

> ::: {.remark} 
> *Kontinierliche Daten* werden auch als *metrische Daten*, *varianzskalierte Daten* oder *kardinale Skalenniveaus* bezeichnet. 
> ::: 

@def-kontinuierliche-daten verweist auf die Verhältnisse zwischen zwei Werten. Das Verhältnis ist das Gleiche wie ein Bruch bzw. die Division. Bei diskreten Daten können die Verhältnisse zwischen beliebigen Wertepaaren nicht so gebildet werden, dass auch alle Verhältnisse im gleichen diskreten Wertebereich liegen.


> ::: {#exm-kont-daten}
> Gegeben sind die Werte `1`, `2`, `3` und `4` aus dem *intervallskalierten* Wertebereich der ganzen Zahlen $\mathbb{I}$. 
> 
> Die Verhältnisse zwischen diesen Werten sind 
> $\frac{1}{2}$, $\frac{1}{3}$, $\frac{1}{4}$, $\frac{2}{1}$, $\frac{2}{3}$, $\frac{2}{4}$, $\frac{3}{1}$, $\frac{3}{2}$, $\frac{3}{4}$, $\frac{4}{1}$, $\frac{4}{2}$ und $\frac{4}{3}$. Nur die Verhältnisse $\frac{2}{1}$, $\frac{3}{1}$, $\frac{4}{1}$ und $\frac{4}{2}$ sind wieder ganze Zahlen und würden zum Wertebereich gehören.
> 
> Wäre der Wertebereich mit $\mathbb{R}$ festgelegt worden, dann liegen alle Verhältnisse in diesem Wertebereich. $\mathbb{R}$ ist also ein *kontinuierlicher Wertebereich*.
>
> :::

Alle kontinuierlichen Daten lassen sich auf reelle Zahlen abbilden. 
