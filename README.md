# gprojekt

Frisör Bokningssystem – Databas
Beskrivning

Detta projekt är en enkel relationsdatabas för ett bokningssystem för en frisör.
Databasen används för att lagra information om kunder, tjänster och bokningar.
Syftet är att kunna se vilken kund som bokat en viss tjänst och vid vilken tid.

Databasstruktur

Databasen består av tre huvudtabeller:

Kunder

KundID (Primärnyckel)
Namn
Epost

Denna tabell lagrar information om alla kunder.

Tjanster

TjanstID (Primärnyckel)
Namn
Pris

Denna tabell innehåller frisörens olika tjänster, till exempel klippning eller färgning.

Bokningar

BokningID (Primärnyckel)
KundID (Främmande nyckel)
TjanstID (Främmande nyckel)
Datum

Denna tabell kopplar ihop kunder och tjänster och sparar när bokningen sker.

Relationer

Tabellen Bokningar är kopplad till både Kunder och Tjanster genom främmande nycklar.
Detta gör att databasen kan hålla reda på vilken kund som bokat vilken tjänst.

Constraints

Följande constraints används för att säkerställa dataintegritet:

PRIMARY KEY för unika identifierare
FOREIGN KEY för relationer mellan tabeller
NOT NULL för att säkerställa att viktiga värden inte lämnas tomma
CHECK för att kontrollera att giltiga värden används
DEFAULT för automatiska standardvärden
Trigger

En trigger används för att automatiskt skapa en bokningsbekräftelse.
När en ny bokning läggs till i tabellen Bokningar skapas ett meddelande i en loggtabell (BekraftelseLogg) som simulerar en bokningsbekräftelse.

SQL-frågor

Databasen innehåller SQL-frågor som använder:

JOIN för att kombinera data från flera tabeller
GROUP BY för att analysera bokningar, till exempel hur många bokningar varje tjänst har.
Sammanfattning

Denna databas gör det möjligt att hantera bokningar i ett enkelt frisörsystem genom att lagra kunder, tjänster och bokningar samt automatiskt registrera bokningsbekräftelser.
