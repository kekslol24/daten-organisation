---
execute: 
  echo: false
---
# Daten umformen {#sec-chapter-daten-formen}

::: {.callout-warning}
## Work in Progress
:::

Viele Operationen der vorangegangenen Kapitel setzen eine vektorisierte Datenstruktur voraus. Echte Daten liegen aber meistens nicht in einem Vektor vor, sondern sind über mehrere Vektoren verteilt. Dadurch erscheinen viele Operationen komplexer als sie eigentlich sind. Durch das Umformen von Daten lassen sich viele Operationen stark vereinfachen und in der Ausführung beschleunigen. Die Grundlage vieler komplexer Algorithmen bilden Primär- und Sekundärindizes (@sec-chapter-indizieren-gruppieren). Das Ziel des Umformens ist es, Daten in eine Form zu bringen, die die effiziente Verwendung von Indizes und Gruppierungen ermöglicht.

::: {.callout-note}
## Merke
Das Umformen von Daten dient der Vereinfachung und Beschleunigung von Operationen.
:::

Oft werden nur einzelne Vektoren einer Datenstruktur und nicht die gesamte Datenstruktur umgeformt.

::: {.callout-important}
Alle Umformungen müssen umkehrbar sein, so dass für eine Datenstruktur $D$ die [Gleichung @eq-umformen-umkehrbar] gilt.
:::

$$
f_u(D) \triangleright f^{-1}_u() = f_{id}(D) = D
$$ {#eq-umformen-umkehrbar}

Lässt sich durch wiederholtes Umformen die ursprüngliche Datenstruktur nicht erzeugen, dann liegt eine **partielle Umformung** vor. 

::: {.callout-note}
## Merke
Jede *partielle Umformung* führt zu Informationsverlusst durch *Equivokation*.
:::

## Transponieren

::: {#def-transponieren}
**Transponieren** ist eine Operation, die eine Datenstruktur um 90-Grad dreht. 
:::

Es gibt zwei Arten des Transponierens.

1. Das Transponieren von Matrizen, bei dem die Zeilen und Spalten vertauscht werden. Dabei bleibt die grundsätzliche Struktur der Daten erhalten. 
2. Das Transponieren von Daten, bei mehrere Vektoren zu einem Vektor zusammengefasst werden oder ein Vektor in mehrere Vektoren aufgegliedert wird. Weil sich die Struktur der Daten verändert, wird diese Operation auch als **Reshaping** oder **Pivoting** bezeichnet.

@sec-chapter-matrix-operationen zeigt das Transponieren von Matrizen. Diese Operation wird nur verwendet, wenn eine Matrix mit einer zweiten Matrix multipliziert werden soll und die Orientierung der Matrix nicht für das Kreuzprodukt geeignet ist.

Das Transponieren von Daten entspricht dem Überführen einer Matrix in eine ihrer **Vektorformen** (s. [Abschnitt @sec-matrix-vektor-formen]). Das Transponieren ist jedoch nicht auf Matrizen beschränkt, sondern ist für Vektoren mit beliebeigen Datentyp definiert. Hat eine Datenstruktur aus geschachtelten Vektoren für alle Werte den gleichen Datentyp und haben alle Vektoren die gleiche Länge, dann wird die Datenstruktur **Matrixform** genannt und kann transponiert werden.

::: {.callout-note}
## Merke
Vektoren können nur transponiert werden, wenn alle Vektoren vom gleichen Datentyp sind.
:::

Beim Transponieren wird zwischen der **Vektorform** bzw. *Langform* und der **Matrixform** bzw. *Breitform* unterschieden. Ein Primärindex der *Matrixform* wird zum Sekundärindex der *Vektorform* und umgekehrt. Weil aus der *Vektorform* nicht eindeutig hervorgeht wie die *Matrixform* aufgebaut ist, benötigt das Transponieren einen *zusätzlichen* Sekundärindex, der die Struktur der *Matrixform* beschreibt.

Die *Vektorform* muss nicht zwingend die gleiche Anzahl Werte haben, wie die *Matrixform*. Die *Vektorform* kann auch *weniger Werte* als die *Matrixform* haben. 

::: {#def-kurze-vektorform}
Enthält eine Vektorform weniger Werte als ihre Matrixform, dann wird sie als **kurze Vektorform** bezeichnet.
:::

Beim Transponieren einer *Vektorform* mit weniger Werten als die *Matrixform*, werden die fehlenden Werte aufgefüllt. Dadurch werden neue Werte erzeugt, die nicht in den ursprünglichen Daten enthalten waren.

::: {.callout-note}
## Merke
Das Transponieren einer kurzen Vektorform in ihre Matrixform erzeugt neue Werte und führt zu Informationsverlust durch *Rauschen*.
:::

Dieses Rauschen ist jedoch kontrollierbar, wenn diese Eigenschaft bei der Umformung berücksichtigt wird.

## Hierarchisieren

Nicht immer sind alle umzuformenden Vektoren vom gleichen Datentyp. In diesem Fall können die Werte nicht transponiert werden. Stattdessen müssen die Vektoren in eine hierarchische Datenstruktur überführt werden.

::: {#def-hierarchisieren}
Das Hierarchisieren ist eine Operation, bei der Daten in eine hierarchische Datenstruktur überführt werden.
:::

Die wichtigste Operation beim Hierarchisieren ist das **Einbetten** von Daten. Das Einbetten von Daten ist eine wichtige Operation, um Daten zu strukturieren und zu organisieren. Es bildet die Grundlage für **komplexe Datenstrukturen** mit baumartigen Datenstrukturen (s. [@sec-mengen-und-baeume]). Diese Umformung ist auch als **nesting** bekannt.

::: {.callout-note}
## Merke
Beim Einbetten können die umgeformten Vektoren unterschiedliche Datentypen haben.
:::

Beim Einbetten werden die umgeformten Vektoren entlang eines Sekundärindex gruppiert. Anschliessend werden die gruppierten Vektoren in Teilstichproben getrennt und aus der ursprünglichen Datenstruktur entfernt. Die Teilstichproben enthalten nur die umzuformenden Vektoren. Weil die resultierende Datenstrukturen für alle Gruppen gleich sind, können die Teilstichproben zu einem Vektor zusammengefasst werden.

Weil alle Einträge des Sekundärindex in den neuen Vektor mit den Teilstichproben verlagert wurde, kann der Sekundärindex so reduziert werden, dass jeder *Hash* genau einmal vorkommt. Dadurch hat der Vektor des Sekundärindex die gleiche Länge wie der Vektor mit den Teilstichproben. Die beiden Vektoren können zu einem Datenrahmen zusammengefasst werden, so dass jeder Indexwert mit der zugehörigen Teilstichprobe einen Datensatz bildet. 

Die resultierende Datenstruktur ist eine hierarchische Datenstruktur, die aus einem Vektor von Datenrahmen besteht. In der neuen, eingebetteten Struktur kommen die Indexwerte nur noch einmal vor. Daraus folgt, dass der Sekundärindex in einen Primärindex überführt wurde.

