---
execute: 
  echo: false
---

# Zeichenketten {#sec-chapter-zeichenketten}

Bisher haben wir Zeichenketten als atomare Werte behandelt. In diesem Abschnitt geht es darum, wie wir Zeichenketten säubern, bearbeiten und aufteilen. 

Neben Zahlen gehören Zeichenketten zu den wichtigsten Datentypen, mit denen wir arbeiten. Wir denken bei Zeichenketten oft als erstes an Worte oder Sätze. Das ist aber eine unzureichende Definition für Zeichenketten. 

<p class="alert alert-primary" markdown="1">
**Definition:** Eine Zeichenkette bezeichnet eine Kette von Symbolen. Symbole können Buchstaben, Ziffern, Satzzeichen sowie "nicht-druckbare Zeichen" sein.
</p>

Eine Zeichenkette hat eine Länge, die der Anzahl der Symbole in der Zeichenkette entspricht und jedes Symbol in einer Zeichenkette kann über dessen Position identifiziert werden.

<p class="alert alert-primary" markdown="1">
Wenn Daten als Zeichenketten vorliegen, dann handelt es sich immer um **diskrete Daten**.
</p>


## Einzelne Symbole

### Nicht-druckbare Zeichen

<p class="alert alert-primary"><b>Definition:</b> Als nicht-druckbare Zeichen werden Symbole bezeichnet, die bei der Darstellung einer Zeichenkette nicht angezeigt werden können. Die nicht-druckbaren Zeichen zählen zur Länge einer Zeichenkette und verändern den Inhalt einer Zeichenkette.</p>

Beispiel: Die Zeichenkette `Hallo` unterscheidet sich von der Zeichenkette `Hal<0x08>lo`. 

Excel und R behandeln nicht-druckbare Zeichen unterschiedlich. In Excel werden die nicht-druckbaren Zeichen für die  Darstellung und für Vergleiche entfernt, jedoch werden die nicht-druckbaren Zeichen bei der Länge und beim Extrahieren berücksichtigt. In R werden nicht-druckbare Zeichen bei der Darstellung und bei Vergleichen berücksichtigt. In Excel können wir mit der `IDENTISCH()`-Funktion zwei Zeichenketten nach den gleichen Regeln wie in R vergleichen.

Zu den nicht-druckbaren Zeichen gehören auch Leerzeichen, Tabulatoren und Zeilenumbrüche. Wir können diese speziellen nicht-druckbaren Zeichen nur erkennen, wenn sie von druckbaren Zeichen umgeben sind.

Deutlich wird das an den folgenden Zeichenketten: 

* `Hallo`
* `Hal<0x07>lo`, wobei das Symbol `0x07` für einen Piepton steht
* `Hal<0x08>lo`, wobei das Symbol `0x08` für einmal Rückwärtslöschen steht.

Diese drei Zeichenketten haben in Excel und R die Längen 5, 6 und 6. Excel stellt alle drei Zeichenketten als "Hallo" dar. Ausserdem werden die Zeichenketten als gleich ausgewertet. R wertet die Zeichenketten aus und stellt nicht-druckbare Zeichen prinzipiell als ein Leerzeichen dar. Das Symbol `0x08` wird von R ausgewertet und deshalb wird das vorangehende Symbol gelöscht. Entsprechend wird in unserem Fall `Halo` angezeigt. Ebenfalls werden alle drei Zeichenketten in R als ungleich ausgewertet.

## Die leere Zeichenkette

Ein besonderer Fall ist die *leere Zeichenkette*. Die leere Zeichenkette wird oft als Platzhalter genutzt. Die leere Zeichenkette ist das *neutrale Element* für die Verknüpfung von Zeichenketten.

<p class="alert alert-primary"><b>Definition:</b> Die <i>leere Zeichenkette</i> hat die Länge 0 und enthält keine Symbole.</p>

<p class="alert alert-warning">In Excel lässt sich die leere Zeichenkette von der leeren Zelle nur unterscheiden, indem die Formel betrachtet wird oder die Zelle mit `ISTLEER()` (FALSCH) und `ISTTEXT()` (WAHR) überprüft wird.</p>

