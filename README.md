# DBI_Ausarbeitung
Matura Ausarbeitung für Datenbanken

# Erstellung und Änderung von Tabellen in SQL

## Einleitung
In SQL wird zum erstellen von Tabellen der Befehl Create Table und zum ändern von Tabellen der Alter Table Befehl benutzt.

## Erstellung einer Tabelle
Die Erstellung einer Tabelle erfolgt mit dem CREATE TABLE-Statement. Dabei werden verschiedene Klauseln verwendet, um die Tabellenstruktur festzulegen. Hier sind die wichtigsten Punkte:

CREATE TABLE table_name (
    column1 datatype1,
    column2 datatype2,
    ...
    PRIMARY KEY (column_name),
    FOREIGN KEY (column_name) REFERENCES other_table(column_name),
    ...
);

- 'table_name': Der Name der Tabelle, die erstellt werden soll.
- 'column1', 'column2', ...: Die Namen der Spalten in der Tabelle.
- 'datatype1', 'datatype2', ...: Die Datentypen der jeweiligen Spalten.
- 'PRIMARY KEY (column_name)': Definiert einen Primärschlüssel für die Tabelle.
- 'FOREIGN KEY (column_name) REFERENCES other_table(column_name)': Definiert einen Fremdschlüssel, der auf eine Spalte in einer anderen Tabelle verweist.

## Änderung einer Tabelle
Änderungen an einer Tabelle können mit dem ALTER TABLE-Statement vorgenommen werden. Eine häufige Änderung besteht darin, eine Spalte hinzuzufügen. Hier ist die Syntax dafür:

ALTER TABLE table_name
ADD COLUMN column_name datatype;

- 'table_name': Der Name der Tabelle, zu der eine Spalte hinzugefügt werden soll.
- 'column_name': Der Name der neuen Spalte.
- 'datatype': Der Datentyp der neuen Spalte.

Mit diesen Informationen sind Sie in der Lage, Tabellen in SQL zu erstellen und zu ändern.
