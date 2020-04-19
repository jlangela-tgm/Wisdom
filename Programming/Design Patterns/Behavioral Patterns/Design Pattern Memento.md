# Design Pattern: Memento

> Jan Langela Regincos

Das Memento Pattern ist ein Behavoiural Pattern (Verhaltens Pattern), welches ermöglicht den Zustand eines Objektes zu speichern, um es später wieder in diesen Zustand versetzten zu können. z.B.: Rollback

Dies soll erfolgen ohne die Kapselung zu beinträchtigen. Der Zustand des Objektes wird also in einem anderen Objekt gespeichert und kann von dort wieder ausgelesen werden.

Beispielsweise kann der Benutzer also den aktuellen zustand eines Objektes speichern, wenn er es weiter bearbeiten aber noch auf den alten Zustand wieder zugreifen möchte.

Bsp.: Undo, Spielstand speichern.

## Aufbau/ Umsetztung

### Aufbau

Das Pattern beinhaltet 3 Klassen:

1. Die Klasse dessen Objekt man  speichern können soll (Originator)
2. Die Klasse welche die Zustände der Originators speichern und wieder ausgeben kann. (Memento)
3. Die Klasse die dem Originator den Befehl gibt seinen Zustand zu speichern oder auf ein gespeichertes Memento zurückzusetzten.

### Ablauf

​	Der Originator verfügt über eine Methode mit der er seinen Zustand in ein Memento speichern kann.

​	Das Memento verfügt lediglich über eine getter und Constructor Methode für das Speichern und
​	auslesen des Zustandes.

​	Der Caretaker entscheidet wann ein Memento erstellt werden soll und wann der zustand auf ein altes
​	Memento zurückgesetzt werden soll.

### UML

![MementoUML](\MementoUML.png)

### Beispiel

Ein Beispiel in dem das Memento Pattern implementiert wurde befindet sich in folgendem Repository.

Es handelt sich um ein Kleines Spiel in dem man Verschiedene Pfade zu einem Ziel nehmen kann. Das Spiel implementiert das Speichern und Laden von Spielständen. Ist sich der Spieler also nicht sicher welchen Pfad er nehmen möchte kann er den Spielstand speichern, einem Weg ausprobieren und den gespeicherten Spielstand wieder Laden um den anderen Weg zu wählen.

Der Spielstand (Standort im Spiel) wird als Enum abgespeichert, der aktuelle Wert des Enums wird beim Speichern in ein Memento Objekt gespeichert.

Außerdem wird der Speicherstand in einer Dropdownliste gespeichert, aus welcher an einen beliebigen Spielstand auswählen und Laden kann.

Viel Glück bei der Suche nach dem Ziel.

(zu bewerten ist das package game, ist besser als editor)

https://github.com/jlangela-tgm/Memento-Example



## Quellen:

http://vincehuston.org/dp/memento.html

https://sourcemaking.com/design_patterns/memento