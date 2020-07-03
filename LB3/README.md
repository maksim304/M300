# Containerisierung

Containerisierung erlaubt es ebenfalls auf eine Maschine mehrere unabhängige Kontexte zu haben, in denen Applikationen laufen können. Im Gegensatz zur Virtualisierung ist dieser Ansatz leichtgewichtiger, weil nicht für jeden Kontext ein vollständiges Betriebssystem zur Verfügung gestellt wird. Anstelle dessen wird das vorhandene Betriebssystem über geschickte Dateisystem-Schichten unterschiedlich konfiguriert.


[](https://github.com/maksim304/M300/blob/master/LB3/img/containerisierung.png)

## Vorteile

Auf einer Hardware können unterschiedliche Applikationen unabhängig voneinander laufen. Durch die stärkere Nutzung des Host-Betriebssystems ist der Ansatz leichtgewichtiger. In jedem Kontext kann das Betriebssystem anders konfiguriert werden. Wenn gewünscht sehen sich die verschiedenen Applikationen nicht.

Während Virtualisierung vorwiegend den Server-Bereich adressiert kann Containerisierung problemlos auf jedem Maschinentyp installiert werden. Damit erschließen sich auch Entwicklungsrechner.

Die Beschreibung einer Container-Konfiguration wird ebenfalls zum Artefakt im Entwicklungsprozess.

## Nachteile

Um die Leichtgewichtigkeit zu ermöglichen, müssen für Container andere Konzepte erlernt werden. Während bei Virtualisierung noch die bekannten Konzepte eins-zu-eins übertragen wurden, ist es bei Containern wichtig, die Dateisystem-Schichtung und weitere Spezialkonzepte zu verstehen.

# Docker

Docker ist eine Open-Source-Software, mit der sich Container zur Virtualisierung von Anwendungen erstellen und betreiben lassen. Auf einem Linux-, Windows- oder macOS-basierten Host-System werden mit der Software Laufzeitumgebungen zur Ausführung voneinander isolierter Anwendungen bereitgestellt, ohne dass die Virtualisierung des kompletten Betriebssystems notwendig ist.

# Vorteile der Containerisierung mit Docker
Die Containerisierung mit der frei verfügbaren Software bietet zahlreiche Vorteile. Sie benötigt weniger Ressourcen als virtuelle Maschinen, schottet die Anwendungen aber dennoch sicher untereinander und vom Host-System ab. Ein Container lässt sich in Form einer Image-Datei einfach auf andere Systeme übertragen. Es ist keine neue Installation der Anwendung und ihrer Laufzeitumgebung notwendig. Weitere Vorteile sind:

* die gute Skalierbarkeit durch die Nutzung vieler weiterer Container,
* die einfache Verwaltung vieler Container über Orchestrierungs-Tools wie Kubernetes,
* das schnelles Starten von Containern.