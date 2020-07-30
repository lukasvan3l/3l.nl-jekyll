---
layout: post
title: Met CodeUur data spelen
image: assets/images/graphql-1.png
tags: [ development ]
---

Het CodeUur matching systeem bevat een hoop interessante informatie, over scholen, leerkrachten, gastdocenten en zo meer.

Laat er nou nieuw technisch speelgoed zijn die deze informatie beschikbaar stelt aan andere programmeurs, namelijk GraphQL ([Rahul schreef hier laatst al over](https://medium.com/q42bv/de-toekomst-van-apis-6244fb78b281)). Niet alleen Rahul is er enthousiast over. Ook de makers van Meteor, de techniek waarmee de CodeUur website gebouwd is, zijn enthousiast. Genoeg reden voor mij om er eens in te duiken.

{% include image.html file="graphql-1.png" %}

De uitkomst van een paar dagen programmeren is een GraphQL API die je kan bevragen op [https://www.codeuur.nl/graphiql](https://www.codeuur.nl/graphiql). Klink linksboven op de PLAY knop om de query in het linker scherm uit te voeren, en rechts het resultaat te zien.

De query zelf kun je aanpassen. Er zit *code completion* op, dus als je op een lege regel gaat staan en CTRL+Spatiebalk in toetst, krijg je de mogelijke velden te zien. Als je velden opvraagt waar privacy gevoelige informatie in staat, krijg je *null* terug. CodeUur-medewerkers krijgen die informatie wél te zien, als ze ingelogd zijn op de website.

De query en het resultaat zijn zo weergegeven dat je ook geautomatiseerd deze informatie kan opvragen. Met een beetje programmeerskills kun je bijvoorbeeld de [coördinaten van alle scholen op een Google Maps kaart](https://www.codeuur.nl/kaart) weergeven.

Of een grafiek van de createddate van gastdocenten, zodat je ziet wanneer er veel nieuwe gastdocenten bij zijn gekomen. Die is trouwens best wel makkelijk.

Wacht, laten we m ff samen doen.

**Stap 1**: Haal de createddate van alle gastdocenten op door deze query in het linker scherm te typen en vervolgens op PLAY te drukken.

{% include image.html file="graphql-2.png" %}

**Stap 2**: Kopieer het resultaat uit het rechter scherm, en plak die in [https://konklone.io/json/](https://konklone.io/json/) om het naar een spreadsheet formaat om te smurfen. Download vervolgens het CSV bestand.

{% include image.html file="graphql-3.png" %}

**Stap 3**: En als je die data vervolgens in Google Spreadsheets inlaadt en er een grafiek op loslaat van het aantal unieke aanmeldingen per datum, dan krijg je het volgende:

{% include image.html file="graphql-4.png" %}

Dat is een aardige spike rond [het Wereldrecord](https://www.codeuur.nl/wereldrecord) :)

> Hier is [de spreadsheet als naslagwerk](https://docs.google.com/spreadsheets/d/1PIyTAaNonjqdpE0Z-YqfmH4zbwAOFU3VRC87WSHXE9w/edit?usp=sharing).

Best leuk om zo met data te kunnen kneden! Of zoals collega [@kriepy](https://twitter.com/kriepy) zou zeggen: Meer data is meer beter :) Veel plezier ermee!