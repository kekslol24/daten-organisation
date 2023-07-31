---
# bibliography: references.bib

title: Datentypen

abstract: ""

execute: 
  echo: false
---

## Die fundamentalen Datentypen

Datentypen helfen uns Werte zu organisieren. Wir haben bereits drei wichtige Datentypen kennengelernt. Damit kennen wir bereits den Grossteil der wichtigsten Datentypen für einzelne Werte. Die vollständige Auflistung besteht aus fünf Datentypen:

1. Zahlen (engl. *numerics*)
2. Wahrheitswerte (engl. *booleans*)
3. Zeichenketten (engl. *strings*)
4. Fehlerwerte (engl. *error values*)
5. Die leere Zelle bzw. nicht vorhandene Werte (`NA` in R). 

Diese Datentypen beschreiben jeweils einzelne Werte. 

> **Definition:** **Atomare Datentypen** heissen Datentypen, die Eigenschaften für einzelne Werte festlegen.

### Kein Wert

### Zahlen

### Wahrheitswerte

### Zeichenketten

### Fehlerwerte

## Arten von Datentypen

### Diskrete Daten

### Kontinuierliche Daten

## Datenkodierung

### Zahlensysteme

> Als **Zahlensystem** wird die Schreibweise für Zahlenwerte bezeichnet. 

In der Regel verwenden wir das sog. Dezimalsystem, um Zahlen darzustellen. Das Dezimalsystem hat 10 mögliche Symbole, um Zahlenwerte abzubilden. Diese Symbole sind `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9` und `0`. Damit können wir mit einem Symbol Zahlenwerte zwischen `0` und `9` abbilden. 

Gelegentlich lassen sich bestimmte Phänomene nicht gut im Dezimalsystem abbilden. Dadurch lassen sich Werte nur schwer interpretieren. In solchen Fällen hilft der Wechsel in ein anderes Zahlensystem.

> **Merke:**  Durch den Wechsel des Zahlensystems ändert sich nur die Darstellung, aber nicht der Wert einer Zahl! 

> **Definition:** Die Zahl, die als Grundlage für ein Zahlensystem dient,  wird als **Basis** des Zahlensystems bezeichnet. 

Beim in der Schulmathematik üblichen Dezimalsystem ist die Basis `10`.

> **Definition:** **Zahlensysteme** kodieren Zahlenwerte zu einer gegebenen Basis. 

### Die wichtigsten Zahlensysteme 

| Name | Basis | Symbole |
| :--- | :--- | :--- |
| Binärsystem | `2` | `0`, `1` |
| Oktalsystem | `8` | `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7` |
| Dezimalsystem | `10` | `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9` |
| Duodezimalsystem | `12` | `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`, `A`, `B` |
| Hexadezimalsystem | `16` |  `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`, `A`, `B`, `C`, `D`, `E`, `F` |
| Sexagesimalsystem | `60` | - |

Das Duodezimalsystem und das Sexagesimalsystem treffen wir im Alltag bei Datums- und Zeitwerten, bei Winkeln sowie in der Musik an. Im Deutschen lässt sich das Duodezimalsystem noch an den Zahlworten elf (`11`) und zwölf (`12`) erkennen.

Das binäre Zahlensystem stellt die Grundlage für digitale Computer dar, weil es nur zwei Werte für die Darstellung von Zahlen benötigt. D.h. alle Werte lassen sich als Vielfache von zweier-Potenzen abbilden. Claude Shannon hat bereits 1938 erkannt, dass diese Darstellung sich direkt die Zustände "ein" und "aus" von Schaltern übersetzen lässt, sodass sich alle Berechnungen mit Hilfe der [*Boolschen Algebra*](@08-boolsche-algebra) mit einfachen Schaltungen realisieren lassen. Daraus ergibt sich, dass das kleinste Bit der Informationstheorie sich im Binären-Zahlensystem abbilden lässt. 

Die Zahlensysteme Oktal und Hexadezimal sind für die Abbildung von Werten in Digitalcomputern von besonderer Bedeutung, weil es sich jeweils um ganzzahlige 2er Potenzen handelt. 

