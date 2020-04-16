# Design Pattern: Memento

Das Memento Pattern ist ein Behavoiural Pattern (Verhaltens Pattern), welches ermöglicht den Zustand eines Objektes zu speichern, um es später wieder in diesen Zustand versetzten zu können. z.B.: Rollback

Dies soll erfolgen ohne die Kapselung zu beinträchtigen. Der Zustand des Objektes wird also in einem anderen Objekt gespeichert und kann von dort wieder ausgelesen werden.

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



Beispiel:



## Quellen:

http://vincehuston.org/dp/memento.html

https://sourcemaking.com/design_patterns/memento