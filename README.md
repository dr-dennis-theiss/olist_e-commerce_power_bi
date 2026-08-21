# Olist Business Performance Analysis

Business-Intelligence-gestützte Analyse von Geschäftserfolg, Verkäuferleistung und Marketingdaten bei Olist.

## Projektbeschreibung

Dieses Projekt wurde im Rahmen eines Power-BI-Abschlussprojekts durchgeführt.

Olist ist der größte brasilianische Online-Marktplatz und unterstützt Händler beim Verkauf ihrer Produkte über verschiedene E-Commerce-Plattformen.

Ziel des Projekts ist die datenbasierte Analyse von Geschäftserfolg, Verkäuferleistung und Marketingattributen zur Unterstützung von Marketing- und Vertriebsentscheidungen.

Die Analyse basiert auf realen, anonymisierten E-Commerce-Daten aus den Jahren 2016 bis 2018 und wurde vollständig in Microsoft Power BI umgesetzt.

## Projektziel

Die Analyse soll helfen,

- den Verkaufsprozess besser zu verstehen,
- Erfolgsfaktoren des Marktplatzes zu identifizieren,
- die Leistung von Verkäufern zu bewerten,
- Marketing- und Lead-Attribute zu untersuchen,
- sowie datenbasierte Handlungsempfehlungen für Marketing und Vertrieb abzuleiten.

## Leitfragen

### Leitfrage 1

Welche Faktoren bestimmen den Geschäftserfolg auf dem Olist-Marktplatz?

### Leitfrage 2

Welche Merkmale zeichnen erfolgreiche Verkäufer aus?

### Leitfrage 3

Welche Lead- und Marketingattribute führen zu den erfolgreichsten Verkäufern und wie können diese systematisch identifiziert werden?

## Datenbasis

Die Analyse basiert auf der Datei:

`olist_data.xlsx`

Enthaltene Tabellen:

- olist_customers
- olist_orders
- olist_products
- olist_sellers

Analysezeitraum:

- September 2016 bis Oktober 2018

Die Daten wurden anonymisiert und für Analysezwecke aufbereitet.

## Vorgehensweise

Das Projekt folgt dem klassischen Datenanalyseprozess:

1. Fragen und Problemstellung
2. Datenimport
3. Explorative Datenanalyse (EDA)
4. Datenbereinigung
5. Datenmodellierung
6. Feature Engineering
7. Analyse & Visualisierung
8. Handlungsempfehlungen

Die Analyse erfolgte iterativ:

`Exploration ↔ Datenbereinigung ↔ Analyse`

Erkenntnisse aus der Exploration führten zu Bereinigungsentscheidungen. Analyseergebnisse machten teilweise weitere Anpassungen erforderlich.

## Datenqualität & Datenbereinigung

Während der explorativen Datenanalyse wurden mehrere Datenqualitätsprobleme identifiziert.

### Datenqualitätsprobleme

- Hoher Anteil fehlender Marketinginformationen
- Fehlerhafte Datensätze und Inkonsistenzen
- Fehlende Produkt-, Liefer- und Bewertungsdaten
- Mehrfachkategorien bei Behaviour Profiles

### Datenbereinigung

Durchgeführt wurden unter anderem:

- Duplikatprüfung
- Behandlung von NULL-Werten
- Standardisierung von Marketingattributen
- Korrektur fehlerhafter Werte
- Entfernung irrelevanter Spalten

Beispiele:

- `marketing.origin → no contact`
- `marketing.business_type → unspecified`

## Datenmodell

Für die Analyse wurde ein Star-Schema-Datenmodell aufgebaut.

### Faktentabelle

- olist_orders

### Dimensionstabellen

- olist_customers
- olist_products
- olist_sellers
- DimDate

Zusätzlich wurde eine zentrale DAX-Datumstabelle erstellt und als Datumstabelle definiert.

## Feature Engineering

Im Rahmen des Feature Engineerings wurden zusätzliche Variablen und Kennzahlen entwickelt.

### Berechnete Spalten

#### Delivery Days

Lieferdauer zwischen Bestellung und Zustellung.

#### Days To Close

