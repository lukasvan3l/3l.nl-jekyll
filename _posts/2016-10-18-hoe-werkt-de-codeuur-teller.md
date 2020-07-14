---
layout: post
title: Hoe werkt de CodeUur wereldrecord teller?
image: assets/images/wereldrecord-1.jpeg
tags: [ development, kidsthatcode ]
---

Vorige week heeft CodeUur geschiedenis geschreven door 11.386 kinderen tegelijkertijd te leren programmeren. In 464 verschillende klassen in heel Nederland.

Maar hoe komen we aan dat getal? Voor een wereldrecord is het natuurlijk belangrijk dat het aantal precies klopt. Dus we zijn niet gaan bellen met alle scholen en gevraagd wie er mee hebben gedaan. Natuurlijk hebben we daar iets handigs voor bedacht. Ik heb daar iets voor geprogrammeerd, samen met mijn collega’s bij [Q42](https://q42.nl). Ik ga je nu uitleggen hoe dat werkt.

{% include image.html file="wereldrecord-1.jpeg" caption="11.368 kinderen hebben meegedaan aan het CodeUur Wereldrecord" %}

## De code
Elke website heeft HTML dat ergens op internet staat. Voor wr.codeuur.nl is dat op Github. Dat is leuk, want Github is speciaal gemaakt om code te delen met anderen. Als je alle code wilt doorspitten die nú achter wr.codeuur.nl zit, [kijk hier maar eens](https://github.com/Q42/codeuur-wereldrecord).

Maar ik wil jullie nu de code van de Leerling-teller latenzien, en die staat niet meer online… Gelukkig kun je op Github ook terug in de tijd kijken. Hier is [een link naar de website zoals hij er op 14 oktober uit zag](https://github.com/Q42/codeuur-wereldrecord/tree/wereldrecord). Daar staat het formulier nog wel in index.html. Hieronder link ik af en toe naar de code die ergens verantwoordelijk voor is (of was). Dit zit soms in oudere versies van de code.

## De Leerling-teller
Alle leerlingen hebben voordat de les begon [een formulier op wr.codeuur.nl](https://github.com/Q42/codeuur-wereldrecord/blob/wereldrecord/index.html#L54) ingevuld. Omdat ze in twee of drietallen achter de computer zaten, vulden ze de naam en plaats van de school in en de namen van de leerlingen. Het tellen van de leerlingen is dan toch zo simpel als [het aantal ingevulde namen tellen](https://github.com/Q42/codeuur-wereldrecord/blob/wr-form/realcounter.js#L16)? Niet helemaal.

### Gekke namen
Toen ik naar de ingevulde namen ging kijken, zag ik er een aantal gekke tussen zitten. Bijvoorbeeld met een ‘-’ of een spatie als naam. Waarschijnlijk dacht iemand dat je de velden niet leeg mocht laten, en vulde er daarom zo’n karakter in.

Als je zomaar telt volgens “als er iets ingevuld is, hoog de leerlingteller met 1 op”, dan kom je dus te hoog uit. Ik heb de code dus aangepast zodat hij alleen de namen telt die meer dan 1 karakter hebben.

### Kattenkwaad
Daarnaast was er geen beveiliging tegen heel veel formulieren vanaf dezelfde computer toevoegen. Misschien zouden computers wel hergebruikt worden voor meerdere leerlingen, bijvoorbeeld. Wat ik wel heb gedaan is een [Cookie toegevoegd](https://github.com/Q42/codeuur-wereldrecord/blob/wereldrecord/codeuur-wereldrecord.js#L76) zodat ik kon zien hoeveel formulieren er vanaf dezelfde computer waren toegevoegd.

{% include image.html file="wereldrecord-2.jpeg" %}

Achter de schermen ben ik op zoek naar het échte aantal kinderen

Zo zag ik dat er vanaf sommige computers wel 12 of 13 formulieren waren ingevuld. Zat daar nou een leerling kattekwaad uit te halen? Gelukkig niet, het bleek een leerkracht te zijn die vanaf zijn/haar computer de namen van alle leerlingen invulde! En dat mag, daar is niks op tegen.

Trouwens, er waren maar 14 computers waar cookies uit stonden.

## Het eindresultaat
Uiteindelijk is het formulier maar liefst 6.371 keer ingevuld, één keer per groepje leerlingen. En zijn er totaal 11.368 échte namen verzameld. Met dat getal hebben we nu een wereldrecord :)

Er werd een database connectie geopend voor iedereen die op wr.codeuur.nl kwam. Dat zorgt voor mooie grafiekjes, zoals deze:

{% include image.html file="wereldrecord-3.png" %}

Op 14 oktober 10.000 database connecties

## En nu?
We hebben heel veel kinderen bereikt. Maar we hebben ze alleen nog maar een introductie in programmeren gegeven. Hopelijk zijn er een hoop leerlingen die het zó leuk vonden, dat ze thuis ook verder gaan met programmeren in [Scratch](https://scratch.mit.edu/).

En dat er leerkrachten en scholen zijn die er verder mee willen gaan. Die kunnen in de klas bijvoorbeeld het [Smart Life lesmateriaal](https://smart-life.blink.nl/wereldorientatie/7-8/smart-life) gebruiken, of [ander lesmateriaal van CodeUur](https://www.codeuur.nl/lesmateriaal).

Op de langere termijn kun je nog meer CodeUur materiaal verwachten. We willen kinderen namelijk zo goed mogelijk voorbereiden op een toekomst waar technologie een grote rol in gaat spelen.