Die leere Zeichenkette wird in R immer und in Excel nur als Funktionsparameter durch doppelte Anführungszeichen eingerahmt. Soll eine leere Zeichenkette als  Wert in einer Zelle eingegeben werden, dann ist ein einfacher Apostroph (') einzugeben. 

<p class="alert alert-success" markdown="1">
In R dürfen Sie *optional* auch einfache Anführungszeichen verwenden. Weil das einfache Anführungszeichen (') und der Backtick (`) sehr ähnlich aussehen aber eine andere Bedeutung haben, sollte das einfache Anführungszeichen in R nicht verwendet werden. 
</p> 
*Beispiel leere Zeichenkette in einer Excel-Formel:*

```
=WENN(1 = 1; ""; "Fehler")
```

*Beispiel leere Zeichenkette in R:*

```
leereZeichenkette = ""
```

<p class="alert alert-success">Wenn in Excel eine leere Zeichenkette als Wert in eine Zelle eingetragen werden soll, dann geben wir ein einfaches Anführungszeichen als Wert ein.</p>

*Beispiel für eine leere Zeichenkette als Wert in einer Excel-Zelle im Eingabemodus:*

## Tokens

Nicht immer liegen Zeichenketten bereinigt vor. Sehr häufig müssen wir mit unstrukturierten Texten arbeiten. Das können z.B. freie Antworten aus einem Fragebogen oder E-Mails von unseren Kunden sein. Diese Texte werden als **Korpus** bezeichnet.

<p class="alert alert-primary" markdown="1">
**Definition:** Ein **Korpus** bezeichnet die Texte, die *gemeinsam* in eine Analyse einfliessen.
</p>

Die Texte eines Korpus enthalten oft verborgene Information. Um diese Information zu dekodieren, müssen diese Texte zuerst in eine geeignete Form gebracht werden. Dieser Schritt wird als ***Tokenisierung*** bezeichnet. 

Die Tokenisierung ist ein notwendiger Schritt für die Vorbereitung einer quantitativen Textanalyse. 

<p class="alert alert-primary" markdown="1">
**Definition:** Die **Tokenisierung** bezeichnet die systematische Strukturierung eines Texts in kleinere Einheiten. Diese kleineren Einheiten werden als **Tokens** bezeichnet.
</p>

Für die Auswertung von Texten erzeugen wir aus langen Zeichenketten mehrere kurze Teiltexte. Diese Teiltexte sind die *Tokens*, die analysiert werden sollen. Tokens können  *Absätze* (`paragraph`), *Sätze* (`sentence`), *Worte* (`words`), Zeilen (`line`), Seiten (`page`), *Wortfolgen* (`ngram`) oder auch *Buchstabenfolgen* (`character_shingles`) sein. 
 
<p class="alert alert-secondary" markdown="1">
Wenn wir kodieren, dann erzeugen wir ebenfalls Tokens: Der für die Kodierung markierte Text ist ebenfalls ein Token. Beim Kodieren können Tokens mit unterschiedlicher Wortanzahl entstehen. 
</p>

### Sätze und Absätze

Sätze und Absätze sind besondere Tokens in Texten. 

<p class="alert alert-primary" markdown="1">
**Definition:** Ein **Satz** bezeichnet einen *inhaltlich zusammenhängenden Teiltext*, der durch einen Punkt (`.`), ein Fragezeichen (`?`) oder ein Ausrufezeichen (`!`) beendet wird. 
</p>

<p class="alert alert-primary" markdown="1">
**Definition:** Ein **Absatz** bezeichnet einen *inhaltlich zusammenhängenden Teiltext*, der aus mindestens einem Satz besteht. 
</p>

Die Tokenisierung in Absätze und Sätze wird oft dazu verwendet, um grössere Korpora aus inhaltlich zusammenhängenden Texten zu erzeugen. 

### n-Gramme 

Die Gliederung von Texten in n-Gramme hat in der Textanalyse eine besondere Bedeutung. 

<p class="alert alert-primary" markdown="1">
**Definition:** Ein **n-Gram** bezeichnet eine Wortfolge, die aus `n` aufeinanderfolgenden Worten besteht. 
</p>

Mit Hilfe von n-Grammen lassen sich inhaltlich-relevante Phrasen identifizieren, die bei einer Tokenisierung auf Wortebene verloren gehen würden. 

<p class="alert alert-success" markdown="1">
Das Tokenisieren von Worten ist gleichbedeutend mit dem Tokenisieren von 1-Grammen.
</p>

## Zeichenketten verbinden

Die leere Zeichenkette ist das neutrale Element der Textverkettung.

## Suchen und Ersetzen

Eine  wichtige Operation für Zeichenketten ist das Suchen-und-Ersetzen. Wir können uns das Suchen-und-Ersetzen als eine spezielle Technik zur Mustererkennung vorstellen.

Anstatt umständlich über eine Benutzeroberfläche die Daten zu korrigieren, wollen wir das Bereinigen der Zeichenketten automatisieren. Die Technik ist unter R und Excel identisch. Unter R verwenden wir die `str_replace()`- bzw. die `str_replace_all()`-Funktion. Unter Excel verwenden wir die `WECHSELN()`-Funktion. 

Bevor wir das Suchen-und-Ersetzen starten, müssen wir die betreffenden Zeichenketten bereinigen, denn sonst verfehlen wir unser Ziel. Die einfachste Bereinigung ist das Entfernen von überschüssigen Leerzeichen. In Excel verwenden wir dafür die `GLÄTTEN()`-Funktion oder in R die `str_squish()`-Funktion.

Eine zweite häufig verwendete Bereinigung ist die Transformation auf Kleinbuchstaben oder Grossbuchstaben. Wir entscheiden uns für eine der beiden Varianten und halten diese für diesen Arbeitsschritt durch. Damit stellen wir sicher, dass unsere Ersetzungen unabhängig von der Schreibweise erfolgen.

Für das eigentliche Ersetzen erstellen wir einen Suchvektor und einen Ersetzenvektor. Die beiden Vektoren enthalten die Paare aus Suchmuster und Ersetzung. Diese Paare ordnen wir der Reihe nach, sodass wir diese Schritte nacheinander ausführen können. 

<p class="alert alert-info">
Ersetzen Sie Satzzeichen durch Leerzeichen und nicht durch eine leere Zeichenkette. Dadurch stellen Sie sicher, dass nicht versehentlich Elemente zusammengefügt werden. Wenn Sie alle Sonderzeichen entfernt haben, sollten Sie die Zeichenkette noch einmal von überschüssigen Leerzeichen bereinigen.
</p>

Beispiel Suchen-Ersetzen Vektoren in Excel 

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/gkPKbKn2zIU" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<a href="https://moodle.zhaw.ch/mod/resource/view.php?id=544716"><p class="btn btn-primary"><i class="fa fa-lg fa-download"></i> Datei aus dem Video</p></a>

## Zeichenketten trimmen

TODO

## Suchen-Ersetzen Vektoren in R

In R müssen wir die Wertepaare direkt zuweisen, wobei die Suchmuster Namen und die Ersetzungen die Werte sind. Das folgende Beispiel demonstriert eine solche Zuordnung. 

```
suchen = c("suchetext", "beispiel")
ersetzungen =  c("suche", "bsp")

names(ersetzungen) <- suchen

Text %>% 
    str_squish() %>%          # Leerzeichen Bereinigen
    str_to_lower() %>%        # Grossschreibung ignorieren
    str_replace_all(ersetzungen)  # Suchen-Ersetzen
```

Alternativ mit mutate und direkter Zuordnung der Wertepaare.

```
# Direkte Zuordnung
ersetzungen = c("suchetext" = "suche", 
                "beispiel" = "bsp")

# Suchen und Ersetzen als Funktionskette innerhalb von mutate
textDaten %>% 
    mutate(Texte = Texte %>% 
                        str_squish() %>% 
                        str_to_lower() %>% 
                        str_replace_all(ersetzungen))
```


Das folgende Video veranschaulicht diese Technik:

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/Ev20b0-woqk" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<a href="https://moodle.zhaw.ch/mod/resource/view.php?id=544720"><p class="btn btn-primary"><i class="fa fa-lg fa-download"></i> Notebook und Daten aus dem Video (Zip-Archiv)</p></a>


<p class="alert alert-warning">Beim Suchen und Ersetzen müssen wir aufpassen, dass wir nicht versehentlich Daten ersetzen, die wir später brauchen. Das können z.B. doppelt vorkommende Zeichenketten sein.</p>

<p class="alert alert-info">Oft sind mehrere Durchläufe notwendig, um alle notwendigen Ersetzungen zu identifizieren. Dabei werden die Suchen- und Ersetzenvektoren schrittweise angepasst und erweitert, bis das Ergebnis zufriedenstellend ist.</p>

### Reguläre Ausdrücke

<p class="alert alert-primary" markdown="1">
**Definition:** Als **reguläre Ausdrücke** werden Zeichenketten bezeichnet, mit denen *komplexe Suchmuster* für Zeichenketten beschrieben werden können. Ein regulärer Ausdruck beschreibt die Struktur der zu suchenden Zeichenkette. 
</p>

Reguläre Ausdrücke sind eine Standardtechnik zum Suchen-und-Ersetzen. Sie können z.B. in Jupyter Notebooks eingesetzt werden, um Variablen umzubenennen.

Anders als Excel verfügt R über eine leistungsfähige Mustererkennung für Zeichenketten. Diese Mustererkennung steuern wir über [*reguläre Ausdrücke*](https://stringr.tidyverse.org/articles/regular-expressions.html) oder *Regulärausdruck* (Sauer, 2019). Reguläre Ausdrücke erlauben uns, Muster in Zeichenketten zu finden und diese Muster durch etwas anderes auszutauschen. In R schreiben wir reguläre Ausdrücke als Zeichenketten mit einer besonderen Musterbeschreibungssprache. Wir können an viele Zeichenkettenfunktionen solche regulären Ausdrücke als Parameter übergeben. 

Die wichtigsten Elemente zur Musterbeschreibung mit regulären Ausdrücken sind die folgenden Symbole und Symbolkombinationen: 

* `.` - beschreibt das Vorkommen eines beliebigen Symbols
* `\s` - beschreibt alle Symbole die als Leerzeichen gelten
* `\d` - beschreibt alle Ziffern
* `\w` - beschreibt alle Buchstaben unabhängig von der Gross- und Kleinschreibung
* `*` - beschreibt das Auftreten von Sequenzen von 0 oder mehreren der voranstehenden Symbole
* `+` - beschreibt das Auftreten von Sequenzen von 1 oder mehreren der voranstehenden Symbole
* `?` - beschreibt das Auftreten von Sequenzen  von 0 oder 1 des voranstehenden Symbols
* `{}` - beschreibt das Auftreten von Sequenzen der angegebenen Länge des voranstehenden Symbols
* `^` - steht für den Anfang der Zeichenkette
* `$` - steht für das Ende der Zeichenkette
* `[]` - "Symbolbereich": Die Symbole zwischen den beiden Klammern beschreiben die möglichen Symbole an der Position in der Zeichenkette
* `()` - Gruppiert eine Teilzeichenkette

#### Normale Zeichen in Mustern

Normale Buchstaben oder Ziffern haben keine besondere Bedeutung und bedeuten, dass an der entsprechenden Stelle das jeweilige Symbol vorkommen muss.

```R
zeichenkettenVektor = c( "Daten und Information", "Datenverarbeitung", "Informatik", "Daten Information", "Computation Daten Informatik" )

# der reguläre Ausdruck wäre eigentlich "\w\s\w" die zusätzlichen Backslashs 
# zeigen R an, dass wir den Backslash in unserem Muster haben möchten.

regulaererAusdruck = "Daten In"

zeichenkettenVektor %>% str_detect(regulaererAusdruck) 
# erzeugt c(FALSE FALSE FALSE TRUE TRUE)
```

#### Mustersymbole in R verwenden

Wenn wir ein Symbol in unserem Muster aufnehmen wollen, das normalerweise ein besonderes Symbol für reguläre Ausdrücke ist, dann müssen wir diesem Symbol einen *Backslash* voranstellen. Dieses Voranstellen wird als **"Escaping"** bezeichnet. Weil R reguläre Ausdrücke als Zeichenketten behandelt, müssen wir aufpassen, denn der Backslash ist auch ein reserviertes Symbol in Zeichenketten. Deshalb ist der zweite Backslash notwendig, um den ersten Backslash vor der Zeichenketteninterpretation zu schützen. 

```R
zeichenkette = "Daten und Information"

# der reguläre Ausdruck wäre eigentlich "\w\s\w" die zusätzlichen Backslashs 
# zeigen R an, dass wir den Backslash in unserem Muster haben möchten.

regulaererAusdruck = "\\w\\s\\w"

zeichenkette %>% str_replace(regulaererAusdruck, "p x") # erzeugt "Datep xnd Information"

# Hinweis, um alle Vorkommnisse des Musters auszutauschen, müssen wir 
# str_replace_all() verwenden!
```

### Multiplikatoren

Die Symbole `*`, `+`, `?` und `{}` werden als *Multiplikatoren* bezeichnet. So können Wiederholungen in Mustern abgebildet werden. 

Mit diesen Elementen können wir Zeichenketten beschreiben, ohne die genaue Abfolge der Symbole zu kennen.

Beispiele: 

```
"ab"       # erkennt ab
"a?b"      # erkennt b und ab
"a*b"      # erkennt b, ab, aab, aaab, aaaab usw. 
"a+b"      # erkennt ab, aab, aaab, aaaab usw. 
"a{2}b"    # erkennt aab
"a{2,4}b"  # erkennt aab, aaab und aaaab
"a.b"      # erkennt aab, acb, adb, a3b, a-b usw. 
"a.*b"     # erkennt ab, acb, acdb, a-!%b usw. 

"a\\sb"    # erkennt "a b" oder "a     b" (Achtung doppelter Backslash!)
"\\w\\d"   # erkennt einen Buchstaben, der von einer Ziffer gefolgt wird  (Achtung doppelter Backslash!)
"a[cd]?b"  # erkennt ab, acb und adb

"ab$"      # erkennt ab nur am Ende der Zeichenkette
"^ab"      # erkennt ab nur am Anfang der Zeichenkette
```

<p class="alert alert-info">Gelegentlich wollen wir ein Muster bis zu einem bestimmten Symbol in unserer Zeichenkette finden. In diesem Fall können wir einen negierten Symbolbereich angeben.</p>

Beispiel: 

Gegeben ist die folgende Zeichenkette: 

```
aquaponics = "The term aquaponics [7] is coined by combining two words: aquaculture, which refers to 
 fish farming, and hydroponics—the technique of growing plants without soil.[16]"
```

Wir möchten nun die Zeichenkette ab dem Wort `term` und der öffnenden eckigen Klammer der Referenz markieren. D.h. wir wollen nicht ein beliebiges Zeichen und wollen nicht alle Symbole bis auf die öffnende Klammer explizit ausschliessen. Stattdessen können wir einen *negierten* Symbolbereich angeben. In unserem Fall erlauben wir jedes Zeichen, ausser die öffnende eckige Klammer. Weil die eckige Klammer eine besondere Bedeutung für reguläre Ausdrücke hat, müssen wir sie entsprechend mit Backslash "escapen". Unser regulärer Ausdruck muss entsprechend `"termn [^\\[]+\\["`. Der Teil `[^\\[]+` bedeutet dabei, "alle Symbole ausser der öffnenden eckigen Klammer `[`. Die beiden Backslashs sind dabei die notwendige Escape-Sequenz, um die Klammer vom Symbolbereich zu unterscheiden. 

Der folgende Code demonstriert diesen regulären Ausdruck.

```
aquaponics %>%
    str_match("term [^\\[]+\\[")
```

Das Ergebnis eines regulären Ausdrucks ist normalerweise immer nur der erste Treffer. 

```
"term aquaponics ["
```

Um alle Treffer eines Musters zu erhalten, muss für die entsprechende `_all`-Variante der Funktion verwendet werden. Die folgenden Funktionen haben eine solche Funktionsvariante:

| Bedeutung | Erster Treffer | Alle Treffer |   
| :--- | :--- | : --- | 
| Finde und extrahiere ein Suchmuster | `str_extract()` | `str_extract_all()` | 
| Finde ein Suchmuster und gebe die Zeichenkette zurück | `str_match()` | `str_match_all()` | 
| Finde ein Suchmuster und gebe die Position des Treffers zurück | `str_locate()` | `str_locate_all()` | 
| Finde und lösche ein Suchmuster  | `str_remove()` | `str_remove_all()` | 
| Finde ein Suchmuster und ersetze den Treffer durch eine andere Zeichenkette  | `str_replace()` | `str_replace_all()` | 
| Zeige Suchtreffer für ein Suchmuster an | `str_view()` | `str_view_all()` | 

## Offene Daten annotieren

### Problem

Es sollen bedeutsame Stellen in Texten durch Anmerkungen markiert werden, sodass diese Stellen und die Markierung in R ausgewertet werden können.

<p class="alert alert-primary" markdown="1">
Das Markieren von Textstellen durch Anmerkungen wird als **Textkodierung** bezeichnet.
</p>

### Lösung 

Die Kommentarfunktion von Word ist die einfachste Möglichkeit, um Texte zu kodieren. Diese Funktion finden Sie im Menüband `Überprüfen`. 

Je nach Datenquelle müssen Sie den Text zuvor in ein Word Dokument umwandeln oder via Copy-und-Paste in ein Dokument einfügen. 

### Erklärung

<p class="alert alert-success" markdown="1">
Erstellen Sie für jeden Text ein separates Dokument! Ihre Auswertung wird dadurch einfacher. 
</p>

Nachdem der Text im Word-Format vorliegt, sichern Sie unbedingt das Dokument als unkodierte Fassung in einem separaten Ordner. Sie sollten nun zwei Dokumente haben. Eines der beiden Dokumente bleibt **immer** in der ursprünglichen Rohfassung und wird nicht mehr bearbeitet.

Schliessen Sie das Dokument wieder und öffnen Sie die zu kodierende Fassung. 

Jetzt gehen Sie Schritt für Schritt durch das Dokument und kodieren Ihre Textstellen wie folgt: 

1. Markieren Sie die entsprechende Textstelle. 
2. Klicken Sie auf "Neuer Kommentar". 
3. Geben Sie im Kommentarfeld den Code für die Textstelle ein. 
4. Klicken Sie auf Kommentar abschicken, sonst geht Ihr Code verloren.

<p class="alert alert-success" markdown="1">
Falls Sie mehrere Codes für die gleiche Textstelle verwenden möchten, können 
Sie mehrere Codes in einen Kommentar schreiben. Verwenden Sie das Komma oder ein Semikolon (Strichpunkt) als Trennzeichen. 
</p>

<p class="alert alert-warning" markdown="1">
Wenn Sie mehrere Codes in einen Kommentar schreiben, verwenden Sie **immer** das gleiche Trennzeichen!
</p>

Ihre Codes sollten aus einem einzelnen Wort bestehen. Falls Sie Ihre Codes vorab Variablen zuweisen (können), verwenden Sie einen Doppelpunkt *ohne* Leerschlag, um diese Information bereits bei der Kodierung zu erfassen. Oft ist es einfacher, die Codes nachträglich in R den Variablen zuzuordnen.

<p class="alert alert-success" markdown="1">
Sie können Ihre Codes nachträglich anpassen. Achten Sie dabei darauf, dass Sie den Kommentar nach Ihrer Änderung speichern. 
</p> 
