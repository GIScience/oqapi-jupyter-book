# Dashboard Usage
Auf dieser Seite findest du eine einfache Übersicht darüber, wie du im [ohsome Dashboard](https://dashboard.ohsome.org/en/#backend=ohsomeApi&groupBy=none&time=%2F2026-02-19T12%3A00Z%2FP1M&key=natural&value=tree&types=node&measure=count) navigierst. 

## Lass uns mit den Grundlagen beginnen!
Im oberen linken Tab kannst du zwischen den OSM History Stats und den OSM Quality Analyses wählen.
Die History Stats geben dir Einblicke in die ereignisreiche Entwicklung der OSM-Daten für jede Region und jeden Zeitraum, der dich interessiert.
Die Quality Analyses bieten viele verschiedene Qualitätsindikatoren, mit denen du OSM-Daten für dein Interessensgebiet validieren kannst.

![tabs](abbildungen/tabs_deutsch.png)

## OSM Quality Analyses

### Topic

Topics werden durch eine Menge von OSM-Tags und -Keys definiert, die einem bestimmten Objekt entsprechen. 
Im linken Fenster navigierst du zu *OSM Quality Analysis*.
Unter „Topic“ findest du ein Dropdown-Menü. Öffne es und mache dich mit allen verfügbaren Topics vertraut.
Wähle das Topic aus, das du untersuchen möchtest.
Das OSM-Dashboard erstellt automatisch den passenden OSM-Filter basierend auf dem ausgewählten Topic.

![topic](abbildungen/topics_deutsch.png)

### Area of Interest

Wähle dein Interessensgebiet auf der Karte im rechten Fenster aus. Du kannst entlang von Verwaltungsgrenzen oder mit selbst definierten Bounding Boxes auswählen. Zoome hinein, um eine genauere Abgrenzung deines Interessensgebiets zu erhalten.
Du kannst Abfragen für mehrere Regionen gleichzeitig ausführen. Klicke einfach auf mehrere Gebiete und entferne sie mit einem weiteren Klick oder schließe die blaue Box unter der Karte.

![area_of_interest](abbildungen/Untersuchungsgebiet_Auswahlkarte.png)

### Quality Indicators
Hier kannst du OSM-Daten anhand mehrerer Qualitätsdimensionen analysieren:
**Qualitätsdimensionen**
Vollständigkeit
- Mapping Sättigung
- Attributvollständigkeit
- Gebäudevergleich
- Landbedeckungsvollständigkeit
- Straßenvergleich
Aktualität
- Aktualität
Thematische Genauigkeit
- Thematische Genauigkeit der Landbedeckung
- Thematische Genauigkeit der Straßen
Sonstiges
- Nutzeraktivität


Abhängig vom gewählten Topic findest du die verfügbaren Qualitätsindikatoren zur Auswahl. Wähle die aus, die dich interessieren, und klicke auf den „run query“-Button, um deine Ergebnisse zu laden. 
Wenn du den Indikator Attributvollständigkeit oder Thematische Genauigkeit der Straßen verwendest, kannst du bestimmte Attribute auswählen. Um dies zu nutzen, aktiviere den Indikator und öffne das Dropdown-Menü, um die für dein Topic verfügbaren Attribute zu sehen. Wenn du mehrere Attribute in einer Abfrage auswählst, werden sie als ein gemeinsames Ergebnis dargestellt.

![quality_indicators](abbildungen/Indikatoren_Ausahl.png)