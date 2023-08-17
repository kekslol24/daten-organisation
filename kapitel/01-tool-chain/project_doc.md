---
# bibliography: references.bib

title: Dokumentation

abstract: ""

execute: 
  echo: false
---

Die Projektdokumentation dokumentiert die Organisation und Struktur eines Projekts. Die *Projektdokumentation* unterscheidet sich von einem *Projektbericht*. Die Projektdokumentation enthält alle relevanten Informationen, um ein Projekt nachzuvollziehen und zu reproduzieren. Ein Projektbericht fasst die Methode, die Ergebnisse und ggf. die Rückschlüsse zusammen. 

Eine vollständige **Projektdokumentation** enthält die folgenden Teile.

- Projekthistorie 
- Entscheidungen und Massnahmen
- Projektmotivation bzw. Ausgangslage
- Repository-Organisation
- Technische Information zur Arbeit mit dem Projekt
- Externe Bibliotheken bzw. Abhängigkeiten.
- Vertraulichkeit und Verwendungsrechte

Die Versionierungsgeschichte wird von `git` automatisch erstellt. Die **Commit-Meldungen** dokumentieren die Massnahmen, welche in der zugehörenden Version umgesetzt wurden. Weil Die Commit-Meldungen nicht viel Platz zu dokumentation bieten, werden Entscheidungen in der Regels als **Issues** und Massnamen als **Pull-Requests** einer `git`-Hosting-Plattform dokumentiert. Dabei gilt, dass *offene* Issues oder Pull-Requests noch nicht und *geschlossene* Issues und Pull-Requests vollständig im Projekt umgesetzt wurden. Commit-Meldungen müssen dann nur noch auf die zugehörigen *Issues* referenzieren.

Per Konvention werden in der Datei `README.md` bzw. `README` die Ausgangslage und Motivation, technische Informationen sowie die Repository-Organisation dokumentiert. Diese Dokumentation ist notwendig, um mit dem Projekt arbeiten zu können. Zu den technischen Informationen gehören alle Informationen, die benötigt werden, um mit den Daten oder dem Code zu arbeiten. Für Daten ist die Struktur der Daten, die Namen und die Datentypen der Vektoren anzugeben. Für Code ist die Programmiersprache, eine Anleitung, um den Code laufen zu lassen, sowie ein Beispielaufruf anzugeben. 

Bibliotheken, Module oder Pakete, die in einem Projekt verwendet werden, aber separat installiert werden müssen, bezeichnet man als **externe Abhängigkeiten**. Diese sind ebenfalls zu dokumentieren, damit alle externen Abhängigkeiten in einer neuen Arbeitsumgebung korrekt installiert werden können. Dieser Teil der Projektdokumentation benötigt den Namen der verwendeten Bibliothek sowie die erforderliche Versionsnummer. Für meisten modernen Programmiersprachen existieren sog. *Packetmanager*, welche die externen Abhängigkeiten in einer Datei dokumentieren und installieren können.

Per Konvention wird die **Vertraulichkeit** und **Verwendungsrechte** in der Datei `LICENCE.md` oder `LICENSE` dokumentiert. Dabei handelt es sich um ein rechtliches Dokument, dass oft von einer Organisation oder Auftraggeber vorgegeben wird oder, wie im Fall von Open Source Lizenzen, durch einen Verband erstellt wurden. Die Lizenzdatei wird in aller Regel in einem Projekt nicht oder nur sehr selten geändert. 

> **Achtung:** Fehlt eine Lizenzdatei ist das Projekt nicht lizenzlos, sondern unterliegt dem gesetzlichen Urheberrecht am Wohnsitz der Projektbeteiligten. Damit ein Projekt lizenzlos veröffentlicht werden kann, muss dieses explizit in der Lizenzdatei festgehalten werden. Ein Beispiel für eine solchen Vermerk ist die sog. [MIT Lizenz](https://opensource.org/license/mit/).

> **Achtung:** Die Verwendungsrechte *externer Abhängigkeiten* können die Verwendung des eigenen Projekts beeinflussen. Möglicherweise sind einzelne Module mit den Projektanforderungen nicht vereinbar und dürfen in diesen Fällen auch nicht im Projekt verwendet werden. Es ist deshlab wichtig, die Lizenzbedingungen **aller** externen Abhängigkeiten auf ihre rechtliche Kompatibilität mit dem eigenen Projekt zu prüfen.