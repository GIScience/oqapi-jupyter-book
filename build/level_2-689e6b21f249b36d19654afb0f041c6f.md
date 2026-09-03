# Level 2 - Nutzerdefinierte Attribute und Themen

In dieser Aufgaben werden wir die Qualität von OSM Daten bezüglich von selbstdefinierten Themen und Attributen untersuchen.
Wählt hierfür im ohsome Dashboard zunächst eine beliebige Region in Deutschland aus, für die ihr die Analyse durchführen wollt.

## Attributvollständigkeit: Straßenbreite

Der Indikator zur Berechnung der Attributvollständigkeit erlaubt es die Attribute frei zu definieren bzw. die Definition von bestehenden Attributen anzupassen.
Auf diese Art kann jedes beliebiges Attribut geprüft werden.

:::{admonition} Aufgabe
:class: tip
Versuche zum Thema *Straßen (Autos)* herauszufinden, wie viele Straßen eine Information über ihre Breite besitzen.
Nutze hierfür ein selbst erstelltes Attribut für den Attributvollständigkeitsindikator.
:::

:::{dropdown} Lösung
Wähle das Thema *Straßen (Autos)* aus. Beim Selektieren des Attributvollständigkeitsindikators wähle ein beliebiges Attribut und 
anschließend das blaue Feld neben den Attributen. In diesem Fenster entfernen den bisherigen Filter und setzte stattdessen
`width=*` ein. Anschließend berechne den Indikator für die gewünschte Region.
:::

## Nutzderdefinierte Themen: 

Falls die vordefinierten Themen für eine Analyse nicht ausreichen, kannst du auch selbst ein Thema definieren.

:::{admonition} Aufgabe
:class: tip
Erstelle ein eigenes Thema für alle Autobahnen.
Recherchiere hierfür zunächst den relevanten Filter im [OSM-Wiki](https://wiki.openstreetmap.org/). 
:::

:::{dropdown} Lösung
Deutsche Autobahnen werden mit dem Schlüssel-Wert-Paar *highway=motorway* in OSM kartiert (siehe [hier](https://wiki.openstreetmap.org/wiki/DE:Germany/Autobahn)).
Um uns auf linienhafte Elemente zu reduzieren, fügen wir noch *geometry:line* hinzu.
Zusammen ergibt sich dadurch der Filter *highway=motorway and geometry:line*.
:::

Nun kannst du nun für dein selbstdefiniertes Thema die verschiedenen OSM-Qualitätsindikatoren berechnen.
[Hier ein Beispiel](https://next.ohsome-dashboard.heigit.org/de/#backend=oqtApi&topic=custom-topic&topic-title=Stra%C3%9Fen+%28Autos%29&topic-filter=highway+in+%28motorway%2C+motorway_link%29+and+geometry%3Aline&adminids=-62611&indicators=mapping-saturation%2Ccurrentness%2Cuser-activity) für die Vollständigkeit, Aktualität und Nutzeraktivität für das selbstdefinierte Thema *Autobahnen* in Baden-Württemberg.

