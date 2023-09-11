# Mit Daten arbeiten {#sec-chapter-data-handling}

Damit mit Daten am Computer gearbeitet werden kann, müssen die Werte in die Arbeitsumgebung geladen werden. Genauso müssen die Ergebnisse der Arbeit wieder für die spätere Verwendung gesichert werden. Diese Schritte entsprechen dem *Dekodieren* und *Kodieren* von Information. Aus diesem Grund müssen die Daten sorgfältig behandelt werden, um die Datenintegrität zu gewährleisten. Das bedeutet, dass keine Daten verloren gehen. Diese spezielle Form der Equivokation kann durch ein systematisches Vorgehen vermieden werden. 

Dabei stellen bereits das Lesen und Schreiben von Daten eine eigene Fehlerquelle dar. In diesem Kapitel werden die wichtigsten Schritte beim *Importieren* (Lesen) und *Exportieren* (Schreiben) von Daten diskutiert.

## Importieren

::: {#def-import-data}
Das Lesen eines Datenstroms in eine Datenstruktur wird **Importieren** genannt.
:::

Das Importieren von Daten folgt immer in mehreren Schritten: 

1. *Lesen* eines Datenstroms.
2. *Zuordnung* der Werte zu den richtigen Datentypen.
3. *Auswahl* der zu verarbeitenden Daten.

### Daten einlesen

Beim ersten Schritt werden die Symbole eines Datenstroms in eine geeignete Datenstruktur überführt. Dabei werden die gelesenen Symbole überprüft, ob es sich um Werte oder um eine Trennmarkierung handelt. Die Werte werden entsprechend ihrer Position im Datenstrom oder über Markierungen einer Datenstruktur zugeordnet.

::: {#def-import-parsing}
Die Zuordnung von Werten in einem Datenstrom zu einer Datenstruktur wird **Parsen** genannt. Eine Funktion, die einen Datenstrom in eine Datenstruktur überführt, heisst **Parser**.
:::

Jedes Dateiformat erfordert einen eigenen *Parser*. Wird ein ungeeigneter  *Parser* verwendet, dann werden die Daten nicht korrekt importiert und können nicht weiterverarbeitet werden, weil die Datenstruktur nicht die Organisation der Daten wiedergibt. Deshalb muss beim Importieren immer ein passender Parser für das vorliegende Dateiformat verwendet werden. 

::: {.callout-note}
Für die gängigsten Datenformate existieren eigene Parser. Die Entwicklung eines Parsers für ein bestimmtes Format ist nur selten notwendig. 
:::

Die Auswahl eines geeigneten Parsers liegt in der Verantwortung der Person, die die Daten importiert. In manchen Fällen kann das Dateiformat automatisch erkannt werden. In diesen Fällen wird ein geeigneter Parser automatisch ausgewählt. Diese automatische Auswahl ist aber nicht immer korrekt. Deshalb muss das Ergebnis des Parsers immer überprüft werden.

::: {.callout-important}
## Achtung

Weil beim `CSV`-Format zwei unterschiedliche Trennzeichen verwendet werden, treten beim Importieren oft Fehler auf, weil der Parser für das falsche Trennzeichen verwendet wurde. Bei der Arbeit mit `CSV`-Dateien sollte deshalb eine Datendatei auf das verwendete Trennzeichen geprüft werden. Diese Überprüfung kann entfallen, wenn das Trennzeichen dokumentiert wurde.
:::

::: {.callout-important}
## Achtung
Beim Importieren von CSV-Dateien in der Schweiz muss zusätzlich das Dezimaltrennzeichen geprüft werden. Werden die Daten aus einer Excel-Version mit *deutschen Regionseinstellungen* exportiert, dann wird das Semikolon als Feldtrennzeichen und das Komma als Dezimaltrennzeichen verwendet. Werden die Daten aus einer Excel-Version mit *englischen Regionseinstellungen* exportiert, dann wird das Komma als Feldtrennzeichen und der Punkt als Dezimaltrennzeichen verwendet. 

In der Schweiz wird als Dezimaltrennzeichen wie im Englischen meistens ein Punkt verwendet. Werden Daten aus einer Excel-Version mit *schweizer Regionseinstellungen* werden die Trennzeichen gemischt: Als Feldtrennzeichen wird das Semikolon und als Dezimaltrennzeichen der Punkt verwendet. Das kann beim Import der Daten zu Fehlern führen, wenn das Dezimaltrennzeichen von einem Parser nicht angepasst wurde oder werden kann.
::: 

### Werte zuordnen

Der zweite Schritt beim Importieren ist die Zuordnung der Werte zu den richtigen Datentypen und der richtigen Struktur. Normalerweise versucht ein Parser bereits die richtigen Datentypen zu erkennen. Dabei kann es zu Fehlern kommen, wenn sich die Werte nicht eindeutig einem Datentyp zuordnen lassen oder ein spezieller Datentyp verwendet werden soll. 

Diesem Schritt umfasst auch das Erkennen und Behandeln von Markierungen, welche in internen Strukturen als Variablennamen oder benannten Datenfeldern abgebildet werden. Bei Separator-strukturierten Dateien umfasst dieser Teilschritt die Zuordnung von Überschriften. Bei Markup-Daten werden Tags und Markierungen für die interne Struktur verwendet.

Dieser Schritt umfasst oft auch die Behandlung von ungültigen oder fehlenden Werten.

### Daten auswählen

Gelegentlich werden mehr Daten in einem Datenstrom bereitgestellt, als für die weitere Verarbeitung benötigt werden. In solchen Fällen werden nur die Daten ausgewählt, die für die weitere Verarbeitung benötigt werden. Bei diesem Schritt werden nicht benötigte Daten aus der internen Datenstruktur entfernt. 

::: {.callout-important}
Das Auswählen von Daten bezieht sich ausschliesslich auf die interne Datenstruktur. Die ursprünglichen Daten im Datenstrom dürfen nicht verändert werden.
::: 

## Exportieren

::: {#def-export-data}
Das Schreiben von Daten aus einer Datenstruktur in einen Datenstrom heisst **Exportieren**.
:::

Beim Exportieren werden die Daten aus einer Datenstruktur in einen Datenstrom *serialisiert*. Eine Funktion die eine Datenstruktur in einen Datenstrom überführt, heisst **Serialisierer**.

Ähnlich wie beim Importieren muss auch beim Exportieren existiert für jedes Datenformat ein geeigneter Serializer. Die Wahl eines Serialisierers hängt von der späteren Verwendung der Serialisierung ab. 

::: {.callout-note}
Es ist üblich, die gleichen Daten in verschiedenen Formaten zu serialisieren.
:::

Einige Dateiformat sind sehr komplex. Dadurch sind unvollständige Serialisierungen möglich. Eine unvollständige Serialisierung kann zu Datenverlusten führen. Deshalb sollte für gängige Dateiformate immer ein existierender Serializer verwendet werden.

::: {.callout-tip}
## Praxis

Beim Exportieren von Daten die vorher importiert wurde dürfen die ursprüngliche Daten nicht überschrieben werden, weil sonst Daten verloren gehen können. Stattdessen sollten Daten beim Exportieren in eine separate Datei geschrieben werden.
:::

## Datenmanipulation

Nach dem Importieren und vor dem Exportieren muss die *Datenintegrität* sichergestellt werden. Das bedeutet, dass zwischen allen Werten und Ergebnissen eine systematische Verbindung besteht. Werte dürfen deshalb nicht *willkürlich* verändert, gelöscht oder hinzugefügt werden. 

Ein grosses Problem bei der Arbeit mit Daten ist die *nachträgliche Datenmanipulation*. Dabei werden die erhobenen Daten verändert, wobei sich die Veränderung nicht einwandfrei reproduzieren lässt. 

::: {#def-datenmanipulation}
Eine **Datenmanipulation** heisst jede Veränderung von Daten bei denen Werte unsystematisch hinzugefügt, beliebige Werte verändert oder gelöscht werden.
:::

Weil nach einer Datenmanipulation die ursprünglichen Daten nicht mehr eindeutig reproduziert werden können, lassen sich die Ergebnisse nicht mehr bestätigen oder wiederlegen. Das kommt einem vollständigen Datenverlust gleich, denn alle vorliegenden Daten können manipuliert worden sein. 

::: {.callout-important}
## Keine Datenreproduktion möglich
Wird eine Datenmanipulation entdeckt oder ist eine Manipulation sehr wahrscheinlich, dann ist es **nicht mehr möglich**, die ursprünglichen Daten zu reproduzieren. In diesem Fall gelten **alle Daten** eines Datensatzes als **komprimitiert**. Solche Daten dürfen auf keinen Fall für Analysen weiterverwendet werden.
:::

Eine Datenmanipulation ist von der systematischen Datenverarbeitung abgegrenzt werden. Bei der systematischen Datenverarbeitung werden Daten mit Hilfe von Werkzeugen und definierten Methoden verarbeitet. Dabei gehen keine Daten verloren, werden neue Werte erzeugt oder bestehende Werte verändert. Bei der systematischen Datenverarbeitung lassen sich alle Ergebnisse aus den ursprünglichen Daten herleiten.

::: {.callout-note}
## Merke

Um eine systematische Datenverarbeitung belegen zu können, müssen **Daten**, **Ergebnisse** und **alle Operationen**, die von den Daten zu den Ergebnissen, vorgehalten werden. 
:::

::: {.callout-tip}
## Keine Datenmanipulation
Solange alle Werte im Rahmen des Schemas erhalten bleiben, liegt keine Datenmanipulation vor. Dazu gehören insbesondere:

- Nachvollziehbare logische, methodische und systematische Fehler.
- Korrektur von Vektornamen/Variablen und deren Übersetzung in eine andere Sprache.
- Begründetes Runden, wenn dadurch keine Datenverzerrung entsteht. Als Richtlinie gilt die Messgenauigkeit der verwendeten Instrumente.
- Umbenennen von Dateien und Verzeichnissen.
- Umwandlung von Masseinheiten, z.B. Konvertierung von Grad Fahrenheit in Grad Celsius.
:::

Es gibt zwei Arten der Datenmanipulation. 

Die **absichtliche Manipulation** von Daten erfordert *aktives Eingreifen* einer Person mit Zugang zu den Daten. ist ein schweres professionelles Delikt. Diese Art von Manipulation kann das Löschen von unpassenden Daten sein, das Verändern von Werten betreffen bzw. Werte für die Studienergebnisse *passend machen* oder auch neue Daten *erfinden*. Solche Datenmanipulationen wiegen wissenschaftlich oft schwerer als Plagiarismus und können bei professionellen Analysen als Urkundenfälschung gewertet werden.

Die **versehentliche Datenmanipulation** kommt sehr viel häufiger vor als eine absichtliche Datenmanipulation. Die versehentliche Datenmanipulation kann viele Ursachen haben und reicht von der fehlerhaften Bedienung von Tools und Werkzeugen über Software-Fehler bis zum Überschreiben von Daten mit Ergebnissen. 

Eine sehr häufig vorkommende Form der versehentlichen Datenmanipulation ist die automatische Datentyperkennung von Excel. Dabei werden Daten beim Import oder bei der Eingabe in einer Excel-Arbeitsmappe in einen *unerwünschten* Datentyp geändert, wobei sich auch der Wert der Daten ändert. Wenn durchgehend mit Excel gearbeitet wird, müssen diese Fehler vorgebeugt werden. Diese Praktiken erfordern von allen Beteiligten eine grosse Arbeitsdisziplin, was sich im Alltag nicht immer fordern lässt. Deshalb ist es oft einfacher, die Daten in einem einfacheren Dateiformat (z.B. CSV oder JSON) zu erfassen und anschliessend diese Daten in Excel als externe Daten zu importieren.

::: {.callout-tip}
## Praxis

Um versehentliche Datenmanipulation zu vermeiden, sollte ausser bei Messungen **nie** direkt mit den Daten gearbeitet werden. Stattdessen sollten die Daten **immer** in einer separaten Datei gespeichert und versioniert werden. Aus dieser Datei werden die Daten anschliessend *importiert* und *bearbeitet*. Die Ergebnisse können in *andere* Dateien *exportiert* werden.

Durch die Versionierung kann jederzeit auf die ursprünglichen Daten zurückgegriffen und wiederhergestellt werden, selbst wenn sie versehentlich oder absichtlich überschrieben oder gelöscht wurden. 
::: 
