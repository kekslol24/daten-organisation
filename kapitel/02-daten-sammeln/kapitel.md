---
# bibliography: references.bib
  
execute: 
  echo: false
---

# Daten sammeln {#sec-chapter-daten-sammeln}

Bevor Daten analysiert werden können, müssen sie zuerst gesammelt werden. Je nach dem Ziel und Quelle können Daten *unstrukturiert*, *semi-strukturiert* und *strukturiert* gesammelt werden. Das Ergebnis ist immer ein Datensatz, welcher Werte für die Datenanalyse bereitstellt. Je nach Vorgehensweise kommen unterschiedliche Werkzeuge zum automatisierten und manuellen Datensammeln in Frage.

Das Ziel des Datensammelns ist das Erstellen von *Datensätzen*. 

::: {#def-datensätze}

Ein **Datensatz** umfasst zusammengehörende Werte. 

:::

Beim Sammeln von Daten werden *Beobachtungen* erfasst und dokumentiert. Dabei entspricht ein Datensatz immer einer Beobachtung. Über den zugehörigen Datensatz sollte eine Beobachtung zu einem späteren Zeitpunkt nachvollziehbar sein. Das ist allerdings nur mithilfe der erfassten Daten möglich. 

Durch nicht erfasste Daten geht Information verloren. Dieser Informationsverlust ist grundsätzlich *unvermeidbar*, weil nicht jeder Aspekt einer Beobachtung in Daten kodiert oder erfasst wird. Manche Daten sind für die spätere Analyse von besonderer Bedeutung, weil ohne sie eine Auswertung unmöglich ist. Deshalb müssen die relevanten Daten ***vor*** der Datenerhebung bestimmt werden.

## Das Datenschema

Welche Daten in einem Datensatz erfasst wurden bzw. erfasst werden sollen,  werden in einem **Datenschema** festgehalten. Das Datenschema hat zwei Funktionen.

1. Es legt fest, welche Daten für einen Datensatz erhoben werden müssen. In dieser Funktion ist das Datenschema eine grobe Anleitung welche Daten gesammelt werden sollen.
2. Es dokumentiert, welche Daten in einem Datenssatz vorliegen. Ein Datenschema hilft so Analysten, die Daten richtig zu auszuwerten und zu interpretieren.

Ein Datenschema legt Felder für die Ablage der beobachteten Daten fest.

Jedes Datenfeld erhält immer einen eindeutigen **Namen** für ein Datenfeld. Über den Namen können die im Datenfeld erfassten Daten zugegriffen werden. Die Namen von Datenfeldern dienen der einfacheren Handhabung bei der digitalen Auswertung. Deshalb sollten diese Namen möglichst einfach und gleichzeitig die Daten etwas beschreiben. Damit beim Auswerten weniger Fehler passieren, sollten Namen nur die Zeichen `a-z`, `0-9` und `_` enthalten und mit einem Buchstaben beginnen.

Zusätzlich kann ein Datenfeld einen **Wertebereich** haben. Ein Wertebereich legt die zulässigen Werte für ein Datenfeld fest. Für die automatisierte Auswertung kann es hilfreich sein, auch das **Skalenniveau** (s. [@sec-skalenniveaus]) des Wertebereichs zu dokumentieren.

Falls die Daten eine **Masseinheit** haben, muss diese auch dokumentiert werden.

Es ist üblich, für jedes Datenfeld eine **Kurzbeschreibung** anzugeben. Diese Beschreibung gibt zusätzliche Hinweise über die erfassten Werte. Die Beschreibung ist rein *informativ* und richtet sich an Menschen, die Daten für das Schema erheben oder diese Daten auswerten. 

Grundsätzlich können alle Datenfelder frei bestimmt werden. Einige Datenfelder sind für fast jede Studie gegeben. Zu diesen Datenfelder gehören beispielsweise der *Zeitpunkt der Beobachtung*, der *Ort der Beobachtung*, die *beobachtende Person* und die *Dauer der Beobachtung*. Bei der technischen Datenerfassung können weitere Felder durch die verwendeten Werkzeuge automatisch bereitgestellt werden. Deshalb sollten die technischen Möglichkeiten vor einer Datenerhebung geprüft werden, um das mehrfache abfragen der gleichen Daten zu vermeiden.

## Arten von Daten

Beim Daten sammeln werden drei Arten von Daten unterschieden: 

- Unstrukturierte Daten
- Strukturierte Daten
- Semi-strukturierte Daten

### Unstrukturierte Daten

::: {#def-unstrukturierte-daten}

**Unstrukturierte Daten** haben keinen festgelegten Wertebereich.

:::

Typische unstrukturierte Daten sind Notizen, Transkripte gespochener Sprache oder Videos. Unstrukturierte Daten können Werte von Interesse enthalten, auf die jedoch nicht direkt zugegriffen werden kann.

Unstrukturierte Daten haben den Vorteil, dass sie *Ergebnisoffen* ein. Dadurch sind unstrukturierte Daten offen für neue und unvorgesehene Information. Entsprechend werden Techniken, die unstrukturierte Daten erheben auch als ***offene*** Erhebungstechniken bezeichnet. 

Diese Offenheit hat ihren Preis, denn unstrukturierte Daten sind anfällig gegenüber Rauschen und Equivokation. Ausserdem können einzelne Werte nicht direkt aus unstrukturierte Daten abgelesen werden, sondern müssen (oft umständlich) aus den Daten extrahiert werden. 

::: {.callout-note}

Unstrukturierte Daten erfordern immer zusätzliche Arbeitsschritte, bevor mit den in ihnen vorhandenen Daten gearbeitet werden kann. Diese Arbeitsschritte zusammenfassend werden **Kodieren** (engl. **coding**) genannt. Das Kodieren unstrukturierter Daten führt einheitliche Markierungen, die sog. *Annotationen*, ein, die eine Struktur über die Daten legen.
:::

Ohne vorbereitende Kodierung lassen sich unstrukturierte Daten kaum systematisch analysieren. Sehr häufig handelt es sich bei unstrukturierten Daten um Texte. Im [Kapitel @sec-chapter-zeichenketten] werden einfache Techniken zum Verarbeiten von unstrukturierten Daten beschrieben.

### Strukturierte Daten

::: {#def-strukturierte-daten}

**Strukturierte Daten** haben einen festen Wertebereich. 

::: 

Weil strukturierte Daten einen festen Wertebereich haben, ist sichergestellt, dass nur Werte innerhalb dieses *abgeschlossenen* Bereichs gültig sind. Deshalb werden Techniken, mit denen strukturierte Daten erhoben gelten auch als ***geschlossene*** Erhebungstechniken.

Strukturierte Daten basieren immer auf einer festen Wertebereich, die Information kodiert. In dieser Struktur werden die Daten nach ihrer Bedeutung und ihren zulässigen Wertebereichen organisiert. Die feste Struktur macht strukturierte Daten innerhalb der Struktur weniger anfällig gegenüber Rauschen als unstrukturierte Daten. 

Weil strukturierte Daten eine Struktur zur Informationskodierung vorgeben, lassen sich nur Informationen über diese Struktur kodieren. Das führt zu Equivokation, weil nur die Teile der Information kodiert werden können, die in den Wertebereichen zulässig sind. 

Tabellen sind typische strukturierte Daten, die in Spalten und Zeilen organisiert sind.

Strukturierte Daten sind nicht auf Tabellen beschränkt. 

```{.YAML #lst-structured-yaml lst-cap="Strukturierte Daten im YAML-Format"}
hamster: 
- name: Fred
  gewicht: 175
  zeit: 
- name: Frida
  gewicht: 160
  zeit:
```

### Semi-strukturierte Daten

Neben diesen zwei Arten existieren noch sog. semi-strukturierte Daten. 
Semistrukturierte Daten folgen einer logischen Struktur, die allerdings nicht durchgehend strickt eingehalten wird.

::: {#def-semi-strukturierte-daten}

**Semi-strukturierte Daten** sind *unstrukturierte Daten*, die Markierungen für Werte beinhalten. 

:::

Semi-strukturierte Daten werden oft für das Einbetten  strukturierter Daten in unstrukturierte Datenfelder verwendet. 

Ein typisches Beispiel für semistrukturierte Daten sind Social-Media-Meldungen mit Hashtags und `@`-Nennungen. Mit dem Hash-Symbol (`#`) werden Themen und Inhalte hervorgehoben und mit dem `@`-Symbol werden Nutzende markiert.  Durch die beiden Symbole wird eigendlich unstrukturierten Daten eine zusätzliche Struktur gegeben, auf welche zugegriffen werden kann. Eine Social-Media-Meldung kann keine, ein oder mehrere Hashtags und keine, eine oder mehrere Nennungen enthalten. 

``` {#lst-zhaw-tweet lst-cap="Tweet mit Hashtag [@zhaw_zhaw_2023]"}
Das neue Laborgebäude auf dem ZHAW-Campus Reidbach 
in #Wädenswil wurde gestern eingeweiht. Genutzt wird der
Neubau vom Institut für Lebensmittel- und Getränkeinnovation,
wo unter einem Dach die gesamte Wertschöpfungskette von 
Lebensmitteln erforscht wird. 
https://zhaw.ch/de/ueber-uns/aktuell/news/
detailansicht-news/event-news/
lebensmittelforschung-unter-einem-dach-vereint/
```

Ein anderes Beispiel finden sich regelmässig in Bankmiteilungen im Feld "Verwendungszweck". In diesem Feld werden oft zusätzliche Daten für die Kommunikation zwischen den Beteiligten einer Transaktion hinterlegt. @lst-semistructured zeigt semistrukturierte Daten im Verwendungszweck von Banktransaktionen, diese können für eine Analyse verwendet werden.  

``` {#lst-semistructured lst-cap="Semistrukturierte Daten"}
1   PV2332 PG386.5 SV375.26 
2   PG374.23
3   Ref: 106030763221202, Knr: 783924
```

In diesem Beispiel sind einmal drei Werte, einmal ein Wert und einmal zwei Werte in einem Eintrag vorhanden. Dabei kommt die Buchstabenfolge `PG` einmal als zweiter Wert und einmal alleinstehend vor. Eine Behandlung als Tabelle dieser Werte ist wahrscheinlich nicht zielführend. 

Die Buchstabenfolgen `PV`, `PG` und `SV` sowie `Ref:` und `Knr:` erfüllen den gleichen Zweck, wie Symbole `#` und `@` in Social-Media-Meldungen. Diese Markierungen sind *Codes*, die wichtige Daten hervorheben und relativ leicht identifizieren lassen. Die Codes nehmen das Kodieren unstrukturierter Daten vorweg.  

Solche Codes sind *transaktionsspezifisch*, so dass nicht alle Codes vorkommen müssen und bestimmte Codes nur bei bestimmten Transaktionen vorkommen oder die gleichen Codes in unterschiedlichen Transaktionen andere Bedeutungen haben. Oft folgen diese Codes einem eigenen Schema. 

## Daten erheben

Die eigentliche Datensammlung kann manuell, technisch unterstützt oder automatisch erfolgen. Bei der *manuellen Datenerhebung* werden alle Daten von einer Person erfasst und festgehalten. Bei der *technisch unterstützten Datenerhebung* helfen spezielle Erhebungswerkzeuge, indem 

### Manuelle Datenerhebung

- Notizen
- Transkripte

- Listen
- Formulare
  - Papier
  - MS Forms
  - Google Forms
  - Survey-Tools: Survey Monkey, Lime Survey

Fragetypen in Formularen

- offene Fragen
  - Kurzantwort
  - Langantwort
  - Dateien hochladen
- geschlossene Fragen
  - Single choice (einfachauswahl)
  - Multiple choice (mehrfachauswahl)
  - Ranking (Sortieren, Anordnung)
  - Likert-Skala (Lineare Skala, Bewertung)
  - Semantisches Differential (Bewertung) ("Multiple Choice Grid")
  - Matrix (Multiple Choice Grid)

Durch die Wahl der Fragetypen wird die Information *kodiert*.

### Automatische Datenerhebung

- Sensoren
- Logs

## Referenzen
