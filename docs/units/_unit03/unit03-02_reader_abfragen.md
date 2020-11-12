---
title: Thematische Abfragen
toc: true
toc_label: Inhalt


---


Eine thematische Abfrage führt zu einer den Bedingungen entsprechenden Auswahl aus den abgefragten Attributwerten. Thematische Abfragen sind daher konventionelle (= ohne Raumbezug) Abfragen relationaler Datenbestände. In GIS werden die thematischen Abfragen entweder mit `SQL` (Structured Query Language) oder systeminternen Abfragesprachen durchgeführt. In beiden Fällen werden die einzelnen Befehle üblicherweise mit Hilfe eines graphischen Dialogsystems ausgewählt und zusammengesetzt.

### Input-Daten zu den Operatoren-Beispielen

Die nachfolgenden Beispiele basieren auf den folgenden Input Daten (Geometrie und Relation). Für die logischen Operatoren sind die Venn-Diagramme wie zuvor zu interpretieren.
{% include figure image_path="/assets/images/unit03/0304_input.jpg" alt="Input Daten zu den folgenden Abfragen" caption="Input Daten zu den folgenden Abfragen (GITTA 2005)" %}




### Beispiele zu den unterschiedlichen Abfragen

Machen Sie sich mit der Wirkungsweise der Operatoren vertraut. Nachfolgend finden Sie eine Reihe von SQL-Abfragen. Die resultierenden Ergebnisse sind sowohl als Relation als auch als Geometrie dargestellt.

## Vergleichende Operatoren

{% include figure image_path="/assets/images/unit03/0305_vop.jpg" alt="Vergleichende Operatoren" caption="Abbildung 03-05: Vergleichende Operatoren (GITTA 2005)" %}


## Logische Operatoren

### Die logische Verknüpfung AND
{% include figure image_path="/assets/images/unit03/and_ex.jpg" alt="Die logische Verknüpfung AND" caption="Abbildung 03-07 Die logische Verknüpfung AND (GITTA 2005)" %}



### Die logische Verknüpfung OR
{% include figure image_path="/assets/images/unit03/or_ex.jpg" alt="Die logische Verknüpfung OR" caption="Abbildung 03-08: Die logische Verknüpfung OR (GITTA 2005)" %}

### Die logische Verknüpfung XOR

{% include figure image_path="/assets/images/unit03/xor_ex.jpg" alt="Die logische Verknüpfung XOR" caption="Abbildung 03-08: Die logische Verknüpfung XOR (GITTA 2005)" %}


### Die logische Verknüpfung NOT


{% include figure image_path="/assets/images/unit03/not_ex.jpg" alt="Die logische Verknüpfung NOT" caption="Abbildung 03-08: Die logische Verknüpfung not (GITTA 2005)" %}

### Verschachtelte logische Operatoren

Für die nachfolgend gezeigten verschachtelten logischen Operatoren gelten folgende Angaben:


  * Kreis 1: Baumart = „Lärche“
  * Kreis 2: Vorrat > 110 m<sup>3</sup>/ha
  * Kreis 3: Dichte > 80%

{% include figure image_path="/assets/images/unit03/nestedoperators.png" alt="Verschachtelte logische Operatoren" caption="Abbildung 03-09: Verschachtelte logische Operatoren (GITTA 2005)" %}

## Denken Sie mit...

Betrachten Sie die folgende SQL Abfrage: 

``Select * from Parzelle where (Dichte > 80% and Vorrat > AVER(Parzelle.Vorrat)) or Baumart = „Lärche“``

  * Wie viele Operatoren-Typen können Sie identifizieren?
  * Formulieren Sie die Anfrage in einen normalen Fragetext um.
  * Können Sie die Anfrage mit gleichem Resultat auch anders formulieren?