Dauer vom Erstkontakt bis zum Vertragsabschluss eines Verkäufers.

#### On Time Flag

Kennzeichnung pünktlicher Lieferungen.

### Wichtige Measures

- Revenue
- Orders
- Average Order Value
- Revenue Growth
- Revenue per Seller
- Avg Review
- On Time Rate
- Avg Days To Close

## Seller Scoring

Zur Bewertung der Verkäufer wurde ein eigenes Scoring-Modell entwickelt.

### Bestandteile des Scores

| Komponente | Gewichtung |
|------------|------------|
| Revenue Score | 40 Punkte |
| Order Score | 25 Punkte |
| Delivery Score | 20 Punkte |
| Review Score | 15 Punkte |

### Ziel

Ganzheitliche Bewertung der Verkäuferleistung anhand von:

- Umsatz
- Bestellvolumen
- Lieferqualität
- Kundenzufriedenheit

Maximal erreichbarer Score:

- 100 Punkte

## Analyseergebnisse

### Geschäftsanalyse

- Olist befindet sich im betrachteten Zeitraum in einer Wachstumsphase.
- 2017 ist das einzige vollständig verfügbare Kalenderjahr.
- Wenige Produktkategorien dominieren einen großen Teil des Umsatzes.
- Der Umsatz konzentriert sich auf wirtschaftlich starke Kernregionen Brasiliens.

Wichtigste Produktkategorien:

- Health & Beauty
- Watches & Gifts
- Bed & Bath Table

### Kundenanalyse

- Die Nachfrage konzentriert sich stark auf wenige Regionen.
- São Paulo stellt den wichtigsten Kundenmarkt dar.
- Hohe Umsätze entstehen vor allem durch hohe Bestellvolumina.
- Nachfrage, Bestellwerte und Kundenzufriedenheit entwickeln sich nicht zwangsläufig gemeinsam.

### Verkäuferanalyse

- Umsatz allein erklärt Verkäufererfolg nicht vollständig.
- Erfolgreiche Verkäufer zeichnen sich zusätzlich durch stabile Qualitätskennzahlen aus.
- Kundenzufriedenheit und Lieferperformance liefern wichtige Zusatzinformationen.
- Die umsatzstärksten Verkäufer erzielen ein Vielfaches des durchschnittlichen Verkäuferumsatzes.

### Marketinganalyse

- Marketinginformationen liegen nur für einen kleinen Teil der Verkäufer vor.
- Die Kategorie „No Contact“ dominiert die Marketingdaten.
- Behaviour Profiles unterscheiden sich deutlich hinsichtlich der Conversion-Dauer.
- Reseller erzielen höhere Umsätze je Verkäufer als Manufacturer.
- Das Business Segment Watches weist das höchste Umsatzpotenzial auf.

### Seller Scoring

- Der Seller Score ermöglicht eine objektive und ganzheitliche Verkäuferbewertung.
- Marketing- und Lead-Attribute können anhand der Verkäuferqualität bewertet werden.
- Email, Referral und Organic Search erreichen die höchsten durchschnittlichen Seller Scores.

## Handlungsempfehlungen

### Produktkategorien & Regionen fokussieren

Marketing- und Vertriebsmaßnahmen auf besonders umsatzstarke Produktkategorien und wirtschaftlich starke Kernregionen konzentrieren.

### Verkäuferqualität aktiv steuern

Verkäuferleistung durch den Seller Score ganzheitlich bewerten und besonders erfolgreiche Verkäufer priorisieren.

### Marketingdaten systematisch erfassen

Marketinginformationen standardisieren und erfassen, um erfolgreiche Lead Sources zukünftig belastbar identifizieren und bewerten zu können.

## Zentrale Erkenntnis

Geschäftserfolg, Verkäuferleistung und Marketingattribute stehen in engem Zusammenhang und können gemeinsam genutzt werden, um Marketing- und Vertriebsentscheidungen datenbasiert zu unterstützen.

## Verwendete Technologien

- Microsoft Power BI
- Power Query
- DAX
- Star-Schema-Datenmodell

## Autor

Dennis Theiß

Power-BI-Abschlussprojekt  
DataSmart Point  
2026
