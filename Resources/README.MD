# Was wir wissen

## Basics
So ziemlich alle Schaltungen bestehen aus:
- **Boost-Kondensatoren**
  Diese Kondensatoren bilden mit dem Dynamo einen Schwingkreis, um die
  Leistungsausbeute zu steigern. Scheinen fast überall durch zwei in Reihe
  geschaltete low-ESR-Kondensatoren realisiert zu werden, um teure
  Bipolar-Kondensatoren zu sparen.

  ![ForumsladerV6](assets/Forumslader.png)

  Hier beim Forumslader erkennbar: Es sind jeweils zwei Kondensatoren mit der
  gleichen Kapazität vorhanden.

- **Gleichrichter**
  Eigentlich immer ein Brückengleichrichter aus Dioden. Denkbar wäre auch einer
  aus FETs.

- **Glätt-Kondensator**

- **DC-DC-Konverter**
  Die Spannung wird auf das gewünschte Niveau geregelt, meist 5 V für USB.

## Existierende Schaltungen

### [USB-CHARGER](https://www.instructables.com/DIY-BICYCLE-USB-CHARGER-Fahrradlader-V31/)
- *TODO: Bashi*

### [Forumslader](https://www.forumslader.de/forumslader-pro/technik/elektronik-v6/)
- Misst auch die Geschwindigkeit und so.
- Vorteile:
	- Krass viel Leistung. Wird durch Anpassung der Boost-Kondensatoren an
	  Geschwindigkeit und Dynamo erreicht.
	- Kompakt
	- Eingebauter Akku
- Nachteile
	- **T E U E R**
	- Komplex
	- Kackt laut Siggi ab, wenn der Akku so richtig alle ist.

### [BikeUSB](https://github.com/H3wastooshort/BikeUSBv2)
- Anscheinend nicht besonders ausgereift, scheint auch ein Privatprojekt zu sein.
- Vorteile:
	- Benutzt USB-PD, um halbwegs klug den Ladestrom zu verhandeln Dazu wird
	  dieser [Chip](https://www.onsemi.com/download/data-sheet/pdf/fusb302b-d.pdf)
	  benutzt. Der Chip kann auf jeden Fall was, ist aber nicht so ganz trivial
	  zu verwenden.
	- Hat einen klugen Mechanismus, um sich selbst hochzufahren.
- Nachteile:
	- Benutzt keine Boost-Kondensatoren direkt am Dynamo. WTF?

### Schaltung von Sven und Jere (siehe `Sven+Jere.pdf`)
- Ist nur ein Dynamo.
- Nutzt einen nicht-invertierenden
  [Schmitt-Trigger](https://de.wikipedia.org/wiki/Schmitt-Trigger), um den
  Ausgang vom Dynamo direkt in ein Logik-Signal umzuwandeln.
- Ist nur ein brutaler Prototyp.

### Schaltung von Siggi
- Vorteile:
	- Billig
	- Erstaunlich gute Leistung
	- Geringe Komplexität. Wird auch dadurch erreicht, dass ein großer Teil auf
	  ein fertiges USB-PD-Modul ausgelagert wird.
	- Lässt sich noch per Hand löten ( Workshops mit Noobs).
- Nachteile
	- Hat einen festen Boost-Kondensator
