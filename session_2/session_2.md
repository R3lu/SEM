SEM 2
================
Simon Roth
21.4.2017









<style type="text/css">
body, td {
   font-size: 14px;
}
r.code{
  font-size: 10px;
}
pre {
  font-size: 10px
}
</style>
Datensatz einladen
==================

1.  german: Staatsbürgerschaft

-   1 Ja, ausschließlich
-   2 Ja, neben 2. Staatsbürgerschaft
-   3 Nein

1.  eastwest: Erhebungsgebiet

-   1 West
-   2 Ost

Itembatterien
-------------

**Islamophobie:**

-   mm01: ISLAMAUSUEBUNG IN BRD BESCHRAENKEN
    -   -10 Befragter gehört einer islamischen Religionsgemeinschaft an (Code 1 in rd03)
    -   -9
    -   1 Stimme überhaupt nicht zu
    -   2
    -   3
    -   4
    -   5
    -   6
    -   7 Stimme voll und ganz zu
-   mm02: ISLAM PASST IN DIE DEUTSCHE GESELLSCHAFT
-   mm03: ANWESENHEIT VON MUSLIMEN BRINGT KONFLIKT
-   mm04: STAAT SOLLTE ISLAM. GRUPPEN BEOBACHTEN
-   mm05: MUSLIMISCHER BUERGERMEISTER IN ORDNUNG
-   mm06: UNTER MUSLIMEN SIND VIELE REL. FANATIKER

<!-- **Einbürgerung:** -->
<!-- * mn01: EINBUERGERUNG: SOLLTE HIER GEBOREN SEIN -->
<!-- * mn02: EINBUERGERUNG: DEUTSCHE ABSTAMMUNG HABEN -->
<!-- * mn03: EINBUERGERUNG: DEUTSCH SPRECHEN -->
<!-- * mn04: EINBUERGERUNG: LANGE BEI UNS GELEBT -->
<!-- * mn05: EINBUERGERUNG: LEBENSSTILANPASSUNG -->
<!-- * mn06: EINBUERGERUNG: IN CHRISTLICH.KIRCHE SEIN -->
<!-- * mn07: EINBUERGERUNG: KEINE STRAFTATEN -->
<!-- * mn08: EINBUERGERUNG: EIGENER LEBENSUNTERHALT -->
<!-- * mn09: EINBUERGERUNG: ZU GRUNDGESETZ BEKENNEN -->
<!-- * mn10: KOENNEN MIGRANTEN ECHTE DEUTSCHE WERDEN? -->
**Nationalbewusstsein:**

-   mn11: DEUTSCH SEIN: DEUTSCHE STAATSBUERGERSCH.
-   mn12: DEUTSCH SEIN: CHRISTL.RELIGION ZUGEHOER.
-   mn13: DEUTSCH SEIN: BEKENNTNIS ZUR DEMOKRATIE
-   mn14: DEUTSCH SEIN: VIELE DEUTSCHE BEKANNTE
-   mn15: DEUTSCH SEIN: ALTE STAATSANGEH.AUFGEBEN
-   mn16: DEUTSCH SEIN: VERBUNDENHEIT ZU DEUTSCHL.
-   mn17: DEUTSCH SEIN: ALTE GEBRAEUCHE ABLEGEN
-   mn18: DEUTSCH SEIN: GUT DEUTSCH SPRECHEN
-   mn19: DEUTSCH SEIN: WESTLICHE WERTE TEILEN
-   mn20: DEUTSCH SEIN: MIND. 1 ELTERNTEIL DEUTSCH
-   mn21: DEUTSCH SEIN: IN DEUTSCHLAND GEBOREN

Daten partitionieren
====================

-   sex: GESCHLECHT (Int.: Geschlecht der befragten Person ohne Befragen eintragen!)
    -   1 Männlich
    -   2 Weiblich
-   age: ALTER: metrisch
-   agec: ALTER: KATEGORISIERT 6
    -   18 - 29 Jahre
    -   30 - 44 Jahre
    -   45 - 59 Jahre
    -   60 - 74 Jahre
    -   75 - 89 Jahre
    -   Über 89 Jahre
-   isced97: BEFR.: ISCED 1997 - 6 STUFEN: International Standard Classification of Education (ISCED) 1997, 6 Stufen
    1.  Level - Primary education or first stage of basic education
    2.  Level - Lower secondary or second stage of basic education
    3.  Level - (Upper) secondary education
    4.  Level - Post-secondary non-tertiary education
    5.  Level - First stage of tertiary education
    6.  Level - Second stage of tertiary education
-   Allgemeiner Bildungsabschluss?

Missing Pattern
---------------

NZ (Fragebogen- Split): Befragter hat aufgrund eines methodischen oder inhaltlichen Splits eine Frage oder Item- batterie nicht gestellt bekommen.

<img src="session_2_files/figure-markdown_github/unnamed-chunk-1-1.png" style="display: block; margin: auto;" /><img src="session_2_files/figure-markdown_github/unnamed-chunk-1-2.png" style="display: block; margin: auto;" />

Load VIM package for Visualization and Imputation of Missing Values
-------------------------------------------------------------------

Little Test
-----------

*A Test of Missing Completely at Random for Multivariate Data with Missing Values* Roderick J. A. Little (1988)

**Nullhypothesis: missing values pattern are missing completly at random**

``` r
# install.packages("BaylorEdPsych")
# install.packages("mvnmle")

library(BaylorEdPsych)
little_islam <- LittleMCAR(islam)
little_islam$amount.missing
little_islam$p.value

little_nation <- LittleMCAR(nation)
little_nation$amount.missing
little_nation$p.value
```

2.2 T-Tests
-----------

<img src="session_2_files/figure-markdown_github/unnamed-chunk-6-1.png" style="display: block; margin: auto;" />

2.3 Logistic Regression
-----------------------
