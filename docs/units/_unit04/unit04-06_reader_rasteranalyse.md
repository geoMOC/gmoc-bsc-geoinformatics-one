---
title: – Sichtweite und Sichtfeld
toc: true
toc_label: Inhalt

---


Ein bereits komplexes Beispiel zur Ableitung räumlicher Informationen ist die Sichtbarkeitsanalyse. Bei einer Sichtbarkeitsanalyse wird, ausgehend von einem digitalen Höhenmodell und einem gegebenen Punkt, berechnet, welche anderen Punkte im Gelände sichtbar sind. Das Prinzip von Sichtbarkeitsberechnungen wird zuerst im eindimensionalen Fall gezeigt und dann auf den zweidimensionalen Fall übertragen.

## Anwendung Sichtbarkeitsanalyse
Sichtbarkeitsberechnungen gelangen in verschiedenen Anwendungen zum Einsatz. Ein erstes Beispiel ist die Platzierung eines Aussichtsturms. Mit einem digitalen Geländemodell können innerhalb sehr kurzer Zeit verschiedene Standorte geprüft werden. Außerdem kann die Berechnung mit verschiedenen Turmhöhen durchgeführt werden (Variation von hv). Ein weiteres Beispiel ist die Ausbreitung von elektromagnetischen Wellen (z. B. zur Planung von Mobilfunkantennen). Hier ist zu beachten, dass das Gebiet, in welchem elektromagnetische Signale empfangen werden können, nicht genau mit dem sichtbaren Gebiet übereinstimmt. Im GIS wird dies in der Regel dadurch korrigiert, dass die Höhe eines Punktes einen bestimmten Betrag unter der Sichtbarkeitslinie sein muss, damit an diesem Punkt das Signal nicht empfangen werden kann. Die Höhe dieses Betrages ist abhängig von der Wellenlänge. Ein letztes Beispiel stammt aus der Wildtierbiologie. Ein GIS kann hier eingesetzt werden, um ein optimales Gebiet zur Wiederansiedlung von Tierarten auszuwählen. Das Rocky-Mountain-Bighorn-Schaf beispielsweise hält sich (unter anderem) bevorzugt in Gebieten auf, welche nur von wenigen Orten aus gesehen werden können. Dies reduziert die Wahrscheinlichkeit, von einem Raubtier entdeckt zu werden.


## Sichtbarkeitsanalyse Vektordatenmodell

Im eindimensionalen Fall eines Profils wird zur Ermittlung der Sichtbarkeit eines Zielpunkts berechnet, ob ein Punkt zwischen dem Standort V und dem Zielpunkt P höher liegt als die Verbindungslinie (d. h. die Sichtlinie; engl. line of sight = LOS). Ist dies der Fall, so ist die Sichtlinie LOS blockiert und somit der Zielpunkt nicht sichtbar, andernfalls ist der Zielpunkt sichtbar. Am einfachsten programmiert man einen solchen Test, indem man prüft, ob die Neigung der Linie zwischen dem Standpunkt V und dem überprüften Zielpunkt P auf dem Profil grösser oder kleiner als diejenige der Linie zum letzt-gespeicherten Horizontpunkt Ihor ist. Oder anders gesprochen, ob der Vertikalwinkel γi zum aktuell überprüften Punkt größer (= sichtbar) oder kleiner (= unsichtbar) ist als der Vertikalwinkel γhor des letzten Horizonts.

{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/profil.png" alt="Zweidimensionaler Querschnitt Sichtbarkeitsanalyse" caption="*Zweidimensionaler Längsschnitt Sichtbarkeitsanalyse*" %}

In einem linear interpolierten dreiecksbasierten Geländemodell müssen zuerst die Höhen der Verbindungslinien-Schnittpunkte (von Standort und Zielpunkt) und der Dreiecksvermaschung berechnet werden, wie dies die nächste Abbildung zeigt.

{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/TIN.png" alt="Dreiecksvermaschung  Sichtbarkeitsanalyse" caption="*Dreiecksvermaschung  Sichtbarkeitsanalyse*" %}

Die Höhen an den Schnittpunkten S1 bis Sn können durch lineare Interpolation aus den Höhen der beiden Dreieckspunkte berechnet werden, die die betreffende Dreieckskante beschließen. Als Resultat ergibt sich ein Profil wie im eindimensionalen Fall (siehe Abbildung unten). Auf diesem Profil kann nun derselbe Algorithmus für die LOS-Ermittlung wie oben angewendet werden.

{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/TIN2.png" alt="Längsschnitt  Sichtbarkeitsanalyse Extraktion der Dreicksvermaschungsanalyse " caption="*Längsschnitt   Sichtbarkeitsanalyse Sichtbarkeitsanalyse Extraktion der Dreicksvermaschungsanalyse*" %}

## Rasterbasierte Sichtbarkeitsanalyse

Ermittlung der Profile zwischen Standpunkt V und Zielpunkt P in einem rasterbasierten Geländemodell (Raster) ist ein Sonderfall des dreickvermaschten Ansatzes: Hier kann, analog die Verbindungslinie der durch das Raster gebildeten Quadrate (anstelle der Dreiecke) geschnitten und ein Profil erstellt werden (Abbildung a). Da die Berechnung der Schnittpunkte je nach Rasterauflösung sehr rechenintensiv sein kann, gibt es Näherungsalgorithmen, um ein Profil zu berechnen. In der untenstehenden Abbildung werden zwei davon gezeigt: In Abbildung b) wird entlang der Sichtbarkeitslinie die Höhe in regelmäßigen Abständen abgefragt und gespeichert. Da jede Rasterzelle genau eine Höhe hat, muss somit nur berechnet werden, in welcher Rasterzelle der betreffende Zwischenpunkt liegt. In der Lösung von Abbildung c) wird der Sichtstrahl zuerst gerastert und dann die Höhe der so entstandenen Rasterzellen mit denjenigen des Geländemodells verglichen.

{% include figure image_path="https://minibsc.gis-ma.org/GISBScL3/de/image/computing_los.png" alt="Längsschnitt  Sichtbarkeitsanalyse Rastermodell " caption="*Längsschnitt   Sichtbarkeitsanalyse Sichtbarkeitsanalyse Rastermodell*" %}




