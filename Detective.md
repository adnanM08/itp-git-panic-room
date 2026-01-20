# 🕵️ Git Detective – Ermittlungsprotokoll

Ziel dieser Station ist es, das Repository zu **verstehen**, nicht es zu reparieren.

- Es wird **(noch) nichts geändert**
- Es wird **(noch) nichts repariert**
- Es wird **(noch) nichts committed**

Reparaturen folgen erst im **Panic Room** 🚨

Ausgearbeitet von: Adnan Muzaferovic




## #1 -  Überblick über die Git-History
Welche 2 Commits fallen euch in der History bereits zu Beginn negativ auf? Und warum? 

Die letzten zwei, da der vorletzte Commit nur die Commit-Message "Stuff" hat, und der letzte Commit überhaupt keine Message hat.

## #2 - Ab welchem Commit ist das Projekt nicht mehr stabil?
Woran erkennt ihr, dass es ab hier ein Problem gibt?
Mit welche(n) Befehl(en) könnt ihr das herausfinden?
(Antwort: Commit-ID, Message, Begründung)

**Commit-ID:** a0bc0e2d05936e41434c38e2d2cf718c29a1ddc4  
**Commit-Message:** Remove old docs  
**Befehl:** mvn test  
**Begründung:** Im Commit "Remove old docs" war der Command "mvn test" enthalten, mit dem man das Programm testen kann. Dadurch kann man herausfinden, dass das Problem in Zeile 10 liegt.

## #3 - Welche Datei wurde dabei verändert?
Welche Datei(en) wurden im verdächtigen Commit verändert?
Mit welche(n) Befehlen könnt ihr das herausfinden?
(Antwort: Commit-ID, geänderte Datei(en), Kurzbeschreibung der Änderung)

**Commit-ID:** 50da5b1caf09339b68ce5d4ace7368a7b99f013e  
**Geänderte Datei(en):** Calculator.java, CalculatorText.java  
**Beschreibung:** Die Zeile "return a/b" wurde mit a/0 ersetzt.

## #4 - Wer hat die entscheidende Stelle verändert?
Welche Datei ist besonders relevant und warum?
Mit welche(n) Befehlen kannst du dies rausfinden? 
(Antwort: Datei, Commit-ID der relevanten Änderung, Commit Message, betroffene Code-Stelle, warum ist diese Stelle wichtig?)

**Datei:** Calculator.java  
**Commit-ID:** 50da5b1caf09339b68ce5d4ace7368a7b99f013e  
**Commit Message:** Update  
**Code-Stelle:** Zeile 10  
**Wieso:** Weil in dieser Zeile der Bug sich befindet.

## #5: Vergleich vor und nach der Änderung
Was ist der Unterschied im Code, bevor und nachdem das Problem entstanden ist? Mit welchem Befehl kannst du das rausfinden? 

**Befehl:** git diff
**Unterschied:** Vorher stand in der Zeile "return a/b" anstatt "return a/0"