| Name | Basis | 2er-Potenz |
| :--- | :--- | :--- |
| Binär | `2` |$2^1$|
| Oktal | `8` |$2^3$|
| Hexadezimal | `16` |$2^4=2^{2^2}$|

Der Exponent der 2er-Potenz der Basis zeigt an, wie viele Stellen im Binärsystem (Bits) mit dem jeweiligen System abgebildet werden können. Ein Byte bildet per Konvention zwei Stellen im Hexadezimalsystem oder 8 Bit ab. 

> Hexadezimal-Werte werden recht häufig beim Programmieren verwendet, wie z.B. für das Kodieren von Buchstaben und Satzzeichen. Damit diese Werte leichter von Werten im Dezimalsystem unterschieden werden können, werden Werten im Hexadezimalsystem per Konvention die beiden Symbole `0x` vorangestellt.

**Beispiele**

| Dezimal  | Hexadezimal |
| ---: | ---: |
| `0`  | `0x0` |
| `1` | `0x1` |
| `2` | `0x2` |
| `3` | `0x3` |
| `4` | `0x4` |
| `8` | `0x8` |
| `9` | `0x9` |
| `10` | `0xA` | 
| `15` | `0xF` | 
| `16` | `0x10` |

> **ACHTUNG!** Excel hält sich nicht an diese Konvention. Hexadezimalwerte werden direkt eingegeben und müssen anschliessend in Zahlenwerte mit der Funktion `HEXINDEZ()` konvertiert werden. 

### Binärzahlen

> Binärzahlen kodieren Zahlenwerte zur Basis 2.

Daraus folgt, dass für jede Ziffer genau zwei Symbole (Ziffern) zur Verfügung stehen: `0` und `1`. 

Wie in anderen Zahlensystemen entspricht eine Stelle im Binärsystem einer Potenz zur gegebenen Basis. Das ist bei Binärwerten `2`. Jede Stelle für eine Ziffer kann also einer 2er-Potenz gleichgesetzt werden.

Die Besonderheit des Binärsystems ist, dass alle Werte als Summe von 2er-Potenzen dargestellt werden können. Diese Summe wird als *additive Darstellung* bezeichnet. 

| Wert | Binärwert | Additive Darstellung | Hexadezimal | 
| ---: | ---: | :---: | ---: | 
| `0` | `0000` | 0 | `0` | 
| `1` | `0001` | $ 2^0 $ | `1` |
| `2` | `0010` | $ 2^1 $ | `2` | 
| `3` | `0011` | $ 2^1 + 2^0 $ | `3` |
| `4` | `0100` | $ 2^2 $ | `4` |
| `5` | `0101` | $ 2^2 + 2^0 $ | `5` |
| `6` | `0110` | $ 2^2 + 2^1 $ | `6` | 
| `7` | `0111` | $ 2^2 + 2^1 + 2^0 $ | `7` |
| `8` | `1000` | $ 2^3 $ | `8` |
| `9` | `1001` | $ 2^3 + 2^0 $ | `9` |
| `10` | `1010` | $ 2^3 + 2^1 $ | `A` |
| `11` | `1011` | $ 2^3 + 2^1 + 2^0 $ | `B` | 
| `12` | `1100` | $ 2^3 + 2^2 $ | `C` |
| `13` | `1101` | $ 2^3 + 2^2 + 2^0 $ | `D` |
| `14` | `1110` | $ 2^3 + 2^2 + 2^1 $ | `E` |
| `15` | `1111` | $ 2^3 + 2^2 + 2^1 + 2^0 $ | `F` |

Aus dieser Tabelle kann man ablesen, dass die Ziffer `1` im Binärsystem bedeutet, dass die 2er-Potenz an der entsprechenden Stelle aktiv ist. 

