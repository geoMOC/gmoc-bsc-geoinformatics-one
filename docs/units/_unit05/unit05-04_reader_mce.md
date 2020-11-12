---
title:  Multikriterien, Multiziel-Analyse 
toc: true
toc_label: Inhalt


---



## Schema einer Multikriterien-Analyse (MCE)

Im einfachsten Fall der Entscheidungsunterstützung mit GIS gilt es, Räume oder Standorte zu finden, die für eine Zielsetzung mehrere Kriterien erfüllen oder optimieren. Im Fallbeispiel der Gemeinde LAhntal besteht die Zielsetzung in einem ersten Ansatz darin, die besten Lebensräume für die Wildkatze auf dem Gemeindegebiet zu identifizieren. Angenommen, die Katze bevorzugt siedlungsferne und bewaldete Gebiete, so lassen sich daraus zwei Suchkriterien formulieren. Liegen wie in diesem Fall mehrere Kriterien, aber nur eine Zielsetzung vor, so spricht man von einer Multikriterien-Evaluation (Multi Criteria Evaluation, MCE).

1. *Problemdefinition:*
Der erste Schritt einer MCE besteht in der Definition des Problems. Beim Fallbeispiel der Gemeinde St. Gittal könnte die Problemdefinition wie folgt lauten: „Welche Teile des Gemeindegebietes eignen sich als Lebensraum für den Wolf?“

2. *Kriterienwahl:*
Der nächste Schritt ist die Wahl der Kriterien. Die gewählten Kriterien sollten die Charakteristik des gesuchten Standorts oder Raumes möglichst gut widerspiegeln. Kriterien können sowohl räumlicher Natur (Geometrie, Topologie) als auch sachlicher Natur sein (Attribute). Ein räumliches Kriterium ist etwa der Abstand des potenziellen Lebensraumes des Wolfs zur nächsten Siedlung. Die Einschränkung auf die Bodennutzungsklasse „Wald“ ist hingegen ein sachliches Kriterium. Weiter gibt es harte, unbedingt zu erfüllende Kriterien („must-have“) 

3. *Operationalisierung der Kriterien:*
Sind die Kriterien einmal bestimmt, müssen sie in präzise, messbare Kenngrößen übersetzt werden. Diesen Vorgang nennt man Operationalisierung. So könnte das Kriterium „nicht zu nahe am Siedlungsgebiet“ in die Angabe einer Mindestdistanz zur Bauzone in Meter übersetzt werden. Man spricht davon, dass die Kriterien zu verrechenbaren Kenngrößen operationalisiert werden. In den meisten Fällen entsprechen die einzelnen Kriterien je einer Datenschicht im GIS (Layer mit Siedlungsnähe, Wald-Layer).

4. *Schaffung eines gemeinsamen Bezugs – Datenintegration:*
Die Datenintegration schafft Vergleichbarkeit durch gemeinsame Messskalen, gleiche Datentypen (Raster/Vektor) sowie gleiche Auflösungen und gleiche Referenzsysteme.

5. *Verschneidung:*
Identifikation der geeignetsten Räume: Nun werden die verschiedenen Kriterien miteinander verrechnet, um die gesuchten Standorte oder Räume zu ermitteln. Dazu gibt es mehrere mögliche Vorgehensweisen:
  * Logische (Boolesche) Verschneidung: In jeder Datenschicht finden sich nur binäre wahr/falsch-Informationen (true/false, Wald/Nichtwald), aus deren logischer Verschneidung die gesuchten Standorte und Räume ermittelt werden. Der Booleschen Verschneidung ist die Unit „Boolesche Verschneidung“ gewidmet.
  * Gewichtete Verschneidung: Fast nie wird die simple Unterscheidung in wahr und falsch der komplexen Realität gerecht. Eine wesentliche Verbesserung der Resultate kann erreicht werden, wenn die einzelnen Datenschichten mit Gewichten versehen werden. Im Fallbeispiel könnte z. B. die Entfernung zur Siedlung viel weniger wichtig sein als das Rückzugsgebiet Wald. Dazu könnte die Ebene mit der Entfernung zur Siedlung mit einem Gewichtsfaktor, z. B. mal fünf, versehen werden. Diese Themen werden separat behandelt (Units „Gewichtete Verschneidung“ und „Bestimmung der Gewichte“)
  * Fuzzy Overlay: Erhebungsfehler der Eingangsdaten und falsch gewählte Kriterien bergen die Gefahr von Evaluierungsfehlern. In einer Multikriterien-Evaluation können geeignete Gebiete verkannt und ungeeignete fälschlicherweise als geeignet klassifiziert werden. Eine Lösung dieses Problems besteht in der Auflösung scharfer Grenzen. Für die räumlichen Daten heißt das, dass Grenzen nicht als scharfe Linien, sondern als Übergangszonen repräsentiert werden. Bei den Attributen lösen unscharfe Wertebereiche die scharfen Klassengrenzen ab. Dieses Konzept beruht auf der Idee der Fuzzy Set Theory („fuzzy“ im Sinne von „unscharf“). Auf diese Ansätze wird erst im Intermediate Level vertieft eingegangen.
