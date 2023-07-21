# DBI_Ausarbeitung
Matura Ausarbeitung für Datenbanken

##  1) Normalformen

---
**Frage:**

Was bedeuten die Begriffe 1NF, 2NF und 3NF in Bezug auf Datenbanken? Erkläre die Normalformen und gib ein Beispiel für jede.

---

1NF, 2NF und 3NF sind die ersten drei Typen der Datenbanknormalisierung. Sie stehen für die erste Normalform, die zweite Normalform und die dritte Normalform.

Die Norminalisierung beschreibt den Prozess der Strukturierung und Umorganisierung eines retionalen Datenbankschemas. Informationen werden in mehrere Tabellen aufgeteilt und über Beziehungen mit dem Ziel miteinander verknüpft, Redundanzen, Inkonsistenzen und Anomalien zu vermeiden und beseitigen. 

Unnormierte Form UNF:
Bevor die Informationen norminaliesiert wurden befinden sie sich in der Unnormierten Form. Die unnormierte Form ist die Ausgangsform einer Datenbank, in der Daten nicht in Tabellen aufgeteilt und nicht durch Beziehungen miteinander verbunden sind. In dieser Form können Datensätze redundant und inkonsistent sein und es können Anomalien auftreten.

Beispiel:

![image](https://github.com/Lukas2380/DBI_Ausarbeitung/assets/96386473/9677f9c2-f051-480f-8985-544fef03fae4)

Erste Normalform 1NF:
In der ersten Normalform (1NF) werden alle Attribute einer Tabelle atomisiert, das heißt, sie sind nicht mehr in Teilwerte unterteilt. Jeder Datensatz hat einen eindeutigen Schlüssel und es gibt keine wiederholenden Gruppen von Attributen in einer Tabelle.

Beispiel:

![image](https://github.com/Lukas2380/DBI_Ausarbeitung/assets/96386473/d1e1949f-588e-4402-b1f0-425cf8fbed6a)

Zweite Normalform 2NF:
In der zweiten Normalform (2NF) sind alle Nicht-Schlüsselattribute funktional abhängig vom gesamten Schlüssel. Das bedeutet, dass es keine Teilschlüssel gibt, von denen ein Nicht-Schlüsselattribut abhängig ist.

Beispiel:
 
![image](https://github.com/Lukas2380/DBI_Ausarbeitung/assets/96386473/07a2c544-2b36-4f74-961e-19c744ac1784)

Dritte Normalform 3NF:
In der dritten Normalform (3NF) sind alle Nicht-Schlüsselattribute transitiv abhängig vom Schlüssel. Das bedeutet, dass es keine Abhängigkeiten zwischen Nicht-Schlüsselattributen in einer Tabelle gibt.

Beispiel:

![image](https://github.com/Lukas2380/DBI_Ausarbeitung/assets/96386473/9faa8290-e66f-4f06-9c4e-0de43e847dbc)


## 2.) Erstellung und Änderung von Tabellen in SQL

---
**Frage:**

Wie erstellt und ändert man Tabellen in SQL? Zeige anhand eines Beispiels, wie man eine Tabelle in SQL erstellt und wie man eine Spalte in einer Tabelle hinzufügt.

---

## Einleitung
In SQL wird zum erstellen von Tabellen der Befehl Create Table und zum ändern von Tabellen der Alter Table Befehl benutzt.

## Erstellung einer Tabelle
Die Erstellung einer Tabelle erfolgt mit dem CREATE TABLE-Statement. Dabei werden verschiedene Klauseln verwendet, um die Tabellenstruktur festzulegen. Hier sind die wichtigsten Punkte:

```sql
CREATE TABLE table_name (
    column1 datatype1,
    column2 datatype2,
    ...
    PRIMARY KEY (column_name),
    FOREIGN KEY (column_name) REFERENCES other_table(column_name),
    ...
);
```

- 'table_name': Der Name der Tabelle, die erstellt werden soll.
- 'column1', 'column2', ...: Die Namen der Spalten in der Tabelle.
- 'datatype1', 'datatype2', ...: Die Datentypen der jeweiligen Spalten.
- 'PRIMARY KEY (column_name)': Definiert einen Primärschlüssel für die Tabelle.
- 'FOREIGN KEY (column_name) REFERENCES other_table(column_name)': Definiert einen Fremdschlüssel, der auf eine Spalte in einer anderen Tabelle verweist.

### Erstellung einer Tabelle mittels Select auf eine andere Tabelle:

```sql
CREATE TABLE new_table_name AS
    SELECT column1, column2,...
    FROM existing_table_name
    WHERE ....;
```

## Änderung einer Tabelle
Änderungen an einer Tabelle können mit dem ALTER TABLE-Statement vorgenommen werden. Eine häufige Änderung besteht darin, eine Spalte hinzuzufügen. Hier ist die Syntax dafür:

```sql
ALTER TABLE table_name
ADD COLUMN column_name datatype;
```

- 'table_name': Der Name der Tabelle, zu der eine Spalte hinzugefügt werden soll.
- 'column_name': Der Name der neuen Spalte.
- 'datatype': Der Datentyp der neuen Spalte.

## 3.) Einfügen und Ändern von Daten in SQL

---
**Frage:**

Wie legt und ändert man Daten in SQL an? Zeige anhand eines Beispiels, wie man Daten in eine Tabelle einfügt und wie man bereits vorhandene Daten aktualisiert.

---

Um Daten in eine Tabelle einzufügen, wird das INSERT INTO-Statement verwendet. Hier ist die Syntax dafür:

```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

- ‘table_name’: Der Name der Tabelle, in die die Daten eingefügt werden sollen.
- ‘column1’, ‘column2’, …: Die Namen der Spalten, in die die Daten eingefügt werden sollen.
- ‘value1’, ‘value2’, …: Die Werte, die in die jeweiligen Spalten eingefügt werden sollen.

Hier ein Beispiel:

```sql
INSERT INTO customers (first_name, last_name, email)
VALUES ('John', 'Doe', 'john.doe@example.com');
```
In diesem Beispiel wird ein neuer Datensatz in die Tabelle ‘customers’ eingefügt. Der Vorname ist ‘John’, der Nachname ist ‘Doe’ und die E-Mail-Adresse ist ‘john.doe@example.com’.

### Aktualisieren von Daten

Um bereits vorhandene Daten in einer Tabelle zu aktualisieren, wird das UPDATE-Statement verwendet. Hier ist die Syntax dafür:

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE some_column = some_value;
```

- ‘table_name’: Der Name der Tabelle, in der die Daten aktualisiert werden sollen.
- ‘column1 = value1’, ‘column2 = value2’, …: Die Spalten und ihre neuen Werte.
- ‘WHERE some_column = some_value’: Die Bedingung, unter der die Daten aktualisiert werden sollen.

Hier ein Beispiel:

```sql
UPDATE customers
SET first_name = 'Jane'
WHERE last_name = 'Doe';
```

In diesem Beispiel wird der Vorname aller Kunden mit dem Nachnamen ‘Doe’ auf ‘Jane’ geändert.