Jede Ziffer im Binärsystem kann ausserdem als eigenständiges Symbol einer Nachricht verstanden werden. Weil im Binärsystem nur die beiden Ziffern `0` und `1` möglich sind, müssen beim Dekodieren nur diese Beiden Werte unterschieden werden. Jedes andere Zahlensystem kodiert Zahlen mit mehr als zwei Ziffern.

#### 2er-Potenzen und Speichergrössen

Nach diesem Prinzip werden auch die Kapazitäten von Datenspeichern als 2er-Potenzen beschrieben.

| Name | Abkürzung | gespeicherte Byte |
| :--- | :--- | :--- |
| Byte | B |$2^0 = 1$|
| Kilobyte | KB |$2^{10} = 1024^1$|
| Megabyte | MB |$2^{20} = 1024^2 = 1048576$|
| Gigabyte | GB |$2^{30} = 1024^3 = 1073741824$|
| Terabyte | TB |$2^{40} = 1024^4 = 1099511627776$|


<p class="alert alert-warning" markdown="1">
Die *wissenschaftliche Schreibweise* ist **kein eigenes Zahlensystem**.  Sie ist nur eine *Vereinheitlichung* der Schreibweise im Dezimalsystem, um sehr grosse und/oder sehr kleine Zahlen kompakt darstellen zu können. 
</p>

### Winkelangaben als irrationales Zahlensystem

Winkelangaben werden oft als Vielfache von $\pi$ angegeben. Diese Werte werden auch als *Radiant* anstatt als Grad bezeichnet. Dabei handelt es sich um ein Zahlensystem zur Basis $\pi$.

- $\frac{\pi}{6}$ = 30°
- $\frac{\pi}{4}$ = 45°
- $\frac{\pi}{3}$ = 60°
- $\frac{\pi}{2}$= 90°
- $\frac{2\pi}{3}$= 120°
- $\pi$= 180° 
- $\frac{3\pi}{2}$= 270°
- $2\pi$= 360°

### Prinzip eines Zahlensystems

Die in der Mathematik verwendeten Zahlensysteme sind sog. *additive Zahlensysteme*. Die Schreibweise wird durch Addition und Multiplikation mit der jeweiligen Basis bestimmt. 

Das Zählen funktioniert dabei wie folgt: 

1. Es wird bei `0` gestartet. 
2. Die nächste Ganzzahl wird durch Addition mit `1` erreicht. 
3. Es wird das nächste Ziffernsymbol ausgewählt. 
4. Gibt es für die jeweilige Basis keine Ziffernsymbole für die Ganzzahl mehr, wird die nächsthöhere Stelle um `1` erhöht. 

**Beispiele**

| Dezimal | Binär | Oktal | Hexadezimal |
| ---: | ---: | ---: | ---: |
| `0` | `0` | `0` | `0x0` |
| `1` | `1` | `1` | `0x1` |
| `2` | `10` | `2` | `0x2` |
| `3` | `11` | `3` | `0x3` |
| `4` | `100` | `4` | `0x4` |
| `8` | `1000` | `10` | `0x8` |
| `9` | `1001` | `11` | `0x9` |
| `10` | `1010` | `12` | `0xA` | 
| `15` | `1111` | `17` | `0xF` | 
| `16` | `10000` | `100` | `0x10` |
| `255` | `11111111` | `377` | `0xFF` |
| `256` | `100000000` | `400` | `0x100` |

## Wissenschaftliche Schreibweise von Zahlen

> Als **wissenschaftliche Notation** wird die Schreibweise von Zahlen mit Hilfe von Potenzen zur Basis 10 bezeichnet. 

Bei der wissenschaftlichen Notation wird die erste Ziffer einer Zahl vor ein Komma gesetzt und alle restlichen Ziffern nach dem Komma. Anschliessend werden die restlichen Ziffern gezählt und als 10er-Potenz angegeben. 

Bei kleinen Zahlen wird ähnlich vorgegangen: Die erste Ziffer ungleich `0` wird vor ein Komma gesetzt und alle folgenden Stellen danach. Anschliessend werden alle Nullen und die Ziffer vor dem Komma gezählt und als negative 10er-Potenz angegeben.
 