6. *Verifikation/Evaluation:*
Im letzten Schritt sollten die Resultate mit einer Referenz verglichen werden. Dies ist dann möglich, wenn im Feld erhobene Referenzdaten beigezogen werden können („ground truth“). Der letzte Schritt wird oft vernachlässigt. Aber beachten Sie: Eine Eignungskarte ohne Abschätzung ihrer Güte und Verlässlichkeit ist oft das Papier nicht wert, auf das sie gedruckt wurde!

##  Multizielanalyse (Multi Objective Evaluation, MOE)
	

Will die Gemeinde Lahntal den Dorffrieden von Caldern wahren, muss sie bestrebt sein, die Wünsche der Umweltfreunde, der Landwirte und der Freizeitsuchenden unter einen Hut zu bringen. Es ist leicht ersichtlich, dass die Ziele der verschiedenen Interessengruppen sehr unterschiedlich sind.

*  Es gibt Fälle, bei denen verschiedene Nutzungsansprüche auf der gleichen Parzelle realisiert werden können. Bei Einhaltung bestimmter Regeln könnten Wanderwege durchaus durch ein Wolfshabitat führen.
*  Daneben können sich Landnutzungsansprüche auch gegenseitig ausschliessen. Eine Parzelle kann nicht gleichzeitig Wikdkatzenhabitat, Bildungsparcours und Golfplatz sein. In solchen Fällen gilt es, verschiedene Planungsvarianten gegeneinander abzuwägen und schliesslich den Raum entsprechend seiner Eignung auf die verschiedenen Nutzungen aufzuteilen.

Im Gegensatz zur MCE liegen hier also mehrere Ziele vor, man spricht deshalb von einer Entscheidungsunterstützung mit mehreren Zielen (Multi Objective Evaluation, MOE).


{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/MOE_thumb.gif" alt="MOE (GITTA 2005)" caption="Eignungsanalyse bei zwei sich ausschliessenden Nutzungsansprüchen für den Marburg Open Forest (MOF) bei Caldern" %}


Die Abbildung zeigt das Resultat einer Eignungsanalyse bei zwei sich ausschliessenden Nutzungsansprüchen für den Marburg Open Forest (MOF) bei Caldern: Die beiden Ziele heissen „geeignet als Wildkatzenhabitat“ (Ziel A) und „geeignet für Freizeitnutzung“ (Ziel B). Ganz links sehen Sie eine Reihe von Eingangslayern der Eignungsanalyse, u.a. die Layer „Landnutzung” (oben) und „Hangneigung“ (Mitte). Die Karte daneben zeigt die räumliche Zuordnung des Waldgebietes auf die beiden Nutzungen. Weiss eignet sich weder für (A) noch für (B). Dunkelgrau wurde (A) und hellgrau wurde (B) zugeordnet. Dort wo sich Hellgrau und Dunkelgrau überlagern, besteht ein Nutzungskonflikt (Rot).
Im Diagramm rechts kann jeder Punkt des Raumes entsprechend seiner Eignung für (A) und (B) eingetragen werden. Je mehr ein Punkt einem Kriterium entspricht, desto höher ist sein entsprechender Prozentwert. Sowohl für (A) als auch für (B) kann ein Grenzwert angegeben werden, ab welchem ein Punkt der entsprechenden Nutzung zugewiesen wird. Im roten Rechteck oben rechts liegen alle Punkte mit einem Nutzungskonflikt. Für sie muss nun im Einzelnen entschieden werden, welcher Nutzungsklasse sie zugeordnet werden sollen. Im einfachsten Fall wird ein Konfliktpixel der Nutzung zugesprochen, für die es besser geeignet ist: Liegt das Konfliktpixel im Entscheidungsplot über der roten Linie, erhält es die Nutzung (B), andernfalls (A).
