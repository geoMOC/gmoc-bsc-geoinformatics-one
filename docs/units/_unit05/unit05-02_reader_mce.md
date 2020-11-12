---
title: Eignungsanalysen
toc: true
toc_label: Inhalt
panel1:  
  - url: https://minibsc.gis-ma.org/GISBScL3/de/image/steinschlaglegende.gif
    image_path: https://minibsc.gis-ma.org/GISBScL3/de/image/steinschlaglegende.gif
    title: "Steinschlaggefährungsanalyse der Gemeinde Saas Baalen (GITTA 2005)"
    alt: "Steinschlaggefährungsanalyse der Gemeinde Saas Baalen (GITTA 2005)"


---


Am leichtesten lassen sich die Anforderungen kombinierter Kriterien zur Findung räumlicher Merkmalskombinationen anhand eines Fallbeispiels erarbeiten. So häufen sich die Beispiele konnkurierender Interessensgruppen und auch gesetzlich garantierter Schutzzustände von Windkraftanalggen, Wildschweinschäden bis hin zur potenziellen  Wolf-, Luchs- oder Wildkatzenverbreitung. 

Das frühe *Fallbeispiel St. Gittal*  geht dieser Art der räumlichen Analyse mit der derzeit hochaktuellen Frage *„Welche Flächen der Gemeinde von St. Gittal eignen sich für die Wiederansiedlung eines großen Raubtieres?“* (vgl. [KORA 2005](https://minibsc.gis-ma.org/GISBScL4/de/material/wolf_kora.pdf); [Baumgartner 1995](https://minibsc.gis-ma.org/GISBScL4/de/material/facts1995_wolf.pdf))nach. Es zeigt anschaulich die konkreten Anforderungen auf. Selbst in dieser einfachen Analyse wird die Komplexität von Eignungsanalysen im Kontext der Wirkungen der daraus abgeleiteten Entscheidungen bzw. Handlungsempfehlungen deutlich. 

Die Grundlage einer derartigen Analyse sind räumliche Suchtechniken basierend auf unterschiedlichen Kriterien. Diese setzen sich aus mehreren einfachen Suchen mit z.B. nur einem Suchkriterium *„Welche Gebiete von St. Gittal sind mit Wald bedeckt?“* ist  zusammen. Erst die Kombination mehrerer Suchkriterien führt zu Lösungsvorschlägen die dann *bewertet* werden müssen. Ein GIS ermöglicht solche Kombinationen durch die Verschneidung mehrerer Informationsebenen. Erst die Überlagerung von Informationen z.B. zum Bodentyp, der Vegetation und Topographie erlaubt es die gestellte Frage zu beantworten. Der Begriff *Eignungsanalyse* bezeichnet die Suche nach Standorten oder Räumen, die sich durch eine Kombination bestimmter Eigenschaften auszeichnen. Das Resultat einer Eignungsanalyse ist häufig eine *Eignungskarte*. Sie zeigt in Form einer thematischen Karte, welche Standorte oder Räume sich für die vorgegebene Nutzung besonders gut eignen (z.B. landwirtschaftliche Eignungskarte). Die invertierte Variante der Eignungskarte ist die Gefährdungs- oder Gefahrenkarte. Sie identifiziert Gebiete, die aufgrund gegebener Kriterien einer bestimmten Gefahr besonders ausgesetzt sind (z.B. Lawinengefährdungskarten).

Die Eignungsanalyse wird vielfach eingesetzt zur Unterstützung der Entscheidungsfindung in Planungsprozessen, z.B. in der Umweltplanung. Dabei gilt es oft abzuklären, wo der geeignetste Standort für ein bestimmtes Objekt liegt (z.B. für ein Kraftwerk, eine Seilbahn, ein Naturschutzgebiet). Für die Entscheidungsträger der Gemeinde St. Gittal könnte es z.B. nützlich sein, den Standort eines Kinderspielsplatzes oder Streichelzoos auf mögliche Rückzugsräume des Wolfes abzustimmen.

Eine ganze Reihe mathematischer Methoden erlaubt es, verschiedene Alternativen einer Entscheidung aufgrund bestimmter Kriterien und Wertungen gegeneinander abzuwägen. Oft kommt ein Methodenmix zum Einsatz. Komplexe Entscheidungsunterstützungs-Systeme (Decision Support Systems, DSS) helfen den Entscheidungsträgern, die verschiedenen Optionen zu vergleichen.

Handelt es sich um ein räumliches Entscheidungsproblem, so ist die Integration von Entscheidungsunterstützungsmethoden in ein GIS zielführend. Ein GIS übernimmt das Datenmanagement, erweitert die DSS-Logik um räumliche Analysefunktionen und ermöglicht den Zugang zu den Eingangsdaten und den Resultaten durch kartographische Darstellungen. Die Kombination von DSS und GIS erleichtert es den Entscheidungsträgern, Alternativen gegeneinander abzuwägen, und sie kann zu transparenten und damit objektiveren Entscheidungen führen.

## Gefährdungsanalyse

Mit Hilfe von Geländemodellen (Werteoberflächen) können in einem GIS relativ komplexe Sachverhalte modelliert werden. Nachfolgend wird gezeigt, wie man mit Hilfe eines GI-S potenziell von Steinschlag betroffene Gebiete identifizieren kann. Als Ausgangsdaten sind folgende kontinuierliche Rauminformationen verfügbar:

  * Felsflächen
  * Waldflächen
  * Digitales Geländemodell

### Beispiel Steinschlagmodellierung

Nachfolgend ist die Konzeption einer GIS gestützten einfachen Steinschalgsgefärdungskarte dargestellt. Konzeptionell wird anstehender Fels (Felsflächen) als potenzielles Anrissgebiet betrachtet. Unter der schlichten Annahme, dass nach Newtons Gravitationsgesetz fallende Steine sich exakt entlang der *Falllinie* talwärts bewegen, wird zur Identifikation der gravitativ betroffenen Unterlieger von jeder Felsfläche (Pixel, Polygon) die Falllinie berechnet. Die gravitative Steinbewegung kommt, so die Annahme, zum Stillstand, wenn das *Pauschalgefälle* das erste Mal geringer als 31 Grad wird (empirischer Schwellwert). Weiterhin wird die Annahme getroffen, dass in Waldgebieten ein Stein schneller zum Stillstand kommt (Bäume wirken als Hindernisse). Daher wird dort den Schwellenwert des Pauschalgefälles höher gesetzt (z.B. auf 33 Grad). Die untenstehende Abbildung zeigt das Resultat einer solchen Analyse in der Umgebung der Gemeinde Saas Baalen. Rot eingefärbt sind die steinschlaggefährdeten Gebiete, wobei der Farbton das resultierende Pauschalgefälle in Grad repräsentiert.



{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/steinschlagresult.jpg" alt="Steinschlaggefährdung (GITTA 2005)" caption="Steinschlaggefährungsanalyse der Gemeinde Saas Baalen (GITTA 2005)" %}

{% include gallery id="panel1"  layout = "forth"  %}
