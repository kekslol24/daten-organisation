---
execute: 
  echo: false
---

# Daten organisieren

Daten sind das wichtigste Gut der Datenwissenschaften. Deshalb sollte sorgsam und systematisch mit ihnen umgegangen werden. 

## Daten strukturieren

Im [Kapitel @sec-chapter-daten-sammeln] wurde die Bedeutung des Datenschemas für das Sammeln von Daten behandelt. Ein Schema gibt vor, welche Werte einen Datensatz bilden. Dieser Abschnitt konzentriert sich auf die Umsetzung des Datenschemas. 

### Begriffe


::: {#def-messereignis}

:::

::: {#def-entitaet}

:::

::: {#def-grundgesamtheit}
Alle prinzipiell messbaren Entitäten bilden die **Grundgesamtheit**.
::: 

::: {#def-stichprobe}
Die Gesamtheit der zusammengehörenden Daten ist eine **Stichprobe**. Eine Stichprobe bildet die beobachteten Entitäten ab.
::: 

Die **Statistik** befasst sich mit den Methoden, um von Stichproben auf die ursprüngliche **Grundgesamtheit** zu schliessen. Aus Sicht der Daten und Datenverarbeitung ist die Grundgesamtheit *unerheblich*, weil die nicht gemessene Aspekte oder Entitäten unbekannt bleiben müssen!



### Daten normalisieren

Wenn Daten in einer Tabelle jeweils ein Messereignis repräsentieren, dann liegen sie in **Normalform** vor. In der Normalform ist die Tabelle gleichbedeutend mit der zugehörigen Stichprobe. Jede Zeile ist der Datensatz einer beobachteten Entität. Die Spalten repräsentieren die Messungen.

## Daten ablegen

### Dateien und Verzeichnisse

### Datenverlust vermeiden

- min. zwei speicherorte (replikation)
- versionierung
- archivierung


## Daten bereitstellen und teilen

### Datenbanken

### Webseiten, URLs und APIs

### Cloud-Speicher




--- ALT

Uns begegnen meistens Daten in Form von Tabellen. Solche Tabellen repräsentieren **Messungen**, die wir auswerten und analysieren möchten. Diese Messungen bilden einen Ausschnitt einer **Grundgesamtheit** ab. Ohne an dieser Stelle genauer auf das statische Konzept der Grundgesamtheit einzugehen, sind Daten in der Regel eine *gemessene* **Stichprobe** einer Grundgesamtheit.

> 

> **Definition**: Als **Stichprobe** wird die Gesamtheit der zusammengehörenden Daten bezeichnet.

In der Praxis sind Tabellen identisch mit der jeweiligen Stichprobe. 

> Stichproben werden in **R** als ``Data-Frame`` bezeichnet. Data-Frames werden mit der ``tibble()``- oder der ``data.frame()``-Funktion erzeugt.

> Stichproben werden in **Excel** oft als ``Tabelle`` bezeichnet. Excel-Tabellen werden nicht immer vom jeweiligen Arbeitsblatt unterschieden.

Wir repräsentieren Daten immer als eine Kombination aus Werten und Kontext, den sogenannten **Metadaten**. Zu den Metadaten gehören insbesondere Informationen über die *Bezeichnung*, den *Wertebereich* und die *Masseinheit*. Dabei kann es vorkommen, dass Wertebereich und Masseinheit nicht vorhanden sind. 

Die Metadaten einer Stichprobe werden in der Regel separat von der Stichprobe dokumentiert. Sie werden über die **Vektorennamen** in einer Tabelle referenziert. Als Vektorenname werden die Spaltenüberschriften bezeichnet. In einer Stichprobe haben die Werte in einer Spalte daher immer die gleichen Eigenschaften. 

> **Definition**: Stichprobenwerte mit den gleichen Metadaten werden als **Vektoren** bezeichnet.

Entsprechend bilden die Werte in der gleichen Spalte einen solchen Vektor.

> **Definition**: Die Zeilen einer Stichprobe beschreiben zusammengehörende Werte. Diese Werte werden als **Datensatz** bezeichnet.

> Gelegentlich werden Stichproben zeilenweise erfasst. Solche Stichproben können durch **Transponieren** in eine Spaltenform gebracht werden. In diesem Fall werden die Werte insgesamt um 90 Grad gedreht angeordnet.

Ein Datensatz kann Werte aus einer oder mehreren Messungen beinhalten. Das folgende Beispiel zeigt einen Datensatz mit Werten aus mehreren Messungen bzw. Messereignissen. Jeder Vektor in dieser Stichprobe entspricht dabei unabhängigen Messungen. 

<img src="https://github.com/dxiai/ct-resourcen/raw/main/bilder/stichprobe_nicht_normal.png" alt="Stichprobe mit mehreren Messereignissen pro Datensatz" width="500" height="182" class="img-responsive atto_image_button_text-bottom">

Ein **Messereignis** bezeichnet das gleichzeitige Erheben zusammengehörender Daten. Wenn Sie beispielsweise das gleiche Objekt zu unterschiedlichen Zeitpunkten messen, dann liegen unterschiedliche Messereignisse vor. Diese Messungen sind entsprechend **unabhängig** voneinander. Wir können uns das an einem Raum veranschaulichen, dessen Temperatur und Helligkeit wir regelmässig messen. Die am Montag um 13 Uhr gemessene Temperatur und Helligkeit gehören zum gleichen Messereignis. Die beiden gemessenen Werte sind unabhängig von anderen Messungen zu früheren oder späteren Zeitpunkten.

> Beachten Sie, dass die Unabhängigkeit die Messereignisse betrifft und nicht mit *unabhängigen Variablen* in der Statistik verwechselt werden darf.

> **Definition**: Beziehen sich alle Werte in den gleichen Datensätzen einer Stichprobe immer auf das gleiche *Messereignis*, dann liegt die Stichprobe in **Normalform** vor.

Das folgende Beispiel zeigt einen Ausschnitt einer Stichprobe in Normalform des oben dargestellten Beispiels.

[Stichprobe in Normalform](https://github.com/dxiai/ct-resourcen/blob/main/bilder/stichprobe_normalform.png?raw=true)

Die Anzahl der Datensätze in einer normalisierten Stichprobe entspricht der Anzahl der *unabhängigen* Messereignisse.
