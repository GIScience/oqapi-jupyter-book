# Attributvollständigkeit

Der Attributvollständigkeits-Indikator gibt an, wie detailliert und vollständig zusätzliche Attribute, z.B. Straßennahme oder Höchstgeschwindikeit, in deinem Untersuchungsgebiet kartiert sind. Für diesen Indikator wählst du im Drop-Down-Menü ein Attribut aus, das untersucht werden soll. 

:::{margin}
<img src="../../abbildungen/attributvollständigkeit.png" width="250"/>
</div>
:::

Abhängig vom *Thema* kannst du aus einer unterschiedlichen Auswahl an Attributen wählen. Wenn du mehr als ein Attribut in einer Anfrage auswählst, werden die Ergebnisse kombiniert und die Ergebnisgrafik zeigt den Prozentsatz aller Elemente, die alle ausgewählten Attribute besitzen.

:::{dropdown} **Custom Attributes definieren**
Es können auch mehrere oder selbsterstellte Attribute definiert werden.
:::

## Ergebnis
Die Ergebnisse der Abfrage findest du im Ergebnisprotokoll unten.
Das grüne, gelbe oder rote Banner oben links zeigt den Attribut-Vollständigkeitsgrad an.

<img src="../../abbildungen/attributvollständigkeit_frankfurt.png" width="700"/>

## Methodik
`Intrinsischer Ansatz`

Berechnet den Prozentsatz der Elemente, die ein bestimmtes Attribut enthalten.
Für Punktegeometrien die Gesamtanzahl aller Elemente mit der Anzahl der Elemente verglichen, die die ausgewählten Attribute aufweisen.
Wenn das untersuchte OSM Element eine Linie ist, wird das Verhältnis basierend auf der Länge in km berechnet. 
Bei Polygonen nutzen wir die Fläche in km².

Es gibt drei Qualitätskategorien:
- niedrige Completeness < 25%
- mittlere Completeness 25% - 75%
- hohe Completeness > 75%

Die Grenzwerte für die Qualitätskategorien wurden durch die Betrachtung vieler Gebiete und Attribute festgelegt und sollten nicht als objektive Metrik verstanden werden.

## Beispiele

In folgendem Beispiel sehen wir wie wichtig es ist, das richtige Thema auszuwählen. Wir wollen die Attributvollständigkeit der Straßennamen für die Frankfurter Innenstadt herausfinden.

Auf dieser Abbildung sehen wir das Ergebnis für das Thema _Straßen(alle highways)_. Knapp 40% ist eine mittelmäßige Vollständigkeit und ein überraschendes Ergebnis für eine deutsche Großstadt. Spätestens jetzt muss uns auffallen, dass hier etwas eventuell nicht ganz stimmt. Das Thema _Straßen(alle highways)_ beinhaltet nicht nur von Autos befahrbare Straßen, sondern sämtliche Wege für motorisierten Verkehr sowie Rad- und Fußwege. Da viele Rad- und Fußwege keinen expliziten Namen haben, ist das Ergebnis der Abfrage nur knapp 40%.

<div>
<img src="../../abbildungen/attributvollständigkeit_frankfurt.png"/>
</div>

Wenn wir uns nur für die Straßennamen der Straßen für motorisierten Verkehr interessieren, entscheiden wir uns für das Thema _Straßen(Autos)_. In der nächsten Abbildung sehen wir, dass wir nun für dasselbe Untersuchungsgebiet eine hohe Vollständigkeit erhalten.

<div>
<img src="../../abbildungen/attributvollständigkeit_frankfurt_autos.png" width="700"/>
</div>