# Mit Daten arbeiten

## Importieren

## Exportieren

## Datenmanipulation

Ein grosses Problem bei der Arbeit mit Daten ist die *nachträgliche Datenmanipulation*. Dabei werden die erhobenen Daten verändert. Datenmanipulation kommt einem Datenverlust gleich, weil die ursprünglichen Daten nicht mehr verfügbar sind. 

::: {#def-datenmanipulation}
Eine **Datenmanipulation** heisst jede Veränderung von Daten bei denen Werte hinzugefügt, verändert oder gelöscht werden.
:::

::: {.callout-important}
## Keine Datenreproduktion
Wird eine Datenmanipulation entdeckt oder ist eine Manipulation sehr wahrscheinlich, dann ist es **nicht mehr möglich**, die ursprünglichen Daten zu reproduzieren. In diesem Fall gelten **alle Daten** eines Datensatzes als **komprimitiert**. Solche Daten dürfen auf keinen Fall für Analysen weiterverwendet werden.
:::

::: {.callout-tip}
## Keine Datenmanipulation
Solange die Werte im Rahmen des Schemas erhalten bleiben, liegt keine Datenmanipulation vor. Dazu gehören insbesondere:

- Korrektur von Vektornamen/Variablen und deren Übersetzung in eine andere Sprache
- begründetes Runden - nur wenn dadurch keine Datenverzerrung entsteht. Als Richtlinie gilt die Messgenauigkeit der Instrumente.
- Umbenennen von Dateien und Verzeichnissen.
- Konversion von Masseinheiten.
:::

Es gibt zwei Arten der Datenmanipulation. 

Die **absichtliche Manipulation** von Daten erfordert *aktives Eingreifen* einer Person mit Zugang zu den Daten. ist ein schweres professionelles Delikt. Diese Art von Manipulation kann das Löschen von unpassenden Daten sein, das Verändern von Werten betreffen bzw. Werte für die Studienergebnisse *passend machen* oder auch neue Daten *erfinden*. Solche Datenmanipulationen wiegen wissenschaftlich oft schwerer als Plagiarismus und können bei professionellen Analysen als Urkundenfälschung gewertet werden.

Die **versehentliche Datenmanipulation** kommt sehr viel häufiger vor als eine absichtliche Datenmanipulation. Die versehentliche Datenmanipulation kann viele Ursachen haben und reicht von der fehlerhaften Bedienung von Tools und Werkzeugen über Software-Fehler bis zum Überschreiben von Daten mit Ergebnissen. 

::: {.callout-tip}
## Praxis
Um versehentliche Datenmanipulation zu vermeiden, sollte **nie** direkt mit den Daten gearbeitet werden. Stattdessen sollten die Daten **immer** in einer separaten Datei gespeichert und versioniert werden. Aus dieser Datei werden die Daten anschliessend *importiert* und *bearbeitet*. Die Ergebnisse können in *andere* Dateien *exportiert* werden.

Durch die Versionierung kann jederzeit auf die ursprünglichen Daten zurückgegriffen und wiederhergestellt werden, selbst wenn versehentlich die Daten überschrieben und versioniert wurden. 
::: 