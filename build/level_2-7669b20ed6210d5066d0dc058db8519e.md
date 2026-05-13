# Level 2 - Nutzerdefinierte Attribute und Themen

### Selbst erstellte Attribute für die Attributvollständigkeit

Versuche zum Thema *Straßen (Autos)* herauszufinden, wie viele Straßen eine Information über ihre Breite besitzen. Nutze
hierfür ein selbst erstelltes Attribut für den Attributvollständigkeitsindikator.

:::{dropdown} Lösung
Wähle das Thema *Straßen (Autos)* aus. Beim Selektieren des Attributvollständigkeitsindikators wähle ein beliebiges Attribut und 
anschließend das blaue Feld neben den Attributen. In diesem Fenster entfernen den bisherigen Filter und setzte stattdessen
*width=* ein. Anschließend berechne den Indikator für die gewünschte Region.
:::


### Selbst erstellte Themen

Falls die vordefinierten Themen für eine Analyse nicht ausreichen, kannst du auch selbst ein Thema definieren. Erstelle 
ein eigenes Thema für alle Autobahnen. Recherchiere hierfür den relevanten Filter im [OSM-Wiki](https://wiki.openstreetmap.org/). 

:::{dropdown} Lösung
Deutsche Autobahnen werden mit dem Schlüssel-Wert-Paar *highway=motorway* in OSM kartiert (siehe [hier](https://wiki.openstreetmap.org/wiki/DE:Germany/Autobahn)).
Um uns auf linienhafte Elemente zu reduzieren, fügen wir noch *geometry:line* hinzu. Zusammen ergibt sich dadurch der Filter
*highway=motorway and geometry:line*.
:::


Wähle nun für das Thema *Straßen (Autos)* mindestens zwei weitere Regionen aus um deine Analyse auzuweiten.
Du kannst dabei auch Regionen außerhalb Deutschlands wählen.

:::{admonition} Aufgabe
:class: tip
Welche regionalen Unterschiede kannst du in der Datenqualität feststellen?
:::

:::{dropdown} Lösung
* [Radwege Sao Paolo](https://next.ohsome-dashboard.heigit.org/de/#backend=oqtApi&topic=cycleway&adminids=-4807856&indicators=mapping-saturation%2Ccurrentness)
:::