Neben der ausführlichen wissenschaftlichen Schreibweise wird regelmässig eine abgekürzte Notation verwendet. In dieser Notation wird der Teil $\cdot 10$ durch ein `e` oder `E` ersetzt. Dieses `E` steht für *Exponent*. 

**Beispiele:** 

| Normale Notation | Wissenschaftliche Notation | Kurze wissenschaftliche Notation |
| ---: | ---: | ---: |
| 1 | $1 \cdot 10^0$ | 1e0 |
| 10 | $1 \cdot 10^1$ | 1e1 |
| 100 | $1 \cdot 10^2$ | 1e2 |
| 523140000 | $5.2314 \cdot 10^8$ | 5.2314e8 |
| 0.00000000007234 | $7.234 \cdot 10^-11$ | 7.234e-11 |

Die Stärke der wissenschaftlichen Notation ist die Darstellung sehr grosser oder sehr kleiner Zahlen

Mit dieser Schreibweise lassen sich auch schnell Grössenunterschiede zwischen Werten abschätzen: Dazu wird die Differenz der 10er-Potenzen zweier Zahlen gebildet. Dazu wird die kleinere 10er-Potenz von der grösseren subtrahiert. Das Ergebnis ist wieder eine 10er-Potenz. 

**Beispiel**

- Eine Differenz von 1 entspricht einem ungefähr 10-fachen Grössenunterschied. 
- Eine Differenz von 5 entspricht einem ungefähr 100000-fachen Grössenunterschied.

### Zeichenkodierung

Wir schreiben Texte nicht mit Zahlen, sondern mit Buchstaben, Satz- und Steuerzeichen. Damit wir Texte digital abbilden können, müssen diese Symbole in Zahlen umgewandelt werden. 

<p class="alert alert-primary" markdown="1">
**Definition:** Beliebige Symbole lassen sich durch Zahlenwerte kodieren.
</p>

Weil sich Buchstaben und andere Zeichen nicht direkt als Zahlen übersetzen lassen, bedarf es eines Tricks. Dazu werden alle zu kodierenden Zeichen in einer Liste aufgeschrieben und anschliessend werden alle Zeichen durchnummeriert. Die Nummer des Zeichens wird als Zahlenwert stellvertretend für das jeweilige Zeichen. 

Historisch sind vier Kodierungen für uns von Bedeutung. 

- ASCII - kodiert das Anglo-amerikanische Alphabet mit Ziffern und Satzzeichen in 7 Bit (Zahlen mit max. 7 Stellen binär).
- ANSI - kodiert das Anglo-amerikanische Alphabet mit Ziffern und Satzzeichen in 8 Bit (Zahlen mit max. 8 Stellen binär).
- ISO-8859 - kodiert verschiedene Schriftsysteme in 8 Bit (Zahlen mit max. 8 Stellen binär).
  - ISO-8859-1 (oder ISO Latin 1) - kodiert das westeuropäische Alphabet mit deutschen und französischen Umlauten.
  - ISO-8859-15 (oder ISO Latin 9) - Kodiert das westeuropäische Alphabet wie ISO-8859-1 aber mit dem Euro Symbol (€)
- UTF-8 - kodiert alle gängigen und viele historische Schriftsysteme inkl. Emojis dynamisch mit 8 bis zu 32 Bit. 

Diese Kodierungen sind bis zum Code 01111111 (oder 0x7F) identisch. 

**Vollständige ASCII-Kodierungstabelle** 

