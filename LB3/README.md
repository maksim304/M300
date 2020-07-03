# Containerisierung

Containerisierung erlaubt es ebenfalls auf eine Maschine mehrere unabhängige Kontexte zu haben, in denen Applikationen laufen können. Im Gegensatz zur Virtualisierung ist dieser Ansatz leichtgewichtiger, weil nicht für jeden Kontext ein vollständiges Betriebssystem zur Verfügung gestellt wird. Anstelle dessen wird das vorhandene Betriebssystem über geschickte Dateisystem-Schichten unterschiedlich konfiguriert.


## Vorteile

Auf einer Hardware können unterschiedliche Applikationen unabhängig voneinander laufen. Durch die stärkere Nutzung des Host-Betriebssystems ist der Ansatz leichtgewichtiger. In jedem Kontext kann das Betriebssystem anders konfiguriert werden. Wenn gewünscht sehen sich die verschiedenen Applikationen nicht.

Während Virtualisierung vorwiegend den Server-Bereich adressiert kann Containerisierung problemlos auf jedem Maschinentyp installiert werden. Damit erschließen sich auch Entwicklungsrechner.

Die Beschreibung einer Container-Konfiguration wird ebenfalls zum Artefakt im Entwicklungsprozess.

## Nachteile

Um die Leichtgewichtigkeit zu ermöglichen, müssen für Container andere Konzepte erlernt werden. Während bei Virtualisierung noch die bekannten Konzepte eins-zu-eins übertragen wurden, ist es bei Containern wichtig, die Dateisystem-Schichtung und weitere Spezialkonzepte zu verstehen.

# Docker
