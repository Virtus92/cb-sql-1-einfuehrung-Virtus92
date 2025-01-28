[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=17913320&assignment_repo_type=AssignmentRepo)
# Spaß mit Datenbanken
## SQL
## Structured Query Language

### Entwicklung
The paper, “A Relational Model of Data for large Shared Data Banks,” by Dr. E. F.
Codd, was published in June 1970 in the Association of Computer Machinery (ACM) journal.
Codd’s model is now accepted as the definitive model for relational database management
systems (RDBMS).

ca. 1975 - SEQUEL = **S**tructured English **Q**uery **L**anguage, Vorläufer von SQL wird für
das Projekt System R von IBM 

1979 - **SQL** gelangt mit **Oracle V2** erstmals durch **Relational Software Inc**.
auf den Markt.

1986 - **SQL1** wird von ANSI als Standard verabschiedet.

1987 - **SQL1** wird  auch von ISO als Standard verabschiedet und 1989
nochmals überarbeitet.

1992 - Der Standard **SQL2** bzw. **SQL-92** wird von der ISO verabschiedet. 

1999 - **SQL3** bzw. **SQL:1999** wird verabschiedet. 

2003 - **SQL:2003** wird von der ISO als Nachfolger des SQL:1999
Standards verabschiedet. 

2006 - SQL:2006 ISO/IEC 9075-14:2006 legt fest, wie SQL in Zusammenhang mit
XML verwendet werden kann. 

2008 - SQL:2008 ISO/IEC 9075

2011 - SQL:2011 ISO/IEC 9075:2011 ist die aktuelle Revision des SQL
Standards

### Benefits of SQL
The strengths of SQL benefit all ranges of users including application programmers, database administrators, management and end users.

SQL is a non–procedural language because it:
* processes sets of records rather than just one at a time
* provides automatic navigation to the data

SQL provides commands for a variety of tasks including:
* querying data
* inserting, updating, and deleting rows in a table
* creating, replacing, altering, and dropping objects
* controlling access to the database and its objects
* guaranteeing database consistency and integrity

SQL unifies all of the above tasks in one consistent language

### SQL Generation 4
Gesucht ist der Vorname und der Familienname aller Kunden, die in '4040' wohnen.


3.Generation                      4. Generation
Öffne die Kundendatei             SELECT VORNAME, ZUNAME
Lies den ersten Satz              FROM KUNDE
Solange die Datei nicht leer      WHERE PLZ = '4040'
mache folgendes
  wenn plz = '4040'
    gib Vorname und Zuname aus
  lies den nächsten Satz
Schliesse die Kundendatei


### Subsprache

#### Data Definition Language  (DDL)
dient zur Implementierung des relationalen Modells  in einer Datenbank. Definition von Tabellen, deren Attribute, Typen und Wertebereiche
Beispiel Pseudocode:


erstelle Tabelle kunde mit den Feldern 
kundennummer ganzzahlig, 
vorname zeichenkette


* CREATE - definieren
* ALTER  - ändern
* DROP - löschen

#### Data Manipulation Language (DML)
dient zur Manipulation von Daten:
Abfrage, Ändern, Einfügen, Löschen.

* SELECT - auswählen
* UPDATE - aktualisieren
* INSERT - einfügen
* DELETE - löschen

#### Data Control Language (DCL)
regelt den Zugriff und die Berechtigungen insbesondere in Mehrbenutzersystemen.

* GRANT  - Berechtigungsvergabe
* REVOKE - Berechtigungsentzug
* COMMIT - fixieren von Veränderungen
* ROLLBACK - Zurücksetzen
* LOCK   - sperren 

### Relationale Algebra

Die Grundlagen der Relationalen Datenbanken liegen in den Arbeiten von Edgar F. Codd aus den 60er und 70er Jahren. 

Er entwickelte ein algebraisches Modell (eine Algebra befasst sich mit den Eigenschaften von Rechenoperationen), das sich damit befasst, wie Daten gespeichert, abgefragt und manipuliert werden können.

Die Operationen basieren auf Relationen, den Tabellen.