| | 0	| 1	| 2	| 3	| 4	| 5	| 6	| 7	| 8	| 9	| A	| B	| C	| D	| E	| F |
| :--- |  :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | 
| 0x	| ***NUL***	| SOH	| STX	| ETX	| EOT	|	ENQ	|	ACK	|	BEL	|	***BS***	|	***HT***	|	***LF***	|	VT	|	FF	|	***CR***	|	SO	|	SI	|
|1x	|	DLE	|	DC1	|	DC2	|	DC3	|	DC4	|	NAK	|	SYN	|	ETB	|	CAN	|	EM	|	SUB	|	***ESC***	|	FS	|	GS	|	RS	|	US	|
| 2x	|	 ***SPACE***	| 	!	|	"	|	#	|	$	|	%	|	&	|	'	|	(	|	)	|	*		| +	|	,	|	-	|	.	|	/ |
| 3x	|	0	|	1	|	2	|	3	|	4	|	5	|	6	|	7	|	8	|	9	|	:	|	;	|	<	|	=	|	>	|	?	|
| 4x	|	@	|	A	|	B	|	C	|	D	|	E	|	F	|	G	|	H	|	I	|	J	|	K	|	L	|	M	|	N	|	O	|
| 5x	|	P	|	Q	|	R	|	S	|	T	|	U	|	V	|	W	|	X	|	Y	|	Z	|	[	|	\	|	]	|	^	|	_	|
| 6x	|	`		|a	|	b	|	c	|	d	|	e	|	f	|	g	|	h	|	i	|	j	|	k	|	l	|	m	|	n	|	o	|
| 7x	|	p	|	q	|	r	|	s	|	t	|	u	|	v	|	w	|	x	|	y	|	z	|	{	|	\|	|	}	| ~	| ***DEL*** |

Neben Buchstaben werden auch sog. *nicht-druckbare Zeichen* wie Buchstaben kodiert. Dazu gehören u.a. Leerzeichen, Tabulatoren und Zeilenumbrüche. Viele dieser besonderen Buchstaben haben heute keine Bedeutung mehr. Die Ausnahmen sind: 

- *Leerzeichen/Leerschlag* (`0x20`)
- *Tabulator* (`0x09`)
- *Zeilenumbruch* (`0x0D`) und *Zeilenvorschub* (`0x0A`).
- *ESC* (`0x1B`)
- *Backspace* (`0x08`)
- *Löschen* (Delete) (`0x7F`)


### Ziffernkodierung

Arabische Ziffern werden mit den Werten `0x30` (Ziffer `0`) bis `0x39` (Ziffer `9`) kodiert.

> **Merke:** Ziffern in Zeichenketten sind nicht gleichwertig mit den Ziffern in Zahlen. 

Eine Zahl wird als eine Abfolge von Ziffern dargestellt. Wird ein Wert als Zahl dargestellt, dann werden die Ziffern entsprechend der gewählten Basis interpretiert. Werden Ziffern als Zeichenkette kodiert, dann entspricht der *Wert* der Ziffer der entsprechenden Kodierung. D.h.z.B. die Ziffer `"1"` in einer Zeichenkette hat nicht den Wert `1`, sondern den Wert `49` (`0x31`). Folgen mehrere Ziffern aufeinander in einer Zeichenkette, dann werden die kodierten Zahlen aneinandergereiht. Die Ziffern `"123"` entsprechen deshalb nicht dem Wert `123`, sondern dem Wert `3224115` (`0x313233`). 

> **Excel**, *R* und *Python* konvertieren Ziffern in Zeichenketten *oft* automatisch in die richtigen Zahlenwerte, **solange** keine anderen Zeichen in der jeweiligen Zeichenketten kodiert wurden.

> Nicht alle Programmiersprachen konvertieren Ziffern in Zeichenketten automatisch in Zahlenwerte

### Serialisierung

> **Definition:** Ein Zahlenwert kann bei einer Darstellung zu einer Basis in mehreren Ziffern erfolgen. Diese Zifferndarstellung wird als **Serialisierung** bezeichnet. 

*Serialisierung* bedeutet, dass die Ziffern eines Werts *in einer bestimmten Reihenfolge* dargestellt werden. Jede Ziffer einer solchen Darstellung können wir uns als ein *Symbol* einer Nachricht vorstellen. 

Weil ein Zahlenwert in verschiedenen Zahlensystemen dargestellt werden kann, ergibt sich daraus der folgende Merksatz:

> Ein Zahlenwert hat *mehrere* zulässige Serialisierungen. 

### Anwendung in Excel und R

Damit Werte in Excel und R als Zeichenketten erkannt werden können, müssen die Zeichenketten in doppelte Anführungszeichen (`"`) eingerahmt werden. Ohne diese Anführungszeichen erkennen die beiden Umgebungen die Eingabe nicht als Zeichenkette. 

> **Excels Formel- und Wertemodi**: Excel kennt zwei Modi: Den Formelmodus und den Wertemodus. Der Formelmodus wird bei der Eingabe **immer** durch ein Gleichheitszeichen am Anfang der Eingabe in einer Zelle aktiviert. Im Wertemodus wird ein Wert direkt eingegeben. 

> Im Formelmodus **müssen** Zeichenketten **immer** in doppelten Anführungszeichen (`"`) eingerahmt werden. Beispiel Zahl als Zeichenkette im Formelmodus: ``= "12.34"`` (Die Zeichen werden direkt eingegeben).
> 
> Im Wertemodus werden Zeichenketten optional mit einem einfachen Anführungszeichen (`'`) eingeleitet. D.h. das einfache Anführungszeichen **muss** angegeben werden, wenn eine Zeichenkette nur aus Ziffern besteht, wie ein Währungsbetrag oder wie ein Datum aussieht oder die Zeichenkette mit einem Gleichheitszeichen beginnt. Durch das einleitende Anführungszeichen wird  Excel signalisiert, dass der Wert nicht automatisch in ein anderes Format umgewandelt werden soll. Das einleitende Anführungszeichen wird in der Darstellung verborgen und wird nur beim Bearbeiten der Werte angezeigt. Beispiel Zahl als Zeichenkette im Wertemodus: ``'12.34`` (Die Zeichen werden direkt eingegeben). 

Eine Nachricht kann also in Symbole auf verschiedenen Ebenen zerlegt werden: 

1. Eine Nachricht kann in strukturelle Elemente gegliedert werden (z.B. Sätze). 
2. Strukturelle Elemente können in Worte und Satzzeichen gegliedert werden. 
3. Worte werden in Buchstaben gegliedert.
4. Buchstaben können als Zahlen kodiert werden.
5. Zahlen können in einem Zahlensystem dargestellt werden und diese Darstellung kann in Ziffern *serialisiert* werden. 

Auf jeder dieser Ebenen arbeiten wir mit **Symbolen**.

## Zusammenfassung: Symbole und Bits

Ausgehend von der Informationstheorie bestehen Nachrichten aus Symbolen. Symbole können Sätze, Worte, Wortkombinationen, Buchstaben oder Buchstabenfolgen sein. Ein Symbol repräsentiert einen Teil einer Nachricht.

> **Definition:** Ein Symbol einer Nachricht wird als **Bit** (engl. Teil) bezeichnet. 

In den vorherigen Abschnitten haben wir wichtige Erkenntnisse abgeleitet: 

1. Symbole können aus einfacheren Symbolen zusammengesetzt sein ([[fa-external-link] Symbole](03_symbole.md)). 
1. Zahlensysteme **kodieren** Zahlenwerte zu einer Basis ([[fa-external-link] Zahlensysteme](04_zahlensysteme.md)). 
2. Die Basis eines Zahlensystems legt fest, wie viele Ziffern für Zahlenwerte zur Verfügung stehen ([[fa-external-link] Zahlensysteme](04_zahlensysteme.md)). 
3. Die kleinste Basis für ein Zahlensystem ist 2 ([[fa-external-link] Binärzahlen](04_binaries.md)).
4. Beliebige Symbole als Zahlenwerte abgebildetet werden können ([[fa-external-link] Zeichenketten](04_zeichenkodierung.md)). 
5. Ziffern sind Symbole ([[fa-external-link] Symbole](03_symbole.md)). 

Daraus ergibt sich der folgende Merksatz. 

> **Merke:** Das minimale Bit einer Nachricht ist die Unterscheidung zwischen `0` und `1`.