### Konzepte relationaler Datenbanken
#### Theorie
Alle zu speichernden Informationen, also auch die Beschreibung der Datenbank selbst, werden in Form von Tabellen durchgeführt. 

Mathematische Beschreibung der Relation:
Eine Relation `R` zwischen den Mengen `A` und `B` kann durch die Elementpaare `(a, b)` ausgedrückt werden, für die `aRb` gilt. Eine Relation ist eine Teilmenge des kartesischen Produkts `A x B`.

#### Beispiel
`S` sei die Menge aller österreichischen Städte (Domäne `S`) (Wien, Linz, Eisenstadt, Bregenz, …)

`F` sei die Menge aller österreichischen Flüsse (Domäne `F`) (Mur, Donau, Inn, …)

`R` sei die Relation  `liegt am / liegt an der`

Eine Relation über den beiden Domänen  ist definiert als eine Teilmenge des kartesischen Produktes:
`s  liegt am / an der  f`

### Relation und Tupel
Ein Tupel (Zeile) ist ein Element einer Relation

Ein Telefonbuch ist Beispiel für eine Relation. Ein Tupel besteht aus den Komponenten (Attributen) `Name, Straße und Telefonnummer`.

Das Tupel für die `CODERS.BAY` hat die Attributsausprägungen `Peter Behrens Platz 6 und 073269227070`

### Operationen der relationalen Algebra
* Projektion
* Selektion
* Kartesisches Produkt
* Umbenennung
* Vereinigung
* Differenz

### Beispieltabellen 
#### DEPT

```plaintext
DEPTNO | DNAME       | LOC
---------------------------
10     | ACCOUNTING  | NEW YORK
20     | RESEARCH    | DALLAS
30     | SALES       | CHICAGO
40     | OPERATIONS  | BOSTON
```

#### EMP

```plaintext
EMPNO | ENAME  | JOB       | MGR  | HIREDATE  | SAL  | COMM | DEPTNO
---------------------------------------------------------------------
7369  | SMITH  | CLERK     | 7902 | 17-DEC-80 | 800  |      | 20
...   | ...    | ...       | ...  | ...       | ...  | ...  | ...
```

### Tabellen anlegen
* Der Name der Tabelle
* Der Name jeder Spalte
* Der Typ der Daten, die in jeder Spalte gespeichert werden
* Die Länge jeder Spalte
* Weitere optionale Informationen

#### DEPT

```plaintext
DEPTNO | DNAME       | LOC
---------------------------
10     | ACCOUNTING  | NEW YORK
20     | RESEARCH    | DALLAS
30     | SALES       | CHICAGO
40     | OPERATIONS  | BOSTON
```

```sql
CREATE TABLE DEPT (
 DEPTNO              NUMBER(2) NOT NULL,
 DNAME               CHAR(14),
 LOC                 CHAR(13),
 CONSTRAINT DEPT_PRIMARY_KEY PRIMARY KEY (DEPTNO));
```

#### Einfügen von Tupel

```sql
INSERT INTO Tabelle
VALUES (Liste von Datenwerten);
```

Beispiel:

```sql
INSERT INTO EMP VALUES (7954,'CARTER','CLERK',7698,'7-APR-84',1000,NULL,30);
```

* Einfügen von Null-Werten:

```sql
INSERT INTO EMP (EMPNO,ENAME,HIREDATE,DEPTNO,SAL) VALUES (7955,'WILSON','22-APR-84',30,1500);
```

* Einfügen von Datumswerten:

```sql
INSERT INTO EMP 
VALUES (7657,'MASON','ANALYST',7566,
TO_DATE('4/24/84','MM/DD/YY'), 3400, NULL, 20);
```

### Ändern und Löschen
#### Ändern

```sql
UPDATE EMP
SET JOB = 'SALESMAN' 
WHERE ENAME = 'WILSON’;
```

#### Löschen

```sql
DELETE FROM BONUS
WHERE ENAME = 'WARD';
```

### Daten auslesen (SELECT)

```sql
SELECT DNAME, DEPTNO
FROM DEPT;

SELECT *
FROM EMP 

SELECT DISTINCT JOB
FROM EMP;

SELECT (DISTINCT) DNAME 
FROM DEPT
```
